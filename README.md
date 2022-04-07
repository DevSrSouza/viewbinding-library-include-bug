# How to reproduce

## Step ViewBinding working
This step, the thrid party library in fact is just a module in the project: `implementation(project())`

1. run `./gradlew clean`
2. run `rm -rf app/libs`
23. build: `./gradlew :app:assembleDebug`

Should compile with success


## Step ViewBinding not working
This step, we build the library, generating a Aar and then import the Aar in the app module.

1. run `./gradlew clean`
2. run `./gradlew :mylibrary:assembleRelease`
3. run `./gradlew :app:assembleDebug`

Should fail with:

```
e: app/src/main/java/com/example/androidviewbinding/MainActivity.kt: (16, 30): Unresolved reference. None of the following candidates is applicable because of receiver type mismatch: 
internal val File.root: File defined in kotlin.io
```
