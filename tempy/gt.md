### Useful links:
* [markdown cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
* [.net core cli](https://docs.microsoft.com/pl-pl/dotnet/core/tools/) 
* [vs shortcuts](http://visualstudioshortcuts.com/2017/)


### General useful tips
* explorer - click on folder in address bar (so that it changes in the path) and type cmd - console will open in the location



### .NET Core

#### Basic flow
* Create solution:
    * `dotnet new sln -n "solutionname"`
* Create projects:
    * `dotnet new console -n "consoleappname"`
    * `dotnet new classlib -n "libname"`
    * [see other](https://docs.microsoft.com/pl-pl/dotnet/core/tools/dotnet-new)
* Add projects to the solution:
    * `dotnet sln [solution.sln] add ./folder/proj.csproj` - i tak po kolei w cmd
    * `dotnet sln _solution.sln_ add **/*.csproj` - w git bash
* Add reference among the projects
    * `dotnet add _project.csproj_ reference _project.csproj`

#### dotnet useful
* `--dry-run`
* `dotnet sln _solution.sln_ list`
* `Code .`






### Git

#### Initialize repo and connect with remote

1. Załóż repo zdalne
2. **git init** - lokalnie w katalogu gdzie ma być repo
3. **git remote add origin https://github.com/poruta-ent/_repo_.git** - połączenie repo, origin można zastąpić czymś innym ale wtedy przy pushowaniu trzeba tego czegoś innego używać
4. **git remote -v** - pokazuje zdalne repa

____
#### Configure SSH connection
* ssh-keygen -t rsa -b 4096 -C “twój mail”
* odnajdź plik na dysku i skopiuj go do gita

____
#### Work with branches:
* **git branch -a** - lista branchy, -a daje też remote 
* **git checkout -b branch_name** - zakłada i checkoutuje
* **git diff branch1 branch2** - porównanie dwóch branchy
* **git branch -d branch_name** - usuwa bracnch

____
#### Base merging flow:
* **git status**
* **git add .** 
* **git commit -m "commit message"** 
* **git push -u origin branch_name** 
* pull request na remote
* merge do mastera na remote
* delete remote branch
* **git checkout master** 
* **git pull**
* **git branch -d branch_name**

____
#### Local vs. remote branches
* **git fetch** - ściąga remote na dysk nie naruszając localsów (raczej rzadko bo pull to zawiera)
* **git pull** = git fetch + git merge, merguje zdalną do lokalnej
* **git push -u origin master** - merge lokalnej do zdalnej (master w przykładzie)
* **git diff master origin/master** - merge lokalnej do zdalnej (master w przykładzie)

____
#### Useful tips:
* exit vim - **Esc** *(to exit edit mode)* **:q** *(quits)* or **:wq** *(save and quits)*
* ładny log - **git log --oneline --graph --decorate --all**
