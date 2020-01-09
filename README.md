# LibjpegCompress
调用系统拍照和相册，并压缩图片


使用：
Gradle

```
compile 'me.xiaosai:image_compress:1.0.1'
也可以使用本地库
```

Simple Example：
```
ImageCompress.with(this)
          .load(filePath)
          .setTargetDir(externalStorageDirectory)
          .ignoreBy(150)
          .setOnCompressListener(new ImageCompress.OnCompressListener() {
              @Override
              public void onStart() {
                  Log.e("compress","onStart");
              }
              @Override
              public void onSuccess(String filePath) {
                  Log.e("compress","onSuccess="+filePath);
                  choose_bit.setImageBitmap(BitmapFactory.decodeFile(filePath));
              }
              @Override
              public void onError(Throwable e) {
                  e.printStackTrace();
                  Log.e("compress","onError");
              }
          }).launch();
```
