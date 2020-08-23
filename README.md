# Multiple Media Picker :boom: :star2:
### An android library to pick multiple images and/or videos from built-in gallery. This library is encouraged to use as little memory as possible. 

## NOTE: This was created +4 years ago and I am not making any kind of updates since +2 years. If you feel like this library can help you, feel free to fork or contribute creating pull requess (:

![](https://img.shields.io/badge/license-APACHE%202-ff69b4.svg) ![](	https://img.shields.io/badge/bintray-v.1.0.5-673AB7.svg)

![](https://raw.githubusercontent.com/erikagtierrez/multiple-media-picker/master/cover.jpg)

#### Feel free to ask(or request) me anything about it, just create an issue!

# Usage
Include easily in your project adding the dependency to your build.gradle file.  

```gradle
dependencies {
  compile 'com.erikagtierrez.multiple_media_picker:multiple-media-picker:1.0.5'
}
```
# Getting started
In the activity from where you want to call the library, declare

```java
    static final int OPEN_MEDIA_PICKER = 1;  // Request code
```

and request permissions to read external storage

```java
    Manifest.permission.READ_EXTERNAL_STORAGE
```

Create the intent

```java
    Intent intent= new Intent(this, Gallery.class);
    // Set the title
    intent.putExtra("title","Select media");
    // Mode 1 for both images and videos selection, 2 for images only and 3 for videos!
    intent.putExtra("mode",1); 
    intent.putExtra("maxSelection",3); // Optional
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

The primary colors will be inherited from the project it was called. But you can customize a little more by adding to your `colors.xml`

Title and back button color
```xml
 <color name="titleTextColor">#000000</color>  
```
Unselected image/video tab title
```xml
 <color name="titleTabColor">#000000</color>   
```
Selected image/video tab title!
```xml
<color name="titleSelectedTabColor">#E040FB</color>
``` 

Make sure to override the titleTextColor inside your theme in `styles.xml`

```xml
<item name="titleTextColor">@color/titleTextColor</item>
```

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
