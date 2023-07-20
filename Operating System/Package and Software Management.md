#### Package Dependencies
###### Windows
Locate packages along with it's dependencies-
`Find-Package sysinternals -IncludeDependencies`
an error will show up because the default source of packages is the powershell gallery, which doesn't contain sysinternals package.
All we need to to is tell powershell about a place where it can find sysinternals package.
**Adding package source**
`Register-PackageSource -Name chocolatey -ProviderName Chocolatey -Location http://chocolatey.org `
Now we can install sysinternals by the following command-
`Install-Package sysinternals`
We can also specify the ProviderName in case of confliction.
###### Linux
Install dependencies automatically while installing an package-
``
#### Package Management
###### Windows
We can either use the chocolatry command line tool or use the package management feature that was recently released for Powershell.

Using package management tool to install a package from chocolatey repository-
`Install-Package <packageName> -ProviderName Chocolatey`

###### Linux
**Apt package manager**
- Installs dependencies automatically
The repository source file in Ubuntu is `/etc/apt/sources.list`
**PPA** is a software repository foruploading source packages to be built and published as an Advanced Packaging Tool (apt) repository by Launchpad
**Be careful using a ppa repository instead of original developers repo. It can sometime contain malicious  programs**
Launchpad is a website owned by the organization, Canonical Limited. It allows open source developers to develop, maintain and distribute softwares.
Learn more about ppa and launchpad https://help.launchpad.net/Packaging/PPA
#### Underneath the hood 
###### Windows
`orca.exe` is used to create or edit windows installer packages.
https://drive.google.com/file/d/1RnJ0Xi40ZQKbMoVrcbqn9wp2xSqy_LXo/view
orca.exe-
https://learn.microsoft.com/en-us/windows/win32/msi/orca-exe?redirectedfrom=MSDN
process monitors-
https://learn.microsoft.com/en-us/sysinternals/downloads/procmon
Windows Installer Examples-
https://learn.microsoft.com/en-us/windows/win32/msi/windows-installer-examples?redirectedfrom=MSDN
