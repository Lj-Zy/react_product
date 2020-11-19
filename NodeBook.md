首页
    轮播图使用了swiper插件库来实现
    搜索功能区,没有用到form表单，form表单还需要阻止它的默认事件，过考虑到是移动端的项目也没有必要加回车 所以不加事件 onKeyDown = {this.keyDown}


    
开发中遇到的bug
    <!--
        componentDidMount(){
            window.addEventListener('scroll',()=>{
                this.setState({
                    top : document.documentElement.scrollTop || document.body.scrollTop
                })
            })
        }
        
        如果在一个组件里这么写代码，有没有问题？问题在哪？
        你在window上绑了一个事件，对不对，没有错
        假设这个组件被销毁了，比如说你跳转了一个路由，不显示这个组件了，那么window上的那个事件还存不存在，还是存在的对不对
        this.setState就不会被释放，跳转到其他组件后window.addEventListener('scroll')依然会执行，this.setState就会报一些错误
        实际是这个组件销毁时没有销毁挂载在整个window上的事件

     -->
