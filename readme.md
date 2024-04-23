# Multi-module project.
A practice project used to demonstrate how to set up a multi-module project with Maven and using
Git submodules:
https://git-scm.com/book/en/v2/Git-Tools-Submodules

## Create mvn projects
``
mvn archetype:generate -DinteractiveMode=true
``
->
``
groupid: com.reynolds
artifactid: multi-module-parent/multi-module-1/multi-module-2/multi-module-3
``

### Assign Maven submodules
``
  <modules>
    <module>../multi-module-1</module>
    <module>../multi-module-2</module>
    <module>../multi-module-3</module>
  </modules>
``

## Initialise git repos
``
git config --global user.name "Lawrence Reynolds"
git config --global user.email "lawrence.m.reynolds@googlemail.com"
``

### Create repos on github
multi-module/multi-module-parent

multi-module/multi-module-1

multi-module/multi-module-2

multi-module/multi-module-3

### Each project:
``
git init
git remote add origin https://github.com/Lawrence-M-Reynolds/multi-module-multi-module-parent.git
git branch -M main
git push -u origin main
``
``
git init
git remote add origin https://github.com/Lawrence-M-Reynolds/multi-module-multi-module-1.git
git branch -M main
git push -u origin main
``
``
git init
git remote add origin https://github.com/Lawrence-M-Reynolds/multi-module-multi-module-2.git
git branch -M main
git push -u origin main
``
``
git init
git remote add origin https://github.com/Lawrence-M-Reynolds/multi-module-multi-module-3.git
git branch -M main
git push -u origin main
``

### Setup git submodules
https://git-scm.com/book/en/v2/Git-Tools-Submodules

#### In Parent
``
git submodule add https://github.com/Lawrence-M-Reynolds/multi-module-multi-module-1.git
git submodule add https://github.com/Lawrence-M-Reynolds/multi-module-multi-module-2.git
git submodule add https://github.com/Lawrence-M-Reynolds/multi-module-multi-module-3.git
``

#### Re-checkout
After rechecking out you have to set the branch to "main":
``
git checkout main
``
Add gitignore to each and commit.