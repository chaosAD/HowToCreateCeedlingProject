# Tutorial for Test-Driven Development Course

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
Fix the `project.yml` file to properly build executable file appropriate for Windows (Ceedling was build for Unix systems). Open the file and change `out` to `exe`
```
:extension:
  :executable: .exe
```
Create `.gitignore` to ignore `build` folder that will contains a lot of unnecessary artifacts
```
cat > .gitignore << EOF
build/*
!build/Readme.txt
EOF
```
Create a dummy `Readme.txt` file to avoid `Git` from totally removing the `build` and `test/support` folders: 
```
echo "Do not remove me!" > build/Readme.txt
cp build/Readme.txt test/support/
```
Initialize the folder to be watched by Git:
```
git init
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
git commit -m "Created the <project_name> project"
```

How to Enable Camel/Bumpy Casing
--------------------------------
(No more releveant for version 0.28.xx)
Open the `project.yml` file with an editor of your choice. They place the following commands after `:environment:`:
```
:environment:

:module_generator:
  :naming: bumpy
```


How to Create a New Module in Your Project
------------------------------------------
If you need to know what rake commands that are available, type:
```
ceedling help
```
To create a new module for your project, type:
```
ceedling module:create[<module_name>]
```
Replace the `<module_name>` with the module name of your choice. This will create the 3 following files: 
```
src/<module_name>.h
src/<module_name>.c
test/test_<module_name>.c
```





