# Butler neos-base distribution recipe

This is a recipe for butler to create a basic neos cms installation with some additional packages and a local development environment.
I build this recipe to spin up new neos projects more faster and automated.
So i can start development after some minutes of watching cli or drinking tea.


Butler is a task-runner based on php and configurable with yaml files. (https://github.com/freesh/butler)


For more information about neos cms visit: http://www.neos.io

## Usage:

### install recipe
```
mkdir -p ~/Butler/Project/
cd ~/Butler/Project/
git clone https://github.com/freesh/neos-base.git
```

### use recipe

```
cd myprojectfolder
butler project:run neos-base/neos-base
```

## Features:

This recipe init neos based on actual stable version.


**Sitepackage creation**

You will be asked for a project name and a sitepackage key. This will create a new Sitepackage in the _DistributionPackages_ folder


**Living Styleguide with sitegeist/monocle**

This package brings a wonderful living styleguide to your new neos project.
For further informations visit: https://github.com/sitegeist/Sitegeist.Monocle


**Easy Local Dev with live data**

It is useful to develop local with the same data as in your live system.
This can be easily initialized and updated with the sitegeist/magicwand package.
For further informations visit: https://github.com/sitegeist/Sitegeist.MagicWand


**Docker setup included**

This recipe runs docker-compose to start a database for local installing and setup neos.
All neos dev configuration for this database will be also created.
For PHP no docker container is used. It runs with the flow server:run command.
After running neos-base recipe you can start you local development with:

```
docker-compose up -d && ./flow server:run
```

And than visit the ip which is listed after executing the command.
Local Admin user credentials are: admin:admin ( Don't do this a live, it's just for local development ;) )

**Init Git**

I use this setup for automated initialization of new projects.
This recipe will init a git repository and ask for a remote repository url to push.
You will be asked and have to acknowledge the push. So this is just an option.


**Linting and testing commands for composer.**

Following packages are installed for linting and testing

- sitegeist/neosguidelines
- editorconfig-checker/editorconfig-checker
- squizlabs/php_codesniffer

Commands:
```
composer run lint
composer run test
```


## Don't forget
Butler is an experimental project. ;) So it is not perfect and some refactorings are planed. :)
