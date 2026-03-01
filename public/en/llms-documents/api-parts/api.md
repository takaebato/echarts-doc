# api

## echarts
- **Type**: `Object`

Global echarts object, which can be accessed after including `echarts.js` in script tag or through `require('echarts')` in AMD environment.

## echartsInstance
- **Type**: `Object`

Instance created through [echarts.init](#echarts.init).

## action
- **Type**: `*`

Chart actions supported by ECharts are triggered through [dispatchAction](#echartsInstance.dispatchAction).

**Attention:** The `?:` note in the code shows that this attribute is optional. _EVENT:_ stands for the event that triggers action.

## events
- **Type**: `*`

Event-handling functions are mainly added through [on](#echartsInstance.on) in ECharts. This document describes all event list in ECharts.

Event in ECharts can be divided in two kinds. One is mouse event, which is triggered when mouse clicks on certain component, the other is triggered after dispatches [dispatchAction](#echartsInstance.dispatchAction).

**For example:**

```
myChart.on('click', function (params) {
    console.log(params);
});

myChart.on('legendselectchanged', function (params) {
    console.log(params);
});

chart.on('click', 'series.line', function (params) {
    console.log(params);
});

chart.on('mouseover', {seriesIndex: 1, name: 'xx'}, function (params) {
    console.log(params);
});
```

See [on](#echartsInstance.on) for more detailed info.
