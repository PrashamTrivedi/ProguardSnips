# ProguardSnips
A library that does all proguard work for you.

This is a library which has many proguard configuration files. Thanks to [Android Proguard Snippets library](https://github.com/krschultz/android-proguard-snippets), which has a great collection of proguard configuration files. This library exposes them with help of aar, and `consumerProguardFiles` property which enables aar library to expose proguard configuration, so client application does not have to define any proguard configuration (Except their own class). 

This is not new, as of v 7.0 Google Play Service already expose proguard configs using this concept.

## How can I use this library.
Being just created, I am not planning to upload to jCenter before getting to know how it's being used, so for now you can use jitpack to get this library.

Add it in your build.gradle at the end of repositories:
```groovy
 repositories {
        // ...
        maven { url "https://jitpack.io" }
    }
```

and in your app's build.gradle add this
```groovy
dependencies {
	        compile 'com.github.PrashamTrivedi:ProguardSnips:0.1-snapshot'
	}
```

[![Release](https://img.shields.io/github/tag/PrashamTrivedi/ProguardSnips.svg?label=JitPack-ProguardSnips)](https://jitpack.io/#PrashamTrivedi/ProguardSnips/)

## How can I add new proguard snippets-Or how can I contribute?
- It's recommended not to add any proguard configuration which does not belong to any library, thus if a library requires your app's model class to be configured for proguard add such library here. Cupboard for android fits in this case.

If any library is missing or requires upgrade, fork this library and add proguard configuration in proguard directory. Re-sync this with gradle, and you are ready to run your project.

Any tests, wikis.... etc all contributions are welcome

## How can I make sure that proguard is applied properly?
In my knowledge there are two ways to do that.

1. If all of your configurations applied properly, you should be able to run this module successfully
2. Alternatively you can check your app's build directory>outputs>mapping>{VariantName}>seeds.txt, they have list of classes and members which are not obfuscated.

## What is the future of this library?
For sometimes I am keeping this as a snapshot. So we can sort out any issues we have. I plan this to be on jcenter within a month's time. 

But I feel this library will eventually deprecated, because of `consumerProguardFiles` property, every library should publish it's own configuration to the client app. Once a particular library does that, it will be removed from here. And once we have 0 libraries, this library will be auto deprecated.

# Special Thanks
 - [Android Proguard Snippets library](https://github.com/krschultz/android-proguard-snippets), from where these original proguard snippets came. 
 - [RxJavaProguardRules](https://github.com/artem-zinnatullin/RxJavaProGuardRules), creation of which pushed me to create this library.
 - [Ian Lake's this post](https://plus.google.com/+IanLake/posts/1HfDuFFkMXG) 

## License
   	   Copyright 2015 Prasham Trivedi
   	   Licensed under the Apache License, Version 2.0 (the "License");
   	   you may not use this file except in compliance with the License.
   	   You may obtain a copy of the License at

          http://www.apache.org/licenses/LICENSE-2.0

   	   Unless required by applicable law or agreed to in writing, software
   	   distributed under the License is distributed on an "AS IS" BASIS,
   	   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   	   See the License for the specific language governing permissions and
   	   limitations under the License.
