# Divding and Conquering Your Xcode Projects with Targets

## Introduction

> By selecting the project name in the project navigator,you open the project editor.

> Build settings defined at the target level override any values assigned to those build
> settings at the project level.Therefore,target-level configuration take precedence over
> any project level configurations.

> A target contains instructions - in the form of build settings and build phases - for 
> building a product. A target inherits the project's build settings. Although most develpers
> seldom need to change these settings,you can override any of the project's build settings
> by specifying different settings at the target level.

## A note about "configurations"

> When you create a project,Xcode provides two standard project-level build configurations: 
> debug and release....These two build configurations are probably sufficient for your product
> development needs.Most developers never need to change the values of the vast majority of 
> build settings.

## Separating release settings from debug settings

> when you open an existing project(or create a new one),Xcode
> automatically creates a scheme for each target.The default
> scheme is named after your project.

## A note about Info.plist

> when you *Duplicate*(create) a new target,Xcode creates a new Inof.plist.It gives the new
> target a name you probably don't want and puts the file where you probably don't want.

## Release versus debug dependencies

*Build Phases -> Link Binary With Libraries*
*Build Settings -> Search Paths -> User Header Search Paths*

## Compilation conditions

* Build Settings -> APPle LLVM 9.0 - Preprocessing -> Preprocessor Macros*

> A conditional compilation block allows code to be conditionally
> compiled depending on the value of one or more compilation
> condition.

## Different app flavors/branding


