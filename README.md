# micro-touch

[![NPM version](https://img.shields.io/npm/v/micro-touch.svg)](https://www.npmjs.com/package/micro-touch)

Super basic mobile gesture support tool.   
NPM page: https://www.npmjs.com/package/micro-touch

# Installation

```
npm install micro-touch --save
```

# User Guide

```
import {TouchGesture} from "micro-touch";

tou = new TouchGesture(DOM);
let t2d = new Transform2D(tou.el)
// tou.on("tap", tap);
// tou.on("longTap", longTap);
// tou.on("doubleTap", doubleTap);
// tou.on("pressMove", function (e) {
//     let {moveDistance, startDistance} = e;
//     console.log(moveDistance, startDistance);
// });
tou.on("pinch", function (e) {
    let {pointAngle,startAngle,pointSpace,startSpace,scale,rotate} = e;
    t2d.setRotate(rotate);
})
```

# Note

传入一个DOM对象，对其进行方法监听

- new TouchGesture(DOM)
    
- on(gesture,callback) : 注册事件监听回调函数
    - 'tap' : 元素被单击
    - 'doubleTap' : 元素被双击
    - 'longTap' : 长按元素一秒
    - 'pressMove' : 移动元素
    - 'pinch' : 双指缩放或者旋转时触发
    - "tapDown" | "tapMove" | "tapUp" : 等同于touchstart，touchmove，touchend，但是拓展了事件属性

- off() : 取消注册的回调函数
- destroy() : 销毁注册实例
- interval(lastTime: number, duration: number = 500) : Promise对象判定给定时间是否和当前时间满足间隔
- getMove(p1: point, p2: point) : 获取两个点之间的距离对象
- getAngle(move: move) : 解析move对象，返回角度值（弧度制）
- getMiddlePoint(p1: point, p2: point) : 获取两个点之间的中点坐标
- radian2angle() : 弧度转角度
- angle2radian() : 角度转弧度


# Resources

You can read [micro-touch Documentation](https://github.com/SystemLight/micro-touch) online for more information.

# License

micro-touch uses the MIT license, see LICENSE file for the details.
