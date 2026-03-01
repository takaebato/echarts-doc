# option-gl

## globe
- **Type**: `Object`

地球组件。组件提供了地球的绘制以及相应的坐标系，开发者可以在上面展示三维的散点图、气泡图、柱状图、飞线图。

## geo3D
- **Type**: `Object`

三维的地理坐标系组件。组件提供了三维 GeoJSON 的绘制以及相应的坐标系，开发者可以在上面展示三维的散点图、气泡图、柱状图、飞线图。

## mapbox3D
- **Type**: `Object`

基于 mapbox-gl-js 的地理组件。支持在 mapbox 的地图上绘制三维的散点图，飞线图，柱状图和地图。你可以利用 Mapbox 强大的地图服务和 ECharts GL 丰富的可视化和渲染效果实现你想要的可视化作品。

在使用 mapbox 组件之前你需要先引入 mapbox 的官方 sdk。

```
<script src='https://api.mapbox.com/mapbox-gl-js/v0.38.0/mapbox-gl.js'></script>
<link href='https://api.mapbox.com/mapbox-gl-js/v0.38.0/mapbox-gl.css' rel='stylesheet' />
```

然后获取到 mapbox 提供的 token 后设置到 `mapbox.accessToken` 上。

```
mapboxgl.accessToken = '你的 token';
```

接下来你就可以像使用其它组件一样使用 mapbox 组件了。

```
chart.setOption({
    mapbox: {
        style: 'mapbox://styles/mapbox/dark-v9'
    }
});
```

可以前往 [https://www.mapbox.com/mapbox-gl-js/api/](https://www.mapbox.com/mapbox-gl-js/api/) 了解更详细的关于 mapbox-gl-js sdk 的内容。

## grid3D
- **Type**: `Object`

三维笛卡尔坐标系组件。需要和 [xAxis3D](#xAxis3D)，[yAxis3D](#yAxis3D)，[zAxis3D](#zAxis3D) 三个坐标轴组件一起使用。

可以在三维笛卡尔坐标系上绘制[三维折线图](#series-line3D)，[三维柱状图](#series-bar3D)，[三维散点/气泡图](#series-scatter3D)，[曲面图](#series-surface)。

你可以设置 [postEffect](#grid3D.postEffect), [light](#grid3D.light) 等配置项提升`grid3D`中三维图表的显示效果。

下面是 grid3D 中坐标轴配置项的说明。

![](documents/asset/gl/img/grid3D.png)

* * *

> **注意：** [xAxis3D](#xAxis3D)，[yAxis3D](#yAxis3D)，[zAxis3D](#zAxis3D) 上单独设置的 [axisLine](#xAxis3D.axisLine), [axisTick](#xAxis3D.axisTick), [axisLabel](#xAxis3D.axisLabel), [splitLine](#xAxis3D.splitLine), [splitArea](#xAxis3D.splitArea), [axisPointer](#xAxis3D.axisPointer)\` 会覆盖[grid3D](#grid3D) 下的相应配置项。

## xAxis3D
- **Type**: `Object`

三维笛卡尔坐标系中的 x 轴。可以通过 [grid3DIndex](#xAxis3D.grid3DIndex) 索引所在的[三维笛卡尔坐标系](#grid3D)。

在`xAxis3D`下设置的 [axisLine](#xAxis3D.axisLine), [axisTick](#xAxis3D.axisTick), [axisLabel](#xAxis3D.axisLabel), [splitLine](#xAxis3D.splitLine), [splitArea](#xAxis3D.splitArea), [axisPointer](#xAxis3D.axisPointer) 会覆盖 [grid3D](#grid3D) 下的相应配置项。

## yAxis3D
- **Type**: `Object`

三维笛卡尔坐标系中的 y 轴。可以通过 [grid3DIndex](#yAxis3D.grid3DIndex) 索引所在的[三维笛卡尔坐标系](#grid3D)。

在`yAxis3D`下设置的 [axisLine](#yAxis3D.axisLine), [axisTick](#yAxis3D.axisTick), [axisLabel](#yAxis3D.axisLabel), [splitLine](#yAxis3D.splitLine), [splitArea](#yAxis3D.splitArea), [axisPointer](#yAxis3D.axisPointer) 会覆盖 [grid3D](#grid3D) 下的相应配置项。

## zAxis3D
- **Type**: `Object`

三维笛卡尔坐标系中的 z 轴。可以通过 [grid3DIndex](#zAxis3D.grid3DIndex) 索引所在的[三维笛卡尔坐标系](#grid3D)。

在`zAxis3D`下设置的 [axisLine](#zAxis3D.axisLine), [axisTick](#zAxis3D.axisTick), [axisLabel](#zAxis3D.axisLabel), [splitLine](#zAxis3D.splitLine), [splitArea](#zAxis3D.splitArea), [axisPointer](#zAxis3D.axisPointer) 会覆盖 [grid3D](#grid3D) 下的相应配置项。

## series
- **Type**: `Array`

系列列表。每个系列通过 `type` 决定自己的图表类型。

echarts-gl 加入了丰富的三维可视化类型，包括 [三维柱状图 bar3D](#series.bar3D)，[三维散点图 scatter3D](#series.scatter3D)，[三维飞线 lines3D](#series.lines3D)，[曲面图 surface](#series.surface)，大部分可视化类型都能在多种坐标系组件中使用。而且与 echarts 原先的图例，tooltip 等交互组件有良好的集成。

同时,对原先的二维图表也进行了更多功能上的增强。例如，对于大量数据的散点图和关系图，你可以使用 echarts-gl 中提供的 [scatterGL](#series.scatterGL)，[graphGL](#series.graphGL) 加速绘制和运算。

## series-scatter3D
- **Type**: `Object`

三维散点/气泡图。可以用于[三维直角坐标系 grid3D](#grid3D)，[三维地理坐标系 geo3D](#geo3D)，[地球 globe](#globe)，通过大小，颜色等属性展示数据。

下图示一个三维的 simplex noise 用气泡图绘制出来的例子。

![](documents/asset/gl/img/scatter3D.png)

## series-bar3D
- **Type**: `Object`

三维柱状图。可以用于[三维直角坐标系 grid3D](#grid3D)，[三维地理坐标系 geo3D](#geo3D)，[地球 globe](#globe)，通过高度，颜色等属性展示数据。

下图就是在 [geo3D](#geo3D) 上通过三维柱状图展示世界的人口密度数据。

![](documents/asset/gl/img/geo-bar3D.jpg)

## series-line3D
- **Type**: `Object`

三维折线图。可以用于[三维直角坐标系 grid3D](#grid3D)。

![](documents/asset/gl/img/line3D.png)

## series-lines3D
- **Type**: `Object`

三维的飞线图。跟二维的[飞线图](https://echarts.apache.org/zh/option.html#series-line)一样用于表现起点终点的线数据。更多用在地理可视化上。

下图是使用 [lines3D](#series-lines3D) 在 [globe](#globe) 上可视化飞机航班的一个例子。

![](documents/asset/gl/img/globe-airline.png)

## series-map3D
- **Type**: `Object`

**三维地图**

三维地图主要用于地理区域数据的可视化，配合 [visualMap](https://echarts.apache.org/zh/option.html#visualMap) 组件用于展示不同区域的人口分布密度等数据。

相比于二维的地图，三维地图还能每个区域设置不同的高度，这个高度能够用来展示数据，也能够用来显示建筑数据中建筑的高度。

## series-surface
- **Type**: `Object`

曲面图。支持通过 [parametric](#series-surface.parametric) 绘制[参数曲面](https://en.wikipedia.org/wiki/Parametric_surface)。

下图就是一个配置成金属材质的类似一个金属零件的参数曲面。

![](documents/asset/gl/img/parametric-surface.png)

## series-polygons3D
- **Type**: `Object`

`polygons3D` 用于可视化地图上带有高度信息的多边形数据，常用于建筑群的绘制。下图就是用`polygons3D`绘制的近 50w 数量的纽约建筑群。

![](documents/asset/gl/img/polygons3D-ny.jpg)

## series-scatterGL
- **Type**: `Object`

使用 WebGL 绘制的二维散点/气泡图。

使用方式同 [scatter](https://echarts.apache.org/zh/option.html#series-scatter)。

## series-graphGL
- **Type**: `Object`

使用 WebGL 绘制的关系图，支持大规模的网络/关系数据的布局和绘制。

## series-flowGL
- **Type**: `Object`

`flowGL` 组件通过 WebGL 实现的粒子效果可视化向量场的迹线。

下图是全球的风场通过`flowGL`可视化后的效果。

![](documents/asset/gl/img/flowGL-wind.jpg)
