**借鉴别人代码利用画布及声音api 做的一个音乐的播放动效**

线上地址:http://www.ooo0o.com/2019/fashion_music_cvs/

JS包已经发布到npm上去(https://www.npmjs.com/package/fashion_music_cvs)
````
        npm i fashion_music_cvs


        // vue项目引入方式一:
        // const cvsgetready = require('cvsgetready')
        // Vue.prototype.cvsgetready =cvsgetready

        // vue项目引入方式二:
        import cvsgetready from 'cvsgetready'
        Vue.prototype.cvsgetready =cvsgetready


        // 调用此方法需要传的的params的值应为 下边cvsparams的结构 
        //在组件中使用前 定义好data里的自定义变量,如下的 cvsparams 即可
        ..................
        data(){
            return{
                cvsparams : {
                    cvsdom:'',//画布节点元素
                    size:800,//画布原始默认宽高
                    sourcedom:'',//音频源节点元素
                    bgcolor:'rgba(255,255,0,0.5)'//画布圆圈背景颜色
                }
            }
        )

        ..................
        mounted(){
            //【注意：画布元素必须设置一个方形的父级容器】
            // 参数：画布元素。画布的默认宽度。音频元素。画布中圆圈背景的颜色
            // cvsgetready(document.getElementById('cvs'),800,document.getElementById('music'));
            this.cvsgetready(this.cvsparams.cvsdom,this.cvsparams.size,this.cvsparams.sourcedom,this.cvsparams.bgcolor)
        }

        ..................
        
`````

````
        script引入方式
        
        1. <script src="./music_canvas_show.js"></script>
        2. 合适的时机去调用 cvsgetready('参数') 即可
        // 参数：画布元素。画布的默认宽度。音频元素【注意：画布元素必须设置一个方形的父级容器。代码中已做好适配缩放的设置】。画布中圆圈背景的颜色
        // cvsgetready(document.getElementById('cvs'),800,document.getElementById('music'));

        一般就onload调用就可
        window.onload = function() {
            cvsgetready(document.getElementById('cvs'), 800, document.getElementById('music'), 'rgba(66,66,66,0.6)');
        }

`````

````

项目介绍:       基于canvas及声音api做的音频显示效果

github: https://github.com/Chinegoodman/

项目发起缘由:   一直就想做一个和网易云音乐类似的动效出来。所以闲暇时就研究学习
        
项目过程:       好吧，挺费劲的反正是。。。你喜欢觉得能用就行。哈哈
````
![Image text](http://ooo0o.com/f079620190725141756489.png)