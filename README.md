# Pfizerprimeus

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 15.2.0.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via a platform of your choice. To use this command, you need to first add a package that implements end-to-end testing capabilities.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.io/cli) page.




commands for the git submodule from common to region specific 


#git submodule add https://<username>@github.com/ashishandb2/poc-common.git pfizerprime/projects/shared


checkout to pfizerprime/projects/shared(master)
git checkout master      # or main, depending on branch name
git pull origin master
git pull origin master #it will have the latest code from common 

git submodule update --remote --merge #### this is the command for update the git submodule 






Set branch tracking for the submodule
From your main repo root:

bash
Copy
Edit
git config -f .gitmodules submodule.projects/shared.branch master
Update submodule to latest master

bash
Copy
Edit
git submodule update --remote --merge



[submodule "projects/shared"]
    path = projects/shared
    url = https://github.com/ashishandb2/poc-common.git
    branch = master





in case the submodule created outside than we need to use this 



# 1. Remove submodule entry
git submodule deinit -f projects/shared
git rm -f projects/shared
rm -rf .git/modules/projects/shared

# 2. Re-add submodule in the correct location
git submodule add https://github.com/ashishandb2/poc-common.git pfizerprimeus/projects/shared

# 3. Initialize and fetch submodule content
git submodule update --init --recursive

# 4. Commit the new submodule path
git add .gitmodules pfizerprimeus/projects/shared
git commit -m "Move shared submodule inside pfizerprimeus/projects"






git submodule add https://github.com/ashishandb2/poc-common.git pfizerprimeus/projects/shared
git submodule update --init --recursive
git add .gitmodules pfizerprimeus/projects/shared
git commit -m "Move shared submodule inside pfizerprimeus/projects"
