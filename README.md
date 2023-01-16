# xposed-ktx

A set of Kotlin extensions to the original Xposed API which tries to make writing Xposed modules much less cumbersome.

## Usage

```kotlin
// Initialize xposed-javax first
XposedPlus.setDefaultInstance(XposedPlus.Builder(param))

// Hook something:
findMethod("com.app.Application", "onCreate")
	.hook({ param ->
		// beforeHookedMethod...
	}, { param ->
		// afterHookedMethod...
	})

// or e.g. if you only need afterHookedMethod:
findMethod("com.app.Application", "onCreate")
	.after { param ->
		// afterHookedMethod...
	}
```

## Declaring xposed-ktx as a Gradle dependency

```gradle
allprojects {
    repositories {
        // ...
        maven { url 'https://jitpack.io' }
    }
}

dependencies {
    implementation 'com.github.Kazurin-775:xposed-ktx:1.3.1-mod2'
}
```

This module depends on `com.github.sky-wei:xposed-javax:1.2.0`, which is automatically included in your project's dependency tree (as long as you fetch this module from jitpack.io, as the code above does). No additional configuration is needed.

## License

    Copyright 2018 The sky Authors
    
    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at
    
       http://www.apache.org/licenses/LICENSE-2.0
    
    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.

