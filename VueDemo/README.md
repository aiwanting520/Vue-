案例分析：

1.拆分组件
2.实现静态页面
3.交互
    （1）将header输入的数据添加到Main中
          分析：*实际上就是要更新Main中的数据，那么我们在App中定义了todos数据，所以也只能在这里进行数据的更新，在App中定义更新数据的方法
                *App(Addtodo)方法传递给Header;
                *如何在Header中实现数据的收集以及数据的更新
                    -----数据收集：在input中用v-model="title"收集title数据
                    -----数据更新：在input中添加@keyup.enter事件名为add
                                    {
                                        1.获取输入的数据this.title
                                        2.创建一个todo对象
                                        3.将todo对象的数据传递给App(todos)---->Main(todo)-->Item(更新数据)
                                        4.清除input中的数据（v-module数据双向绑定实现)
                                    }
    (2) 数据删除
          分析：1.确定Item中有状态变化（鼠标上浮，背景颜色和删除按钮是否显示）
                2.在标签中添加监视状态指令
                3.添加状态的监听事件（更新状态的函数）
                4.App中定义删除Item的方法



