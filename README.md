# url-chart

Generate charts from simple urls via `chart.js`.
For example, the following URL:

> https://zhengxiaoyao0716.github.io/url-chart/?i=a,b,c&v=1,2,3

will be parsed as:

```js
import { Chart } from "https://cdn.jsdelivr.net/npm/chart.js@4.4.9/auto/+esm";

new Chart(container, {
  type: "bar",
  data: {
    labels: ["a", "b", "c"],
    datasets: [
      {
        label: "Label1",
        backgroundColor: "rgba(54, 162, 235, 0.5)",
        borderColor: "rgb(54, 162, 235)",
        data: ["1", "2", "3"],
      },
    ],
  },
  options: {},
});
```

---

## URL Params

Basic Params:

- t=TYPE  
  [config.type](https://www.chartjs.org/docs/latest/configuration/#type)
- i=INDEXES  
  [config.data.datasets.data](https://www.chartjs.org/docs/latest/general/data-structures.html#dataset-configuration)
- l=LABEL  
  [config.data.datasets.label](https://www.chartjs.org/docs/latest/general/data-structures.html#dataset-configuration)
- c=COLOR  
  [config.data.datasets.borderColor](https://www.chartjs.org/docs/latest/general/colors.html#per-dataset-color-settings)
- v=VALUES  
  [config.data.datasets.data](https://www.chartjs.org/docs/latest/general/data-structures.html#dataset-configuration)
- c.[override]=?  
  [config[override]](https://www.chartjs.org/docs/latest/configuration/)

Preset params:

- title=String  
  [config.options.plugins.title.text](https://www.chartjs.org/docs/latest/configuration/title.html)
- stacked=x|y|xy  
  [config.options.scales[x|y].stacked](https://www.chartjs.org/docs/latest/charts/bar.html#stacked-bar-chart)
- combo=String,String  
  [config.data.datasets[0].type](https://www.chartjs.org/docs/latest/samples/other-charts/combo-bar-line.html)  
  [config.options.scales[y0|y1]](https://www.chartjs.org/docs/latest/axes/#common-options-to-all-axes)

Other Params:

- dataHint=fontSize
- verbose=true

## Preset Colors

- #36A2EB // blue
- #FF6384 // red
- #FF9F40 // orange
- #FFCD56 // yellow
- #4BC0C0 // green
- #9966FF // purple
- #C9CBCE // grey

---

## Some more complete example:

Pie:

https://zhengxiaoyao0716.github.io/url-chart/?t=doughnut&i=a,b,c,d&v=40,30,20,10&title=Pie%20Example&dataHint=16&verbose=true

Combo:

https://zhengxiaoyao0716.github.io/url-chart/?i=a,b,c,d&l=TestLine&c=36a2eb&v=80,60,40,20&l=TestBarA&c=ff6384&v=1,2,3,4&l=TestBarB&c=4bc0c0&v=3,3,2,2&title=Combo%20Example&combo=Axis0,Axis1&dataHint=16&verbose=true

Stack:

https://zhengxiaoyao0716.github.io/url-chart/?t=bar&i=a,b,c&l=TestA&c=36a2eb&v=1,2,3&s=group&l=TestB&c=ff6384&v=2,2,3&s=group&l=TestC&c=4bc0c0&v=4,3,1&s=group&l=TestD&c=ff9f40&v=7,7,7&title=Stack%20Example&stacked=xy&c.data.datasets.3.stack=alone&c.options.indexAxis=y&verbose=true
