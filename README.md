# Android Actionsheet

[![API](https://img.shields.io/badge/API-14%2B-red.svg?style=flat)](https://android-arsenal.com/api?level=14)
[![](https://jitpack.io/v/inibukanadit/android-actionsheets.svg)](https://jitpack.io/#inibukanadit/android-actionsheets)

Android Actionsheet is an Android Library to build Actionsheet (iOS UIActionSheet) component, iOS7 style, custom color etc

![alt text](https://image.ibb.co/bzgpFy/mm_min.png)
![alt text](https://www.appcoda.com/wp-content/uploads/2014/05/t11_1_normal_action_sheet.jpg)

## Installation

-  Add the following to your project level `build.gradle`:
 
```gradle
allprojects {
    repositories {
        maven { url 'https://jitpack.io' }
    }
}
```
  -  Add this to your app `build.gradle`:
 
```gradle
implementation 'com.github.inibukanadit:android-actionsheets:0.3-alpha1'
```

## How to use in Java.

```java
ArrayList<String> data = new ArrayList<>();

data.add("Delete it");
data.add("Copy");
data.add("Move");
data.add("Duplicate");

new ActionSheet(MainActivityJava.this,data)
                        .setTitle("What do you want to do with the file")
                        .setCancelTitle("Cancel")
                        .setColorTitle(getResources().getColor(R.color.title))
                        .setColorTitleCancel(getResources().getColor(R.color.action))
                        .setColorData(getResources().getColor(R.color.action))
                        .create(new ActionSheetCallBack() {
                            @Override
                            public void data(@NotNull String data, int position) {
			    	// check the position to determine which menu to handle
                            }
                        });
```

## How to use in Kotlin.
```kotlin
val data by lazy { ArrayList<String>() }

data.add("English")
data.add("Indonesia")

ActionSheet(this,data)
                   .setTitle("Select Country")
                   .setCancelTitle("Cancel")
                   .setColorTitleCancel(Color.parseColor("#FF4081"))
                   .setColorTitle(Color.parseColor("#FF4081"))
                   .setColorData(Color.parseColor("#FF4081"))
                   .create(object : ActionSheetCallBack {
                       override fun data(data: String, position: Int) {
                           if ("English".equals(data)) {
                               // action
                           } else if("Indonesia".equals(data)) {
                               // action
                           }
                       }
                   })
```
  
## With variable

  -  Initialize variable:
```java
ActionSheet actionSheet;

actionSheet = new ActionSheet(MainActivityJava.this,data)
                        .setTitle("What do you want to do with the file")
                        .setCancelTitle("Cancle")
                        .setColorTitle(getResources().getColor(R.color.title))
                        .setColorTitleCancel(getResources().getColor(R.color.action))
                        .setColorData(getResources().getColor(R.color.action));
                        
actionSheet.create(new ActionSheetCallBack() {
                    @Override
                    public void data(@NotNull String data, int position) {
                        // switch or if handle
                    }
                });
```
## Features

Function      				   | description
-------------------------------------------| -------------
.hideTitle()  			           | hide the Title
.setFontTitle(R.font.meryana_script)       | change the font of Title
.setFontData(R.font.meryana_script)        | change the font of text Data
.setFontCancelTitle(R.font.meryana_script) | change the font of Cancel
.setSizeTextTitle(30)		 	   | change the size of Title
.setSizeTextData(30)		           | change the size of text Data
.setSizeTextCancel(30)			   | change the size of Cancel



License
=======
Copyright 2018 [M Khoiron](https://medium.com/@khoiron)

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

Al-hamdulillahi Rabbil 'alamin And Special thanks to [JetBrains](https://github.com/JetBrains) and [jitpack.io](https://github.com/jitpack-io) for their contributions to this project.
