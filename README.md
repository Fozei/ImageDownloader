# ImageDownloader
A imagedownloader based on Android-Universal-Image-Loader

Thanks for nostar13 first, this lib just modified some basic methods of nostar13's UIL lib.
And the use age is totally same as UIL, details please see :
https://github.com/nostra13/Android-Universal-Image-Loader

This lib is useful when you just want to download some pictures and save is as a file, nor you want to
decode it.

For example, you want to display a huge image, such as a WorldMap, if you use UIL or Glide to load it
directly, it may be subsampled, so the pic will be indistinct when you scale it large. At this time, use
this lib, download it only and did not decode it, use another lib named subsampling-scale-image-view
to load it, that will be perfect.
subsampling-scale-image-view:
https://github.com/davemorrissey/subsampling-scale-image-view


Methods Change:
```
private ImageLoadingListener imageLoadingListener = new ImageLoadingListener() {
        @Override
        public void onLoadingStarted(String imageUri, View view) {

        }

        @Override
        public void onLoadingFailed(String imageUri, View view, FailReason failReason) {

        }

        @Override
        public void onLoadingComplete(String imageUri, View view, Bitmap loadedImage, File file) {
            //do your work here
        }

        @Override
        public void onLoadingCancelled(String imageUri, View view) {

        }
    };
```

NOTE: for decrease memory load, this lib discard the function of decode images, so in method onLoadingComplete,
the loadedImage reference is a null !!!!
