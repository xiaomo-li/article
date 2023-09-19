# echarts 地图详解

## 获取地图数据

[阿里云数据可视化平台](https://datav.aliyun.com/portal/school/atlas/area_selector)
[可获取乡镇数据的开源库 AreaCity-JsSpider-StatsGov](https://github.com/xiangyuecn/AreaCity-JsSpider-StatsGov)

## 引入图片的方式

```js
// 方式一
'symbol': 'image://' + require("../../assets/tunnels.png")

'itemStyle': {
            color: require("./image/位图.png"), //地区颜色
            opacity: 1,
            borderWidth: 0,
            borderColor: "#98F9FF00",
            }
// 方式二
import tunnels from '@/assets/tunnels.png'


========================================
  data () {
    return {
      tunnels
    }
  },
=========================================

 'symbol': 'image://' + tunnels


```

## echarts 地图参数

## echarts map 添加纹理

[多个不同纹理](https://blog.csdn.net/u012169821/article/details/116107536?spm=1001.2101.3001.6661.1&utm_medium=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7ERate-1-116107536-blog-129811199.235%5Ev38%5Epc_relevant_default_base&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7ERate-1-116107536-blog-129811199.235%5Ev38%5Epc_relevant_default_base&utm_relevant_index=1)

## 扩展插件

[awesome-echarts](https://github.com/ecomfe/awesome-echarts)
