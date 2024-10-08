### 1. 布局
布局主要包括垂直、水平、网格、流动；
在网格布局中，可以进行如下设置达到特定效果：
 - 使用`android:layout_columnSpan="2"`可以使从当前元素开始往后两个格子合并展示，达到类似于excel中的单元格合并的效果。
 - 使用`android:layout_columnWeight="1"`可以设置当前单元格在本行中所占据的权重，在展示时计算所有设置了权重的元素综合并取百分比比例。
 - 使用`android:layout_gravity="fill"`
```xml
<GridLayout
    android:id="@+id/gridLayout"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:rowCount="2"
    android:columnCount="2"
    android:layout_margin="16dp"
    android:orientation="horizontal">

    <!-- 第一行的视图，占据两列 -->
    <TextView
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_columnSpan="2"
        android:layout_gravity="fill"
        android:text="This is the merged first row"
        android:gravity="center"
        android:background="#FFDDDD"
        android:padding="16dp" />

    <!-- 第二行的第一个单元格 -->
    <Button
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:text="Button 1"
        android:layout_gravity="fill"
        android:layout_columnWeight="1" />

    <!-- 第二行的第二个单元格 -->
    <Button
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:text="Button 2"
        android:layout_gravity="fill"
        android:layout_columnWeight="1" />
</GridLayout>

```
在水平布局中需要指定水平还是垂直对齐    `android:orientation="vertical"` or     `android:horizontal="horizational"`