## ButterKnife Proguard

Butter Knife generates and uses classes dynamically which means that static analysis tools like ProGuard may think they are unused. In order to prevent them from being removed, explicitly mark them to be kept. To prevent ProGuard renaming classes that use @Bind on a member field the keepclasseswithmembernames option is used.

```
-keep class butterknife.** { *; }
-dontwarn butterknife.internal.**
-keep class **$$ViewBinder { *; }

-keepclasseswithmembernames class * {
    @butterknife.* <fields>;
}

-keepclasseswithmembernames class * {
    @butterknife.* <methods>;
}
```
