---
title: mpath
slug: Web/SVG/Element/mpath
---
{{SVGRef}}

{{ SVGElement("animateMotion") }} 元素的`mpath`子元素使{{ SVGElement("animateMotion") }} 元素能够引用一个外部的{{ SVGElement("path") }}元素作为运动路径的定义。

## 用法

{{svginfo}}

## 示例

```html
<svg width="100%" height="100%"  viewBox="0 0 500 300"
     xmlns="http://www.w3.org/2000/svg"
     xmlns:xlink="http://www.w3.org/1999/xlink" >

  <rect x="1" y="1" width="498" height="298"
        fill="none" stroke="blue" stroke-width="2" />

  <!-- Draw the outline of the motion path in blue, along
          with three small circles at the start, middle and end. -->
  <path id="path1" d="M100,250 C 100,50 400,50 400,250"
        fill="none" stroke="blue" stroke-width="7.06"  />
  <circle cx="100" cy="250" r="17.64" fill="blue"  />
  <circle cx="250" cy="100" r="17.64" fill="blue"  />
  <circle cx="400" cy="250" r="17.64" fill="blue"  />

  <!-- Here is a triangle which will be moved about the motion path.
       It is defined with an upright orientation with the base of
       the triangle centered horizontally just above the origin. -->
  <path d="M-25,-12.5 L25,-12.5 L 0,-87.5 z"
        fill="yellow" stroke="red" stroke-width="7.06"  >
    <!-- Define the motion path animation -->
    <animateMotion dur="6s" repeatCount="indefinite" rotate="auto" >
       <mpath xlink:href="#path1"/>
    </animateMotion>
  </path>
</svg>
```

实时输出：

{{EmbedLiveSample("Example",250,165)}}

## 属性

### 全局属性

- [核心属性](/en/SVG/Attribute#Core) »
- [Xlink 属性](/en/SVG/Attribute#XLink) »
- {{ SVGAttr("externalResourcesRequired") }}

### 专有属性

- {{ SVGAttr("xlink:href") }}

## DOM 接口

该元素实现了[`SVGMPathElement`](/en/DOM/SVGMPathElement)接口。

## 相关的内容

- {{ SVGElement("animateMotion") }}
