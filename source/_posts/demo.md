---
title: demo
date: 2019-07-04 21:40:28
tags:
cover: true
---

`codes`   //单行代码放置于一对反引号中    
          //4空格+codes亦可实现单行代码

```java       //代码块放置于3个反引号中间，回车即可换行     
Stream<String> language = Stream.of("java", "python", "C++","php","java");
Set<String> setResult = language.collect(Collectors.toSet());
setResult.forEach(System.out::println);
 
```

```java
public static int getSizeInBytes(@Nullable Bitmap bitmap) {
    if (bitmap == null) {
        return 0;
    }

    // There's a known issue in KitKat where getAllocationByteCount() can throw an NPE. This was
    // apparently fixed in MR1: http://bit.ly/1IvdRpd. So we do a version check here, and
    // catch any potential NPEs just to be safe.
    if (Build.VERSION.SDK_INT > Build.VERSION_CODES.KITKAT) {
        try {
            return bitmap.getAllocationByteCount();
        } catch (NullPointerException npe) {
            // Swallow exception and try fallbacks.
        }
    }

    if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.HONEYCOMB_MR1) {
        return bitmap.getByteCount();
    }

    // Estimate for earlier platforms.
    return bitmap.getWidth() * bitmap.getRowBytes();
}
```
