## **一 Java概述**

* javac命令编译为字节码.class文件，java命令执行.class字节码，解释型执行

* Java是面向对象的解释型语言，与C语法类似，但抛弃了令人困惑的语法：重载运算符，多继承等，指针改为引用。

* Java只支持类class间的单继承，但可支持接口interface间的多继承。

* 接口interface，仅定义派生要用到的方法，而方法的具体实现取决于派生类，在继承中扮演重要的角色。

---

## **二 Java面向对象概述**

* **继承extends**

![](Note_pic/20b9441240e63f62e1f64390f34ad9d.jpg)

* **多态polymophism**

**方法重载：**一个类中定义了多个方法名相同,而他们的参数的数量不同或数量相同而类型和次序不同

**方法重写**：方法重写是在子类存在方法与父类的方法的名字相同,而且参数的个数与类型一样,返回值也一样的方法。重写可能有@Override的标识符。

![](Note_pic/db71ad0d8dfd17d8bf3a168145b97af.jpg)

* **抽象与接口**

其中接口支持多重继承，定义一些Drivable等特性

![](Note_pic/65c19e1c11003338ab7ea4c41b4cddc.jpg)

* **源文件及包**

除下面的要求以外，.java文件的名称应与public对应的类名相同

![](Note_pic/5bf1d5608cf85da4b9b739f60bd69a6.jpg)

---

## **三 Java数据与变量类型**

分为内置数据类型与引用数据类型.

  * **内置数据类型**：

byte short int float double boolean char

  * **引用数据类型**：

![](Note_pic/b860a205691d3e0bd0ef97356266a57.jpg)

  * **值传递与引用传递**

对象默认为引用传递，基本数据类型为值传递.

![](Note_pic/e96709a8473cfddb9626a376edaca4f.jpg)

  * **Java的常量**

在Java中使用final关键字来修饰常量，通常全大写来命名变量.

  * **访问控制修饰符**

1.主要分为private public 与 protected. 

2.default 为包级别，也即只能被同一包中的其他类访问.

3.类和接口不能使用private修饰，类不能用protected修饰

![](Note_pic/7b68d74dbacf86fc4b006b7c5976708.jpg)

上述几种修饰符的约束条件：

![](Note_pic/6aed5286df7314a4130fa9c80a849eb.jpg)

---

## **四 Java中的各种类**

    a. **Number&Math类**

            1. Java 语言为每一个内置数据类型提供了对应包装类（Integer、Long、Byte、Double、Float、Short），都是抽象类 Number 的子类~(初始化Number类变量时需要new)~

        I. Java 的 Math 包含了基本数学运算的属性和方法(floor round ceil)，Math 的方法都被定义为 static 形式，通过 Math 类可以在主函数中直接调用

        II. 实际上，Java提供装箱(基本类型到包装类型)与拆箱操作(反之)

    b. **Character类**

        I. 包含isLetter() isxxx()... toxxx()...等具体操作，具体函数请查询Java文档

    c. **String与StringBuffer类**

        I. String类无法被修改而StringBuffer/StringBuilder类对象可以被修改.

        II. StringBuilder与StringBuffer间区别为是否线程安全，后者安全而前者效率更高，具体方法见JavaAPI文档

    d. **Scanner类**

![](Note_pic/403dae2d8c3bc493a4a97669eee4c58.jpg)

        I. 程序可以通过java.util.Scanner类来获取用户的输入，上面是创建一个Scanner对象的基本语法.

        II. **next() 与 nextLine() 方法获取输入的字符串**，在读取前我们一般需要 使用 hasNext 与 hasNextLine 判断是否还有输入的数据.

![](Note_pic/4a88618212425ab0c867fa8b6ac4860.jpg)

    * **Tips：next()与nextline()的异同**

![](Note_pic/667210bc0b480343d0d44f52f2b880b.jpg)

![](Note_pic/6c21cb5087f25b750846ba13ef1d545.jpg)

    * **Tips：对基本数据类型，存在hasNextxxx()与nextxxx()等函数，比如Int Double**

### e. **Object类**

Object 类是所有类的父类，位于自动导入的 java.lang 包中，若未明确继承父类，将隐式继承 Object类.

      * 包含clone(),hashcode(),equals() ,wait()等方法.


---

## **五 Java数组**

  * **数组声明与初始化**

上方为Java风格的数组定义，下方为C风格的数组定义，建议使用前者.

![](Note_pic/01e1cc44152a28d4ed0c94c6ecf1229.jpg)

创建数组时，可以使用枚举的方法{4，1，2}，也可以使用new的方法.

![](Note_pic/b7716184a5a095e3947d4a16cc69ee3.jpg)

  * **数组为引用传递**

---

# **六 调用与构造函数**

  * 运行一个程序时候再传递给它消息。这要靠传递命令行参数给main()函数实现(在编译命令中在 javac后->java时添加命令行参数)

  * 类中构造函数的特点有：与类名相同且没有返回类型，支持子类super调用(但不能被继承)，自动调用(使用 new 创建对象时)，使用this表示实例对象自身

![](Note_pic/09b2a666bd8d6a1767ae39ef5cbbe7a.jpg)

---

# **七 Java面向对象精讲**

  * **Java继承**

    * **extends关键字**

![](Note_pic/ae02f3838658a93639cdbf8e70cf910.jpg)

    * **继承中子类与父类的关系**

            1. 子类拥有父类非 private 的属性、方法。

            2. 子类可以拥有自己的属性和方法，即子类可以对父类进行扩展。

            3. 子类可以用自己的方式实现父类的方法。

            4. 子类是不继承父类的构造器（构造方法或者构造函数）的，它只是调用––当父类为~非参数构造器时，隐式调用~；为~参数构造器时，显式调用~

    * **implements关键字**

            1. Java在设计父类时，不允许使用多继承，但implements 关键字可以变相的使java具有多继承的特性(**接口**)

            2. 如下图，即为一个多继承接口的实例

![](Note_pic/b5ef6e2ea74850775e539c21d8760f7.jpg)

    * **super 与 this 关键字**

            1. super 关键字：可以通过 super 关键字来实现对父类成员的访问，用来引用当前对象的父类

            2. this 关键字：指向自己的引用，引用当前对象，即它所在的方法或构造函数所属的对象实例

  * **Java多态**

![](Note_pic/202579414e81d987e279aa44515f45f.jpg)

    * 当使用多态方式调用方法时，首先检查父类中是否有该方法，如果没有，则编译错误；如果有，再去调用子类的同名方法。

    * 要想调用父类中被重写的方法，则必须使用关键字 super

  * **Java抽象类**

    * 抽象类不能实例化对象，被继承，才能被使用

    * 在 class 前添加 **abstract** 关键字定义抽象类

    * **抽象方法：**

            1. Abstract 关键字同样可以用来声明抽象方法，抽象方法只包含一个方法名，而没有方法体

            2. 如果一个类包含抽象方法，那么该类必须是抽象类

![](Note_pic/250a3f361332e161c5c68b5758e24cd.jpg)

  * **Java接口**

        I. 定义：**接口是抽象方法的集合**，一个类通过继承接口的方式，从而来继承接口的抽象方法

        II. **特点**：

            1. 接口无法被实例化，但是可以被实现

            2. 一个实现接口的类，必须实现接口内所描述的所有方法，否则就必须声明为抽象类

            3. 接口是隐式抽象的，当声明一个接口及其方法时，不必使用abstract关键字

            4. 接口中的方法都是公有的

        III. **接口的声明与实现**

**声明**：可见度即public等限定关键字

![](Note_pic/fcb88940041d70cb9315d0eba49519c.jpg)

**实现：在class的声明后增加implements关键字**

![](Note_pic/6299b261c0aea755c66ceb610a192ff.jpg)

    * **标记接口**

标记接口是没有任何方法和属性的接口.它仅仅表明它的类属于一个特定的类型(例如awt包里的MouseEvent接口，接口体为空)

---

# **八 Java 文件组织**

    * **Java包 (Package)**

路径应该是 **pkg1/pkg2/pkg3/xxx.java**

![](Note_pic/453c711acd434d2c82cf57dfd9006a2.jpg)

      * **Java中常用pkg**

java.lang-打包基础的类

java.io-包含输入输出功能的函数

      * **import关键字**

import 关键字用于导入其他类或包中定义的类型，以便在当前源文件中使用这些类型

# **九 Java数据结构**

  * **数组Arrays**

存储固定大小的相同类型的元素，随机访问元素效率高，但大小固定，插入和删除元素较慢

![](Note_pic/ab58075ae7b4a479aea4920922f3221.jpg)

  * **列表Lists**

Java 提供了多种列表实现，如 ArrayList 和 LinkedList

![](Note_pic/a2ef34fe2ac16a9a6f79705d341e8b1.jpg)

下面是ArrayList与LinkedList的使用实例

![](Note_pic/06d910c414c7d27690fb3f1381d3d05.jpg)

  * **集合 Sets**

![](Note_pic/05d06fd30366cae1c484b1bd27d423a.jpg)

  * **映射 Maps**

用于存储键值对，常见用HashMap(基于哈希表)与TreeMap(基于红黑树)来实现Maps

![](Note_pic/9ec65b9b638f335c6a469bbce525360.jpg)

此外还有优先队列(堆)PriorityQueue<>，队列Queue<>常见的实现有 LinkedList 和 PriorityQueue，栈Stack<>等等，细节请参考Java文档

---

# **十 Java集合框架**

Java 集合框架主要包括两种类型的容器，一种是集合（Collection），存储一个元素集合，另一种是图（Map），存储键/值对映射。

Collection 接口又有 3 种子类型，List、Set 和 Queue，再下面是一些抽象类，最后是具体实现类，常用的有 ArrayList、LinkedList、HashSet、LinkedHashSet、HashMap、LinkedHashMap 等等。

![](Note_pic/555f745ae38cde79f221bcd6042e2e6.jpg)

    * **内置集合类**

    * **ArrayList数组队列**

![](Note_pic/39d172115fe8c4bd101245401f243ff.jpg)

      * 常用方法：add()，remove()，.size()，set(index,content)

      * ArrayList 中的元素实际上是对象,<E>中的数据类型为基本类型的包装类

      * ArrayList排序一般使用Collections类的sort：Collections.sort(sites);

    * **LinkedList链表**

      * 与 ArrayList 相比，LinkedList 的增加和删除的操作效率更高，而查找和修改的操作效率较低 (即链表和数组的比较)

      * **常用方法：add(),addFirst(),remove(),removeFirst(),get()**

![](Note_pic/e43d50cd823d2f18f415f1fd0ff047d.jpg)

    * **HashSet哈希集合(即集合**

    * **HashMap哈希映射(即字典**

    * **Iterator迭代器**

      * 迭代器（Iterator）是 Java 集合框架中的一种机制，是一种用于遍历集合（如列表、集合和映射等）的接口，提供了一种统一的方式来访问集合中的元素

      * **初始化迭代器**

Iterator<String> it = 可迭代对象.iterator();

      * **常用方法**

![](Note_pic/af4776c22ac72bafe836348ecb83166.jpg)

      * **实例**

![](Note_pic/63bd253c0037af262a140c4397a0356.jpg)

---

# **十一 Java序列化与网络编程**

  * **序列化**

    * 序列化是一种将对象转换为字节流的过程，用于将对象保存磁盘或网络传输.

    * 通过 **java.io.Serializable** 接口(前文“标记接口”)实现，可序列化的类需要implement java.io.Serializable 接口

    * ObjectOutputStream类可用于序列化可序列化对象.(暂时感觉用不太上，这里先省略)

  * **Java网络编程(待使用时再补充)**

---

* **十二 Java多线程**

![](Note_pic/ae2fc4846a9e93edaca754b6095ba44.jpg)

事实上，Java中存在**实现runnable接口**、**继承Thread类**主要的两种方式来创建线程，核心是类中public void run()方法与public void start().

![](Note_pic/18cb88d342fb5c912c26daa5091a581.jpg)

**对象方法：**

![](Note_pic/2c2efd8e39d5eeb5bd3039af98e102d.jpg)

**Thread类静态方法：**

Thread.yield() - 暂停当前线程对象，执行其他进程

Thread.sleep(long millisec) - 线程对象睡眠x毫秒

**多种线程创建方法比较：**

  * 采用实现 Runnable、Callable 接口的方式创建多线程时，线程类只是实现了 Runnable 接口或 Callable 接口，还可以继承其他类

  * 继承 Thread 类的方式创建多线程时，编写简单，如果需要访问当前线程，则无需使用 Thread.currentThread() 方法，直接使用 this 即可获得当前线程
