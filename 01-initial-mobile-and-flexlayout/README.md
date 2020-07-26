# 前端开发分类
  * PC端开发
  * 移动端开发
    * 移动Web开发
      > 此课程讲的是移动Web开发
    * 原生app开发
      > ios android的原生应用用Object C java语言
    * 混合式开发(Hybrid App)
      > 在webview上运行，移动Web套了一个原生App的壳子
    * 微信小程序/公众号开发

# 分辨率
* 显示器1920*1080分辨率是什么意思?
* 手机屏幕 1792*828分辨率是什么意思? 
  > 就是说 纵向上有 1792 个点 / 横向上有 828 个点
  > 假设手机屏幕是 4 * 2分辨，就是8个点描述手机所有显示信息清楚呢 还是 1792* 828个点描述手机所有显示信息清楚呢？
# CSS像素和物理像素
  * 物理像素: 就是上面说的"点" 也叫"设备像素" 缩写dp
  * CSS像素：  (又叫逻辑像素，aip设备独立像素)
  * 他们有什么关系呢?
  * 1个CSS像素不管是标清屏还是高清屏大小是没有变化的，只不过用来显示CSS像素的"点"变多了
  * 开发中会使用CSS像素，浏览器会自动推算出一个CSS像素用几个"点"来描述
# 设备像素比(dpr)
  * dpr = 设备像素 / CSS像素(同一方向, 缩放比是1的情况下)
  * 假设标清屏上1个CSS像素对应1个"点(物理像素)" dpr = 1; 在高清屏上1个CSS像素对应2个"点(物理像素)" 那么 dpr = 2
  * dpr = 2 表示1个CSS像素使用2*2个设备像素来绘制
# 标清和高清屏
  * 什么是标清屏？什么高清屏
  * 标清屏 dpr = 1, 高清屏 dpr = 2 || > 2;
# 缩放
  * 缩放 - 放大：
    * 双击一下屏幕/两指缩放屏幕放大，缩放到底缩放的是什么东西？
    * 缩放改变的是CSS像素的大小，不变的是物理像素(设备像素)，缩放改变只是CSS像素对应的物理像素的数量
    * 以标清屏为例： 1个CSS像素 = 1个物理像素 (没有缩放的情况)
    * 缩放两倍之后, 1个CSS像素横向对应2个物理像素，纵向对应2个物理像素
    * 那么就是用4个物理像素像素1个CSS像素了, 视觉看就是放大了 
    * 那.. CSS像素 比 屏幕物理宽度就变了啊 原来是1/2显示，现在铺满整屏了
  * 缩放 - 缩小：
    * 以标清屏为例： 1个CSS像素 = 1个物理像素 (没有缩放的情况)
    * 缩小1/2之后, 2*2个CSS像素 = 1个物理像素
    * 那么就是1个物理像素显示了2*2个CSS像素了
    * 视觉上就是 原来是1/2显示，现在1/8显示了
  * 不管是放大还是缩小，物理像素是不会变化的
# PPI/DPI
  * 每英寸(inch)的物理像素点的数量
  * 也可以用dpi表示 每英寸的"点"  => 像素密度
  * PPI可以用计算出来的，对角线的长度可以根据width和height和勾股定理算出来 

# 视口(viewport)
  * 一个pc网页 width: 980px; 里面有一张手机图片 width: 375px;
  * chrome切成移动端显示的时候 就看不清了 980变成了375, 图片 原375,视觉上就缩放了的更小了(不出现横向滚动条的情况下)
  >  \<meta name="viewport" content="width=device-width, initial-scale=1">
  >  content="width=375 ..设置视口宽度
>  initial-scale=1"     初始缩放比例 maximum-scale=1, minimum-scale=1" 最大/最小 ==  user-scalable=no"
  * JS获取视口宽度(CSS物理像素)和dpr(设备像素比)
  ```js
        console.log(window.innerWidth);
        console.log(document.documentElement.clientWidth);
        console.log(document.documentElement.getBoundingClientRect().width);

        var viewWidth = document.documentElement.clientWidth || window.innerWidth;

        // 兼容性问题，不要用  有的浏览器获取到了居然是分辨率(物理像素) 那可定不行
        // console.log(screen.width);

        // dpr
        console.log(window.devicePixelRatio);
  ```
# box-sizing
  * box-sizing: content-box || border-box;
  * content-box  加了内边距向外扩展 总大小变了
  * border-box   加了内边距向内压缩 总大小不变
  * padding border 是一样的
  * content-box 描述的是宽高内容的宽高
  * border-box  描述的宽高是包括边框的的宽高
  * pc/mobile兼容性?

# 图标字体
  * 具有字体的特色和小图标的一些特性
  * why不继续使用图片呢? 大，改颜色得重做，放大失真(位图)， 字体文件矢量图可设置颜色
  * iconfont.cn
    * 车 添加入库(多个) => 添加项目 => 在线(css)/下载本地
      * demo.css..不要, 就拿iconfont.css以及4个字体文件
      * css里font-face引入字体文件 => 改一下字体文件路径
      * Unicode兼容IE6？
    * 星 
# flex布局
  * 容器属性
  * 项目属性

# 媒体查询
  * 策略
# 移动端单位