主要是一些代码写法规范上的考量

1. 有意义的命名

2. 函数

   - 尽可能保持短小(20行以内最佳)
   - 只做一件事(感觉很难实现,在写一个逻辑复杂得业务时候,怎么能保证函数只做1件事?)
   - 每个函数保持是一个层级,不要混杂层级, 自顶向下规则
   - 使用描述性的名称
     - "长而具有描述性的名称,要比短而令人费解的名称号,要比描述性的长注释好", 这句话我觉得非常对
   - 函数参数
     - "最理想的输入参数数量为0, 其次为1, 再次为2, 应尽量避免3个以上
     - "表示参数丑陋不堪,向函数传入布尔值简直是骇人听闻的做法" 
     - "如果函数需要2,3个或以上的参数,说明其中的一些参数应该封装为类了"
     - 死函数,永不调用的函数应该尽快的删除

3. 注释

   - 注释不是越多越好
   - 注释应该是一些关键信息,或者一些法律,事务,提醒等重要信息
   - 注释应该表达准确正确的信息,而不是过时信息,通常作者,最后修改时间等元数据不该在注释中出现
   - 废弃的注释应该尽快删除
   - 功能明显的代码块不需要进行注释,否则就是冗余注释(如 i++ \\i自增)
   - 注释掉的注释应该尽快删除

4. 格式

   - 在封包声明,导入声明和每个函数之间,都有空白行隔开
   - 垂直顺序, 被调用的函数应该放在执行调用的函数下面,自顶而下
   - 概念相关, 概念相关的函数应该放在一起
   - 应该尽力保持代码行短小, 80个字符为上限
   - 空格符的用法, 在操作符,函数参数周边加上空格符,达到强调操作,分隔的效果

5. 错误处理

   - 错误处理很重要,但不是全部,如果到处都是凌乱的错误处理代码,搞乱了代码逻辑, 就是错误的做法
   - 使用异常,而非返回码
   - 别返回null值
   - 别传递null值,除非API要求你传递null值

6. 类

   - 公共静态变量先出现 然后是私有静态变量
   - 类应该短小,类的命名应该描述其权责, 如果该类无法精确额的描述,那么侧面说明该类可能拥有过多的权责

7. 系统

8. 迭代

   - 表达力,代码应尽可能表达清晰, 花时间调整代码以便于其他人进行理解
   - 尽可能少的类和方法

9. 并发编程

   - "对象是过程的抽象,线程是调度的抽象"

10. 一般性问题

    - 忽视安全
      - 关闭编译器的警告可能有助于代码的构建成功,但也存在无穷无尽的调试的风险

    - 重复
      - 每次看到重复的代码,都代表着遗漏的了抽象
    - 死代码
      - 注意删除死代码
    - 前后一致
      - 包括函数命名,变量命名等
    - 晦涩的意图
      - 代码要尽可能具有表达力
      - 使用解释性的变量
      - 函数名称应该表达其行为
      - 理解算法
      - 遵循标准约定
      - 避免否定性条件(否定式要比肯定式难以理解)
      - 函数应该只做一件事(也就是说功能要尽可能的分解)
    - 在较高的层级放置可配置数据

