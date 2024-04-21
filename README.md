# Ex.No:8 To create a gallery control using android studio to display images or photos.


## AIM:

To create a gallery control using android studio to display images or photos.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:

Prepare Images: Gather the images you want to display in the gallery and store them in the res/drawable folder of your Android project.

Design Layout: Create the layout for the main activity (activity_main.xml). Include a Gallery widget to display the images and an ImageView to show the selected image.

Set up Adapter: Develop a custom adapter class (CustomizedGalleryAdapter.java) that extends BaseAdapter. Override necessary methods like getCount() and getView() to handle the gallery items and their display.

Initialize Gallery: In the main activity (MainActivity.java), initialize the Gallery widget and set its adapter to the custom adapter you created.

Handle Item Selection: Implement functionality to respond when the user selects an image from the gallery. Update the ImageView with the selected image accordingly.

## PROGRAM:
```
/*
Program to print the text “GalleryControl”.
Developed by:212222040144
Registeration Number :SANDHYA B N
*/
```
Activity main.xml:
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <Gallery
        android:id="@+id/gallery"
        android:layout_width="fill_parent"
        android:layout_height="wrap_content"
        android:layout_alignParentTop="true"
        android:layout_centerHorizontal="true"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.889" />

    <ImageView
        android:id="@+id/imageView"
        android:layout_width="fill_parent"
        android:layout_height="fill_parent"
        android:layout_below="@+id/gallery"
        android:layout_centerHorizontal="true"
        android:scaleType="fitCenter" />

</androidx.constraintlayout.widget.ConstraintLayout>
```
Mainactivity.Java:
```
package com.example.gallerycontol;

import android.app.Activity;
import android.content.Context;
import android.os.Bundle;
import android.view.View;
import android.view.ViewGroup;
import android.widget.AdapterView;
import android.widget.BaseAdapter;
import android.widget.Gallery;
import android.widget.ImageView;

public class MainActivity extends Activity {

    private Integer[] mImageIds = {
            R.drawable.image1,
            R.drawable.image2,
            R.drawable.image3,
            R.drawable.image4
    };

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Gallery gallery = (Gallery) findViewById(R.id.gallery);
        gallery.setAdapter(new ImageAdapter(this));

        gallery.setOnItemClickListener(new AdapterView.OnItemClickListener() {
            @Override
            public void onItemClick(AdapterView<?> parent, View view, int position, long id) {
                ImageView imageView = (ImageView) findViewById(R.id.imageView);
                imageView.setImageResource(mImageIds[position]);
            }
        });
    }

    public class ImageAdapter extends BaseAdapter {
        private Context mContext;

        public ImageAdapter(Context c) {
            mContext = c;
        }

        public int getCount() {
            return mImageIds.length;
        }

        public Object getItem(int position) {
            return null;
        }

        public long getItemId(int position) {
            return 0;
        }

        public View getView(int position, View convertView, ViewGroup parent) {
            ImageView imageView = new ImageView(mContext);
            imageView.setImageResource(mImageIds[position]);
            imageView.setLayoutParams(new Gallery.LayoutParams(150, 100));
            imageView.setScaleType(ImageView.ScaleType.FIT_XY);
            return imageView;
        }
    }
}
```


## OUTPUT


![WhatsApp Image 2024-04-21 at 18 20 33_832a778c](https://github.com/sandhyabalamurali/gallerycontrol/assets/115525118/cf2be3bb-1eca-4eb2-a1cb-2b57208fd103)

![WhatsApp Image 2024-04-21 at 18 20 33_ba48c514](https://github.com/sandhyabalamurali/gallerycontrol/assets/115525118/8e650a81-3fd7-4329-a7c8-d9c0bb46b4e6)


## RESULT
Thus a Simple Android Application to create a gallery control using android studio to display images or photos is developed and executed successfully.

