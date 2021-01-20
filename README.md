# Document on notion

[xml, `merge` tag with constraintlayout, create your own template & landscape layout](https://www.notion.so/xml-merge-tag-with-constraintlayout-create-your-own-template-landscape-layout-624b6722d85544f78114e891549832a2)


### header_template.xml

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/450e445b-c6c4-46ba-a63f-d895e178ce5b/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/450e445b-c6c4-46ba-a63f-d895e178ce5b/Untitled.png)

```xml
<?xml version="1.0" encoding="utf-8"?>
<merge xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:parentTag="androidx.constraintlayout.widget.ConstraintLayout">

    <androidx.constraintlayout.widget.Placeholder
        android:id="@+id/placeholder_image"
        android:layout_width="0dp"
        android:layout_height="0dp"
        app:layout_constraintVertical_bias="0.0"
        app:layout_constraintHorizontal_bias="1.0"
        app:layout_constraintDimensionRatio="16:9"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:content="@+id/image"/>

    <androidx.constraintlayout.widget.Placeholder
        android:id="@+id/placeholder_button"
        android:layout_width="50dp"
        android:layout_height="50dp"
        android:layout_marginEnd="64dp"
        android:layout_marginBottom="24dp"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintBottom_toBottomOf="@+id/placeholder_image"
        app:layout_constraintTop_toBottomOf="@+id/placeholder_image"
        android:layout_marginRight="64dp"
        app:content="@+id/button"/>

</merge>
```

### Layout Variation for landscape mode

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ff9d0e48-3f85-4630-bc23-cb73a5bd377d/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ff9d0e48-3f85-4630-bc23-cb73a5bd377d/Untitled.png)

- Landscape layout

```xml
<?xml version="1.0" encoding="utf-8"?>
<merge xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:parentTag="androidx.constraintlayout.widget.ConstraintLayout">

    <androidx.constraintlayout.widget.Placeholder
        android:id="@+id/placeholder_image"
        android:layout_width="0dp"
        android:layout_height="0dp"
        app:content="@+id/image"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.0"
        app:layout_constraintWidth_percent="0.5" />

    <androidx.constraintlayout.widget.Placeholder
        android:id="@+id/placeholder_button"
        android:layout_width="50dp"
        android:layout_height="50dp"
        android:layout_marginEnd="64dp"
        android:layout_marginRight="64dp"
        android:layout_marginBottom="24dp"
        app:content="@+id/button"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent" />

</merge>
```

### Usage

- include

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".UseTemplateLayoutActivity">

    <ImageView
        android:id="@+id/image"
        android:src="@drawable/ic_launcher_foreground"
        android:scaleType="centerCrop"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"/>
    
    <com.google.android.material.floatingactionbutton.FloatingActionButton
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:src="@android:drawable/ic_dialog_email"/>

    <include layout="@layout/header_template"/>

</androidx.constraintlayout.widget.ConstraintLayout>
```