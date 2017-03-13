# learn

sass、gulp、 webpack、 swiper.js、 fullpage.js、 superslide.js、 jqMobile、 SenCha Touch、Frozen UI、animate.css、axios、koa、express
metronic
coreadmin
15620791420
41272219930509004x
344436616@qq.com
http://louiszhai.github.io/2016/06/13/regexp/ 正则表达式
只愿一生爱一人
https://ant.design/docs/react/introduce  react
18258801347
yun826574

https://github.com/hbxeagle/rem/blob/master/README.md
segmentfault.com
http://www.zzbaoguan.com/  上线项目
http://www.zqrck.com 上线项目

http://www.cnblogs.com/ganmy/p/6029774.html  vue环境搭建
http://www.open-open.com/lib/view/open1476240930270.html  vue环境搭建
http://www.jianshu.com/p/a8701d724e70 vue环境搭建
http://www.jb51.net/article/96966.htm vue环境搭建

http://jiongks.name/blog/just-vue项目实战
https://segmentfault.com/a/1190000007556806  vue项目
http://www.cnblogs.com/wisewrong/p/6255817.html    vue-cli

https://github.com/nicejade/Front-end-tutorial 前端资料

https://tianxiangbing.github.io/react-cn/docs/getting-started.html     react文档

http://www.zhangxinxu.com/jq/stylus/  css预编译

AppID       wx6bc84180c30734f0
AppSecret   87f7bdc12cd1e721d99e5efd9d2933c7




如果我用你待我的方式来待你，恐怕你早已离去。

凡事换个角度，假如你是我，你未必有我大度 ！


  var Dpr = 1, uAgent = window.navigator.userAgent;
        var isIOS = uAgent.match(/iphone/i);
        var isYIXIN = uAgent.match(/yixin/i);
        var is2345 = uAgent.match(/Mb2345/i);
        var ishaosou = uAgent.match(/mso_app/i);
        var isSogou = uAgent.match(/sogoumobilebrowser/ig);
        var isLiebao = uAgent.match(/liebaofast/i);
        var isGnbr = uAgent.match(/GNBR/i);
        function resizeRoot(){
            var wWidth = (screen.width > 0) ? (window.innerWidth >= screen.width || window.innerWidth == 0) ? screen.width : window.innerWidth : window.innerWidth, wDpr, wFsize;
            var wHeight = (screen.height > 0) ? (window.innerHeight >= screen.height || window.innerHeight == 0) ? screen.height : window.innerHeight : window.innerHeight;
            if (window.devicePixelRatio) {
                wDpr = window.devicePixelRatio;
            } else {
                wDpr = isIOS ? wWidth > 818 ? 3 : wWidth > 480 ? 2 : 1 : 1;
            }
            if(isIOS) {
                wWidth = screen.width;
                wHeight = screen.height;
            }
            // if(window.orientation==90||window.orientation==-90){
            //     wWidth = wHeight;
            // }else if((window.orientation==180||window.orientation==0)){
            // }
            if(wWidth > wHeight){
                wWidth = wHeight;
            }
            wFsize = wWidth > 1080 ? 144 : wWidth / 7.5;
            wFsize = wFsize > 32 ? wFsize : 32;
            window.screenWidth_ = wWidth;
            if(isYIXIN || is2345 || ishaosou || isSogou || isLiebao || isGnbr){//YIXIN 和 2345 这里有个刚调用系统浏览器时候的bug，需要一点延迟来获取
                setTimeout(function(){
                    wWidth = (screen.width > 0) ? (window.innerWidth >= screen.width || window.innerWidth == 0) ? screen.width : window.innerWidth : window.innerWidth;
                    wHeight = (screen.height > 0) ? (window.innerHeight >= screen.height || window.innerHeight == 0) ? screen.height : window.innerHeight : window.innerHeight;
                    wFsize = wWidth > 1080 ? 144 : wWidth / 7.5;
                    wFsize = wFsize > 32 ? wFsize : 32;
                    // document.getElementsByTagName('html')[0].dataset.dpr = wDpr;
                    document.getElementsByTagName('html')[0].style.fontSize = wFsize + 'px';
                    document.getElementById("fixed").style.display="none";
                },500);
            }else{
                // document.getElementsByTagName('html')[0].dataset.dpr = wDpr;
                document.getElementsByTagName('html')[0].style.fontSize = wFsize + 'px';
                document.getElementById("fixed").style.display="none";
            }
            // alert("fz="+wFsize+";dpr="+window.devicePixelRatio+";UA="+uAgent+";width="+wWidth+";sw="+screen.width+";wiw="+window.innerWidth+";wsw="+window.screen.width+window.screen.availWidth);
        }
        resizeRoot();








function adapt(designWidth, rem2px){
  var d = window.document.createElement('div');
  d.style.width = '1rem';
  d.style.display = "none";
  var head = window.document.getElementsByTagName('head')[0];
  head.appendChild(d);
  var defaultFontSize = parseFloat(window.getComputedStyle(d, null).getPropertyValue('width'));
  d.remove();
  document.documentElement.style.fontSize = window.innerWidth / designWidth * rem2px / defaultFontSize * 100 + '%';
  var st = document.createElement('style');
  var portrait = "@media screen and (min-width: "+window.innerWidth+"px) {html{font-size:"+ ((window.innerWidth/(designWidth/rem2px)/defaultFontSize)*100) +"%;}}";
  var landscape = "@media screen and (min-width: "+window.innerHeight+"px) {html{font-size:"+ ((window.innerHeight/(designWidth/rem2px)/defaultFontSize)*100) +"%;}}"
  st.innerHTML = portrait + landscape;
  head.appendChild(st);
  return defaultFontSize
};
var defaultFontSize = adapt(640, 100);
