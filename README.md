# **<font face="微软雅黑">燚博云前端编码规范</font>**

## <font face="微软雅黑">前端代码风格</font>

### 一、文件命名

- 组件命名首字母大写 驼峰式命名

```javascript
DatePicker.vue
```

- 其他文件首字母小写 驼峰式命名

```javascript
datePicker.css
```

### 二、HTML 编码规范

#### 2.1 标签与属性

1、class 小写 使用 **模块名\_功能名** 例:

```html
<a class="home_conatiner"></a>
```

**eg: 如项目名过长可酌情缩写**

2、id 首字母小写 驼峰式命名

```html
<a id="balckLine"></a>
```

3、所有 html 属性必须添加双引号（非单引号）。

```javascript
// 禁止
<div id=mainframe> 或 <div id='mainframe'>

// 推荐
<div id="mainframe">
```

4、标签属性顺序

属性应该按照特定的顺序出现以保证易读性；

- class
- id
- name
- data-\*
- src, for, type, href, value , max-length, max, min, pattern
- placeholder, title, alt
- aria-\*, role
- required, readonly, disabled

class 是为高可复用组件设计的，所以应处在第一位；

id 更加具体且应该尽量少使用，所以将它放在第二位

#### 2.2 风格

1、格式缩进

html 编码统一格式化显示，使用一个 Tab 键进行分层缩进 (2 个空格宽度)，使整个页面结构层次清晰，方便阅读和修改。

2、模块注释

html 较大独立模块之间注释格式统一使用：

```html
<!--模块 start-->
<!--模块 end-->
```

或者：

```html
<!-- XXX模块 -->

<!-- /XXX模块 -->
```

### 三、CSS 编码规范

#### 3.1 CSS 引用规范

1、**<font color=red>所有 CSS 均为外部调用，不得在页面书写任何内部样式或行内样式；</font>**

2、内部模块之间注释（建议 @模块英文名，好查找）：

```css
/* @header 头部 -----------------------------------------------------------*/
.infoArea {
}

/* 单行注释 */
.specArea {
}

/* @footer 页尾 ----------------------------------------------------------*/
.price {
}
```

3、引号

最外层统一使用双引号；

url 的内容要用引号；

属性选择器中的属性值需要引号。

```css
.element:after {
  content: '';
  background-image: url('logo.png');
}

li[data-type='single'] {
  ...;
}
```

#### 3.2 杂项

1. 不允许有空的规则；

2. 元素选择器用小写字母；

3. 去掉小数点前面的 0；

4. 去掉数字中不必要的小数点和末尾的 0；

5. 属性值'0'后面不要加单位；

6. 同个属性不同前缀的写法需要在垂直方向保持对齐，具体参照右边的写法；

7. 无前缀的标准属性应该写在有前缀的属性后面；

8. 不要在同个规则里出现重复的属性，如果重复的属性是连续的则没关系；

9. 不要在一个文件里出现两个相同的规则；

10. 用 border: 0; 代替 border: none;；

11. 选择器不要超过 4 层（在 scss 中如果超过 4 层应该考虑用嵌套的方式来写）；

12. 尽量少用'\*'选择器。

### 四、 JavaScript 规范（jslint/eslint）

#### 4.1 JS 注释规则

1、文件头部注释

```javascript
/**
 * @created : 2017/09/15
 * @author : Mr.Wang
 * @desc : 当前js模块功能描述
 **/
```

2、方法注释

```javascript
/**
 * @description 加法运算
 * @param {Number} num1 加数
 * @param {Number} num2 被加数
 * @return {Number} result 结果
 */
function add(num1, num2) {
  return num1 + num2
}
```

3、单行注释

双斜线后，必须跟一个空格；
缩进与下一行代码保持一致；
可位于一个代码行的末尾，与代码间隔一个空格。

```javascript
var funName = function(arg1, arg2) {
  this.arg1 = arg1

  // 单行注释说明(上面添加一空行, //与说明之间空一格)
  this.arg2 = arg2
}
```

#### 4.2 JS 命名规则

1、方法命名

- 变量名应由 26 个大小写字母（A..Z，a..z），10 个数字（0..9），和“\_”（下划线）组成。
- 首字母小写 驼峰式命名
- 私有方法以\_开始
- 构造函数 首字母大写 驼峰式命名
  动词 | 含义 | 返回
  :-: | :-: | :-:
  can| 判断是否可执行某个动作(权限)| 函数返回一个布尔值。true：可执行；false：不可执行
  has| 判断是否含有某个值 |函数返回一个布尔值。true：含有此值；false：不含有此值
  is| 判断是否为某个值| 函数返回一个布尔值。true：为某个值；false：不为某个值
  get|获取某个值| 函数返回一个非布尔值
  set |设置某个值 |无返回值、返回是否设置成功或者返回链式对象
  load| 加载某些数据| 无返回值或者返回是否加载完成的结果
- 特殊情况

```javascript
// 'ID'在变量名中全大写
var goodID

// 'URL'在变量名中全大写
var reportURL

// 'Android'在变量名中大写第一个字母
var AndroidVersion

// 'iOS'在变量名中小写第一个，大写后两个字母
var iOSVersion
```

2、 杂项

1、用'===', '!=='代替'==', '!='；

2、不要像这样使用构造函数，例：new function () { ... }, new Object；

3、不要在内置对象的原型上添加方法，如 Array, Date；

4、不要在内层作用域的代码里声明了变量，之后却访问到了外层作用域的同名变量；

5、变量不要先使用后声明；

6、不要在一句代码中单单使用构造函数，记得将其赋值给某个变量；

7、不要在同个作用域下声明同名变量；

8、不要在一些不需要的地方加括号，例：delete(a.b)；

9、不要声明了变量却不使用；

10、不要在应该做比较的地方做赋值；

11、debugger，console 不要出现在线上的代码里；

12、数组中不要存在空元素；

13、不要在循环内部声明函数；

4.3 vue 风格
1、prop 定义尽量详细

```javascript
props: {
  status: {
    type: String,
    required: true
  }
}
```

2、 避免 v-if 和 v-for 用在一起
3、 生命周期函数按照加载顺序 置于下方

```javascript
export default {
  name:'MyComponents';
  data() {
    mes: 'hello world'
  },
  prop: {
    status: {
      type: String,
      required: true
    }
  },
  computed: {},
  watch: {},
  methods: {},
  beforeCreat() {},
  created() {},
  beforeMount() {},
  mounted() {}
}
```

#### 5.其他

其他未被提及的 具体依照 eslint 规范
