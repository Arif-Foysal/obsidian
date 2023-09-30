#microComputer #Microprocessor #Microcontroller 

## Programming an arduino

You can use Arduino IDE application to upload code to the arduino.
Link- https://www.arduino.cc/en/software
### Windows
Just download the .exe file from the website.

### Linux
#linux 

**Naive approach:**
Install Arduino IDE from 3rd party package managers e.g. flatpak, snap etc.

**My preferance:**
1. Download appimage from the website and run it.
2. If you want the appimage integrated to the application list, follow these steps-
	![[integrating appimage to application list]]
	just replace the appimage file path accordingly.
#### Trubleshooting

Ref: https://support.arduino.cc/hc/en-us/articles/360016495679-Fix-port-access-on-Linux#processes

While uploading code to arduino, sometimes we may get error like-
`avrdude: ser_open(): can't open device "/dev/ttyACM0": Permission denied`

This happens because your user account doesn't have the necessary permissions to access the serial port.
There are a few ways you can fix this issue-
##### Add yourself to the dialout group
Most Linux configurations have a `dialout` group for full and direct access to serial ports. By adding your user account to this group you will have the necessary permissions for Arduino IDE to communicate on the serial ports.

1. Open Terminal.
    
2. Enter the following command, replacing `<username>` with the name of your account.
    
    ```
    sudo usermod -a -G dialout <username>
    ```
    
3. Restart your computer for the changes to take effect.
    

**If the group wasn’t found, or if you still get an error**, the `dialout` group may have a different name.

1. In _Tools > Port_, note the name of the port your board is connected to, such as `dev/ttyACM0` or similar.
    
2. Open Terminal.
    
3. Enter this command:
    
    ```
    ls -l <port>
    ```
    
    Take note of the group name in the response:
    
    ```
    crw-rw---- 1 <user> <group> 188, 0 5 apr 23.01 <port>
    ```
    
4. To add your user to the group, enter the following command in the terminal, replacing `<group>` with the group name from the previous step, and `<username>` with your username:
    
    ```
    sudo usermod -a -G <group> <username>
    ```
    
5. Restart your computer for the changes to take effect.

##### Check for processes blocking the port

Another cause of errors are other processes that are using the port.

1. Identify the name of the port you’re trying to access. The port name may appear in the error output, but you can also see it in the **Tools > Port** menu.
    
    It will usually start with `/dev/tty`, for example, `/dev/ttyACM0`.
    
2. Open your computer’s command line application (often referred to as shell, terminal, console, prompt or various other names). Look for it in your launcher, or try the Ctrl + Alt + T keyboard shortcut (available on most Linux systems).
    
3. Input the following command, replacing `<port name>` with the port name for your board.
    
    ```
    lsof <port name>
    ```
    
    The output may look something like this:
    
    ```
    username@computer:~$ lsof /dev/ttyACM0
    COMMAND   PID     USER   FD   TYPE DEVICE SIZE/OFF NODE NAME
    java    13854 username   87u   CHR  166,0      0t0  950 /dev/ttyACM0
    ```
    
    The first value returned is the **process name**, which in this case was `java`. This is because another instance of the IDE is running with the Serial Monitor open. The second value, in this case `19772`, is **the Process identifier (PID)**. We can get more info with this command (replace `<PID>` with the PID in your input):
    
4. To get more information about the process, use the `ps` command:
    
    ```
    ps <PID>
    ```
    
    In this case the resulting output was:
    
    ```
    username@computer ~ % ps 13854                 
      PID   TT  STAT      TIME COMMAND
    13854   --  -      5:28.07 /home/username/Downloads/arduino-ide_2.0.0-beta.2_Linux_64bit  
    ```
    
    Note the path in the **COMMAND** column. In this example, an instance of Arduino IDE is using the port.
    
    > **Note:** In some cases, the parent process may be more informative.
    > 
    > You can use this command: `ps -o ppid= <PID> | xargs ps`
    
5. Using the process name or path may be able to find and close an application that’s running the process.
    
6. If you can’t locate the source of the processs, you can terminate the process using the `kill` command.
    
    Type the following in Terminal:
    
```bash
kill <PID>
```
If the process still doesn’t stop, you can use add the `-9` flag to force it to quit:
    
```bash
kill -9 <PID>
```
    
7. Try uploading your sketch again.

##### using chmod to grant permission
If you want to grant permission temporarily, you can use `chmod` command.

```bash
sudo chmod a+rw /dev/ttyACM0
```

this will grant read and write permissions to the current user. 
>[!Note]
>The permissions will be gone once you disconnect the board or reboot your system.

##### creating [[udev]] to automatically grant permissions when the board is connected

Here's how you can create a [[udev]] rule to automatically grant serial port permissions when the `/dev/ttyACM0` device is connected:

1. **Create a Rule File:** Create a new rule file in the `/etc/udev/rules.d/` directory. You can name the file, for example, `99-usb-serial.rules`. You will need superuser privileges to create this file. You can use a text editor or the terminal to create this file:

 ```bash
 sudo nano /etc/udev/rules.d/99-usb-serial.rules
 ```
    
2. **Add the Rule:** Inside the file, add a line to match the `/dev/ttyACM0` device and specify the action to be taken when the device is connected. For example, to run the `chmod` command, you can write:
```bash
SUBSYSTEMS=="usb", KERNEL=="ttyACM0", MODE="0666"
```

In this rule, `SUBSYSTEMS=="usb"` specifies that the rule applies to USB devices, `KERNEL=="ttyACM0"` specifies that it matches the `ttyACM0` device, and `MODE="0666"` grants read and write permissions to everyone.
3. **Save and Exit:** Save the file and exit the text editor.
4. **Reload `udev` Rules:** After creating or modifying a `udev` rule, you need to reload the `udev` rules for the changes to take effect. You can do this without restarting your computer by running:
```bash
sudo udevadm control --reload-rules
```

Now, every time the `/dev/ttyACM0` device is connected to your computer, it should automatically have the necessary permissions without requiring you to manually run the `chmod` command. Please note that these steps are specific to Linux systems; the process might differ on other operating systems.