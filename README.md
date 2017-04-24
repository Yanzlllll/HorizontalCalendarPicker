# HorizontalCalendarPicker
Support the horizontal slide and picker
#### 预览图：
![预览图](http://i2.muimg.com/567571/61ef000f3b1c8313.gif)
#### 使用方法
**xml：**

```
<com.example.cusview_horizontal_slide.HorizontalPicker
            android:id="@+id/hpText"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_gravity="center"
            app:textSize="18sp"
            app:itemMargin="5dp"
            app:itemHeight="40dp"
            app:itemWidth="40dp"
            app:backgroundSelector="@drawable/selector_background_example"
            app:textColorSelector="@color/selector_text_view"/>
```
**java:**

```
HorizontalPicker hpText = (HorizontalPicker) findViewById(R.id.hpText);
HorizontalPicker.OnSelectionChangeListener listener = new HorizontalPicker.OnSelectionChangeListener() {
            @Override
            public void onItemSelect(HorizontalPicker picker, int index) {
                HorizontalPicker.PickerItem selected = picker.getSelectedItem();
                textView.setText((selected.hasDrawable() ? "Item at " + (picker.getSelectedIndex() + 1) + " is selected" : selected.getText() + " is selected"));
            }

        };

        List<HorizontalPicker.PickerItem> textItems = new ArrayList<>();
        for(int i=1;i<=17;i++){
            textItems.add(new HorizontalPicker.TextItem("S"+i));
        }
        hpText.setItems(textItems,1);
        hpText.setChangeListener(listener);
```
*支持图片：*

```
  List<HorizontalPicker.PickerItem> imageItems = new ArrayList<>();
        imageItems.add(new HorizontalPicker.DrawableItem(R.drawable.icon_led));
        imageItems.add(new HorizontalPicker.DrawableItem(R.drawable.icon_ir));

        hpImage.setItems(imageItems);
        hpImage.setSelectedIndex(0);
        hpImage.setChangeListener(listener);
```
**支持自定义属性设置：**

```
<declare-styleable name="HorizontalPicker">
        //文本大小
        <attr name="textSize" format="dimension"/>
        //背景颜色
        <attr name="backgroundSelector" format="reference"/>
        //选中的文字颜色
        <attr name="textColorSelector" format="reference"/>
        //子条目高度
        <attr name="itemHeight" format="dimension"/>
        //子条目宽度
        <attr name="itemWidth" format="dimension"/>
        //子条目分隔宽度
        <attr name="itemMargin" format="dimension"/>
    </declare-styleable>
```

