# Guide to Android Plug-In Techniques

[!cover](https://img10.360buyimg.com/n1/s200x200_jfs/t25717/130/277544800/77121/dfab18dd/5b6aaf4eNf244aca8.jpg)

The url of Chinese book: https://item.jd.com/12408095.html


## Context ##

### Part 1: Basic Knowledge ###

  * Chapter 1: Plugable from Past to Future(https://www.cnblogs.com/Jax/p/9547734.html)
    * [1.1 What is the plug-in？](https://www.cnblogs.com/Jax/p/9549311.html)
    * [1.2 Why need pluggable?](https://www.cnblogs.com/Jax/p/9549320.html)
    * [1.3 Android Plug-in History](https://www.cnblogs.com/Jax/p/9549341.html)
    * [1.4 The usage of plugability](https://www.cnblogs.com/Jax/p/9549355.html)
    * [1.5 React Native, A better alternative](https://www.cnblogs.com/Jax/p/9549361.html)
    * [1.6 Why only in China?](https://www.cnblogs.com/Jax/p/9549367.html)
    * [1.7 All components require plug-in?](https://www.cnblogs.com/Jax/p/9549373.html)
    * [1.8 Double-Opening and Virtual Machine](https://www.cnblogs.com/Jax/p/9549384.html)
    * [1.9 From Native to HTML5](https://www.cnblogs.com/Jax/p/9549395.html)

  * Chapter 2: In-depth Knowledge of Android
    * 2.1 Overview
    * 2.2 The working principle of Binder
    * 2.3 The working principle of AIDL
    * 2.4 The working principle of AMS
    * 2.5 The working principle of Activity
        * 2.5.1 How to launch an App
    * 2.6 Navigation in App
    * 2.7 Context family
    * 2.8 The working principle of Service
        * 2.8.1 Start Service in a new process
        * 2.8.2 Start Service in the same process
        * 2.8.3 Bind Service in the same process
    * 2.9 The working principle of BroadcastReceiver
        * 2.9.1 Register a BroadcastReceiver
        * 2.9.2 Send a BroadcastReceiver
        * 2.9.3 Kinds of BroadcastReceiver
    * 2.10 The working principle of ContentProvider
        * 2.10.1 ContentProvider
        * 2.10.2 Anonymous Shared Memory(ASM)
        * 2.10.3 Communication between ContentProvider and AMS
    * 2.11 PMS
        * 2.11.1 The working principle of PMS
        * 2.11.2 Process of App installing
        * 2.11.3 PackageParser
        * 2.11.4 ActivityThread and PackageManager
    * 2.12 ClassLoader family
    * 2.13 Parent Delegate
    * 2.14 MultiDex
    * 2.15 Implect a music App
        * 2.15.1 Solution1: Base on 2 BroadcastReceiver
        * 2.15.2 Solution2: Base on 1 BroadcastReceiver
    * 2.16 Summary

  * Chapter 3: Reflection
    * 3.1 Basic reflection syntax
        * 3.1.1 Reflect a class by string 
        * 3.1.2 Reflect class memebers
        * 3.1.3 Reflect generic class 
    * 3.2 jOOR
        * 3.2.1 Reflect a class by string 
        * 3.2.2 Reflect class memebers 
        * 3.2.3 Reflect generic class
    * 3.3 Encapsulation on the basic reflection syntax 
        * 3.3.1 Reflect constructor 
        * 3.3.2 Reflect instance method
        * 3.3.3 Reflect static method 
        * 3.3.4 Reflect field
        * 3.3.5 Reflect generic class
    * 3.4 Further encapsulation of Reflection
    * 3.5 Summary

  * Chapter 4: Proxy pattern
    * 4.1 What’s Proxy pattern?
        * 4.1.1 AIDL
        * 4.1.2 Add/Remove Permission 
        * 4.1.3 Image Stub 
        * 4.1.4 Mock Class
        * 4.1.5 Write Log
    * 4.2 Proxy.newProxyInstance
    * 4.3 Hook AMN
    * 4.4 Hook PMS
    * 4.5 Summary

  * Chapter 5: Hook startActivity
    * 5.1 startActivity method in 2 forms
    * 5.2 Hook startActivity method of Activity
        * 5.2.1 Solution 1: Hook startActivityForResult method of Activity
        * 5.2.2 Solution 2: Hook mInstrumentation field of Activity
        * 5.2.3 Solution 3: Hook getDefault method of AMN
        * 5.2.4 Solution 4: Hook mCallback field of H
        * 5.2.5 Solution 5: Hook Instrumentation again
    * 5.3 Hook startActivity method of Context
        * 5.3.1 Solution 6: Hook mInstrumentation field of ActivityThread
        * 5.3.2 Conclusion: Solution 3 is the best way
    * 5.4 Start an activity without declaring in AndroidManifest
        * 5.4.1 How to hook AMS 
        * 5.4.2 First half of Hook 
        * 5.4.3 Second half of Hook: Hook mCallback field of H
        * 5.4.4 Second half of Hook: Hook mInstrumentation field of ActivityThread
        * 5.4.5 The fault of AMS Hook
    * 5.5 Summary

### Part 2: Solution ###

  * Chapter 6: Basic Knowledge of Plug-in 
    * 6.1 Load dex from another Apk
    * 6.2 Interface oriented programming
    * 6.3 Plug-in thinning
    * 6.4 Plug-in debug 
    * 6.5 Plug-in solution of Application
    * 6.6 Summary

  * Chapter 7: Resources in plug-in(1)
    * 7.1 How to load resources in Android
        * 7.1.1 Kinds of resources
        * 7.1.2 Resources and AssetManager
    * 7.2 Plug-in Solution of Resources
    * 7.3 Skin changing by Plug-in
    * 7.4 Another solution of Skin changing
    * 7.5 Summary

  * Chapter 8: The simplest Plug-in solution 
    * 8.1 Declare Plug-In components in AndroidManifest of HostApp
    * 8.2 Load class in Plug-in
    * 8.3 Start service in Plug-In
    * 8.4 Load resources in Plug-In
    * 8.5 Summary

  * Chapter 9: Plug-In solution of Activity
    * 9.1 Start a Plug-In Activity not declared in AndroidManifest
    * 9.2 Plug-In solution of Activity: base on dynamic replacing
        * 9.2.1 The working principle of starting an Activity
        * 9.2.2 Add Plug-In Activity in cache
        * 9.2.3 Solution 1 of loading class in Plug-In: Create DexClassLoader for each Plug-In apk
        * 9.2.4 Hook more classes
    * 9.3 Solution 2 of loading class in Plug-In: merge all the Plug-In dex into one array
    * 9.4 Plug-In Solution of Resources 
    * 9.5 Support LaunchMode in Plug-In
    * 9.6 Solution 3 of loading class in Plug-In: Hook ClassLoader
    * 9.7 Summary

  * Chapter 10: Plug-In solution of Service
    * 10.1 The relationship between Service and Activity
    * 10.2 StubService
    * 10.3 Plug-In solution of startService
    * 10.4 Plug-In solution of bindService
    * 10.5 Summary

  * Chapter 11: Plug-In solution of BroadcastReceiver
    * 11.1 Receiver overview
    * 11.2 Plug-In Solution of dynamic BroadcastReceiver
    * 11.3 Plug-In Solution of static BroadcastReceiver
    * 11.4 Final Plug-In Solution of static BroadcastReceiver 
    * 11.5 Summary

  * Chapter 12: Plug-In solution of ContentProvider
    * 12.1 ContentProvider overview
    * 12.2 A simple Demo to introduce ContentProvider
    * 12.3 Plug-In Solution of ContentProvider
    * 12.4 When to hook ContentProvider
    * 12.5 Forward ContentProvider from host to plug-in
    * 12.6 Summary  

  * Chapter 13: A plug-in framework base on Static Proxy: DL
    * 13.1 The concept of Static Proxy
    * 13.2 A simple demo to intriduce Static Proxy
        * 13.2.1 Navigation from HostApp to another App
        * 13.2.2 Communication between ProxyActivity and plug-in Activity
        * 13.2.3 The logic of plug-in activity 
    * 13.3 Navigation in the plug-in App
    * 13.4 Abandon “that” keyword
    * 13.5 Navigation from plug-in to outside
    * 13.6 Interface oriented programming in DL
    * 13.7 Support LaunchMode in plug-in 
    * 13.8 Summary  

  * Chapter 14: Support Service and BroadReceiver in DL
    * 14.1 Support Service in DL
    * 14.2 Support BindService in DL
    * 14.3 StubService in DL
    * 14.4 Final Plug-In solution of Service: combination of dynamic hook and static proxy
        * 14.4.1 Parse Service component in Plug-In App
        * 14.4.2 Create a Service object by reflection
        * 14.4.3 ProxyService and ServiceManager
        * 14.4.4 Plug-In solution of bindService
    * 14.5 Support BroadcastReceiver in DL
    * 14.6 Summary  

  * Chapter 15: Resources in plug-in(2)
    * 15.1 The process of Android App packaging
    * 15.2 Hook AAPT
        * 15.2.1 Hook AAPT and generate new command
        * 15.2.2 Use new AAPT in plug-in
        * 15.3 public.xml 
    * 15.4 Plug-in uses resources in HostApp 
    * 15.5 Summary

  * Chapter 16: A plug-in framework base on Fragment 
    * 16.1 AndroidDynamicLoader overview
    * 16.2 A simple plug-in demo base on Fragment
    * 16.3 Fragment Navigation inside plug-in
    * 16.4 Fragment Navigation from plug-in to outside
    * 16.5 Summary

### Part 3: Techniques related ###

  * Chapter 17: H5 Downgrade
    * 17.1 from Activity to HTML5
    * 17.2 from HTML5 to Activity
    * 17.3 Support BackPress
    * 17.4 Summary  

  * Chapter 18: Obfuse on plug-in
    * 18.1 Basic obtuse concept on plug-in
    * 18.2 Solution 1: No obfuse MyPluginLibrary
    * 18.3 Solution 2: Obfuse MyPluginLibrary
        * 18.3.1 Configure multidex
        * 18.3.2 Configure proguard
        * 18.3.3 Remove redundant apk in Plugin1.apk
    * 18.4 Summary

  * Chapter 19: Incremental Update
    * 19.1 How to use Incremental Update
    * 19.2 Make patch file for Plug-In 
    * 19.3 Download and unzip patch file
    * 19.4 Merge patch file
    * 19.5 Summary

  * Chapter 20: Plug-in Solution of SO
    * 20.1 Make a simple SO
    * 20.2 Use SO in App
    * 20.3 The working principle of SO
    * 20.4 Plug-in Solution 1 of SO, base on System.load
    * 20.5 Plug-in Solution 2 of SO, base on System.loadLibrary
    * 20.6 Summary

  * Chapter 21: Hook App packaging process 
    * 21.1 Gradle Plug-In project
        * 21.1.1 Create Gradle Plug-In project
        * 21.1.2 Extension
        * 21.1.3 Hook packaging process
    * 21.2 Mock resources.arsc
        * 21.2.1 How to find resource in Android
        * 21.2.2 Function of AAPT
        * 21.2.3 The working principle of gradle-small
        * 21.2.4 How to use gradle-small
        * 21.2.5 Plugin family in gradle-small
        * 21.2.6 Editor family in gradle-small
    * 21.3 Summary

  * Chapter 22: summary of plug-in technology
    * 22.1 Plug-in engineering
    * 22.2 Load class in Plug-in
    * 22.3 Which class can be Hook?
    * 22.4 Plug-in Solution of Activity
    * 22.5 Plug-in Solution of Resources
    * 22.6 What’s Fragment?
    * 22.7 Common Plug-in Soultion of Service, ContentProvider, BroadcastReceiver plug-in
    * 22.8 Plug-in Soultion specific to Service 
    * 22.9 Plug-in Soultion specific to BroadcastReceiver
    * 22.10 Plug-in Soultion specific to ContentProvider
    * 22.11 Summary



