# Dynamic-Tabs-Android
#
## 1.In your activity_main.xml make TabLayout
    <?xml version="1.0" encoding="utf-8"?>
    <androidx.constraintlayout.widget.ConstraintLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <com.google.android.material.tabs.TabLayout
        android:id="@+id/tabLayout"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:minHeight="?actionBarSize"
        app:tabGravity="fill"
        app:tabMode="fixed"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        android:background="#1db995">
    </com.google.android.material.tabs.TabLayout>

    <androidx.viewpager.widget.ViewPager
        android:id="@+id/viewPager"
        android:layout_width="match_parent"
        android:layout_height="match_parent">
    </androidx.viewpager.widget.ViewPager>
    
    </androidx.constraintlayout.widget.ConstraintLayout>

#
#### 2. In your MainActivity find views for TabLayout and do some arrangements for making dynamic tabs

            for (int k = 0; k <10; k++) {
            tab.addTab(tab.newTab().setText("" + k));
        }

        adapter = new TabAdapter
                (getSupportFragmentManager(), tab.getTabCount());
        viewPager.setAdapter(adapter);
        viewPager.setOffscreenPageLimit(1);
        viewPager.addOnPageChangeListener(new TabLayout.TabLayoutOnPageChangeListener(tab));
#
##### Note : from the above code, this for() loop is the key to success where we are making dynamic fragments and adding them to tab layout you can make as many dynamic fragments as you want.

         for (int k = 0; k <10; k++) {
                    tab.addTab(tab.newTab().setText("" + k));
                }




#### Output:
<img src="https://github.com/Alfaizkhan/Dynamic-Tabs-Android/blob/master/images/frg1.png" width="360" height="640"> | <img src="https://github.com/Alfaizkhan/Dynamic-Tabs-Android/blob/master/images/frg2.png" width="360" height="640">
