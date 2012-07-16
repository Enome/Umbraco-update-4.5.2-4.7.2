# Python Marcos

- Go to http://umbraco.codeplex.com/releases/view/81011
- Download "Support for IronPython/IronRuby macros"
- Copy everything to bin except for the ruby stuff
- Copy Python files to -> MacroScripts
- If the macro files import an other python file that file needs to put into /python dir. I used utils.py file a lot so put it in /python/utils.py


# Static Files

- Copy media -> media
- Copy scripts -> scripts
- Copy images -> images
- Copy masterpages -> masterpages


# Web.config

- Copy/Set  - appSettings > add key="umbracoDbDSN"
- Copy/Set -  appSettings > add key="umbracoConfigurationStatus" value="4.7.2"


# Imagegen

- Just reinstall it again.
- It now installs at /ImageGen.ashx and not in /umbraco/ImageGen.ashx. So remove /umbraco from /umbraco/ImageGen.ashx in macros


# ClientDependency (less/js) minification/parsing

- debug=false in web.config ( for some reason it didn't work locally with debug=true )

# Less

Download less.dll from http://www.dotlesscss.org/

Add the following to web.config depending on what version of IIS6 you use. More info on [here](http://blog.mattbrailsford.com/2010/08/12/using-dotless-and-the-client-dependency-framework-in-umbraco/)

IIS6

```xml
<configuration>
 <system.web>
 <httpHandlers>
 <add verb="*" path="*.less" type="dotless.Core.LessCssHttpHandler, dotless.Core" validate="false" />
 </httpHandlers>
 </system.web>
</configuration>
```

IIS7

```xml
<configuration>
 <system.webServer>
 <handlers>
 <remove name="DotLessCss" />
 <add name="DotLessCss" verb="*" path="*.less" type="dotless.Core.LessCssHttpHandler, dotless.Core" preCondition="integratedMode" />
 </handlers>
 </system.webServer>
</configuration>
```