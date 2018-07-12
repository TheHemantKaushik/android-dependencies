# android-dependencies
Easily manage your Android project dependencies!

## How to use:
Add this line to your project's `build.gradle` file:

`apply from: 'dependencies.gradle'`

In module's `build.gradle`:

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


## That's it!