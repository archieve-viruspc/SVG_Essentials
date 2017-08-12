## SVGForeignObjectElement

[SVGForeignObjectElement接口介绍](https://developer.mozilla.org/zh-CN/docs/Web/API/SVGForeignObjectElement)

[SVG-foreignObject元素介绍](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/foreignObject)

- [SVGForeignObjectElement](SVGForeignObjectElement)

- [foreignObject](foreignObject)

- [switch]()
### SVGForeignObjectElement

SVGForeignObjectElement实现了访问`[<foreignObject>](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/foreignObject)`元素属性的接口以及操作它们的方法。

### foreignObject

foreignObject允许在SVG中嵌入外部XML应用，这些外部应用可能是不同的用户代理绘制的图形内容，嵌入的内容与普通的SVG元素一样也受SVG坐标转换以及图形处理的影响。

foreignObject 内的元素假设与SVG具有不同的命名空间。如果不指定命名空间除非浏览器能识别，否则则不会被绘制，多层嵌套时也是如此。比如在一个SVG中使用foreignObject中嵌入一个非SVG文档，而这个非SVG文档中又嵌入了另一个SVG文档这种情况。

一般在使用foreignObject时，结合[switch](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/switch)元素和requiredExtensions(https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/requiredExtensions)属性一起使用，因为foreignObject这个元素可能会不被支持。使用switch是为了在foreignObject元素不支持时提供一个备选方案。

```html
<svg width='600' height='400' xmlns='http://www.w3c.org/2000/svg' style='border:2px steelblue solid'>
	<switch>
		<foreignObject x='100' y='100' width='100' height='100'>
			<div xmlns="http://www.w3.org/1999/xhtml" style='border:1px red solid'>
				这里是一段很长很长很长很长很长很长的文字字字
			</div>
		</foreignObject>
		<text x='100' y='100'>
			<tspan x="10" y="10">这里是一段很长很长很长</tspan>
  			<tspan x="10" y="20">很长很长的文字字字</tspan>
		</text>
	</switch>
</svg>
```

![image](https://github.com/xswei/SVG_Essentials/blob/master/image/foreignObject.jpg)