# FlycoTabLayout

修改自[H07000223/FlycoTabLayout](https://github.com/H07000223/FlycoTabLayout)，修复了一些Bug，增加了一些属性，支持ViewPager2.


一个Android TabLayout库,目前有3个TabLayout

* SlidingTabLayout:参照[PagerSlidingTabStrip](https://github.com/jpardogo/PagerSlidingTabStrip)进行大量修改.
    * 新增部分属性
    * 新增支持多种Indicator显示器
    * 新增支持未读消息显示
    * 新增方法for懒癌患者
    
    ```java
        /** 关联ViewPager,用于不想在ViewPager适配器中设置titles数据的情况 */
        public void setViewPager(ViewPager vp, String[] titles)

        /** 关联ViewPager,用于连适配器都不想自己实例化的情况 */
        public void setViewPager(ViewPager vp, String[] titles, FragmentActivity fa, ArrayList<Fragment> fragments)

        public void setViewPager2(ViewPager2 vp)

        public void setViewPager2(ViewPager2 vp, ArrayList<String> titles)

        /** 支持单独使用 **/
        public void setTabData(String[] titles)
    ```

* CommonTabLayout:不同于SlidingTabLayout对ViewPager依赖,它是一个不依赖ViewPager可以与其他控件自由搭配使用的TabLayout.
    * 支持多种Indicator显示器,以及Indicator动画
    * 支持未读消息显示
    * 支持Icon以及Icon位置
    * 新增方法for懒癌患者
    
    ```java
        /** 关联数据支持同时切换fragments */
        public void setTabData(ArrayList<CustomTabEntity> tabEntitys, FragmentManager fm, int containerViewId, ArrayList<Fragment> fragments)
    ```

* SegmentTabLayout

## Demo
![](https://github.com/H07000223/FlycoTabLayout/blob/master/preview_1.gif)

![](https://github.com/H07000223/FlycoTabLayout/blob/master/preview_2.gif)

![](https://github.com/H07000223/FlycoTabLayout/blob/master/preview_3.gif)


1. Add it in your root build.gradle at the end of repositories:
```groovy
allprojects {
    repositories {
        ...
        maven { url 'https://jitpack.io' }
    }
}
```
2. Add the dependency
[![](https://jitpack.io/v/li-xiaojun/FlycoTabLayout.svg)](https://jitpack.io/#li-xiaojun/FlycoTabLayout)
```
dependencies {
    implementation 'com.github.li-xiaojun:FlycoTabLayout:Tag'
}
```

## Attributes

|name|format|description|
|:---:|:---:|:---:|
| tl_indicator_color | color |设置显示器颜色
| tl_indicator_height | dimension |设置显示器高度
| tl_indicator_width | dimension |设置显示器固定宽度
| tl_indicator_margin_left | dimension |设置显示器margin,当indicator_width大于0,无效
| tl_indicator_margin_top | dimension |设置显示器margin,当indicator_width大于0,无效
| tl_indicator_margin_right | dimension |设置显示器margin,当indicator_width大于0,无效
| tl_indicator_margin_bottom | dimension |设置显示器margin,当indicator_width大于0,无效 
| tl_indicator_corner_radius | dimension |设置显示器圆角弧度
| tl_indicator_gravity | enum |设置显示器上方(TOP)还是下方(BOTTOM),只对常规显示器有用
| tl_indicator_style | enum |设置显示器为常规(NORMAL)或三角形(TRIANGLE)或背景色块(BLOCK)
| tl_underline_color | color |设置下划线颜色
| tl_underline_height | dimension |设置下划线高度
| tl_underline_gravity | enum |设置下划线上方(TOP)还是下方(BOTTOM)
| tl_divider_color | color |设置分割线颜色
| tl_divider_width | dimension |设置分割线宽度
| tl_divider_padding |dimension| 设置分割线的paddingTop和paddingBottom
| tl_tab_padding |dimension| 设置tab的paddingLeft和paddingRight
| tl_tab_space_equal |boolean| 设置tab大小等分
| tl_tab_width |dimension| 设置tab固定大小
| tl_textsize |dimension| 设置字体大小
| tl_textSelectSize |dimension| set text select size
| tl_textFontPath |dimension| set text font typaface
| tl_textSelectColor |color| 设置字体选中颜色
| tl_textUnselectColor |color| 设置字体未选中颜色
| tl_textBold |boolean| 设置字体加粗
| tl_iconWidth |dimension| 设置icon宽度(仅支持CommonTabLayout)
| tl_iconHeight |dimension|设置icon高度(仅支持CommonTabLayout)
| tl_iconVisible |boolean| 设置icon是否可见(仅支持CommonTabLayout)
| tl_iconGravity |enum| 设置icon显示位置,对应Gravity中常量值,左上右下(仅支持CommonTabLayout)
| tl_iconMargin |dimension| 设置icon与文字间距(仅支持CommonTabLayout)
| tl_indicator_anim_enable |boolean| 设置显示器支持动画(only for CommonTabLayout)
| tl_indicator_anim_duration |integer| 设置显示器动画时间(only for CommonTabLayout)
| tl_indicator_bounce_enable |boolean| 设置显示器支持动画回弹效果(only for CommonTabLayout)
| tl_indicator_width_equal_title |boolean| 设置显示器与标题一样长(only for SlidingTabLayout)
