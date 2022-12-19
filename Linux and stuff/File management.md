## Replace a string in a file in bash
```bash
sed -i 's/search_string/replace_string/' filename
```

warning: This will change every occerances
This can be also done using script-
```bash
#!/usr/bin/bash  

# Assign the filename  
filename=$1  
  
# Take the search string  
read -p "Enter the search string: " search  
  
# Take the replace string  
read -p "Enter the replace string: " replace  
  
if [[ $search != "" && $replace != "" ]]; then  
sed -i "s/$search/$replace/" $filename  
fi
```

