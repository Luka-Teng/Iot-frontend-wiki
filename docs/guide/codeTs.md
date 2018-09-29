### Typescript代码规范

!> TS最好都要过一遍教程，理解了才能知道怎么写代码。

1. 变量的区分，命名：TS的变量可以大致分为基础变量，对象，方法，类，类型变量五种。

2. 定义
  1. 创建的基础变量，对象需要定义类型
  2. 定义的方法至少要定义参数的类型
  3. 定义的方法，如果方法体内会用到this，且该方法不是箭头函数，则需要显示的定义this。 
  4. 赋值的方法可以不需要定义，ts会依靠推论自己去做验证。
  5. 类的实例变量需要先定义，才能使用。
  6. 变量声明但是没有赋值的情况下（包括普通变量，实例变量），不能赋值其属性。

3. React相关
  1. 无状态组件需要定义传递的参数props，否则默认不存在props。
  2. 状态组件需要在在泛型内定义props，state，context，如果不写则会默认props, state为空对象，context为any。

4. 引入无声明的JS库
  1. node_modules: 需要在lib文件夹下创建js引入引出，并创建声明文件声明。
  2. src: 直接在js文件所在目录下创建同名声明文件。

5. interface & type
  interface: interface主要用于对对象的约束，对方法的约束，对类实例的约束（广义上也是对对象的约束）。
  type: 主要用于简单的类型，交叉类型，联合类型等。不可用于继承和实现。

6. 注意事项
  1. 谨慎使用类型断言。
  2. 兼容性问题，详细可以参考下[兼容性章节](http://www.css88.com/doc/typescript/doc/handbook/Type%20Compatibility.html)。
  3. 理解[装饰器](http://www.css88.com/doc/typescript/doc/handbook/Decorators.html)的用法，这个在处理非业务相关功能的时候十分好用。
