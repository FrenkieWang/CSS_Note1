# 文档流

**文档流（Normal Flow)z**是指在网页中元素排列和定位的默认机制。在没有应用 CSS 布局技术（如 Flexbox、Grid 或定位）改变元素默认行为的情况下，元素按照文档流的规则进行布局。
默认的文档路方向是 从上到下 从左到右

文档流的基本原则包括：

### 块级元素（Block-level elements）
- **排列方式**：默认情况下，块级元素会占据完整的容器宽度（如 `<div>`、`<p>`、`<h1>` 等），并在垂直方向上一个接一个地排列。
- **高度和宽度**：块级元素的默认宽度是其父容器的宽度，而高度则根据内容自动调整。
- **用途**：通常用于构造网页的结构和布局框架。

### 行内元素（Inline elements）
- **排列方式**：行内元素不会独占一行，而是按顺序排列在同一行内，直到填满行宽，然后才会换行（如 `<span>`、`<a>`、`<img>` 等）。
- **高度和宽度**：行内元素的宽度和高度通常由其内容决定，不会占据完整的行宽。
- **用途**：通常用于文本内的小段内容，如链接、强调文本等。


### 文档流的定位
- **垂直定位**：块级元素在文档流中按顺序从上到下排列。
- **水平定位**：行内元素和行内块元素在文档流中从左到右排列（在从左到右的阅读顺序的语言环境中），直到可用空间被填满，然后换行到下一行继续排列。



# 内边距(Padding) 和 外边距(Margin)

在CSS中，`padding`和`margin`用来控制元素间的空间关系，达到预期的布局效果。

`padding`用于控制元素内容与其边界的距离，增强可读性和美观性。
`margin`常用于控制元素之间的空间，实现布局分隔和元素对齐。

`padding`和`margin`是两个处理元素间距的重要属性，但它们应用的范围和方式有所不同：

### Padding（内边距）
- `padding`指的是元素内容与其边框之间的空间。
- 它位于元素的边框内侧，增加`padding`会增加元素的尺寸。
- `padding`可以影响元素的背景色或背景图像，背景会延伸到`padding`区域。


### Margin（外边距）
- `margin`是元素与其他元素之间的空间，位于元素边框的外侧。
- 增加`margin`不会增加元素自身的尺寸，而是增加其与其他元素的距离。
- `margin`不会影响元素的背景色或背景图像，它是透明的。
- 特别的，`margin`可以设置为负值，这样可以使元素重叠或者更紧密地排列。

### 功能对比
- **背景影响**：`padding`的增加会影响元素的背景范围，而`margin`不影响背景。
- **可视化效果**：`padding`会增加元素的实际尺寸，而`margin`则影响元素之间的间距，但不影响元素本身的尺寸。

### 设置边距的方法
- 可以单独设置`padding-top`、`padding-right`、`padding-bottom`、`padding-left`，或者使用`padding`属性一次性设置所有四个方向的内边距。
- 也可以单独设置`margin-top`、`margin-right`、`margin-bottom`、`margin-left`，或者使用`margin`属性一次性设置所有四个方向的外边距。
`padding`属性可以接受1到4个值，这些值分别控制元素的上、右、下、左内边距。具体规则如下：
1. **一个值**：元素的所有四个方向（上、右、下、左）的距离。
2. **两个值**：第一个值应用于上下内边距，第二个值应用于左右内边距。
3. **三个值**：第一个值应用于上内边距，第二个值应用于左右内边距，第三个值应用于下内边距。
4. **四个值**：它们分别应用于上、右、下、左内边距（顺时针方向）。

### 设置居中的方法 - `margin: auto;`

`margin: auto;` 能够在某些情况下实现子元素在父元素中的水平居中，主要是因为当元素的`margin`设置为`auto`时，浏览器会自动计算并分配等量的空间到元素的两边，从而实现居中效果：

1. **水平居中**：当一个块级元素（如`div`）的左右`margin`被设置为`auto`，并且该元素有一个固定的宽度时，浏览器会尝试为左右`margin`分配相等的空间，从而使得元素在水平方向上居中于其父元素。这是因为`margin: auto;`会使得元素尝试占据所有可用的水平空间，但由于元素宽度固定，剩余的空间会被均匀分配到左右两侧的`margin`中。
2. **垂直居中**：纯粹使用`margin: auto;`来实现垂直居中是有限制的，它通常需要与其他CSS属性配合使用（如在一个绝对定位的元素中设置`top: 0; bottom: 0; margin: auto;`可以实现垂直居中）。仅仅使用`margin: auto;`并不能直接实现垂直居中，因为在标准文档流中，垂直方向的`margin`不会自动分配空间来实现居中。
3. **块级元素**：`margin: auto;`主要适用于块级元素。对于内联元素，`margin: auto;`不会产生居中效果，因为内联元素不响应垂直方向的`margin`设置。
4. **宽度**：为了使`margin: auto;`有效，元素不能是自然流动宽度（即，它不能是`width: auto;`或占满整个父容器的宽度）。元素需要有一个设置了具体值的`width`属性或者以其他方式限制了宽度，以便浏览器能计算出需要分配给`margin`的空间。
5. **父元素宽度**：`margin: auto;`使元素居中的效果依赖于父元素有足够的宽度。如果父元素宽度不够，即使设置了`margin: auto;`，元素也无法正确居中。


`margin: auto;`不是控制元素居中的最佳方法，
请看下面章节 的 [#Flex布局](#flex-layout)



# 脱离文档流--Position

CSS 中的 `position` 属性用于指定元素的定位方式，包括 `static`、`relative`、`absolute`、`fixed` 和 `sticky`。默认值是 `static`。

### `position: static`

- **默认值**：所有元素默认的 `position` 值是 `static`。
- **行为**：静态定位的元素按照正常的文档流进行布局。即元素出现在其在文档中的位置，不受 `top`、`right`、`bottom`、`left` 属性的影响。

### `position: relative`

- **行为**：相对定位的元素首先按照正常文档流布局，然后根据 `top`、`right`、`bottom`、`left` 属性的值相对于其在正常文档流中的位置进行偏移。元素的偏移不会影响其他元素的位置。
- **用途**：当你想稍微调整元素的位置而不影响布局时，使用相对定位是很有用的。

### `position: absolute`

- **行为**：绝对定位的元素从文档流中完全脱离，并且可以使用 `top`、`right`、`bottom`、`left` 属性相对于其最近的已定位的祖先元素进行定位。如果没有已定位的祖先元素，则相对于初始包含块（通常是 `<html>` 元素或者 `viewport`）进行定位。
- **用途**：当你想要将一个元素完全脱离正常的文档流，并精确地控制其位置时，使用绝对定位是最佳选择。

### 父元素 `relative` 与子元素 `absolute`

当父元素设置为 `position: relative;` 而子元素设置为 `position: absolute;` 时，子元素会相对于父元素进行定位。这意味着子元素的 `top`、`right`、`bottom`、`left` 属性将以父元素的边界为参考，而不是整个文档或视口。这种组合在布局设计中非常有用，因为它允许您相对于父元素精确地定位子元素，而不受其他文档内容的影响。

这个特性使得 `position: relative;` 和 `position: absolute;` 的组合成为创建复杂布局和组件时的强大工具，比如模态窗口、下拉菜单和覆盖效果等。

### `position: fixed`

- **行为**：元素会相对于浏览器窗口（视口）进行定位，这意味着即使页面滚动，元素也会保持在指定的位置不动。fixed 定位的元素从正常的文档流中脱离，因此它不会占据页面上的空间，也不会影响其他元素的布局。
- **用途**：创建不随页面滚动而移动的导航栏。显示始终可见的社交媒体图标。制作弹出式广告或信息框，需要始终可见。

### `position: stikcy`

- **行为**：基于用户滚动位置的混合定位方式。元素在页面上的初始位置是相对定位（relative），但当页面滚动到达某个阈值时（例如，元素达到视口的顶部），它就变为固定定位（fixed），直到其父容器的边界被滚动出视口为止。
- **用途**：制作表格标题在滚动时保持在顶部可见。创建在用户向下滚动页面时变为固定的导航菜单。

  

<a id="flex-layout"></a>
# Flex布局

Flexbox 是 CSS 的一种布局模式，旨在提供一种更有效的方式来布置、对齐和分布容器内的项，即使它们的大小未知或动态变化。Flexbox 使复杂的布局变得简单，对于响应式设计尤其有用。

### `flex-direction`

`flex-direction` 属性决定了 Flex 容器内主轴（main axis）的方向。主轴的方向决定了 Flex 项是如何在 Flex 容器中排列的。`flex-direction` 可以有以下值：

- **`row`**（默认）: Flex 项沿水平方向，从左到右排列（在LTR语言模式下）。
- **`row-reverse`**: Flex 项沿水平方向，但是从右到左排列。
- **`column`**: Flex 项沿垂直方向，从上到下排列。
- **`column-reverse`**: Flex 项沿垂直方向，但是从下到上排列。

### `justify-content`

`justify-content` 属性定义了 Flex 项沿主轴的对齐方式。这个属性可以帮助分配 Flex 项之间以及容器内部的空白空间。`justify-content` 的常用值包括：

- **`flex-start`**（默认）: Flex 项排列在容器的开始端。
- **`flex-end`**: Flex 项排列在容器的结束端。
- **`center`**: Flex 项在容器中居中对齐。
- **`space-between`**: Flex 项在容器中均匀分布，第一个项在开始端，最后一个项在结束端。
- **`space-around`**: Flex 项在容器中均匀分布，容器两端（第一个和最后一个）与容器边界之间的空间，是 Flex 项之间空间的一半。
- **`space-evenly`**: Flex 项在容器中均匀分布，所有项（包括开始端和结束端）的空间相等。

### `align-items`

`align-items` 属性定义了 Flex 项沿交叉轴的对齐方式。交叉轴垂直于主轴。`align-items` 的作用是解决 Flex 项在容器的交叉轴方向上应该如何对齐的问题。常用的值包括：

- **`stretch`**（默认）: Flex 项被拉伸以填满容器的交叉轴，但也可以被其内容的高度或设定的高度所限制。
- **`flex-start`**: Flex 项沿交叉轴的起点对齐。
- **`flex-end`**: Flex 项沿交叉轴的终点对齐。
- **`center`**: Flex 项在交叉轴上居中对齐。
