# css3-review
Review the key points of CSS3


## 一、background背景设置

```
/* background-origin设置图片从哪里开始显示 */

/* 图片从padding左上角开始显示的 */
/* background-origin: padding-box; */
/* 图片从border左上角开始显示 */
/* background-origin: border-box; */
/* 图片从content左上角开始显示 */
background-origin: content-box;


/* background-clip设置图片显示结束的位置 */

/* 图片显示到padding结束 */
/* background-clip: padding-box; */
/* 图片显示到border结束 */
/* background-clip: border-box; */
/* 图片显示到content结束 */
background-clip: content-box;

/* background-size设置背景图大小 */

/* 图片保持高宽比，并纵向铺满 */
/* background-size: cover; */
/* 图片保持高宽比，并横向铺满 */
/* background-size: contain; */
/* 图片显示百分比，横向 纵向 */
/* background-size: 100% 100%; */
/* 图片显示绝对值，第一个参数为横向，第二个为纵向。第二个不传则为auto，auto表示保持高宽比铺开。 */
background-size: 100px 200px;
```

## 二、border-radius边框圆角及阴影

```
/* border-radius设置圆角 */

/* 直接设置四个角的值 */
/* border-radius: 50px; */

/* 按顺时针顺序，从左上开始逐一设置圆角 */
border-radius: 10px 20px 30px 40px;

/* 传入2个参数，第一个表示左上和右下，第二个表示左下和右上 */
border-radius: 10px 30px;

/* 传入3个参数，第一个表示左上，第二个表示左下和右上，第三个表示右下 */
border-radius: 10px 20px 30px;

/* 合阴影box-shadow: h-shadow v-shadow blur spread color inset; */

/* 可传入多套参数，显示多重阴影 */
/*
  h-shadow	必需的。水平阴影的位置。允许负值
  v-shadow	必需的。垂直阴影的位置。允许负值
  blur	可选。模糊距离
  spread	可选。阴影的大小
  color	可选。阴影的颜色。在CSS颜色值寻找颜色值的完整列表
  inset	可选。从外层的阴影（开始时）改变阴影内侧阴影 
*/
box-shadow: 10px 20px 5px 10px blue inset, 20px 10px 10px 5px red ;
```

## 三、border-image边框的图片设置

```
/* border-image: source slice width outset repeat|initial|inherit; 设置边框显示图片 */

/* border-image-source引入边框图片 */
border-image-source: url("border.png");


/* border-image-slice: number|%|fill; */

/* fill表示将引入的图片完整显示在边框四角 */
/* border-image-slice: fill; */

/* border-image-slice 表示边框显示占图片的宽度 */
/* 值为数字时，即要显示的部分实际的宽度，值的数量和分布同margin */
border-image-slice: 360 320 250 300;

/* 值为百分比时，即要显示的部分在原图的百分比，值的数量和分布同margin */
/* border-image-slice: 5% 10% 15% 20%; */


/* border-image-width: px|number|%|auto; 图片的宽度，数字表示比例 */
border-image-width: 10px 20px 30px 40px;
/* border-image-width: 0.5 1 1.5 2; */
/* border-image-width: 10% 20% 30% 40%; */


/* border-image-outset 图片超出边框的距离，支持px和Number，Number表示与border宽度的比例 */

border-image-outset: 10px 20px 30px 40px;
/* border-image-outset: 0 0.5 1 2; */


/* border-image-repeat: stretch|repeat|round|initial|space|inherit;; */

/* 四条边的图片会被拉伸 */
/* border-image-repeat: stretch; */

/* 图片平铺，若图片无法完整显示，则会被裁剪 */
/* border-image-repeat: repeat; */

/* 图片平铺，若图片无法完整显示，则会自动缩放 */
border-image-repeat: round;

/* 图片平铺，若图片无法完整显示，则只显示四个角，其余空白 */
/* border-image-repeat: space; */
```

## 四、text-shadow文本阴影

```
/* text-shadow: h-shadow v-shadow blur color; 水平方向，垂直方向，阴影的模糊度，阴影的颜色 */
text-shadow: 5px 5px 5px red;
```

## 五、属性选择器

```
/* 与p拥有共同父级，并在p之后的所有ul */
p~ul{
  background-color: green;
}

/* 与p拥有共同父级，并在p之后的所有ul */
p+ul{
  background-color: pink;
}


/* 属性选择器，可参考正则表达式来理解 */
/* 查找a标签中具有href属性，且属性值以P开头的标签 */
a[href^="P"]{
  background-color: yellow;
}
/* 查找的a标签中具有href属性，且属性值以mp4结尾的标签 */
a[href$="mp4"]{
  background-color: deeppink;
}
/* 查找具有href属性，并且值包含l的标签 */
a[href*="l"]{
  background-color: black;
}
```

## 六、其他选择器

```
/*目标选择器，点击a，找到id为four的p标签，找到后改变背景颜色*/
p:target{
  background-color: orangered;
}

/*设置选中的内容后，改变背景颜色*/
p::selection{
  background-color: yellow;
}


/* 为非p标签设置属性 */
:not(p) {
  border: 1px solid green;
}


div{
  width: 200px;
  height: 150px;
  border: 3px solid red;
}

/*设置第一个文字的样式*/
div:first-letter{
  font-size: 30px;
  color: yellow;
}

/*设置第一行的文字样式*/
div:first-line{
  background-color: green;
}
```

## 七、结构伪类选择器

```
/* 所有的li中的第一个 */
li:first-child{
  background-color: green;
}
/* 最后一个li */
li:last-child{
  background-color: yellow;
}
/* 第三个li */
li:nth-child(3){
  background-color: orange;
}
/* 倒数第五个li */
li:nth-last-child(5){
  background-color: red;
}
/* 选择奇数或偶数标签，odd为奇数，even偶偶数 */
li:nth-child(odd){
  background-color: blue;
}
```

## 八、linear-gradient线性渐变和径向渐变

```
/* background: linear-gradient(direction, color-stop1, color-stop2, ...); 线性渐变 */
/* 渐变方向，每一步渐变的颜色（支持px和%），若两步的颜色相同，则不会渐变，形成单色的环 */
/* background-image: linear-gradient(to right,yellow,green); */
/* background-image: linear-gradient(90deg,yellow,green); */

background-image: linear-gradient(
  to left,
  /* to left top, */
  /* 135deg, */
  red 20%,
  green 40%,
  blue 60%,
  pink 80%
);


/* background-image: linear-gradient(
  135deg,
  red 20%,
  green 20%,
  green 40%,
  blue 40%,
  blue 60%,
  pink 60%,
  pink 80%
); */
}


/* 径向渐变 */
.cls{
width: 300px;
height: 300px;
border: 1px solid red;
margin: 50px auto;
border-radius: 50%;
/* 显示渐变的半径，原点位置，每一步渐变的颜色（支持px和%），若两步的颜色相同，则不会渐变，形成单色的环 */
/* background-image: radial-gradient(100px at center,red,green); */
/* background-image: radial-gradient(100px at 10px 150px,red,green); */


background-image: radial-gradient(
  150px at center,
  red 10%,
  green 10%,
  green 20%,
  yellow 20%,
  yellow 30%,
  pink 30%,
  pink 40%,
  blue 40%,
  blue 50%,
  orange 50%,
  orange 60%,
  yellowgreen 60%,
  yellowgreen 70%,
  Aqua 70%,
  Aqua 80%,
  Aquamarine 80%,
  Aquamarine 90%,
  LightPink 90%,
  LightPink 100%
);
```

## 九、transform-2D转换

```
/* transform 用于设置元素的2d和3d转换，默认为2d */

/* translate(x, y) 元素相对于原来的位置的偏移 */
/* transform: translate(-100px); */
/* transform: translate(100px, 100px); */

/* rotate(angle) 元素相对于z轴旋转 */
/* transform: rotate(60deg); */

/* scale(x[,y]?) 缩小和放大，宽是原来的1.5倍，高是原来0.5倍 */
/* transform: scale(1.5, 0.5); */

/* skew(x-angle,y-angle)相对x轴倾斜30deg，也相对y轴倾斜30deg */
/* transform: skew(30deg, 30deg); */

/* transform 属性的简写形式 */
transform: translate(100px, 100px) rotate(60deg) scale(1.5, 0.5) skew(30deg, 30deg);
```

## 十、transform-3D转换

```
.box {
  width: 600px;
  height: 500px;
  background-color: pink;
  margin: 100px auto 0;

  /* perspective: number|none; 元素与视图的距离，即z=0的距离，为正则在屏幕外部。需要设置在父级元素中。 */
  /* perspective不可为负，为负则在屏幕内部，即无法被观察。 */
  perspective: 1000px;
}

.cls {
  width: 100px;
  height: 100px;
  background-color: green;
  font-size: 36;
  line-height: 100px;
  text-align: center;
  margin: 0 auto;

  /* transform-style: flat|preserve-3d; 设置transform属性显示为2d或3d。 */
  transform-style: preserve-3d;
}

.box:hover .cls {
  /* translate3d(x,y,z) 设置x、y、z轴的偏移，也可分3个轴书写 */
  /* transform: translate3d(50px, 100px, 150px); */
  /* transform: translateX(100px); */
  /* transform: translateY(100px); */
  /* transform: translateZ(100px); */

  /* rotate3d(x,y,z,angle) 设置x、y、z轴的旋转，也可分3个轴书写 */
  /* 参考 https://developer.mozilla.org/zh-CN/docs/Web/CSS/transform-function/rotate3d */
  /* transform: rotate3d(1, 0, 0, 90deg); */
  /* transform: rotateX(30deg); */
  /* transform: rotateY(30deg); */
  /* transform: rotateZ(30deg); */

  /* scale3d(x,y,z) 设置x、y、z轴的缩放，也可分3个轴书写 */
  transform: scale3d(2, 2, 2);
  /* transform: scaleX(2); */
  /* transform: scaleY(2); */
  /* scaleZ参考 https://developer.mozilla.org/zh-CN/docs/Web/CSS/transform-function/scaleZ */
  /* transform: scaleZ(2); */

  /* skew(x-angle,y-angle)相对x轴倾斜30deg，也相对y轴倾斜30deg */
  /* transform: skew(30deg, 30deg); */
  /* transform: skewX(30deg); */
  /* transform: skewY(30deg); */
}
```

## 十一、transition过渡

```
/* 过渡就是设定元素的开始和结束状态，以及动画的延迟、持续时间、动画速度曲线后，中间过程由浏览器自动处理形成的动画。 */
    .cls{
      width: 200px;
      height: 200px;
      background-color: green;

      /* transition: property duration timing-function delay; 过渡属性，执行一次性的过渡动画 */

      /* transition-property 需要过渡的属性，all表示所有属性 */
      transition-property: all;
      
      /* transition-duration 执行动画的时间 */
      transition-duration: 2s;
      
      /* transition-timing-function 动画执行速度曲线，支持linear|ease|ease-in|ease-out|ease-in-out|cubic-bezier(n,n,n,n) */
      transition-timing-function: linear;

      /* transition-delay 延迟执行动画的时间 */
      transition-delay: 1s;
    }
    .cls:hover{
      width: 300px;
      height: 300px;
      background-color: red;
    }
```

## 十二、animation动画

```
.box{
  width: 0;
  height: 0;
  border-left: 100px dashed red;
  border-top: 100px dashed green;
  border-right: 100px dashed blue;
  border-bottom: 100px dashed orange;
  border-radius: 50%;

  /* animation: name duration timing-function delay iteration-count direction fill-mode play-state; */

  /* animation-name 绑定动画的@keyframes名 */
  animation-name: rotate;

  /* animation-duration 动画持续时间 */
  animation-duration: 1s;

  /* animation-timing-function 动画执行速度曲线，支持linear|ease|ease-in|ease-out|ease-in-out|cubic-bezier(n,n,n,n) */
  animation-timing-function: linear;

  /* animation-delay 延迟执行动画的时间 */
  animation-delay: 0s;

  /* animation-iteration-count 动画执行次数，infinite为无限次 */
  animation-iteration-count: 3;

  /* animation-direction: normal|reverse|alternate|alternate-reverse|initial|inherit; */
  /* normal	默认值。动画按正常播放。	测试 » */
  /* reverse	动画反向播放。	测试 » */
  /* alternate	动画在奇数次（1、3、5...）正向播放，在偶数次（2、4、6...）反向播放。 */
  /* alternate-reverse	动画在奇数次（1、3、5...）反向播放，在偶数次（2、4、6...）正向播放。 */
  animation-direction: alternate;

  /* animation-fill-mode: none|forwards|backwards|both|initial|inherit; */
  /* 设置为forwards时，动画完成后会停留在停止状态不会返回初始状态。 */
  /* 参考 https://www.w3cplus.com/css3/css-animation-fill-mode-property.html */
  /* none	默认值。动画在动画执行之前和之后不会应用任何样式到目标元素。 */
  /* forwards	在动画结束后（由 animation-iteration-count 决定），动画将应用该属性值。 */
  /* backwards	动画将应用在 animation-delay 定义期间启动动画的第一次迭代的关键帧中定义的属性值。这些都是 from 关键帧中的值（当 animation-direction 为 "normal" 或 "alternate" 时）或 to 关键帧中的值（当 animation-direction 为 "reverse" 或 "alternate-reverse" 时）。 */
  /* both	动画遵循 forwards 和 backwards 的规则。也就是说，动画会在两个方向上扩展动画属性。 */
  /* animation-fill-mode: none; */
  animation-fill-mode: forwards;
  /* animation-fill-mode: backwards; */
  /* animation-fill-mode: both; */
  /* animation-fill-mode: initial; */
}

.box:hover{
  /* 将动画状态修改为暂停 */
  animation-play-state: paused;
}

/*定义一个动画集   这个动画的名字就是:rotate*/
@keyframes rotate {
  from{
    /*开始状态*/
    transform: rotateZ(90deg);
  }
  to{
    /*动画的状态*/
    transform: rotateZ(180deg);
  }
}


@keyframes rotate2 {
  0%{
    /*开始状态*/
    transform: rotateZ(30deg);
  }
  20%{
    /*动画的状态*/
    transform: rotateZ(60deg);
  }
  80%{
    /*动画的状态*/
    transform: rotateZ(90deg);
  }
  100%{
    transform: rotateZ(120deg);
  }
}
```

## 十三、flex弹性布局父元素属性

```
.box{
  width: 400px;
  height: 400px;
  border: 1px solid red;

  /* 将父级元素设置为display: flex; 则开启弹性布局 */
  /* 参考 http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html */
  display: flex;

  /* justify-content: flex-start|flex-end|center|space-between|space-around|initial|inherit; */
  /* 子元素在主轴（默认为横轴）的方向的对齐的方式的设置 */
  /* flex-start	默认值。子元素布局在主轴头部。 */
  /* flex-end	子元素布局在主轴尾部。 */
  /* center	子元素居中。 */
  /* space-between	子元素均匀分布在容器内，子元素之间保持均匀的间距，头尾元素贴紧容器边缘。 */
  /* space-around	子元素均匀分布在容器内，子元素之间保持均匀的间距，头尾元素与边缘保持1/2元素间距。 */

  /* justify-content: flex-start; */
  /* justify-content: flex-end; */
  /* justify-content: center; */
  /* justify-content: space-between; */
  /* justify-content: space-around; */


  /* align-items: stretch|center|flex-start|flex-end|baseline|initial|inherit; 侧轴对齐方式 */
  /* stretch	默认值。子元素在侧轴方向被拉伸到100%。此时不可设置侧轴的长度值，即'min/max-width/height'值。 */
  /* center	子元素在侧轴居中显示。 */
  /* flex-start	子元素位于侧轴头部。 */
  /* flex-end	子元素位于侧轴尾部。 */
  /* baseline	以子元素第一行文字的基线对齐。 */

  /* align-items: stretch; */
  /* align-items: center; */
  /* align-items: flex-start; */
  /* align-items: flex-end; */
  align-items: baseline;


  /* flex-flow: flex-direction flex-wrap|initial|inherit; flex-flow属性是flex-direction属性和flex-wrap属性的简写形式，默认值为row nowrap。 */

  /* flex-direction: row|row-reverse|column|column-reverse|initial|inherit; 主轴方向调整 */
  /* row	默认值，即主轴为横轴。 */
  /* row-reverse	以横轴为主轴，但方向相反，为从右到左。即元素从右到左依次排列。 */
  /* column	将主轴改为纵轴。 */
  /* column-reverse	以纵轴为主轴，但方向相反，为从下到上。即元素从下到上依次排列。 */

  /* flex-direction: row; */
  /* flex-direction: row-reverse; */
  /* flex-direction: column; */
  /* flex-direction: column-reverse; */

  /* flex-wrap: nowrap|wrap|wrap-reverse|initial|inherit; */
  /* nowrap	默认值。子元素不换行，若子元素宽度之和超过父元素，则自动缩小子元素宽度。 */
  /* wrap	保持子元素设定的宽度，若子元素宽度之和超过父元素，则进行换行。 */
  /* wrap-reverse	保持子元素设定的宽度，若子元素宽度之和超过父级元素，则进行换行。
      元素从父元素的最后一行开始，方向排列，但子元素之间的顺序还是按照主轴方向排列。 */

  /* flex-wrap: nowrap; */
  flex-wrap: wrap;
  /* flex-wrap: wrap-reverse; */

  /* align-content: stretch|center|flex-start|flex-end|space-between|space-around|initial|inherit; */
  /* 该属性在设置了flex-wrap: wrap;时，才起作用。 */
  /* stretch	默认值。将元素拉伸，效果与align-items: stretch;相同 */
  /* center 将元素都集中在父元素的中部显示，而align-items: center;是将父元素分割成多行，子元素在每行居中显示。 */
  /* flex-start 将子元素都集中在父元素头部显示，而align-items: flex-start;是将父元素分割成多行，子元素在每行头部显示。 */
  /* flex-end 将子元素都集中在父元素尾部显示，而align-items: flex-end;是将父元素分割成多行，子元素在每行尾部显示。 */
  /* space-between 效果同justify-content: space-between;，但是以侧轴排列。
      子元素均匀分布在容器内，子元素之间保持均匀的间距，头尾元素贴紧容器边缘。 */
  /* space-around 效果同justify-content: space-around;，但是以侧轴排列。
      子元素均匀分布在容器内，子元素之间保持均匀的间距，头尾元素与边缘保持1/2元素间距。 */

  /* align-content: stretch; */
  /* align-content: center; */
  /* align-content: flex-start; */
  /* align-content: flex-end; */
  /* align-content: space-between; */
  /* align-content: space-around; */
}

.dv {
  width: 100px;
  height: 100px;
}
.dv1{
  /* align-item: stretch;时，不可设置高度。 */
  background-color: red;
}
```

## 十四、flex弹性布局子元素属性

```
.box{
  width: 400px;
  height: 400px;
  border: 1px solid red;
  display: flex;/*设置为可伸缩的父级元素*/
  flex-wrap: wrap;
}
.dv1{
  width: 100px;
  height: 100px;
  background-color: red;

  /* 参考 http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html */

  /* order 定义子元素排列顺序，越小越靠前。 */
  /* order: 2; */

  /* flex: flex-grow flex-shrink flex-basis|auto|initial|inherit; */
  /* flex: 1 1 auto; */

  /* flex-grow 规定各元素之间的相对比例，若某元素为2，其他元素为1，则该元素宽度为其他元素2倍。 */
  flex-grow: 1;
  
  /* flex-shrink 定义了在元素占满父元素时，若宽度小于元素原始设置宽度时，元素的缩放比例。
      为0则表示元素保持设定的宽度（为flex-basis的值，若flex-basis设置为auto，则为元素本身的宽或高）不进行缩小。 */
  flex-shrink: 1;

  /* flex-basis 定义了各元素在按照flex-grow值分配空间之后，比其他元素多占用的空间值。
      例如按flex-grow分配空间之后，每个元素占用100px，而该元素会占用200px。 */
  flex-basis: auto;
  /* flex-basis: 150px; */

  /* align-self: auto|stretch|center|flex-start|flex-end|baseline|initial|inherit; */
  /* 设置单个元素的对齐方式，效果同align-items。 */
  /* align-self: auto; */
  /* align-self: stretch; */
  align-self: center;
  /* align-self: flex-start; */
  /* align-self: flex-end; */
  /* align-self: baseline; 在设置了flex-wrap: wrap;时才有效果。 */
  /* align-self: baseline; */
}
```
