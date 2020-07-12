# 学习笔记
## 语言通识
  1. 语言： <br>
    非形式语言： 语法没有严格的规定（英文、中文） <br>
    形式语言：严格定义（乔姆斯基谱系，包含关系）
    + 0型：无限制文法(产生式书写无限制)
    + 1型： 上下文相关文法（根据前后判别每个符号）
    + 2型： 上下文无关文法 （产生式左边只有一个非终结符）
    + 3型： 正则文法 （都可用正则表达式表示）
    > javascript 非严格意义上，大部分表达式是上下文无关无法，特殊情况特殊处理
  2. 产生式（BNF）
    + 用尖括号扩起来的名称表示语法结构名
    + 语法结构分成基础结构和需要用其他语法结构定义的复合结构
      + 基础结构称终结符
      + 复合结构称非终结符
      > 终结符不是程序终止的意思，类似树中节点的意思。字符串表示终结符
    + 引号和中间的字符表示终结符
    + 可以有括号，括号扩起来产生不同的语法的结构，产生一组
    + * 表示重复多次
    + | 表示或
    + +表示至少一次
  3. 图灵完备性
    + 命令式 ---- 图灵机 （go to\if else）
    + 声明式 ---- lambda（递归）
## javascript 类型
  1. Number
  2. String
  3. Boolean (true false)
  4. Null
  5. Undefined
  6. Object
  7. Symbol: 返回唯一值，只有通过创建时给的值能访问到，可用在Object key中，增加唯一性和隐私性。
  ## Number 
  + JavaScript 内部，所有数字都是以64位浮点数形式储存，即使整数也是如此。所以，1与1.0是相同的，是同一个数。由于浮点数不是精确的值，所以一些计算比较也会出现误差。
  + 精度表示
    + 根据国际标准 IEEE 754，JavaScript 浮点数的64个二进制位，从最左边开始，是这样组成的。
    + 第1位：符号位，0表示正数，1表示负数，决定了一个数的正负
    + 第2位到第12位（共11位）：指数部分，决定了数值的大小
    + 第13位到第64位（共52位）：小数部分（即有效数字），决定数值的精度
  ## String
  ### 运行时
  + 字符串（Character）,一种抽象的概念，由Code Point(数字)表示，由一定的编码方式编译
  + 编码集（字符集）
    + ASCII: 自规定127个字符
    + Unicode: 划分不同的片区，000-fff，基于两个字节的编码
    + GB(与Unicode不兼容)
      + GB2312
      + GBK
      + GB18030
    + ISO-8859
    + BIG5
  + UTF
  ### 语法
  + “ ‘ `
  ## null undefind
  + null 代表空值，typeof 返回object，关键词、
  + undefind 表示没有值
  ## Object
  + 语法
    + key可以是 string or symbol
    + value
      + data property: 数据属性描述状态， 如果data里放函数，那么也可以描述行为
        + [[value]]
        + writeable
        + enumerable
        + configurable
      + accessor property: 数据属性描述行为
        + get
        + set
        + enumerable
        + configurable
  + api
    + {} . [] Object.defineProperty
      > 提供基本对象机制，通过语法创建对象，访问属性和定义新的属性，改变属性的特征值
    + Object.create/Object.setPrototypeOf/Object.getPrototypeOf
      + 原型相关
      + Object.create指定原型的创建对象
      + Object.setPrototypeOf/Object.getPrototypeOf修改获取原型
    + new/class/extends
    + new/function/prototype 不推荐
