# HTML5 Study Note

## HTML5 文档结构

HTML5已经不同于其早期版本，配合JavaScript，可以提供更为丰富的用户互动功能，在为用户带来更好体验的同时吸引用户更多回访和使用网站应用。HTML5使用其语义系统定义的模块设计网页的文档结构，而不是依靠网页浏览器渲染引擎的内部规则，因为来自不同厂商的浏览器可能规则不同。

使用HTML5的语义标记不仅可以设计更具结构化的网页，也可以为用户在不同页面浏览提供优化，同时为搜索引擎检索网页提供便利。这一部分介绍的内容包括，HTML5的语义标记，HTML的布局容器，为搜索引擎做优化，为页面阅读器做优化。

HTML5的主要语义标记包括如下组件：
* <article> 定义自包含的区域
* <aside> 定义在页面主要布局外小片区域
* <figcaption> 定义图片组件的说明
* <figure> 定义图片容器，可以包含图像或表格
* <footer> 定义页面底部区域
* <header> 定义页面顶部区域
* <hgroup> 定义一系列标题，从H1到H6
* <mark> 定义高亮强调的文字
* <nav> 定义页面导航栏
* <progress> 定义任务进度
* <section> 定义文档中特有内容

在进入对以上语义标记的介绍前，先看HTML文档的框架：
```
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8"/>
    <title></title>
</head>
<body>
    <!-- page content goes here -->
    Hello World!
</body>
</html>
```

对于以上空白框架这里不展开介绍，只是以后添加的代码追加在`body`组件中。

### <header>和<footer>

大部分网页都有类似页眉或页脚的部分，停靠在所有页面顶端和底端，这两个部分可以通过`header`和`footer`来标记。只是仅做出标记并不能实现其各自的功能，但提供了进一步定义其格式和使用这些标记的可能。

整个网页的`header`部分可以包括公司名称和商标，或者也包括导航栏。其内部最常见组件就是标题，包括从一级到六级的所有标题。且`article`或`section`组件也可以有自己的`header`，其中同样是放置标题。当然，除了标题也可以放置其他任何合理的语义标记。

```
    <header>
        <h1>A finctional company website</h1>
    </header>
    <article>
        <header>
            <h1>The first new article</h1>
        </header>
    </article>
```

### <nav>

大部分的网页都会在页眉处设置导航栏，用于放置到网站内部子页面的连接。有时在侧边栏也会放置导航栏，除了链接到网站内的子页面也可以连接到网站外部的其他页面。

```
    <header>
        <h1>A fictional company website</h1>
        <nav>
            <a href="Home.html">Document Structure</a>
            <a href="Blog.html">Writing Code</a>
            <a href="About.html">Styles</a>
        </nav>
    </header>
```

### <hgroup>

有时候多级标题会放在一起，使用标题组`hgroup`标记可以将标题统一到一个语义标记下，后期如果有格式或动作定义就方便了许多，这里虽然暂时没有多级标题的应用，也可以先将标题组标记写上。

```
    <header>
        <hgroup>
            <h1>A fictional company website</h1>
        </hgroup>
        <nav>
            <a href="Home.html">Document Structure</a>
            <a href="Blog.html">Writing Code</a>
            <a href="About.html">Styles</a>
        </nav>
    </header>
```

### <article>

文章标记代表语义完整的一个组件，可以是一篇杂志文章或博客文章等，总之是独立出来也不影响其含义的理解。文章内可以有子文章，但后者必须与前者相关。

```
    <article>
        <header>
            <h1>The first new article</h1>
        </header>
        <p>Some information about the first article</p>
    </article>
    <article>
        <header>
            <h1>The second new article</h1>
        </header>
        <p>Some information about the second article</p>
    </article>
    <article>
        <header>
            <h1>The third new article</h1>
        </header>
        <p>Some information about the third article</p>
    </article>    
```

### <section>

文章标记不足以分割更小的内容单位，或者需要就个别问题提供更为详细的内容，而又不想打破整个文章的连贯意义，可以使用`section`标记。需要注意的是，`section`标记需要在`article`标记之内，`section`标记内的第一个标记常常是`<header>`或者`<hgroup>`。

```
    <article>
        <header>
            <h1>The first new article</h1>
        </header>
        <section>
            <h1>Section 1</h1>
            <p>Some detail about section 1</p>
        </section>
        <section>
            <h1>Section 2</h1>
        </section>
    </article>
```

注意，从网页顶级标题的`h1`到`article`中的`h1`再到`section`中的`h1`，各级文档结构下的`h1`格式有所不同，这与更早版本的HTML不同，因为HTML5增强了HTML文本自身的层级结构，因此需要理解各语义标记的默认层级关系。

### <aside>

对于不在当前页面主流中的内容，如侧边栏、注释、或广告，可以使用`aside`标记标注。与`nav`标记类似，`aside`标记本身并不会将被标注的内容放置到边栏，只是提供了进一步定义格式和动作的可能。

```
        <section>
            <h1>Section 1</h1>
            <p>Some detail about section 1</p>
            <aside>Some content to be aside</aside>
        </section>
```

### <figcaption> and <figure>

为了为文字的内容添加更多详情和参考信息，经常需要插入图片或图表，`figure`和`figcaption`可以插入图像和图像备注。注意`img`和`figcaption`作为`figure`的子元素，和默认格式的缩进。

```
    <article>
        <header>
            <h1>The third new article</h1>
        </header>
        <p>The third article is about cats</p>
        <figure>
            <img src="1_2.jpg" style="width:240px; height:150px" />
            <figcaption>Cat enjoys staying in box.</figcaption>
        </figure>
    </article>
```

### <progress>

为了显示目标或任务的进程，可以使用`progress`标记，对于可预知结束值的进度，如下载文件或众筹款项的进展，或不可预知结束值的进度，如从服务器接收信息或文件，可以使用不同的进度条。进度条中的`value`值代表当前值，一般使用`JavaScript`做动态更新。

```
    <article>
        <header>
            <h1>The second new article</h1>
        </header>

        <p>The goal is to have 1000 users:</p>
        <span>0</span>
        <progress value="150" max="1000"></progress>
        <span>1000</span>

        <p>Some download is in progress, please wait:</p>
        <progress max="100"></progress>
    </article>
```

### <mark>

通过定制背景颜色从文本中强调出重点部分。

```
        <section>
            <h1>Section 2</h1>
            <p>Something <mark style="background-color: yellow">
                important</mark> goes here</p>
        </section>
```

### <div>

以上介绍的HTML5新添加的语义标记主要是替换在早期HTML版本中过多使用的`div`标签。在将若干常用标签抽取和标准化后，HTML文档更易于维护其结构和保持风格一致。但再次强调，以上语义标记不会默认添加格式，而只是为以后添加格式和动作提供了可能和便利。

## HTML布局容器

即便可以使用格式美化HTML文档，基本的布局仍然十分重要。使用`div`或`table`标记是最常见的做法。`div`组件提供更为动态的页面布局，`table`组件更适用于静态的页面布局。

### <div>

`div`标记提供的仅仅是空的容器，一切布局定义都要通过相关的ID实施。

```

```

### <table>

在布局定义方面，`table`标记本身是易用的，加上`thead`和`tfoot`可以更好增强表格组件的语义功能。问题是其静态属性，整个网站的布局更新需要逐页操作，十分不便。

```
    <table>
        <tr>
            <td colspan="3" id="Header">Header</td>
        </tr>
        <tr>
            <td rowspan="3" id="LeftBar">LeftBar</td>
            <td rowspan="3" id="MainContent">MainContent</td>
            <td id="RightSideTop">RightSideTop</td>
        </tr>
        <tr>
            <td id="RightSideMiddle">RightSideMiddle</td>
        </tr>
        <tr>
            <td id="RightSideBottom">RightSideBottom</td>
        </tr>
        <tr>
            <td colspan="3" id="Footer">Footer</td>
        </tr>
    </table>
```

### 搜索引擎优化

搜索引擎优化，SEO，可以独立写成一本书。这里介绍使用HTML5的标记优化搜索引擎对网页的索引，以便配合搜索引擎的算法更好的让目标用户找到网页。

旧的HTML规范过多应用`div`标记，不便搜索引擎了解文档内容。HTML5引入的`article`和`section`标记构成网页内容的主体，而以上标记包括`body`标记下的`hgroup`和`h1`标记作为标题也会得到搜索引擎的优先处理。因此，合理使用以上标签对配合搜索引擎的索引算法，增强网站的易用性很重要。

### 屏幕阅读器优化

屏幕阅读器将HTML文本从文字转换为语音，为有视觉障碍的用户提供便利。旧的HTML规范使用`div`标记所有容器，用`h1`到`h6`的各级标题作为文档结构标记。但HTML5的新规范推荐使用`article`，`section`，`nav`和`aside`，配合`h1`标记，实现对文本结构的标记。

```
    <article>
        <h1>Pre-HTML5 Style</h1>
        <section>
            <h1>Fruits and Vegetables</h1>
            <h2>Fruits</h2>
            <h3>Round Fruits</h3>
            <h3>Long Fruits</h3>
            <h2>Vegetables</h2>
            <h3>Green</h3>
            <h3>Colorful</h3>
        </section>
    </article>
    <article>
        <h1>HTML5 Style</h1>
        <section>
            <h1>Fruits and Vegetables</h1>
            <section>
                <h1>Round Fruit</h1>
            </section>
            <section>
                <h1>Long Fruit</h1>
            </section>
        </section>
        <section>
            <h1>Vegetables</h1>
            <section>
                <h1>Green</h1>
            </section>
            <section>
                <h1>Colorful</h1>
            </section>
        </section>
    </article>
```

有趣的是，在`section`内如果使用`h1`意外的标题标记，默认的`h2`可能会比`h1`的字体还大，因此这里再次强调，在`section`内只需要使用`h1`标题，如果需要划分子标题和子文档结构，额外建立`section`组件即可。

### 重构网页

相对于传统的HTML文本格式的网页，HTML5标准下的网页文本更易读，对比一下两个规格下的文档就可以明白。只是旧标准下的`table`标签自带布局定义，而新的HTML标准与旧标的`div`标记类似，需要进一步的格式定义才能使使用的标签起作用。

旧的HTML标准下的网页文档：
```
    <table>
        <tr><td colspan="3"><div id="header">
            <h1>An Experiment</h1>
        </div></td></tr>
        <tr>
            <td>
                <a href="">Home</a>
                <a href="">Page 1</a>
                <a href="">Page 2</a>
                <a href="">Page 3</a>
            </td>
            <td>
                <div id="content">
                    <div id="anArticle">
                        <h1>An Article</h1>
                        <h2>Second Header</h2>
                        <div id="moreInfo">
                            More Information
                        </div>
                    </div>
                </div>
            </td>
            <td>
                <div id="profile">
                    Some Profile
                </div>
            </td>
        </tr>
        <tr>
            <td>
                <div id="footer">
                    This page is copyright protected.
                </div>
            </td>
        </tr>
    </table>
```

新的HTML5标准下的文档：
```
    <header>
        <hgroup>
            <h1>An Experiment</h1>
        </hgroup>
        <nav>
            <a href="">Home</a>
            <a href="">Page 1</a>
            <a href="">Page 2</a>
            <a href="">Page 3</a>
        </nav>
    </header>
    <article>
        <hgroup>
            <h1>An Article</h1>
        </hgroup>
        <section>
            <h1>Second Header</h1>
            <p>More information</p>
        </section>
        <aside>
            Some Profile
        </aside>
    </article>
    <footer>
        This page is copyright protected.
    </footer>
```

## UI Controls

### 添加和修改HTML组件

为了在用户和网页之间互动，需要了解JavaScript的使用方法。作为准备知识补充如下内容。

#### 文档对象模型

文档对象模型（DOM Document Object Model）代表可以通过编程方式互动的HTML页面结构。通过DOM提供的API编程接口，页面中对象的创建和修改全部可以通过JavaScript完成。

选择DOM组件的方法有：
* getElementById: 通过HTML组件的ID访问个别对象
* getElementByClassName: 通过CSS类访问所有该类对象
* getElementByTagName: 通过组件名称访问所有该类对象
* querySelector: 检索并访问匹配指定CSS定义的第一个对象
* querySelectorAll: 检索并访问匹配指定CSS定义的所有对象

注意：
* 根据CSS类名选择对象可能跨组件，如`p`和`h1`甚至`div`。
* 返回多个对象时，通过`NodeList`传递，可按数组方式处理。
* `jQuery`同样可以查找和返回DOM对象，可以另行了解。

修改DOM组件的方法有：
* parent.removeChild(child): 删除并返回母组件下的子组件
* element.remove(): 删除母组件，不返回任何值
* createElement: 创建组件，并返回新建组件
* appendChild: 添加组件到方法主体，并返回添加的组件
* insertBefore: 添加组件到指定子组件的前面
* replaceWith(): 使用指定组件替换母组件
* replaceChild(): 使用指定组件替换母组件中指定的子组件

注意：
* 删除和添加操作需要在母组件上操作，注意方法的主体。
* 创建组件后如果不添加到其他文档组件，没有实际意义。
* 没有`removeNode()`方法，只有`remove()`。
* 没有`replaceNode()`方法，只有`replaceWith()`。
* 在用`replaceWith()`方法时，最好为新组件设置ID。
* 

文档对象模型组件的属性：
* childNodes: 母组件下的所有子组件列
* firstChild: 子组件列表中的第一项
* lastChild: 子组件列表中的最后一项
* hasChildNodes: 判断母组件下是否包含子组件

```
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8"/>
    <title></title>
    <script>
        window.onload = function () {
            // var element = document.getElementById("outerDiv");
            // alert(element.innerHTML);

            // var paragraphs = document.getElementsByTagName("p");
            // alert(paragraphs.length);

            // var paragraphs = document.getElementsByClassName("subPara");
            // alert("<p> elements with class subParas: " + paragraphs.length);

            // var rows = document.querySelectorAll("td");
            // alert("number of rows: " + rows.length);

            // var innerDiv = document.querySelector("#innerDiv");
            // alert("content of the innerDiv:" + innerDiv.innerHTML);

            // var parent = document.getElementById("innerDiv");
            // var toRemove = document.getElementById("P3");
            // var removed = parent.removeChild(toRemove);
            // alert("removed element: " + removed.innerHTML);

            // var toRemove = document.getElementById("P4");
            // oRemove.remove();

            // var innerDiv = document.getElementById("innerDiv");
            // var newDiv = document.createElement("div");
            // newDiv.setAttribute("id", "newInnerDiv");
            // for (var i = 0; i < innerDiv.childNodes.length; i++) {
            //     var anchor = newDiv.appendChild(document.createElement("a"));
            //     anchor.setAttribute("href", "#");
            //     anchor.text = innerDiv.childNodes[i].textContent;
            //     newDiv.appendChild(document.createElement("br"));
            // }
            // innerDiv.replaceWith(newDiv);

            // var newListItem = document.createElement("li");
            // var newItemText = document.createTextNode("A REPLACED List Item!");
            // newListItem.appendChild(newItemText);
            // var list = document.getElementsByTagName("ul")[0];
            // list.replaceChild(newListItem, list.childNodes[0]);

            // var beforeAdd = document.getElementById("innerDiv");
            // var addChild = document.createElement("p");
            // addChild.innerText = "My new paragraph element";
            // var addedChild = beforeAdd.appendChild(addChild);
            
            // var addedChild = document.getElementById("innerDiv")
            //     .appendChild(document.createElement("p"));
            // addedChild.innerText = "Another newly added paragraph!";

            // var inserted = document.getElementById("innerDiv").insertBefore(
            //     document.createElement("p"),
            //     document.getElementsByClassName("subPara")[1]);
            // inserted.innerText = "My newly inserted paragraph!";

            // var list = document.getElementsByTagName("ul")[0];
            // if (list.hasChildNodes()) {
            //     var newFirst = list.insertBefore(document.createElement("li"),list.firstChild);
            //     newFirst.innerText = "The NEW First List Item!";
            //     var newLast = list.insertBefore(document.createElement("li"),list.lastChild);
            //     newLast.innerText = "This should be the SECOND last item!";
            // }
        }
    </script>
</head>
<body>
    <div id="outerDiv">
        <p class='mainPara'>Main Paragraph</p>
        <ul>
            <li>First List Item</li>
            <li>Second List Item</li>
            <li>Third List Item</li>
            <li>Fourth List Item</li>
        </ul>
        <div id="innerDiv">
            <p class='subPara', id='P1'>Paragraph 1</p>
            <p class='subPara', id='P2'>Paragraph 2</p>
            <p class='subPara', id='P3'>Paragraph 3</p>
            <p class='subPara', id='P4'>Paragraph 4</p>
        </div>
        <table>
            <tr>
                <td>Row 1</td>
            </tr>
            <tr>
                <td>Row 2</td>
            </tr>
            <tr>
                <td>Row 3</td>
            </tr>
            <tr>
                <td>Row 4</td>
            </tr>
            <tr>
                <td>Row 5</td>
            </tr>
        </table>
        <input type="text"/>
        <input type="submit" value="Submit" />
    </div>
</body>
</html>
```

#### 媒体控制

视频组件`video`带有如下属性：
* src: 资源路径，可以是本地或者远程URL路径。
* autoplay: 是否在页面加载时自动播放，默认否。
* controls: 是否显示例如播放和暂停等播放控件。
* height/width: 视频的长宽，默认用原始长宽值。
* loop: 是否循环播放，默认否。
* poster: 指定图片占位符，默认使用视频第一帧。

注意：
* 不同浏览器的视频支持能力不同，可提供多种视频。
* `video`内可放多个`source`支持不同视频格式。
* 不支持`video`组件的浏览器可显示`object`内容。
* 浏览器支持`video`但不支持给的视频格式则会报错。
* 隐藏默认控件后，可以自定义播放控件的样式和功能。
* 自定义的播放控件需要在媒体缓冲完成后才能使用。

视频对象支持的方法：
* play(): 从当前位置播放
* pause(): 在当前位置暂停播放
* volume: 允许用户调整音量
* currentTime: 视频的当前位置

音频组件`audio`与视频组件类似，这里略过。

```
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8" />
    <title>Media Control</title>
    <style>
        img:hover {
            cursor: pointer;
        }
    </style>
    <script>
        var video;
        window.onload = function () {
            video = document.getElementById("sampleVideo");
        }
        function play() { video.play(); }
        function pause() { video.pause(); }
        function back() { video.currentTime -= 5; }
    </script>
</head>

<body>
    <video src="https://file-examples.com/wp-content/uploads/2017/04/file_example_MP4_480_1_5MG.mp4" , controls loop
        autoplay poster="1_2.jpg" height="270" width="480"></video>

    <table>
        <tr>
            <td>
                <video id="sampleVideo" poster="1_2.jpg" height="270" width="480">
                    <source src="https://file-examples.com/wp-content/uploads/2017/04/file_example_MP4_480_1_5MG.mp4"
                        type="video/mp4" />
                    <source src="https://file-examples.com/wp-content/uploads/2018/04/file_example_OGG_480_1_7mg.ogg"
                        type="video/ogg" />
                    <object>
                        <p>Video is not supported by this browser.</p>
                    </object>
                </video>
            </td>
            <td>
                <img id="backButton" src="2_back.png" onclick="back();" /><br />
                <img id="playButton" src="2_play.png" onclick="play();" /><br />
                <img id="pauseButton" src="2_pause.png" onclick="pause();" /><br />
            </td>
        </tr>
    </table>

    <audio controls>
        <source src="https://file-examples.com/wp-content/uploads/2017/11/file_example_MP3_700KB.mp3" type="audio/mp3" />
        <source src="https://file-examples.com/wp-content/uploads/2017/11/file_example_OOG_1MG.ogg" type="audio/ogg" />
        <p>Your browser does not support HTML5 audio.</p>
    </audio>
</body>

</html>
```

#### 图像功能

HTML5提供了`canvas`画布组件用于绘图，基本定义是ID和长宽，组件内部可放简单的说明，在浏览器无法识别`canvas`组件时显示。

画布以左上角为原点，向右为X轴取正值，向下为Y轴取正值。一个长宽分别为600和400的画布，右上、左下和右下的坐标分别为(600,0)、(0,400)和(600,400)。

使用`canvas`绘图的流程如下：
* 在窗口加载的函数中引用画板组件，并创建背景对象。
* 使用相关方法绘制图形，并设置颜色格式等效果，
* 绘出图形，使其对用户可见。
* 一些所有图形通用的属性设置如下：
    * stroke: 绘出线使其对用户可见
    * lineWidth: 定义直线宽度
    * lineCap: 可定义直线端点为圆形`round`
    * strokeStyle: 定义直线颜色等
    * fillStyle: 定义填充的颜色或图案

绘制直线的方法和属性：
* beginPath: 重置或开始绘制一条新的直线
* moveTo: 将背景移动到指定的坐标点
* lineTo: 设置绘制直线的终点

绘制方形的方法：
* rect: 通过起点和长宽的定义绘制方形
* x, y: 前两个参数，定义方形的左上角起点
* width: 第三个参数，定义宽度
* height: 第四个参数，定义高度
* fillRect: 填充颜色，使用如上参数

绘制圆弧的方法：
* arc: 标准圆弧，根据开始和终止角度，以及半径绘出
* quadradicCurveTo: 二次曲线，允许定义弧度的陡峭程度
* bezierCurveTo: 复杂的圆弧，可偏向一边的圆弧

绘制圆弧使用的参数：
* X and Y: 第一和第二个参数，定义圆弧的圆心
* radius: 第三个参数，定义半径
* startAngle, endAngle: 第四和第五个参数，定义开始和终止角度
* counterclockwise: 最后一个参数，定义顺时针或逆时针方向 

绘制二次曲线使用的参数：
* controlX, controlY: 自定义控制点，也就是曲线的顶点
* endX, endY: 曲线终止点
* 二次曲线即将从`moveTo`到终止点的直线向上提起到自定义控制点

绘制贝塞尔曲线的参数：
* controlX, controlY: 头两个参数设置第一个控制点
* control2X, control2Y: 中间两个参数设置第二个控制点
* endX, endY: 最后两个参数设置曲线的终点
* 曲线在两个控制点的牵引下发生扭转

在绘制图形之间，只要没有发起新的`beginPath`或者使用`closePath`命令，锚点途径的所有轨迹都是有效。因此借助移动经过路径自动有效的特性，可以绘制一些看似复杂的图案。

除了填充固定颜色，也可以填充过渡色，或放射形过渡色，甚至图片或文字
* createLinearGradient: 方法定义起始和结束过渡点，加上`addColorStop`定义过渡比和颜色。
* createRadialGradient: 分别定义起始和结束的圆心坐标和半径，加上过渡比和颜色。
* createPattern: 设置背景图案，注意定义图像对象并在加载后调用该方法。
* drawImage: 绘出指定图片，指定左上角坐标，可重定义图片宽和高。
* strokeText: 可在图片中插入空心文字，根据`font`、`textAlign`、`strokeStyle`等定义。
* fillText: 可在图片中插入实心文字，根据`font`，`textAlign`、`fillStyle`等定义。

```
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8" />
    <title>Canvas and SVG</title>
    <style>
        canvas {
            border: 1px solid black;
        }
    </style>
    <script>
        window.onload = function () {
            var drawingSurface = document.getElementById("drawingSurface");
            var ctxt = drawingSurface.getContext("2d");

            // ctxt.beginPath();
            // ctxt.moveTo(20,20);
            // ctxt.lineTo(225, 350);
            // ctxt.lineTo(300,20);
            // ctxt.lineTo(400,350);
            // ctxt.lineWidth = 10;
            // ctxt.lineCap = "round";
            // ctxt.strokeStyle = '#0f0';
            // ctxt.stroke();

            // ctxt.beginPath();
            // var x, y;
            // x = 400;
            // y = 300;
            // ctxt.rect(300-(x/2),200-(y/2),x,y);
            // ctxt.fillStyle = "CornflowerBlue";
            // ctxt.fillRect(300-(x/2),200-(y/2),x,y);
            // ctxt.stroke();

            // ctxt.beginPath();
            // ctxt.arc(150, 100, 75, 0, 2 * Math.PI, false); 
            // ctxt.lineWidth = 25;
            // ctxt.strokeStyle = 'lime'; // #0f0
            // ctxt.stroke();
            
            // ctxt.beginPath();
            // ctxt.arc(450, 100, 75, 1.5 * Math.PI, 2 * Math.PI, false);
            // ctxt.lineWidth = 25;
            // ctxt.strokeStyle = 'blue';
            // ctxt.stroke();

            // ctxt.beginPath();
            // ctxt.arc(150, 300, 75, 1 * Math.PI, 1.5 * Math.PI, false);
            // ctxt.lineWidth = 25;
            // ctxt.strokeStyle = 'cyan'; // #0ff
            // ctxt.stroke();

            // ctxt.beginPath();
            // ctxt.arc(450, 300, 75, .5 * Math.PI, 1 * Math.PI, false);
            // ctxt.lineWidth = 25;
            // ctxt.strokeStyle = 'red';
            // ctxt.stroke();

            // ctxt.beginPath();
            // ctxt.moveTo(10,380);
            // ctxt.quadraticCurveTo(450,-250,580,380);
            // ctxt.lineWidth = 25;
            // ctxt.strokeStyle = 'red';
            // ctxt.stroke()

            // ctxt.beginPath();
            // ctxt.moveTo(5,200);
            // ctxt.bezierCurveTo(200,-200,200,400,595,200);
            // ctxt.lineWidth = 5;
            // ctxt.strokeStyle = 'cyan';
            // ctxt.stroke();

            // ctxt.beginPath();
            // ctxt.arc(150,200,100,0,1.2*Math.PI,false);
            // ctxt.lineTo(70,80);
            // ctxt.arc(150,200,100,1.4*Math.PI,1.6*Math.PI,false);
            // ctxt.lineTo(230,80);
            // ctxt.arc(150,200,100,1.8*Math.PI,0,false);
            // ctxt.lineCap = "round";
            // ctxt.strokeStyle = 'cyan';
            // ctxt.lineWidth = 10;
            // ctxt.fillStyle = 'cyan';
            // ctxt.fill();
            // ctxt.stroke();

            // ctxt.beginPath();
            // ctxt.arc(450,200,100,0,1.2*Math.PI,false);
            // ctxt.quadraticCurveTo(330,60,380,20);
            // ctxt.arc(450,200,100,1.4*Math.PI,1.6*Math.PI,false);
            // ctxt.lineTo(520,20);
            // ctxt.strokeStyle = 'coral';
            // ctxt.lineWidth = 10;
            // ctxt.fillStyle = 'coral';
            // ctxt.fill();
            // ctxt.stroke();
            // ctxt.beginPath();
            // ctxt.arc(450,200,100,0,1.8*Math.PI,true);
            // ctxt.quadraticCurveTo(570,60,520,20);
            // ctxt.strokeStyle = 'coral';
            // ctxt.lineWidth = 10;
            // ctxt.fillStyle = 'coral';
            // ctxt.fill();
            // ctxt.stroke();

            // ctxt.lineWidth = 5;
            // ctxt.rect(50,50,500,300);
            // var gradient = ctxt.createLinearGradient(10,200,590,200);
            // gradient.addColorStop(0.143, "red");
            // gradient.addColorStop(0.286, "orange");
            // gradient.addColorStop(0.429, "yellow");
            // gradient.addColorStop(0.572, "green");
            // gradient.addColorStop(0.715, "blue");
            // gradient.addColorStop(0.858, "indigo");
            // gradient.addColorStop(1, "violet");           
            // ctxt.fillStyle = gradient;
            // ctxt.fill();
            // ctxt.stroke();

            // ctxt.lineWidth = 5;
            // ctxt.rect(50,50,500,300);
            // var gradient = ctxt.createRadialGradient(200,150,5,300,200,150);
            // gradient.addColorStop(0.143, "red");
            // gradient.addColorStop(0.286, "orange");
            // gradient.addColorStop(0.429, "yellow");
            // gradient.addColorStop(0.572, "green");
            // gradient.addColorStop(0.715, "blue");
            // gradient.addColorStop(0.858, "indigo");
            // gradient.addColorStop(1, "violet");
            // ctxt.fillStyle = gradient;
            // ctxt.fill();
            // ctxt.stroke();

            // ctxt.lineWidth = 5;
            // ctxt.rect(50,50,500,300);
            // var img = new Image();
            // img.src = "2_play.png";
            // img.onload = function () {
            //     var pat = ctxt.createPattern(img, "repeat");
            //     ctxt.fillStyle = pat;
            //     ctxt.fill();
            //     ctxt.stroke();
            // }

            // var img = new Image();
            // img.src = "1_2.jpg";
            // img.onload = function() {
            //     ctxt.drawImage(img,50,50,img.width*.8,img.height*.8);
            //     ctxt.stroke();
            // }

            // ctxt.strokeText("1. Stroke text in default.", 50, 50);
            // ctxt.font = "24px arial";
            // ctxt.strokeText("2. Stroke text with altered font.", 50, 75);
            // ctxt.strokeStyle = "red";
            // ctxt.strokeText("3. Stroke text with altered color.", 50, 100);
            // ctxt.fillStyle = "blue";
            // ctxt.fillText("4. Fill text with altered color", 50, 125);
            // ctxt.textAlign = "center";
            // ctxt.fillStyle = "cyan";
            // ctxt.fillText("5. Fill text centered", drawingSurface.width/2,
            //     drawingSurface.height/2);
        }
    </script>
</head>

<body>
    <canvas id="drawingSurface" width="600" height="400">
        Your browser does not support HTML5.
    </canvas>
</body>

</html>
```

以上介绍的是画布`canvas`标记，除此以外`svg`标记也可以用来插入可变矢量SVG（Scalable Vector Graphics）图形。这是一种基于XML命名空间的嵌入组件，支持属性、格式和事件。

```
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8" />
    <title>SVG</title>
    <script language="javascript">
        function Red(evt) {
            var circle = evt.target;
            circle.setAttribute("style", "fill: red");
        }

        function Green(evt) {
            var circle = evt.target;
            circle.setAttribute("style", "fill: green");
        }
    </script>
</head>

<body>
    <!-- <svg>
        <circle id="circle" cx="50" cy="50" r="50" fill="green" onmouseover="Red(evt)" onmouseout="Green(evt)" />
    </svg> -->

    <!-- <svg>
        <rect id="lightStandard" x="0" y="0" width="200" height="60" fill="black" />
        <circle id="redLight" cx="40" cy="30" r="25" fill="red" />
        <circle id="amberLight" cx="100" cy="30" r="25" fill="yellow" />
        <circle id="greenLight" cx="160" cy="30" r="25" fill="green" />
    </svg> -->

    <!-- <svg>
        <polygon points="10,25 30,75 10,125 100,125, 70,75, 100,25" fill="purple" />
        <polyline points="110,50 130,70 150,32 162,125 178,65 196,70"
            style="stroke:orange; fill:none; stroke-width:5;" />
        <line x1="210" y1="25" x2="220" y2="125" style="stroke:blue;stroke-width:3" />
        <ellipse cx="270" cy="75" rx="30" ry="50" fill="green" />
        <text x="0" y="15" style="stroke: black;stroke-width:1;">
            Examples of SVG Shapes and Text</text>
    </svg> -->

    <svg id="mySVG">
        <image href="1_2.jpg" width="360" height="150" />
    </svg>

</body>

</html>
```

总的来说，`canvas`通过JavaScript引用HTML容器并创建图形，而`svg`直接在HTML容器中定义图形，后者运行消耗的资源更多，在资源紧缺时可以考虑使用`canvas`。
