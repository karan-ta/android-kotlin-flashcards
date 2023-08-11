
---
tags: review
---

in which method you will save the data when app goes in background
?
onSaveInstanceState
<!--SR:!2023-08-13,4,270-->

In which scenario onDestroy will be called directly after onCreate
?
when finish is called in onCreate
<!--SR:!2023-08-13,4,270-->

What is apk::Android executable format

what does apk contain
?
compiled code, resources , manifest file, miscellaneous files

What is AppCompat
?
it provides compatible api for different versions.

What is fragment
?
Wrapper around layout resources and their widgets.  
Many apps might consist of a single activity, with each different  
"screen" being represented by a fragment that uses associated layout resources and  
code. The user, as part of using the app, will switch from fragment to fragment as  
needed — for example, clicking a button might cause another fragment to be shown  
on the screen.

what is a service
?
service is an application component that facilitates an app to run in the bg for doing long running taks without a ui 
 1. foreground  services : notification : eg media ; download 
 2. background : 
 3. bounded services 

What is viewmodel
?
The ViewModel class is designed to store and manage UI-related data in a lifecycle conscious way. The ViewModel class allows data to survive configuration changes such as screen rotations.
The purpose of ViewModel is to encapsulate the data for a UI controller to let the data survive configuration changes

What is livedata
?
LiveData is an observable data holder class.  
Lifecycle awareness ensures LiveData only updates app component observers that are in an active lifecycle state.

What is a mipmap
?
Home screen launcher icon is a mipmap. Everything else is a drawable

Types of resources
?
Drawables,mipmaps,colors,layouts,strings

what info is present in androidmanifest
?
name,icon,permissions, allow device wide backups.

4 types of components
?
activities,services,content providers, broadcast receivers

intent-filter
?
describes under what conditions , the activity will be displayed .  
example  
<action android:name="android.intent.action.MAIN" /><category android:name="android.intent.category.LAUNCHER" /> Launcher Activity.

component tags present in manifest
?
<activity>, <service>, <provider>, <receiver>  
They might have an <intent-filter>  
• They might have other attributes as well (e.g., android:permission )

What is this dependency :  
com.android.tools.build:gradle
?
Android Plugin for gradle.

What is this dependency :  
org.jetbrains.kotlin:kotlin-gradle-plugin ,
?
how to compile kotlin code

Viewmodels
?
provide UI state and access to the business logic










