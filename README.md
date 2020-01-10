
#　TTK前端的开发注意事项，主要有以下几点:

1、sf操作统一放到reducer里设置,如果有批量写状态的话，还是调用reducer的updateArr方法,action里尽量不要写sf操作（IE9下已经证明sf效率非常低，而且不符合Redux的设计原则）。

2、后端返回的数据，要有取舍的setstate,特别是数据量大的时候不要放state里。

3、data.js里尽量少用表达式，可以减少重复渲染。

4、如果业务场景需要新的第三方组件，不要直接import，使用按需加载，组件库里不要加index2.js,index3.js这样的组件了(添加新的插件有专人负责，私自添加无法生效)

5、表格控件选型标准(可编辑表格必须统一使用datagrid，数据量大需要启用lazyload特性，带多重表头的表格统一使用ant table,数据量大的情况下，要启用virtual table特性)

6、静态资源图片统一放到vendor/image下，按模块名存放。

7、app名称必须小写，组件名首字母大写，可参考(ttk-fed规范)。

8、使用的settimeout,setinterval必须要清除，注册的事件要在页面卸载后销毁。

9、禁止开发app的样式互相冲突，每个app的样式按名称隔离。

10、禁止组件库里出现业务代码，所有组件开发要遵守react开发规范。

11、data.js里，children同级中，name不要重复。

12、方法、变量，必须加注释，便于维护、升级、协同。

13、一个方法中，尽可能地只实现1个功能。

14、代码的缩进等格式不一致，需统一使用同配置的美化插件。

15、react组件中，属性名不对，如：class，应该用className。

16、组件传值注意类型(组件的API参考antd官网)如：

1）Col 的span，应该传入number类型，有些传入了string。

2）DatePicker的disableDate，应该传入function，有些传入了string。

3）react的列表，key值，应该是独一无二的不变的值，有些传入了数组的索引index

17、action.js里的主要功能包括接口调用、页面动作
reducer.js里的主要功能是对接口返回的数据进行操作、存储
如果遵循以上原则的话，那在action里sf的机会就会很少了


TTK使用指南：[http://www.ttkteam.com/](http://www.ttkteam.com/)
GITHUB:[https://github.com/thethreekingdoms](https://github.com/thethreekingdoms)
TTK官网：[https://thethreekingdoms.github.io/](https://thethreekingdoms.github.io/)
