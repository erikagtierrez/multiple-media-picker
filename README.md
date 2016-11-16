# Multiple Media Picker :boom: :star2:
### An android library to pick multiple images and/or videos from built-in gallery. This library is encouraged to use as little memory as possible. 

[![Join the chat at https://gitter.im/Multiple-Media-Picker/Lobby](https://badges.gitter.im/Multiple-Media-Picker/Lobby.svg)](https://gitter.im/Multiple-Media-Picker/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge) ![](https://img.shields.io/badge/license-APACHE%202-ff69b4.svg) 

![](https://raw.githubusercontent.com/erikagtierrez/multiple-media-picker/master/cover.jpg)

#### Feel free to ask(or request) me anything about it, just create an issue or join the gitter chat!

# Usage
Include easily in your project adding the dependency to your build.gradle file.  

```gradle
dependencies {
  compile 'com.erikagtierrez.multiple_media_picker:multiple-media-picker:1.0.0'
}
```
# Getting started
In the activity from where you want to call the library, declare

```java
    static final int OPEN_MEDIA_PICKER = 1;  // Request code
```
Create the intent

```java
    Intent intent= new Intent(this, Gallery.class);
    //Set the title
    intent.putExtra("title","Select media");
    startActivityForResult(intent,OPEN_MEDIA_PICKER);
```

and override onActivityResult 

```java
@Override
    protected void onActivityResult(int requestCode, int resultCode, Intent data) {
        // Check which request we're responding to
        if (requestCode == OPEN_MEDIA_PICKER) {
            // Make sure the request was successful
            if (resultCode == RESULT_OK && data != null) {
                 ArrayList<String> selectionResult=data.getStringArrayListExtra("result");
            }
        }
    }
```

## Custom styles

The colors will be inherited from the class it was called.

# License

```
Copyright 2016 Erika Gutierrez

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
