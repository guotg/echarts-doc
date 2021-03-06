
{{target: series-funnel}}

# series.funnel(Object)

**漏斗图**

**示例：**
~[600x400](${galleryViewPath}funnel&reset=1&edit=1)

## type(string) = 'funnel'

{{ use: partial-series-name() }}

## min(number) = 0
指定的数据最小值。

## max(number) = 100
指定的数据最大值。

## minSize(string) = '0%'
数据最小值 [min](~series-funnel.min) 映射的宽度。

可以是绝对的像素大小，也可以是相对[布局宽度](~series-funnel.width)的百分比，如果需要最小值的图形并不是尖端三角，可通过设置该属性实现。

## maxSize(string) = '100%'
数据最大值 [max](~series-funnel.max) 映射的宽度。

可以是绝对的像素大小，也可以是相对[布局宽度](~series-funnel.width)的百分比。

## sort(string) = 'descending'
数据排序， 可以取 `'ascending'`, `'descending'`。

## gap(number) = 0
数据图形间距。

{{ use: partial-legend-hover-link }}

## funnelAlign(string) = 'center'
水平方向对齐布局类型，默认居中对齐，可用选项还有：'left' | 'right' | 'center'

## label(Object)
{{use:partial-label-desc(name="漏斗图")}}
### normal(Object)
{{use:partial-funnel-label(
    prefix="###",
    position=true,
    formatter=true
)}}
### emphasis(Object)
{{use:partial-funnel-label(
    prefix="###",
    position=false,
    formatter=true
)}}

## labelLine(Object)
标签的视觉引导线样式，在 [label 位置](~series-funnel.label.normal.position) 设置为`'left'`或者`'right'`的时候会显示视觉引导线。
{{ use: partial-funnel-label-line(prefix='##') }}

## itemStyle(Object)
{{use:partial-item-style-desc}}
### normal(Object)
{{use:partial-item-style(
    prefix="###",
    useColorPalatte=true,
    hasCallback=true
)}}
### emphasis(Object)
{{use:partial-item-style(prefix="###")}}


{{ use: component-rect-layout-width-height(
    componentName="漏斗图",
    defaultLeft=80,
    defaultTop=60,
    defaultRight=80,
    defaultBottom=60
) }}


## data(Array)
{{ use: partial-1d-data-desc }}
### name(string)
数据项名称。
### value(number)
数据值。

### label(Object)
单个数据的标签配置。
#### normal(Object)
{{use:partial-funnel-label(
    prefix="####",
    position=true,
    formatter=false
)}}
#### emphasis(Object)
{{use:partial-funnel-label(
    prefix="####",
    position=false,
    formatter=false
)}}

### labelLine(Object)
{{ use: partial-funnel-label-line(prefix='###') }}

### itemStyle(Object)
{{use:partial-item-style-desc}}
#### normal(Object)
{{use:partial-item-style(prefix="####")}}
#### emphasis(Object)
{{use:partial-item-style(prefix="####")}}

{{use: partial-marker(
    prefix="#",
    galleryEditorPath=${galleryEditorPath},
    seriesType="funnel"
)}}

{{ use:partial-silent(
    prefix="#"
) }}

{{use:partial-animation(
    prefix="#",
    galleryEditorPath=${galleryEditorPath}
)}}




{{ target: partial-funnel-label }}
#${prefix} show(boolean) = false
{{ if: ${position} }}
#${prefix} position(string) = 'outside'
标签的位置。

**可选：**
+ `'left'`

    漏斗图左侧，通过[视觉引导线](~series-funnel.labelLine)连到相应的梯形。

+ `'right'`

    漏斗图右侧，通过[视觉引导线](~series-funnel.labelLine)连到相应的梯形。

+ `'inside'`

    漏斗图梯形内部。

+ `'inner'` 同 `'inside'`。
+ `'center'` 同 `'inside'`。

{{ /if }}
{{ if: ${formatter} }}
#${prefix} formatter(string|Function)
{{ use: partial-1d-data-label-formatter(extra = {
    percent: {
        desc: '百分比',
        type: 'number'
    }
}) }}
{{ /if }}
#${prefix} textStyle(Object)
标签的字体样式。
{{ use:partial-text-style(prefix=${prefix} + '#') }}


{{ target: partial-funnel-label-line }}
#${prefix} normal(Object)
普通状态下视觉引导线的样式。
##${prefix} show(boolean)
是否显示视觉引导线。
##${prefix} length(number)
视觉引导线第一段的长度。
##${prefix} lineStyle(Object)
{{use:partial-line-style(prefix="##" + ${prefix})}}
#${prefix} emphasis(Object)
高亮状态下视觉引导线的样式。
##${prefix} show(boolean)
是否显示视觉引导线。
##${prefix} lineStyle(Object)
{{use:partial-line-style(prefix="##" + ${prefix})}}


