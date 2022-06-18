# python Arduino file

it's just a script that create a file with Arduino ,
because I'm tired from writing the same file a lot, so i can now just ran this file and create the project 
,just by typing `c -theFileName`
<hr>

```python
import os
path = f"{os.getcwd()}"
cmd = "c -"
FileName = input("")
if FileName.startswith(f"{cmd}"):
    File = FileName.replace(f"{cmd}", "")
    if os.path.isdir(f"{path}/DICTIONARY/{File}") == False:
      os.makedirs(f"{path}/DICTIONARY/{File}/")
      os.mknod(f"{path}/DICTIONARY/{File}/{File}.ino")
      os.mknod(f"{path}/DICTIONARY/{File}/functions.h")
      with open(f"{path}/CustomFunctions.txt") as f:
        with open(f"{path}/DICTIONARY/{File}/functions.h","w")  as file:
          file.write(f"{f.read()}")
  	
      with open(f"{path}/ArduinoSnippet.txt") as f:
        with open(f"{path}/DICTIONARY/{File}/{File}.ino","w") as file:
          file.write(f"{f.read()}")
    else: print("dictionary already exists. Please choose another name")
```
