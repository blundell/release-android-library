release-android-library
=======================

Remote script to create a maven compatible release of an android library (aar). This release comes in a zip or exploded form and is only created locally inside your own build folder. You can these use these files to release to JCenter or Maven Central.

Matching blog post here: [blog.blundell-apps.com/locally-release-an-android-library-for-jcenter-or-maven-central-inclusion/](http://blog.blundell-apps.com/locally-release-an-android-library-for-jcenter-or-maven-central-inclusion/)

####adding to your library
```
apply plugin: 'com.android.library'

ext {
    PUBLISH_GROUP_ID = 'com.blundell'
    PUBLISH_ARTIFACT_ID = 'example-library-name'
    PUBLISH_VERSION = '1.0.0'
}

android {
    // configs, flavors etc
}

dependencies {
    // dependencies
}

// Copy the file locally and use
apply from: 'android-release-aar.gradle'
// or use the remote copy to keep update with latest changes
apply from: 'https://raw.githubusercontent.com/blundell/release-android-library/master/android-release-aar.gradle'
```


####useage

`./gradlew clean build generateRelease`

####example output


```
 :engine:zipRelease
 :engine:generateRelease
 Release 1.0.0 can be found at /Users/Blundell/Developer/git_repo/ExampleAndroidLibrary/build/release/1.0.0/
 Release 1.0.0 zipped can be found /Users/Blundell/Developer/git_repo/ExampleAndroidLibrary/build/release-1.0.0.zip

 BUILD SUCCESSFUL
 
 Total time: 23.609 secs
```
