# Tutorial for Test-Driven Development course

How To Create a new Ceedling Project
------------------------------------

Create a new project by typing
```
ceedling new <project_name>
```
Replace the `<project_name>` with the your project name of choice. Then enter into the the folder created:
```
cd <project_name>
```
Create `.gitignore` to ignore `build` folder that will contains a lot of unnecessary artifacts
```
echo "build/*" > .gitignore
```
Create a dummy `Readme.txt` file to avoid `Git` from totally remove the `build` folder: 
```
echo "Do not remove me!" > build/Readme.txt
```
Then add all new files to the Git staging area:
```
git add --all
```
Type:
```
git status
```
This will list all files in the staging are in green color. Make sure `.gitignore` and `build/Readme.txt` is in the list. Finally, type:
```
git commit -m "Create the <project_name> project"
```

How to Create a New Module in Your Project
------------------------------------------
If you need to know what rake commands that are available, type:
```
rake -T
```
To create a new module for your project, type:
```
rake module:create[<module_name>]
```
Replace the `<module_name>` with the module name of your choice. This will create the 3 following files: 
```
src/<module_name>.h
src/<module_name>.c
test/test_<module_name>.c
```





