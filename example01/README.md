##### Example 01 UI

> dp，像素密度，设备屏幕尺寸无关的，描述控件间距离等    (记：device)  
> sp，描述**字体**大小    (记：script)  
> px，像素，相对的绝对单元，与CSS相似等，图片等  (记：Pixel)



RelativeLayout: 相对布局
LinearLayout: 线性布局
ConstraintLayout: 约束布局

###### Relative Layout & Linear Layout


Linear与Relative布局的区别: 如果层级多的使用RelativeLayout
![](https://raw.githubusercontent.com/zhanyeye/Figure-bed/img/img/20190607101909.png)

LinearLayout 主要属性

- android:orientation，LinearLayout方向
  `vertical` ,  `horizontal`
- android:layout_gravity，**相对于**该控件的**父组件**，控件本身的显示位置。仅在LinearLayout内有效，受android:orientation属性影响
  `bottom` , `center`
- android:gravity，**控件内**内容的显示位置
- android:layout_weight，比重，android:orientation **相应方向的值需设为0dp**
  `android:layout_width="0dp"   android:layout_weight="1"`



###### ConstraintLayout

它的出现主要是为了解决布局嵌套过多的问题 [link](https://www.jianshu.com/p/17ec9bd6ca8a)

添加依赖 : 在app/build.gradle文件中添加ConstraintLayout的依赖 

```
implementation 'com.android.support.constraint:constraint-layout:1.1.3'
```

与Relative的区别：**仅对相同位置/方向进行相对的约束**  
![](https://raw.githubusercontent.com/zhanyeye/Figure-bed/img/img/20190607091106.png)


![](https://raw.githubusercontent.com/zhanyeye/Figure-bed/img/img/20190607092539.png)

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout  ...>
    <TextView
        android:id="@+id/textView"
        android:text="TextView_A"
        ...
        tools:layout_editor_absoluteX="189dp"
        tools:layout_editor_absoluteY="253dp" />

    <TextView
        android:id="@+id/textView2"
        android:text="TextView_B"
        ...
        android:layout_marginBottom="56dp"
        app:layout_constraintBottom_toTopOf="@+id/textView"
        tools:layout_editor_absoluteX="280dp" />

    <TextView
        android:id="@+id/textView3"
        android:text="TextView_C"
		...
        android:layout_marginBottom="72dp"
        app:layout_constraintBottom_toBottomOf="@+id/textView"
        tools:layout_editor_absoluteX="101dp" />
</androidx.constraintlayout.widget.ConstraintLayout>
```

