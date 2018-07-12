# android-dependencies
Easily manage your Android project dependencies!

## How to use:

### 1. Add `dependencies.gradle` file to your project's root directory.

<br>

### 2. Add this line to your project's `build.gradle` file:

`apply from: 'dependencies.gradle'`

<br>

### 3. In module's `build.gradle`:

    android {
        def config = rootProject.extensions.getByName("ext")

        compileSdkVersion config["androidCompileSdkVersion"]

        defaultConfig {
            minSdkVersion config["androidMinSdkVersion"]
            targetSdkVersion config["androidTargetSdkVersion"]
        }
        // Other configurations...
    }

    dependencies {
        def dependencies = rootProject.ext.dependencies
        def testDependencies = rootProject.ext.testDependencies

        implementation dependencies.kotlin

        testImplementation testDependencies.junit
    }

<br>

## That's it!