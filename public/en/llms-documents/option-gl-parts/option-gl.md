# option-gl

## globe
- **Type**: `Object`

Globe component. The component provides the drawing of the Earth and the coordinate system. The developer can display 3D Scatter, 3D Bubble, 3D Bar, 3D Lines on it.

## geo3D
- **Type**: `Object`

A 3D geographic coordinate system component. The component can draw a 3D GeoJSON and coordinate system. Developers can display 3D Scatter, 3D Bubble, 3D Bar, 3D Lines on it.

## mapbox3D
- **Type**: `Object`

A geographic component based on mapbox-gl-js. Support for drawing [3D Scatter](#series-scatter3D), [3D Lines](#series-lines3D), [3D Bar](#series-bar3D), [3D map](#series-map3D) on mapbox maps. You can take advantage of Mapbox's powerful map service and ECharts GL's rich visualization and rendering effects to achieve the visualization you want.

You need to introduce the official sdk of mapbox before using the mapbox component.

```
<script src='https://api.mapbox.com/mapbox-gl-js/v0.38.0/mapbox-gl.js'></script>
<link href='https://api.mapbox.com/mapbox-gl-js/v0.38.0/mapbox-gl.css' rel='stylesheet' />
```

Then get the token provided by mapbox and set it to `mapbox.accessToken`.

```
mapboxgl.accessToken = 'your token';
```

Then you can use the mapbox component just like any other component.

```
chart.setOption({
    mapbox: {
        style: 'mapbox://styles/mapbox/dark-v9'
    }
});
```

Go to [https://www.mapbox.com/mapbox-gl-js/api/](https://www.mapbox.com/mapbox-gl-js/api/) for more details on `mapbox-gl-js sdk`.

## grid3D
- **Type**: `Object`

3D cartesian coordinate system component. It requires [xAxis3D](#xAxis3D), [yAxis3D](#yAxis3D)and [zAxis3D](#zAxis3D) axis components to be used together.

You can draw [3D Lines](#series-line3D), [3D Bar](#series-bar3D), [3D Scatter](#series-scatter3D), [surface](#series-surface) on the 3D Cartesian coordinate system.

You can set the [postEffect](#grid3D.postEffect), [light](#grid3D.light) and other configuration items to improve the display of 3D charts in `grid3D`.

Below is a description of the axis configuration items in grid3D.

![](documents/asset/gl/img/grid3D.png)

* * *

**Note：** The [axisLine](#xAxis3D.axisLine), [axisTick](#xAxis3D.axisTick), [axisLabel](#xAxis3D.axisLabel), [splitLine](#xAxis3D.splitLine), [splitArea](#xAxis3D.splitArea), [axisPointer](#xAxis3D.axisPointer) set separately on [xAxis3D](#xAxis3D), [yAxis3D](#yAxis3D), [zAxis3D](#zAxis3D) will cover the corresponding configuration items under [grid3D](#grid3D).

## xAxis3D
- **Type**: `Object`

The X-axis in a 3D cartesian coordinate system. You can use [grid3DIndex](#xAxis3D.grid3DIndex) to index [3D cartesian coordinate system](#grid3D).

The [axisLine](#xAxis3D.axisLine), [axisTick](#xAxis3D.axisTick), [axisLabel](#xAxis3D.axisLabel), [splitLine](#xAxis3D.splitLine), [splitArea](#xAxis3D.splitArea), [axisPointer](#xAxis3D.axisPointer) set separately on [xAxis3D](#xAxis3D) will cover the corresponding configuration items under [grid3D](#grid3D).

## yAxis3D
- **Type**: `Object`

The Y-axis in a 3D cartesian coordinate system. You can use [grid3DIndex](#yAxis3D.grid3DIndex) to index [3D cartesian coordinate system](#grid3D).

The [axisLine](#yAxis3D.axisLine), [axisTick](#yAxis3D.axisTick), [axisLabel](#yAxis3D.axisLabel), [splitLine](#yAxis3D.splitLine), [splitArea](#yAxis3D.splitArea), [axisPointer](#yAxis3D.axisPointer) set separately on [yAxis3D](#yAxis3D) will cover the corresponding configuration items under [grid3D](#grid3D).

## zAxis3D
- **Type**: `Object`

The Z-axis in a 3D cartesian coordinate system. You can use [grid3DIndex](#zAxis3D.grid3DIndex) to index [3D cartesian coordinate system](#grid3D).

The [axisLine](#zAxis3D.axisLine), [axisTick](#zAxis3D.axisTick), [axisLabel](#zAxis3D.axisLabel), [splitLine](#zAxis3D.splitLine), [splitArea](#zAxis3D.splitArea), [axisPointer](#zAxis3D.axisPointer) set separately on [zAxis3D](#zAxis3D) will cover the corresponding configuration items under [grid3D](#grid3D).

## series
- **Type**: `Array`

Series list. Each series decides its diagram type through `type`.

ECharts-gl adds a rich 3D visualization type. Including \[3D bar\] (~series.bar3D), \[3D scatter\] (~series.scatter3D), \[3D lines\] (~series.lines3D), \[surface\] (~series. Surface), Most visualization types can be used in a variety of coordinate system components, and are well integrated with the original echarts legend, tooltip, and other interactive components.

At the same time, more functional enhancements have been made to the original 2D chart. For example, for scatter chart and diagrams of large amounts of data, you can use [scatterGL](#series.scatterGL), [graphGL](#series.graphGL) provided in echarts-gl to speed up drawing and operations.

## series-scatter3D
- **Type**: `Object`

3D scatter chart. It can be used to display data in [grid3D](#grid3D), [geo3D](#geo3D), [globe](#globe) using attributes such as size、color and so on.

This example is a 3D simplex noise drawn with a bubble chart.

![](documents/asset/gl/img/scatter3D.png)

## series-bar3D
- **Type**: `Object`

3D bar. It can be used to display data in [grid3D](#grid3D), [geo3D](#geo3D), [globe](#globe) using attributes such as size 、color and so on.

The figure below shows the population density data of the world through a 3D bar chart on \[geo3D\] (~geo3D).

![](documents/asset/gl/img/geo-bar3D.jpg)

## series-line3D
- **Type**: `Object`

3D Line. Can be used for \[grid3D\] (~grid3D)

![](documents/asset/gl/img/line3D.png)

## series-lines3D
- **Type**: `Object`

3D lines. Like the 2D \[lines\] ([https://echarts.apache.org/zh/option.html#series-line)](https://echarts.apache.org/zh/option.html#series-line\)), it is used to represent the line data from the start point to the end point. More is used in geographic visualization.

Below is an example of a visual airplane flight using [lines3D](#series-lines3D) on [globe](#globe).

![](documents/asset/gl/img/globe-airline.png)

## series-map3D
- **Type**: `Object`

**3D map**

3D maps are mainly used for visualizing geographic area data. With the \[visualMap\] ([https://echarts.apache.org/en/option.html#visualMap](https://echarts.apache.org/en/option.html#visualMap)) component, it can be used to display data such as population distribution density in different regions.

Compared to 2D maps, 3D maps can set different heights for each area. This height can be used to display data and to display the height of the building in the building data.

## series-surface
- **Type**: `Object`

Surface. Support to drawn the \[Parameter surface\] ([https://en.wikipedia.org/wiki/Parametric\_surface](https://en.wikipedia.org/wiki/Parametric_surface)) by [parametric](#series-surface.parametric).

The figure below is a parametric surface similar to a metal part configured as a metal material.

![](documents/asset/gl/img/parametric-surface.png)

## series-polygons3D
- **Type**: `Object`

`polygons3D` is used to visualize polygon data with high information on the map, which is often used for drawing of buildings. The picture below shows the nearly 50w number of New York buildings drawn with `polygons3D`.

![](documents/asset/gl/img/polygons3D-ny.jpg)

## series-scatterGL
- **Type**: `Object`

A 2D scatter/bubble plot drawn using WebGL.

It is used in the same way as [scatter](https://echarts.apache.org/en/option.html#series-scatter).

## series-graphGL
- **Type**: `Object`

Uses WebGL to drawn the relational chart, support the layout and rendering of large-scale network/relational data.

## series-flowGL
- **Type**: `Object`

The `flowGL` component visualizes the traces of the vector field through the particle effects implemented by WebGL.

The figure below shows the effect of the global wind field visualized by `flowGL`.

![](documents/asset/gl/img/flowGL-wind.jpg)
