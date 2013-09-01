ShelfView
=========

Android application that allows a very easy-compatible Shelf View for smartphone and tablet.

Image Result
-----

**1) Smartphone view :**

![Capture Project Smartphone](http://i42.tinypic.com/6i4d9g.png)

**2) Tablette view :**

![Capture Project Tablette](http://i40.tinypic.com/6gxvl3.png)


Create
-----

###XML :
```xml
<?xml version="1.0" encoding="utf-8"?>
<ScrollView xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/sclView"
    android:layout_width="fill_parent"
    android:layout_height="wrap_content" >

    <TableLayout
        android:id="@+id/tblLayout"
        android:layout_width="fill_parent"
        android:layout_height="fill_parent"
        android:padding="0dp"
        android:scrollbars="none"
        tools:ignore="ScrollViewSize" >
    </TableLayout>

</ScrollView>
```

###JAVA :
```java
int numRow = 8;
int numCol = 15;

TableLayout tblLayout = (TableLayout) findViewById(R.id.tblLayout);

for(int i = 0; i < numRow; i++) {
	HorizontalScrollView HSV = new HorizontalScrollView(this);
	HSV.setLayoutParams(new LayoutParams(LayoutParams.MATCH_PARENT,
			LayoutParams.MATCH_PARENT));

	TableRow tblRow = new TableRow(this);
	tblRow.setLayoutParams(new LayoutParams(LayoutParams.MATCH_PARENT, 
			LayoutParams.WRAP_CONTENT));
	tblRow.setBackgroundResource(R.drawable.bookshelf);

	for(int j = 0; j < numCol; j++) {
		ImageView imageView = new ImageView(this);
		imageView.setImageResource(R.drawable.book);

		tblRow.addView(imageView,j);
	}

	HSV.addView(tblRow);
	tblLayout.addView(HSV, i);
}
```
