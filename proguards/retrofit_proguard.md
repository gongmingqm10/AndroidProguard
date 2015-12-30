## Retrofit Proguard

If you are using Proguard in your project add the following lines to your configuration:

```
-dontwarn retrofit.**
-keep class retrofit.** { *; }
-keepattributes Signature
-keepattributes Exceptions
```
