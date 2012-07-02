# Python Marcos

- Go to http://umbraco.codeplex.com/releases/view/81011
- Download "Support for IronPython/IronRuby macros"
- Copy everything to bin except for the ruby stuff
- Copy Python files to -> MacroScripts
- If the macro files import an other python file that file needs to put into /python dir. I used a lot of utils.py file so put it in /python/utils.py


# Media

- copy media -> media


# Images

- Copy images -> images


# Web.config

- Copy/Set  - appSettings > add key="umbracoDbDSN"
- Copy/Set -  appSettings > add key="umbracoConfigurationStatus" value="4.7.2"


# Imagegen

- Just reinstall it again.
- It now installs at /ImageGen.ashx and not in /umbraco/ImageGen.ashx. So remove /umbraco from /umbraco/ImageGen.ashx in macros


# Javascript

- Copy scripts -> scripts


# Masterpages

- Copy masterpages -> masterpages


# ClientDependency (less/js) minification/parsing

- debug=false in web.config ( for some reason it didn't work locally with debug=true )

