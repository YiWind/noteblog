# 笔记记录

### rect形状 看起来是基于X轴向正Y轴或者负Y轴走的原理：
 - 看起来朝负Y轴走是因为全部都基于相同的一个Y轴的值。
 - 看起来朝正Y轴走是因为在Y轴相同的基础上减去了他们自身的高度。

### 缩放
 - v3：`var scale = d3.scale.linear();`
 - v4：`var scale = d3.scaleLinear();` 版本改变了
 - domain 输入范围的意思
 - range 输出范围的意思
```
scale.domain([100, 500]); 
scale.range([50, 250]);  // 输出范围缩小了1倍
```
缩放分析:
缩放的**domain**的*最大值*设置为**data**的*最大值*，
**range**的*最大值*设置为**可显示区域（比如屏幕）**的*最大值*，
这样data的每一个值就会跟可显示区域的位置**一一对应**。 
注意[0,maxw]和[maxw,0]是有区别的（反向）

### 获取dom节点
```javascript
var canvas = d3.select("canvas").node(),
context = canvas.getContext("2d"),
canvasWidth = canvas.width;
```

### d3.scaleQuantize 构建一个量化比例尺

