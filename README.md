# <center>Flutter 组件大全</center>
#### <center>Powder by [Shikong](http://skcks.cn)</center>
###### <center>2019.09.28</center>

# 常用组件

## Container （容器组件）

|      **属性名**      |      **类型**      |                                         **说明**                                         |
| :------------------: | :----------------: | :--------------------------------------------------------------------------------------: |
|         key          |        Key         |                            Container 唯一标识符，用于查找更新                            |
|      alignment       | AlignmentGeometry  |  **控制 child 的对齐方式**，在Container 或者 Container 父节点尺寸大于child尺寸时才有效   |
|       padding        | EdgeInsetsGeometry |          Decoration 内部的空白区域，如果有 child 的话，child 位于 padding 内部           |
|        color         |       Color        | 用来设置 Container 背景颜色，如果设置了 foregroundDecoration 的话，可能会覆盖 color 效果 |
| foregroundDecoration |     Decoration     |                                 绘制在 child 前面的装饰                                  |
|        width         |       double       |                   Container 的宽度，设置为 double.infinity 可撑满布局                    |
|        height        |       double       |                   Container 的高度，设置为 double.infinity 可撑满布局                    |
|     constraints      |   BoxConstraints   |                              添加到 child 上的额外约束条件                               |
|        margin        | EdgeInsetsGeometry |                        围绕在 Decoration 和 child 之外的空白区域                         |
|      transform       |      Matrix4       |                                设置 Container 的变换矩阵                                 |
|        child         |       Widget       |                                Container 中的内容 Widget                                 |

## Image （图片组件）

- **Image：从 ImageProvider 获取图像**
- **Image.asset：加载资源图片**
- **Image.file：加载本地图片**
- **Image.network：加载网络图片**
- **Image.memory：加载 Uint8List 资源图片**
  
|       属性名       |     类型     |                                                            说明                                                             |
| :----------------: | :----------: | :-------------------------------------------------------------------------------------------------------------------------: |
|       image        | ImageProvide |                                           抽象类，需要自己实现获取图片数据的操作                                            |
|   width / height   |    double    |                                               Image 显示区域的宽度和高度设置                                                |
|        fit         |    Boxfit    |                                               图片填充模式，详细参数见 BoxFit                                               |
|       color        |    Color     |                                                          图片颜色                                                           |
|   colorBlendMode   |  BlendMode   |                                            图层混合模式，可以对颜色进行混合处理                                             |
|     alignment      |  Alignment   |                                                     控制图片的摆放位置                                                      |
|       repeat       | ImageRepeat  |                 设置图片的重复模式。<br> noRepeat：不重复<br> repeatX: x轴方向重复<br> repeatY: y轴方向重复                 |
|    centerSlice     |     Rect     |                                 当图片需要被拉伸显示时， centerSlice 定义的矩形区域会被拉伸                                 |
| matchTextDirection |     bool     | matchTextDirection 与 Directionality 配合使用<br>TextDirection.ltr：从左向右展示图片<br>TextDirection.rtl：从右向左展示图片 |
|  gaplessPlayback   |     bool     |              当 ImageProvider 发生变化后，重新加载图片的过程中是否保留原图片。<br> true：保留<br>false：不保留              |

## Boxfit （Box缩放）

|       取值       |                                     描述                                     |
| :--------------: | :--------------------------------------------------------------------------: |
|   BoxFit.fill    |                       全图显示，内容可能拉伸，填满容器                       |
|  BoxFit.contain  |                    全图显示，内容按原比例显示，不填满容器                    |
|   BoxFit.cover   |                         内容可能拉伸、裁剪，填满容器                         |
| BoxFit.fitWidth  |                       内容可能拉伸、裁剪、填满容器宽度                       |
| BoxFit.fitHeight |                       内容可能拉伸、裁剪、填满容器高度                       |
|   Boxfit.none    |                                   原始大小                                   |
| BoxFit.scaleDown | 效果与 BoxFit.contain 类似，但不允许显示大小超过原内容大小，只能缩小不能放大 |

## Text （文本组件）

|     属性名      |     类型      |      默认值       |                                    说明                                    |
| :-------------: | :-----------: | :---------------: | :------------------------------------------------------------------------: |
|      data       |    String     |                   |                             数据为要显示的文本                             |
|    maxLines     |      int      |         0         |                              文本最大显示行数                              |
|      style      |   TextStyle   |       null        |                   文本样式，可定义字体大小、颜色、粗细等                   |
|    textAlign    |   TextAlign   | TextAlign.center  |  文本对齐方式<br>取值有：center、left、right、start、end、justify、values  |
|  textDirection  | TextDirection | TextDirection.ltr | 文本显示方向<br>TextDirection.ltr：从左到右<br>TextDirection.rtl：从右到左 |
| textScaleFactor |    double     |        1.0        |                                字体缩放系数                                |
|    textSpan     |   TextSpan    |       null        |                       文本块，可以包含文本内容及样式                       |

## Icon （图标组件）
- **IconButton：可交互的 Icon**
- **Icons：框架自带的 Icon 集合**
- **IconTheme：Icon 主题**
- **ImageIcon：通过 AssetImages 或者其他图片显示 Icon**

|    属性名     |     类型      |      默认值       |                                            说明                                             |
| :-----------: | :-----------: | :---------------: | :-----------------------------------------------------------------------------------------: |
|     color     |     Color     |       null        |                                         图标的颜色                                          |
|     icon      |   IconData    |       null        |                                       展示的具体图标                                        |
|     style     |   TextStyle   |       null        |                         文本样式，可定义文本字体大小、颜色、粗细等                          |
|     size      |    double     |       24.0        |                                         图标的大小                                          |
| textDirection | TextDirection | TextDirection.ltr | Icon 组件里文本内容的显示方向<br>TextDirection.ltr：从左到右<br>TextDirection.rtl：从右到左 |

## IconButton （图标按钮组件）

|    属性名     |       类型        |         默认值          |               说明               |
| :-----------: | :---------------: | :---------------------: | :------------------------------: |
|   alignment   | AlignmentGeometry |    Alignment.center     | 定义 IconButton 的 Icon 对齐方式 |
|     icon      |      Widget       |          null           |          展示的具体图标          |
|     color     |       Color       |          null           |          图标组件的颜色          |
| disabledColor |       Color       | ThemeData.disabledColor |    图标按钮被禁用时的按钮颜色    |
|   iconSize    |      double       |          24.0           |            图标的大小            |
|   onPressed   |   VoidCallback    |          null           |      当按钮按下时触发的事件      |
|    tooltip    |      String       |                         |    当按钮按下时组件的提示语句    |

## RaisedButton（凸起按钮组件）

|    属性名     |     类型     |         默认值          |               说明               |
| :-----------: | :----------: | :---------------------: | :------------------------------: |
|     color     |    Color     |          null           |            组件的颜色            |
| disabledColor |    Color     | ThemeData.disabledColor |         组件禁用时的颜色         |
|   onPressed   | VoidCallback |          null           |      当按钮按下时触发的事件      |
|     child     |    Widget    |                         | 按钮内的组件，通常为Text文本组件 |
|    enabled    |     bool     |          true           |          是否为禁用状态          |

## ListView （列表组件）
|     属性名      |        类型        |    默认值     |                                  说明                                  |
| :-------------: | :----------------: | :-----------: | :--------------------------------------------------------------------: |
| scrollDirection |        Axis        | Axis.vertical | 列表的排列方向<br>Axis.vertical：垂直方向<br>Axis.horizontal：水平方向 |
|     padding     | EdgeInsetsGeometry |               |                           列表内部的空白区域                           |
|     reverse     |        bool        |     false     |                              组件排列反向                              |
|    children     |   List\<Widget>    |               |                                列表元素                                |

## Gridview （网格列表组件）
- **GridView.count：通过单行展示个数创建 GridView**
- **GridView.extebt：通过最大宽度创建 GridView**

|     属性名      |        类型        |    默认值     |                               说明                               |
| :-------------: | :----------------: | :-----------: | :--------------------------------------------------------------: |
| scrollDirection |        Axis        | Axis.vertical | 滚动方向<br>Axis.vertical：垂直方向<br>Axis.horizontal：水平方向 |
|     reverse     |        bool        |     false     |                           是否反向滚动                           |
|   controller    |  ScrollController  |               |                      控制child滚动时的位置                       |
|     primary     |        bool        |               |   是否是与父节点的 PrimaryScrollController 所关联的主滚动视图    |
|     physics     |   ScrollPhysics    |               |                         滚动视图响应方式                         |
|   shrinkWrap    |        bool        |     false     |              滚动方向的滚动是否由正在查看的内容决定              |
|     padding     | EdgeInsetsGeometry |               |                          四周的空白区域                          |
|  gridDelegate   | SliverGridDelegate |               |              控制 GridView 中子节点布局的 Delegate               |
|   cacheExtent   |       double       |               |                             缓存区域                             |

## Form （表单组件）

#### Form 组件

|    属性名    |     类型     |              说明               |
| :----------: | :----------: | :-----------------------------: |
|     key      |     Key      |  组件在整个 Widget 树中的key值  |
| autovalidate |     bool     |        是否自动提交表单         |
|    child     |    Widget    |   组件 child 只能有一个子组件   |
|  onChanged   | VoidCallback | 当 FormFiled 值改变时的回调函数 |

#### TextFromField 组件

|    属性名    |          类型          |                    说明                    |
| :----------: | :--------------------: | :----------------------------------------: |
| autovaildate |          bool          |                 自动验证值                 |
| initialValue |           T            |               表单字段初始值               |
|   onSaved    |  FormFieldSetter\<T>   | 当 Form 表单调用保存方法 Save 时的回调函数 |
|  validator   | FormFieldValidator\<T> |              Form 表单验证器               |

# Material Design 风格组件
## Material Design 风格组件 列表

|       组件名称       |       中文名称       |                     说明                      |
| :------------------: | :------------------: | :-------------------------------------------: |
|        AppBar        |     应用按钮组件     |                应用的工具按钮                 |
|     AlertDialog      |      对话框组件      |              有操作按钮的对话框               |
| BottomNavigationBar  |    底部导航条组件    |     底部导航条，可以在不同页面间切换视图      |
|         Card         |       卡片组件       |            带有边框阴影的卡片组件             |
|        Drawer        |       抽屉组件       | Drawer 抽屉组件可以实现类似抽屉拉开关闭的效果 |
| FloatingActionButton |     浮动按钮组件     |            应用的主要功能操作按钮             |
|      FlatButton      |     扁平按钮组件     |               扁平化风格的按钮                |
|     MaterialApp      |   Material应用组件   |      Material 代表使用纸墨设计风格的应用      |
|   PopupMenuButton    |     弹出菜单组件     |                 弹出菜单按钮                  |
|       Scaffold       |      脚手架组件      |        实现基本的Material Design 布局         |
|       SnackBar       |     轻量提示组件     |     一个轻量级提示组件，在屏幕的底部显示      |
|     SimpleDialog     |    简单对话框组件    |  简单对话框组件，只起提示作用，没有交互功能   |
|        TabBar        | 水平选项卡及视图组件 |    一个显示水平选项卡的Material Design组件    |
|      TextField       |      文本框组件      |           可接受应用数据文本的组件            |

## MaterialApp （应用组件）

|           属性名           |            类型            |                                                     说明                                                      |
| :------------------------: | :------------------------: | :-----------------------------------------------------------------------------------------------------------: |
|           title            |           String           |                                                应用程序的标题                                                 |
|           theme            |         ThemeData          |                                           定义应用所使用的主题颜色                                            |
|           color            |           Color            |                                                应用的主要颜色                                                 |
|            home            |           Widget           |                                            应用打开时所显示的页面                                             |
|           routes           | Map\<String,WidgetBuilder> |                                            定义应用中页面跳转规则                                             |
|        initialRoute        |           String           |                                                  初始化路由                                                   |
|      onGenerateRoute       |        RouteFactory        | 路由回调函数<br>当通过<br> ```Navigator.of(context).pushNamed```<br>跳转路由,在 routes 找不到时，会调用此方法 |
|      onLocaleChanged       |                            |                                   当系统修改语言的时候，会触发这个回调方法                                    |
|     navigatorObservers     |  List\<NavigatorObserver>  |                                                  导航观察器                                                   |
|   debugShowMaterialGrid    |            bool            |                                           是否显示设计基础布局网格                                            |
|   showPerformanceOverlay   |            bool            |                                               是否显示性能标签                                                |
| debugShowCheckedModeBanner |            bool            |                                           是否显示右上角 debug 标签                                           |

## Scaffold （脚手架组件）

|           属性名           |     类型      |                                                      说明                                                      |
| :------------------------: | :-----------: | :------------------------------------------------------------------------------------------------------------: |
|           appBar           |    AppBar     |                                          显示在页面顶部的一个 AppBar                                           |
|            body            |    Widget     |                                            当前页面所显示的主要内容                                            |
|    floatingActionButton    |    Widget     |                                    在 Material Design 中定义的一个功能按钮                                     |
|  persistentFooterButtons   | List\<Widget> |                                              固定在下方显示的按钮                                              |
|           drawer           |    Widget     |                                                   侧边栏组件                                                   |
|    bottomNavigationBar     |    Widget     |                                            显示在底部的导航栏按钮栏                                            |
|      backgroundColor       |     Color     |                                                    背景颜色                                                    |
| resizeToAvoidBottomPadding |     bool      | 控制界面内容 body 是否重新布局来避免底部被覆盖， 比如当键盘显示时，重新布局避免被键盘盖住 内容。 默认值为 true |

## AppBar （应用按钮组件）

|     属性名      |        类型         |              默认值              |                                                                                    说明                                                                                     |
| :-------------: | :-----------------: | :------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
|     leading     |       Widget        |               null               |                                              在标题前面显示的一个组件，在首页通常显示应用的 logo; 在其他界面通常显示为返回按钮                                              |
|      title      |       Widget        |               null               |                                                             Toolbar 中主要 内容 ，通常显示为当前界面的标题文字                                                              |
|     actions     |    List\<Widget>    |               null               | 一个 Widget列表，代表 Toolbar中所显示的 菜单，对于常 用的 菜 单，通常使用 IconButton 来表示，对于不常用的菜单通常使用 Popup-MenuButton来显示为三 个点，点击后弹出 二级 菜单 |
|     bottom      | PreferredSizeWidget |               null               |                                                         通常是 TabBar。 用来在 Toolbar 标题下面显示 一个 Tab 导航栏                                                         |
|    elevation    |       double        |                4                 |     纸墨设计中组件的 z 坐标顺序，对于可滚动的 SliverAppBar，当 SliverAppBar和内容同级的 时候，该值为 0，当内容滚动 SliverAppBar变为 Toolbar的时候，修改 elevation的值      |
|  flexibleSpace  |       Widget        |               null               |                           一个显示在 AppBar下 方 的 组 件， 高度和 AppBar 高度一样 ， 可以实现一些特殊的效果， 该属性通常在 SliverAppBar 中使用                            |
|   brightness    |     Brightness      | ThemeData.primaryColorBrightness |                                                                    AppBar 的亮度 ，有白色和黑色两种主题                                                                     |
| backgroundColor |        Color        |      ThemeData.primaryColor      |                                                                                   背景色                                                                                    |
|    iconTheme    |    IconThemeData    |    ThemeData.primaryIconTheme    |                                                AppBar 上图标的颜色 、 透明度和尺寸信息 。默认值为 ThemeData.primaryIconTheme                                                |
|    textTheme    |      TextTheme      |    ThemeData.primaryTextTheme    |                                                                             AppBar上的文字样式                                                                              |
|   centerTitle   |        bool         |               true               |                                                       标题是否居 中显示，默认值根据不 同的操作 系统 ， 显示方式不一样                                                       |

## BottomNavigationBar （底部导航条组件）

|    属性名    |              类型              |                         说明                          |
| :----------: | :----------------------------: | :---------------------------------------------------: |
| currentIndex |              int               |              当前索引，用来切换按钮控制               |
|  fixedColor  |             Color              |                    选中按钮的颜色                     |
|   iconSize   |             double             |                     按钮图标大小                      |
|    items     | List\<BottomNavigationBarItem> | 底部导航按钮集<br>每一项为一个BottomNavigationBarItem |
|    onTap     |       ValueChanged\<int>       |           按下其中某个按钮时触发的回调事件            |

## TabBar （水平选项卡及视图组件）

#### TabBar

|    属性名    |     类型      |       说明       |
| :----------: | :-----------: | :--------------: |
| isScrollable |     bool      | 是否可以水平移动 |
|     tabs     | List\<Widget> |   Tab 选项列表   |

#### Tab

| 属性名 |  类型  |   说明   |
| :----: | :----: | :------: |
|  icon  | Widget | Tab 图标 |
|  text  | String | Tab 文本 |

#### TabBarView

|   属性名   |     类型      |                        说明                         |
| :--------: | :-----------: | :-------------------------------------------------: |
| controller | TabController |                  指定视图的控制器                   |
|  children  | List\<Widget> | 视图组件的 child 为一个列表，一个选项卡对应一个容器 |

## Drawer （抽屉组件）

#### Drawer

|  属性名   |  类型  | 默认值 |                 说明                  |
| :-------: | :----: | :----: | :-----------------------------------: |
|   child   | Widget |        | Drawer的 child 可以放置任意可显示对象 |
| elevation | double |  16.0  |           组件的 z 坐标顺序           |

#### DrawerHeader

|   属性名   |        类型        |                                                说明                                                 |
| :--------: | :----------------: | :-------------------------------------------------------------------------------------------------: |
| decoration |     Decoration     |                      header 区域 的 decoration，通常用来设置背景颜色或背景图片                      |
|   curve    |       Curve        | 如果 decoration 发生了变化，则会使用 curve 设置的变化曲线和 duration 设置的动画时间来做一个切换动画 |
|   child    |       Widget       |                                      Header 内所显示的内容控件                                      |
|  padding   | EdgeInsetsGeometry |                                     Header 内控件的 padding 值                                      |
|   margin   | EdgeInsetsGeometry |                                          Header 四周的间隙                                          |

#### UserAccountsDrawerHeader

|        属性名         |        类型        |                           说明                            |
| :-------------------: | :----------------: | :-------------------------------------------------------: |
|        margin         | EdgeInsetsGeometry |                     Header 四周的间隙                     |
|      decoration       |     Decoration     | header 区域 的 decoration，通常用来设置背景颜色或背景图片 |
| currentAccountPicture |       Widget       |                   用来设置当前用户头像                    |
| otherAccountsPictures |   List\<Widget>    |              用来设置当前用户其他账号的头像               |
|      accountName      |       Widget       |                      当前用户的名字                       |
|     accountEmail      |       Widget       |                     当前用户的 Email                      |
|   onDetailsPressed    |    VoidCallback    |   当 accountName 或 accountEmail 被点击时触发的回调函数   |

## FloatActionButton （悬停按钮组件）

|       属性名       |     类型     |    默认值     |                            说明                            |
| :----------------: | :----------: | :-----------: | :--------------------------------------------------------: |
|       child        |    Widget    |               |             child 一般为 Icon，不推荐使用文字              |
|      tooltip       |    String    |               |                        按钮提示文本                        |
|  foregroundColor   |    Color     |               |                           前景色                           |
|  backgroundColor   |    Color     |               |                           背景色                           |
|     elevation      |    double    |      6.0      |                      未点击时阴影大小                      |
| hignlightElevation |    double    |     12.0      |                       点击时阴影大小                       |
|     onPressed      | VoidCallback |               |                      点击时的回调事件                      |
|       shape        | ShapeBorder  | CirecleBorder | 定义按钮的 shape，设置 shape 时，默认的 elevation 将会失效 |

## PopupMenuButton （弹出菜单组件）

|   属性名    |           类型            |                  说明                   |
| :---------: | :-----------------------: | :-------------------------------------: |
|    child    |          Widget           | 如果提供 child 则使用此组件作为弹出菜单 |
|    icon     |           Icon            |     如果提供，则弹出菜单使用此图标      |
| itemBuilder | PopupMenuItemBuilder\<T>  |      菜单项构造器，可以为任意类型       |
| onSelected  | PopupMenyItemSelected\<T> |      当某项菜单被选中时的回调方法       |

## SimpleDialog （简单对话框组件）

|     属性名     |        类型        |        说明        |
| :------------: | :----------------: | :----------------: |
|    children    |   List\<Widget>    |     对话框子项     |
|     title      |       Widget       | 通常是一个文本组件 |
| contentPadding | EdgeInsetsGeometry |  内容部分间距大小  |
|  titlePadding  | EdgeInsetsGeometry |  标题部分间距大小  |

## AlertDialog （提示对话框组件）

|     属性名     |        类型        |               说明               |
| :------------: | :----------------: | :------------------------------: |
|    actions     |   List\<Widget>    |        对话框底部操作按钮        |
|     title      |       Widget       |    对话框标题，通常为文本组件    |
| contentPadding | EdgeInsetsGeometry |         内容部分间距大小         |
|    content     |       Widget       | 内容部分，通常为对话框的提示内容 |
|  titlePadding  | EdgeInsetsGeometry |         标题部分间距大小         |

## SnackBar （轻量提示组件）

|     属性名      |        类型        |   默认值   |                     说明                     |
| :-------------: | :----------------: | :--------: | :------------------------------------------: |
|     action      |   SnackBarAction   |            | 提示消息里执行的动作，如关闭，撤销等点击操作 |
|    animation    | Animation\<double> |            |              给组件添加动画效果              |
|     content     |       Widget       |            |         提示消息内容，通常为文本组件         |
|    duration     |      Duration      | seconds: 4 |                 执行动画时长                 |
| backgroundColor |       Color        |            |               消息面板的背景色               |

## TextField （文本框组件）

|     属性名      |           类型            |            说明            |
| :-------------: | :-----------------------: | :------------------------: |
|    maxLength    |            int            |          最大长度          |
|    maxLines     |            int            |          最大行数          |
|   autocorrect   |           bool            |        是否自动更正        |
|    autofocus    |           bool            |        是否自动对焦        |
|   obscureText   |           bool            | 是否为密码类型（隐藏文本） |
|    textAlign    |         TextAlign         |        文本对齐方式        |
|      style      |         TextStyle         |       输入文本的样式       |
| inputFormatters | List\<TextInputFormatter> |       允许的输入方式       |
|    onChanged    |   ValueChanged\<String>   |       内容改变时回调       |
|   onSubmited    |   ValueChanged\<String>   |       内容提交时回调       |
|     enabled     |           bool            |          是否禁用          |

## Card （卡片组件）

| 属性名 |        类型        |         默认值         |                            说明                            |
| :----: | :----------------: | :--------------------: | :--------------------------------------------------------: |
| child  |       Widget       |                        |              组件的子元素，任意 Widget 都可以              |
| margin | EdgeInsetsGeometry |                        |         围绕在 decoration 和 child 之外的空白区域          |
| shape  |    ShapeBorder     | RoundedRectangleBorder | Card 的阴影效果，默认的阴影效果为圆角的长方形边。弧度为4.0 |

# Cupertino 风格组件 （IOS 风格组件）

## CupertinoActivityIndicator 组件

|  属性名   |  类型  | 默认值 |                   说明                   |
| :-------: | :----: | :----: | :--------------------------------------: |
|  radius   | double |  10.0  |     加载图形的半径值，值越大图形越大     |
| animating |  bool  |  true  | 是否播放加载动画，通常用来做动画控制效果 |

## CupertinoAlertDialog 对话框组件

| 属性名  |     类型      |            说明            |
| :-----: | :-----------: | :------------------------: |
| actions | List\<Widget> |       对话框底部按钮       |
|  title  |    Widget     | 对话框标题，通常为文本组件 |
| content |    Widget     |      对话框的内容部分      |

## CupertinoButton 按钮组件

|    属性名     |     类型     |         默认值          |                  说明                  |
| :-----------: | :----------: | :---------------------: | :------------------------------------: |
|     color     |    Color     |                         |               组件的颜色               |
| disabledColor |    Color     | ThemeData.disabledColor |            组件禁用时的颜色            |
|   onPressed   | VoidCallback |          null           |        按钮按下时触发的回调事件        |
|     child     |    Widget    |                         | 通常为Text文本组件，用来显示按钮的文本 |
|    enable     |     bool     |          true           |             按钮是否被禁用             |

## Cupertino 导航组件集

#### CupertinoTabScaffold

|   属性名   |         类型         |       说明       |
| :--------: | :------------------: | :--------------: |
|   tabBar   |   CupertinoTabBar    |    选项卡按钮    |
| tabBuilder | IndexedWidgetBuilder | 选项卡视图构造器 |

#### CupertinoTabBar

|     属性名      |              类型              |          说明          |
| :-------------: | :----------------------------: | :--------------------: |
|      items      | List\<BottomNavigationBarItem> |   选项卡按钮数据组合   |
| backgroundColor |             Color              |    选项卡按钮背景色    |
|  activerColor   |             Color              | 选中的选项卡按钮前景色 |
|    inconSize    |             double             |     选项卡图标大小     |

#### CupertinoTabView

| 属性名  |            类型            |       说明       |
| :-----: | :------------------------: | :--------------: |
| builder |       WidgetBuilder        | 选项卡视图构造器 |
| routes  | Map\<String,WidgetBuilder> |  选项卡视图路由  |

#### CupertinoPageScaffold

|     属性名      |              类型              |                说明                |
| :-------------: | :----------------------------: | :--------------------------------: |
| backgroundColor |             Color              |             页面背景色             |
|  navigationBar  | ObstructingPreferredSizeWidget | 顶部导航按钮，包含左中右三个子组件 |
|      child      |             Widget             |           页面的主要内容           |

#### CupertinoNavigatinBar

|  属性名  |  类型  |              说明              |
| :------: | :----: | :----------------------------: |
|  middle  | Widget | 导航栏中间组件，通常为页面标题 |
| trailing | Widget | 导航栏右侧组件，通常为菜单按钮 |
| leading  | Widger | 导航栏左侧组价，通常为返回按钮 |

# 页面布局

## 页面布局及装饰组件列表

|       组件名称       |     中文名称      |                                   说明                                    |
| :------------------: | :---------------: | :-----------------------------------------------------------------------: |
|        Align         |     对齐布局      |                           指定 child 的对齐方式                           |
|     AspectRatio      |    调整宽高比     |                        根据设置的宽高比调整 child                         |
|       Baseline       |    基准线布局     |                     所有 child 底部所在的同一条水平线                     |
|        Center        |     居中布局      |                    child 处于水平和垂直方向的中间位置                     |
|        Column        |     垂直布局      |                       对 child 所在垂直方向进行排列                       |
|    ConstrainedBox    |     限定宽高      |                            限定 child 的最大值                            |
|      Container       |     容器布局      |                容器布局是一个组合的 Widget，包含定位和尺寸                |
|      FittedBox       |     缩放布局      |                             缩放以及位置调整                              |
| FractionallySizedBox |    百分比布局     |                   根据现有控件按照百分比调整 child 尺寸                   |
|       GridView       |     网格布局      |                          对多行多列同时进行操作                           |
|     IndexedStack     |    栈索引布局     | IndexedStack 继承至 Stack，显示第 index 个 child，其他 child 都是不可见的 |
|      LimitedBox      |   限定宽高布局    |                            对最大宽高进行限制                             |
|       ListView       |     列表布局      |                            用列表方式进行布局                             |
|       Offstage       |     开关布局      |                             控制是否显示组件                              |
|     OverflowBox      |  溢出父容器显示   |                      允许 child 超出父容器的范围显示                      |
|       Padding        |     填充布局      |                       处理容器与其 child 之间的间距                       |
|         Row          |     水平布局      |                        对 child 在水平方向进行排列                        |
|       SizedBox       |   设置具体尺寸    |                  用一个特定大小的盒子来限定 child 的宽高                  |
|   Stack/Alignment    | Alignment 栈布局  |           根据 Alignment 组件的属性将 child 定位在 Stack组件上            |
|   Stack/Positioned   | Positioned 栈布局 |          根据 Positioned 组件的属性将 child 定位在 Stack 组件上           |
|        Table         |     表格布局      |                         使用表格的行和列进行布局                          |
|      Transform       |     矩阵转换      |               做矩阵变换，对 child 做平移、旋转、缩放等操作               |
|         Wrap         |  按宽高自动换行   |                    按宽度或高度，让 child 自动换行布局                    |

## Padding （填充布局）

| 属性名  |        类型        |             说明             |
| :-----: | :----------------: | :--------------------------: |
| padding | EdgeInsetsGeometry | 填充值可以使用EdgeInsets方法 |

## Align （对齐布局）

|    属性名    |     值      |     说明     |
| :----------: | :---------: | :----------: |
| bottomCenter | （0.5,1.0） |   底部中心   |
|  bottomLeft  | （0.0,1.0） |    左下角    |
| bottomRight  | （1.0,1.0） |    右下角    |
|    center    | （0.5,0.5） | 水平垂直居中 |
|  centerLeft  | （0.0,0.5） |  左边缘中心  |
| centerRight  | （1.0,0.5） |  右边缘中心  |
|  topCenter   | （0.5,0.0） |   顶部中心   |
|   topLeft    | （0.0,0.0） |    左上角    |
|   topRight   | （1.0,0.0） |    右上角    |

## Row （水平布局）

|       属性名       |        类型        |                      说明                      |
| :----------------: | :----------------: | :--------------------------------------------: |
| mainAxisAlignment  | MainAxisAlignment  |                 主轴的排列方式                 |  |
| crossAxisAlignment | CrossAxisAlignment |                 次轴的排列方式                 |  |
|    mainAxisSize    |    MainAxisSize    | 主轴应该占据多少空间<br>max：最大<br>min：最小 |  |
|      children      |   List\<Widget>    |         组件子元素，本质是一个List列表         |  |

## Column （垂直布局）

|       属性名       |        类型        |                      说明                      |
| :----------------: | :----------------: | :--------------------------------------------: |
| mainAxisAlignment  | MainAxisAlignment  |                 主轴的排列方式                 |
| crossAxisAlignment | CrossAxisAlignment |                 次轴的排列方式                 |
|    mainAxisSize    |    MainAxisSize    | 主轴应该占据多少空间<br>max：最大<br>min：最小 |
|      children      |   List\<Widget>    |         组件子元素，本质是一个List列表         |

## Stack/Alignment

|  属性名   |       类型        |      默认值       |                                                                                                                                   说明                                                                                                                                   |
| :-------: | :---------------: | :---------------: | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| aligement | AligementGeometry | Aligement.topLeft | 定位位置有以下几种：<br>bottomCenter：底部中间位置<br>bottomLeft：底部左侧位置<br>bottomRight：底部右侧位置<br>center：正中间位置<br>centerLeft：中间居左位置<br>centerRight：中间居右位置<br>topCenter：顶部居中位置<br>topLeft：顶部居左位置<br>topRight：顶部居右位置 |

## Stack/Positioned

| 属性名 |  类型  |          说明          |
| :----: | :----: | :--------------------: |
|  top   | double | 子元素相对顶部边界距离 |
| bottom | double | 子元素相对底部边界距离 |
|  left  | double | 子元素相对左侧边界距离 |
| right  | double | 子元素相对右侧边界距离 |

## OverflowBox （溢出父容器显示组件）

|  属性名   |       类型        |         说明          |
| :-------: | :---------------: | :-------------------: |
| alignment | AlignmentGeometry |       对齐方式        |
| minWidth  |      double       | 允许 child 的最小宽度 |
| maxWidth  |      double       | 允许 child 的最大宽度 |
| minHeight |      double       | 允许 child 的最小高度 |
| maxHeight |      double       | 允许 child 的最大高度 |

## SizedBox （设置具体尺寸组件）

| 属性名 |       类型        | 说明  |
| :----: | :---------------: | :---: |
| width  | AlignmentGeometry | 宽度  |
| height |      double       | 高度  |

## ConstrainedBox （限定最大最小宽高布局）

|   属性名    |      类型      |                                  说明                                  |
| :---------: | :------------: | :--------------------------------------------------------------------: |
| constraints | BoxConstraints | 添加到 child 上的额外限制条件，类型为 BoxConstraints，限制最大最小宽高 |
|    child    |     Widget     |                          子元素，任意 Widget                           |

## LimitedBox （限定最大宽高布局）

|  属性名   |  类型  |      说明      |
| :-------: | :----: | :------------: |
| maxWidth  | double | 限定的最大宽度 |
| maxHeight | double | 限定的最大高度 |

## AspectRatio （调整宽高比）

|   属性名    |  类型  |        说明         |
| :---------: | :----: | :-----------------: |
| aspectRatio | double |       宽高比        |
|    child    | Widget | 子元素，任意 Widget |

## FractionallySizedBox （百分比布局）

|    属性名    |       类型        |   说明   |
| :----------: | :---------------: | :------: |
|  aligement   | AligementGeometry | 对齐方式 |
| widthFactor  |      double       | 宽度因子 |
| heightFactor |      double       | 高度因子 |

## Table （表格布局）

|          属性名          |            类型            |                                                                    说明                                                                    |
| :----------------------: | :------------------------: | :----------------------------------------------------------------------------------------------------------------------------------------: |
|       columnWidths       | Map\<int,TableColumnWidth> |                                                              设置每一列的宽度                                                              |
|    defaultColumnWidth    |      TableColumnWidth      |                                                        默认的每一列宽度值，默认均分                                                        |
|      textDirection       |       TextDirection        |                                                                  文字方向                                                                  |
|          border          |        TableBorder         |                                                                  表格边框                                                                  |
| defaultVerticalAlignment | TableCellVerticalAligement | 默认垂直方向对齐方式：<br>top：放置在顶部<br>middle：垂直居中<br>bottom：放置在底部<br>baseline：文本 baseline 对齐<br>fill：充满整个 cell |
|       textBaseline       |        TextBaseline        |                                        defaultVerticalAlignment 为 baseline 的时候，会用到这个属性                                         |

## Transform （矩阵转换）

|      属性名       |       类型        |                          说明                          |
| :---------------: | :---------------: | :----------------------------------------------------: |
|     transform     |      Matrix4      |                     一个4x4的矩阵                      |
|      origin       |      Offset       | 旋转点，相对于左上角顶点的偏移，默认旋转点是左上角顶点 |
|     alignment     | AlignmentGeometry |                        对齐方式                        |
| transformHitTests |       bool        |                点击区域是否也做响应改变                |

## Baseline （基准线布局）

|    属性名    |     类型     |                                         说明                                          |
| :----------: | :----------: | :-----------------------------------------------------------------------------------: |
|   baseline   |    double    |                             baseline数值，从顶部开始计算                              |
| baselineType | TextBaseline | baseline类型<br>alphabetic：对齐字符底部的水平线<br>ideographic：对齐任意字符的水平线 |

## Offstage （控制是否显示组件）

|  属性名  | 类型  | 说明  |
| :------: | :---: | :---: |
| offstage | bool  | true  | 默认为 true 时不显示，为 false 时会显示该组件 |

## Wrap （按宽高自动换行布局）

|       属性名       |        类型        |          默认值          |               说明               |
| :----------------: | :----------------: | :----------------------: | :------------------------------: |
|     direction      |        Axis        |     Axis.horizontal      |            主轴的方向            |
|     alignment      |   WrapAlignment    |   WrapAlignment.start    |       主轴方向上的对齐方式       |
|      spacing       |       double       |           0.0            |         主轴方向上的间距         |
|    runAlignment    |   WrapAlignment    |   WrapAlignment.start    | run 的对齐方式，run 为新的行或列 |
|     runSpacing     |       double       |           0.0            |            run 的间距            |
| crossAxisAlignment | WrapCrossAlignment | WrapCrossAlignment.start |       次轴方向上的对齐方式       |
|   textDirection    |   TextDirection    |                          |             文本方向             |
| verticalDirection  | VerticalDirection  |  VerticalDirection.down  |      定义 children 摆放顺序      |

# 手势

## GestureDetecor （手势检测组件）

|         事件名         |                         描述                         |
| :--------------------: | :--------------------------------------------------: |
|       onTapDown        |                点击屏幕立即触发此方法                |
|        onTapUp         |                     手指离开屏幕                     |
|         onTap          |                       点击屏幕                       |
|      onTapCancel       |                   此次点击事件结束                   |
|      onDoubleTap       |               快速连续两次点击同一位置               |
|      onLongPress       |                       长按屏幕                       |
|  onVerticalDragStart   |             与屏幕接触，可能开始垂直移动             |
|  onVerticalDragUpdate  |              与屏幕接触并在垂直方向移动              |
|   onVerticalDaragEnd   | 不再与屏幕接触，并在停止接触屏幕时以特定速度垂直拖动 |
| onHorizontalDragStart  |             与屏幕接触，可能开始水平移动             |
| onHorizontalDragUpdate |              与屏幕接触并在水平方向移动              |
|  onHorizontalDaragEnd  | 不再与屏幕接触，并在停止接触屏幕时以特定速度水平拖动 |

## Dismissible （滑动删除）

|      属性名      |           类型           |             说明             |
| :--------------: | :----------------------: | :--------------------------: |
|   onDismissed    | DismissDirectionCallback | 当包裹的组件消失后回调的函数 |
| movementDuration |         Duration         |      定义组件消息的时长      |
|     onResize     |       VoidCallback       |   组件大小改变时回调的函数   |
|  resizeDuration  |         Duration         |       组件大小改变时长       |
|      child       |          Widget          |       组件包裹的子元素       |

# 组件装饰和视觉效果

## Opactiy

| 属性名  |  类型  |                   说明                   |
| :-----: | :----: | :--------------------------------------: |
| opacity | double | 不透明度，0.0为完全透明，1.0为完全不透明 |
|  child  | Widget |             子元素，任意组件             |

## BoxDecoration （装饰盒子）

|    属性名    |         类型         |       默认值       |                              说明                              |
| :----------: | :------------------: | :----------------: | :------------------------------------------------------------: |
|    shape     |       BoxShape       | BoxShape.rectangle |                            形状取值                            |
|    color     |        Color         |                    |                      用来渲染容器的背景色                      |
|  boxShadow   |   List\<BoxShadow>   |                    |                            阴影效果                            |
|   gradient   |       Gradient       |                    | 渐变色<br>LinearGradient：线性渐变<br>RadialGradient：环形渐变 |
|    image     |   DecorationImage    |                    |                            背景图片                            |
|    border    |      BoxBorder       |                    |                            边框样式                            |
| borderRadius | BorderRadiusGeometry |                    |                           边框的弧度                           |

## RotatedBox （旋转盒子）

|    属性名    | 类型  |          说明           |
| :----------: | :---: | :---------------------: |
| quarterTurns |  int  | 旋转次数，旋转一次为90° |

## Clip （剪裁处理）

- **ClipOval：圆形剪裁**
- **ClipRRect：圆角矩形剪裁**
- **ClipRect：矩形剪裁**
- **ClipPath：路径剪裁**

#### 通用属性

|    属性名    |         类型         |           说明           |
| :----------: | :------------------: | :----------------------: |
|   clipper    | CustomClipper\<Path> | 裁剪路径，如椭圆，矩形等 |
| clipBehavior |         Clip         |         裁剪方式         |

## 自定义画板

- **画直线：drawLine()**
- **画圆：drawCircle()**
- **画椭圆：drawOval()**
- **画矩形：drawRect()**
- **画点：drawPoints()**
- **画圆弧：drawArc()**
  
#### Paint

|    属性名     |     类型      |                         参考值                          |         说明         |
| :-----------: | :-----------: | :-----------------------------------------------------: | :------------------: |
|     color     |    Colors     |                    Colors.blueAccent                    |       画笔颜色       |
|   strokeCap   |   StrokeCap   |                     StrokeCap.round                     |     画笔笔触类型     |
|  isAntiAlias  |     bool      |                          true                           |    是否启用抗锯齿    |
|   blendMode   |   BlendMode   |                  BlendMode.execlusion                   |     颜色混合模式     |
|     style     | PaintingStyle |                   PaintingStyle.fill                    | 绘画样式，默认为填充 |
|  colorFilter  |  ColorFilter  | ColorFilter.mode(Colors.blueAccent,BlendMode.exclusion) |     颜色渲染模式     |
|  maskFilter   |  MaskFilter   |             MaskFilter(BlurStyle.inner,3.0)             |     模糊遮罩效果     |
| filterQuality | FilterQuality |                   FilterQuality.high                    |  颜色渲染模式的质量  |
|  strokeWidth  |    double     |                          16.0                           |      画笔的粗细      |

# 动画

## AnimatedOpacity

|  属性名  |   类型   |         说明          |
| :------: | :------: | :-------------------: |
| opacity  |  double  |      组件透明度       |
|  child   |  Widget  | AnimatedOpacity子元素 |
| duration | Duration |       动画时长        |

## Hero

| 属性名 |  类型  |                        说明                         |
| :----: | :----: | :-------------------------------------------------: |
|  tag   | String | 唯一标记，前后两个路由页中的Hero组件的tag值必须相同 |
| child  | Widget |                  子元素，任意组件                   |
