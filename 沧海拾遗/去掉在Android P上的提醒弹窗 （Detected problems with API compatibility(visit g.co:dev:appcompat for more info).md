# 去掉在Android P上的提醒弹窗 （Detected problems with API compatibility(visit g.co/dev/appcompat for more info)

来源：[去掉在Android P上的提醒弹窗 （Detected problems with API compatibility(visit g.co/dev/appcompat for more info)](https://www.jianshu.com/p/f87fe39caf1d)

Android P 后谷歌限制了开发者调用非官方公开API 方法或接口，也就是说，你用反射直接调用源码就会有这样的提示弹窗出现，非 SDK 接口指的是 Android 系统内部使用、并未提供在 SDK 中的接口，开发者可能通过 Java 反射、JNI 等技术来调用这些接口。但是，这么做是很危险的：非 SDK 接口没有任何公开文档，必须查看源代码才能理解其行为逻辑。
 但是源码是JAVA写的，万物皆可反射，所以还是可以用反射干掉这个 每次启动都会弹出的提醒窗口

```
private void closeAndroidPDialog(){
        try {
            Class aClass = Class.forName("android.content.pm.PackageParser$Package");
            Constructor declaredConstructor = aClass.getDeclaredConstructor(String.class);
            declaredConstructor.setAccessible(true);
        } catch (Exception e) {
            e.printStackTrace();
        }
        try {
            Class cls = Class.forName("android.app.ActivityThread");
            Method declaredMethod = cls.getDeclaredMethod("currentActivityThread");
            declaredMethod.setAccessible(true);
            Object activityThread = declaredMethod.invoke(null);
            Field mHiddenApiWarningShown = cls.getDeclaredField("mHiddenApiWarningShown");
            mHiddenApiWarningShown.setAccessible(true);
            mHiddenApiWarningShown.setBoolean(activityThread, true);
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
```

将这个方法在app初始化时候调用一次，这个弹窗就不会出现了