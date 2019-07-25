**借鉴别人代码利用画布及声音api 做的一个音乐的播放动效**

线上地址:http://www.ooo0o.com/2019/fashion_music_cvs/

JS包已经发布到npm上去(https://www.npmjs.com/package/fashion_music_cvs)
````
        npm i fashion_music_cvs


        // vue项目引入方式一:
        // const fashion_music_cvs = require('fashion_music_cvs')
        // Vue.prototype.cvsgetready =fashion_music_cvs

        // vue项目引入方式二:
        import fashion_music_cvs from 'fashion_music_cvs'
        Vue.prototype.cvsgetready = fashion_music_cvs


        //  // 调用此方法需要传的的params的值应为 下边musiccvsparams的结构 
        //  //在组件中使用前 定义好data里的自定义变量,如下的 musiccvsparams 即可
      不//  ..................
      再//  data(){
      需//      return{
      要//          musiccvsparams : {
      这//              cvsdom:'',//画布节点元素
      个//              size:800,//画布原始默认宽高
      参//              sourcedom:'',//音频源节点元素
      数//              bgcolor:'rgba(255,255,0,0.5)'//画布圆圈背景颜色
        //          }
        //      }
        //  )

        ..................
        mounted(){
            //【注意：画布元素必须设置一个方形的父级容器】
            // 参数：画布元素。画布的默认宽度。音频元素。画布中圆圈背景的颜色
            let _this=this;
            _this.cvsgetready(_this.$refs.musiccvs,800,_this.$refs.musicsrc,'rgba(255,255,0,0.8)')
        }

        ..........................................
        <div id="musiccvsbox" ref="musiccvsbox" style="position: fixed;right: 20px; top: 20px; width: 40vw;height: 40vw;">
          <canvas ref="musiccvs" id="musiccvs"></canvas>
      </div>
      <audio style="position: fixed;right: 20px; bottom: 20px;" controls ref="musicsrc" preload="true" src="http://www.ooo0o.com/music/WhenIsawyouIfellinlove.mp3"></audio>
      
        
`````

`````
    注意样式设置：
    // 自定义画布实现音频显示
    #musiccvsbox {
        margin: 0 auto;
        position: relative;
        /* background-color: royalblue; */
        background: url('http://ooo0o.com/4eafc201905200012388758.jpg') center center no-repeat;
        background-size: cover;
    }
    
    #musiccvs {
        display: block;
        /* animation: rotate 6s linear infinite; */
        position: absolute;
        left: 0;
        top: 0;
        transform-origin: 0 0;
    }
    
    @keyframes rotate {
        0% {
            transform: rotate(0deg)
        }
        100% {
            transform: rotate(360deg)
        }
    }
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

github: https://github.com/Chinegoodman/fashion_music_cvs

项目发起缘由:   一直就想做一个和网易云音乐类似的动效出来。所以闲暇时就研究学习
        
项目过程:       好吧，挺费劲的反正是。。。你喜欢觉得能用就行。哈哈
````
![Image text](http://ooo0o.com/f079620190725141756489.png)