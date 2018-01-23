【1】项目框架

【2】规范

Android编码规范

介绍
1. 为什么需要编码规范？

编码规范对于程序员而言尤为重要，有以下几个原因：
一个软件的生命周期中，80%的花费在于维护
几乎没有任何一个软件，在其整个生命周期中，均由最初的开发人员来维护
编码规范可以改善软件的可读性，可以让程序员尽快而彻底地理解新的代码
书写规范
1. 编码格式

文件编码格式统一用UTF-8
2. Tab缩进

Tab缩进统一为4个空格。将Tab size设置为4，切换到不同tab长度的环境时还能继续保持统一的缩进样式。
3. 花括号

花括号不要单独一行，和它前面的代码同一行。而且，花括号与前面的代码之间用一个空格隔开。
public void method() { // Good 
 
} 
 public void method(){ // Bad
}  
 public void method(){ // Bad
 
}
4. 空格

if、else、for、switch、while等逻辑关键字与后面的语句留一个空格隔开。
// Goodif (booleanVariable) {
    // TODO while booleanVariable is true
} else {
    // TODO else
}
 // Badif(booleanVariable) {
    // TODO while booleanVariable is true
}else {
    // TODO else
}
运算符两边各用一个空格隔开。
int result = a + b; //Good
int result=a+b; //Bad
方法的每个参数之间用一个空格隔开。
public void method(String param1, String param2); // Goodmethod(param1, param2); // Goodmethod(param1,param2); // Bad
类和方法花括号前面用一个空格隔开。
public class LoginActivity {//Good

    private void getData() {//Good
        //do something
    }
    
}
public class LoginActivity{//Bad

    private void getData(){//Bad
        //do something
    }
    
}
5. 空行

将逻辑相关的代码段用空行隔开，以提高可读性。空行也只空一行，不要空多行。在以下情况需用一个空行：
两个方法之间
方法内的两个逻辑段之间
方法内的局部变量和方法的第一条逻辑语句之间
常量和变量之间
6. 表达式换行

当一个表达式无法容纳在一行内时，可换行显示，另起的新行用8个空格缩进。
public void someMethod(longExpression1, longExpression2,
        longExpression3, longExpression4, longExpression5);
7. 声明变量

一行声明一个变量，不要一行声明多个变量，这样有利于写注释。
private String param1; // 参数1private String param2; // 参数2
8. 行宽

行宽设置为100，设置格式化时自动断行到行宽位置。
9. 方法行数

一个方法最多不要超过40行代码，如果方法太长，说明当前方法业务逻辑已经非常复杂，那么就需要进行方法拆分，保证每个方法只作一件事。
10. 使用快捷键进行代码自动格式化

Mac Eclipse：command + shift + f
11. 单位

文字大小的单位统一用sp，控件大小的单位统一用dp
12. 资源文件

字符串统一在string.xml中定义
颜色值统一在color.xml中定义，不要使用系统的颜色
尺寸值统一在dimens.xml中定义
命名规范
1. 包命名

命名规则：一个唯一包名的前缀总是全部小写的ASCII 字母并且是一个顶级域名，通常是com，edu，gov，mil，net，org。包名的后续部分根据不同机构各自内部的命名规范而不尽相同。这类命名规范可能以特定目录名的组成来区分部门 (department) ，项目(project)，机器(machine)，或注册名(login names)。
规约：没有特别要求的情况下，包名命名规则为：
域名.公司名称（缩写）.项目名称（缩写）.模块名称
例如： 公司名称是xizi，项目名称是xzmpo，存放Activity模块的包名为：com.xizi.xzmpo.activity
项目中各模块包名：
com.xizi.xzmpo.activity 放所有Activity
com.xizi.xzmpo.adapter 放所有Adapter
com.xizi.xzmpo.app 放Application
com.xizi.xzmpo.db 放数据库
com.xizi.xzmpo.entity 放实体
com.xizi.xzmpo.fragment 放Fragment
com.xizi.xzmpo.service 放服务
com.xizi.xzmpo.util 放工具
com.xizi.xzmpo.widget 放控件
com.xizi.xzmpo.constant 放常量
2. 类和接口命名

命名规则：类名是一个名词，采用大小写混合的方式，每个单词的首字母大写。尽量使你的类名简洁而富于描述。使用完整单词，避免缩写词(除非该缩写词被更广泛使用，像 URL，HTML)。
规约：类名必须使用驼峰规则，即首字母必须大写，如果为词组，则每个单词的首字母也必须要大写，类名必须使用名词，或名词词组。要求类名简单，不允许出现无意义的单词（如 class XXXActivity）。
如：class AboutActivity 正确
如：class AddBookReadPlanActivity 错误！ 应为 class BookReadPlanAddActivity
(BookReadPlan---名词)+(add---动词)=名词
(add---动词)+ (BookReadPlan---名词)=动词
以下为几种常用类的命名：
activity类，命名以Activity为后缀，如：LoginActivity
fragment类，命名以Fragment为后缀，如：CollectFragment
service类，命名以Service为后缀，如：DownloadService
adapter类，命名以Adapter为后缀，如：CouponListAdapter
工具类，命名以Util为后缀，如：EncryptUtil
接口一般要使用able、ible、er 等后缀，如： JPushReceiver
3. 方法命名

命名规则：方法名是一个动词，采用大小写混合的方式，第一个单词的首字母小写，其后单词的首字母大写。
例如： public void run(); public String getBookName();
类中常用方法的命名：
1.类的获取方法（一般具有返回值）一般要求在被访问的字段名前加上get，如
getFirstName()，getLastName()。一般来说，get前缀方法返回的是单个值，find前缀的方法返回的是列表值。
2.类的设置方法（一般返回类型为void）：被访问字段名的前面加上前缀 set，如
setFirstName(),setLastName().
3.类的布尔型的判断方法一般要求方法名使用单词 is或has 做前缀，如isPersistent()，isString()。或者使用具有逻辑意义的单词，例如equal 或equals。
4.类的普通方法一般采用完整的英文描述说明成员方法功能，第一个单词尽可能采用动词，首字母小写，如openFile(), addCount(), initView(), loadData()。
5.构造方法应该用递增的方式写。（参数多的写在后面）。
4. 变量命名

命名规则：第一个单词的首字母小写，其后单词的首字母大写。变量名不应以下划线或美元符号开头，尽管这在语法上是允许的。变量名应简短且富于描述。变量名的选用应该易于记忆，即，能够指出其用途。尽量避免单个字符的变量名，除非是一次性的临时变量。
例如：String bookName;
规约：变量命名也必须使用驼峰规则，但是首字母必须小写，变量名尽可能的使用名词或名词词组。同样要求简单易懂，不允许出现无意义的单词。
如：String bookName; 正确
如：String bookNameString; 错误！
5. 常量命名

命名规则：类常量的声明，应该全部大写，单词间用下划线隔开。
例如：static final int MIN_WIDTH = 4;
例如：static final int MAX_WIDTH = 999;
例如：static final int GET_THE_CPU = 1;
6. 异常命名

自定义异常的命名必须以Exception为结尾。
7. layout命名

规约：layout xml 的命名必须以 全部单词小写，单词间以下划线分割，并且使用名词或名词词组。命名规则为：组件类型_{范围_}功能，范围可选，只在有明确定义的范围内才需要加上。
以下为几种常用的组件类型命名：
activity_{范围_}功能，为Activity的命名格式
fragment_{范围_}功能，为Fragment的命名格式
dialog_{范围_}功能，为Dialog的命名格式
item_list_{范围_}功能，为ListView的item命名格式
item_grid_{范围_}功能，为GridView的item命名格式
header_list_{范围_}功能，为ListView的HeaderView命名格式
footer_list_{范围_}功能，为ListView的FooterView命名格式
8. 控件id命名

规约：layout 中所使用的id必须以全部单词小写，单词间以下划线分割，并且使用名词或名词词组，并且要求能够通过id直接理解当前组件要实现的功能。命名规则为：控件缩写_{范围_}意义，范围可选，只在有明确定义的范围内才需要加上。
如：某TextView @+id/txtbookname 错误 !应为 @+id/txt_book_name
如：某EditText @+id/edtbookname 错误 !应为 @+id/edt_book_name
控件缩写
控件	缩写	控件	缩写
TextView	txt	EditText	edt
Button	btn	ImageButton	ibtn
ImageView	img	ListView	list
RadioGroup	group	RadioButton	rbtn
ProgressBar	progress	SeekBar	seek
CheckBox	chk	Spinner	spinner
TableLayout	table	TableRow	row
LinearLayout	llayout	RelativeLayout	rlayout
ScrollView	scroll	SearchView	search
TabHost	host	TabWidget	widget
9. strings命名

命名规则为： 类型_{范围_}功能，范围可选。
以下为几种常用的命名：
页面标题，命名格式为：title_页面
按钮文字，命名格式为：btn_按钮事件
标签文字，命名格式为：label_标签文字
选项卡文字，命名格式为：tab_选项卡文字
消息框文字，命名格式为：toast_消息
编辑框的提示文字，命名格式为：hint_提示信息
图片的描述文字，命名格式为：desc_图片文字
对话框的文字，命名格式为：dialog_文字
10. colors命名

命名规则为： 以RGB颜色值命名。
如：#000000命名为000000， #797979命名为797979
11. drawable命名

命名规则为： 前缀{_控件}{_范围}{_后缀}，控件、范围、后缀可选，但控件和范围至少要有一个。
图标类，添加ic前缀
背景类，添加bg前缀
分隔类，添加div前缀
默认类，添加def前缀
区分状态时，默认状态，添加normal后缀
区分状态时，按下时的状态，添加pressed后缀
区分状态时，选中时的状态，添加selected后缀
区分状态时，不可用时的状态，添加disable后缀
多种状态的，添加selector后缀（一般为ListView的selector或按钮的selector）
12. 动画文件命名

命名规则为： 动画类型_动画方向
fade_in，淡入
fade_out，淡出
push_down_in，从下方推入
push_down_out，从下方推出
slide_in_from_top，从头部滑动进入
zoom_enter，变形进入
shrink_to_middle，中间缩小
注释规范
Java 程序有两类注释：实现注释(implementation comments)和文档注释(document comments)。实现注释是使用/.../和//界定的注释。文档注释(被称为"doc comments")由/**...*/界定。文档注释可以通过javadoc 工具转换成HTML 文件。
1. 文件头注释

文件顶部统一添加版权声明，声明的内容如下：
    /*
     * 文件名 
     * 版权声明
     * 创建日期
     * 版本信息，版本号
     */
注释模板及设置方法见下面。
2. 类和接口注释

类和接口统一添加javadoc注释，内容如下。
    /**
     * 类和接口的描述信息
     * 作者
     * 创建日期
     */
Eclipse中设置文件头注释及类和接口注释方法如下：
打开 Preference-->Java-->Code Templates-->Code-->New Java files
替换以下模板并保存即可：
/* 
 * @Title:  ${file_name} 
 * @Copyright (c) ${year} 3N CTO Co.,Ltd. All rights reserved 
 * @data:  ${date}
 * @version:  V1.0 
 */
${filecomment}
${package_declaration}
/**
 * ${todo}
 * @Author ${user}
 * @Date Create at ${date} ${time}
 */
${typecomment}
${type_declaration}

3. 方法注释

下面几种方法，都必须添加javadoc注释，说明该方法的用途和参数说明，以及返回值的说明。其他方法也需要加上//或者/**/注释说明。
接口中定义的所有方法
抽象类中自定义的抽象方法
所有类的自定义public方法和protected方法
    /**
	 * 方法用途描述
	 * @param s 说明参数含义
	 * @return 说明返回值含义
	 * @throws IOException 说明发生此异常的条件
	 */
Eclipse设置方法注释模板方法如下：
打开 Preference-->Java-->Code Templates-->Comments-->Methods
替换以下模板并保存即可：
/**
 * ${tags}
 */
4. 类成员变量和常量注释

public和protected成员变量和常量需要使用javadoc形式的注释，以说明当前变量或常量的含义；其他成员变量和常量可以添加//注释，优先采用右侧//来注释，若注释说明太长则在上方添加注释。
    /**现金券**/
    public static final int TYPE_CASH = 1; 
    /**抵扣券**/
    public static final int TYPE_DEBIT = 2; 
    /**折扣券**/
    public static final int TYPE_DISCOUNT = 3; 
     
    private int id; // 券id
    private String name; // 券名称
    private String introduce; // 券简介
5. 其他注释

方法内部的注释 如果需要多行 使用**/*…… */形式，如果为单行是用//……形式的注释。不要在方法内部使用 javadoc 形式的注释“/**……**/”**，简单的区分方法是，javadoc形式的注释在 eclipse中为蓝色，普通注释为绿色。
6. TODO注释

如果代码是暂时的、短期的解决方案或够用但不够完美的使用TODO注释：
//TODO：Remove this code after the UrlTable2 has been checked in.
7. XML注释

规约：如果当前layout 或资源需要被多处调用，或为公共使用的layout（若list_item），则需要在xml写明注释。要求注释清晰易懂。
规约

使用butterknife简化代码；


不要使用 try catch 处理业务逻辑！


代码中不允许出现单独的数字，字符！如果需要使用数字或字符，则将它们按照含义封装为静态常量！（for语句中除外）


判断中如有常量，则应将常量置于判断式的左侧。
如：if (true == isAdmin())


所有if 语句必须用{}包括起来,即便是只有一句；


含有多种运算符的表达式中使用圆括号来避免运算符优先级问题；


如果一个包含二元运算符的表达式出现在三元运算符" ? : "的"?"之前，那么应该给表达式添上一对圆括号。例如：(x >= 0) ? x : -x


使用switch case 结构，如果存在非空的 case 直穿语句，主体里必须有类似 // no break 的注释。


versionName和versionCode在没有特殊要求的情况下，使用以下规范定义：

versionName：2.4.1 逢10进1
versionCode：24101~24199 前3位对应versionName，后面两位是开发或者紧急升级时使用。

如：2.4.4 对应 24401
3.1 对应 31001
1.0 对应 10001
2.4.1紧急修复一个版本，不属于常规升级，可以使用2.4.101 对应24101


【3】控件仓库

【4】问题收集

【5】有趣的网址

【6】项目下载地址
