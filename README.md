实现过程分两部分：


1.使用CSS进行页面布局
（1）通过3层来实现，最底层的固定不动半透明图片，中间层的部分不透明的清晰图片以及最上层的选取框。
（2）在一张大图中显示一小块区域，其它部分隐藏。这块区域是边长100px的正方形，并且左上角相对于整张图片的坐标是x=10px，y=10px,实现方法为：clip：rect（10px，110px，110px，10px）
（3）要将一个宽度为8px的div始终水平居中显示在其父元素中，但其父元素的宽度不确定，用css的实现方法为：
     ｛position:absolute;left:50%;margin-left:-4px;｝
2.使用JS实现效果
（1）鼠标事件：按下事件、释放事件和拖动事件。
（2）拖动效果（放大）：JS获取鼠标位置来确定选取框的位置
（3）鼠标变化时不停的改变选取框的位置和大小从而达到选取框跟随变化的效果。
（4）offsetLeft:元素相对于父元素左边界的距离。
（5）获取鼠标在屏幕中的横坐标：event.clientX。
（6）获取元素div相对于父元素(已定位)的左边距：div.offsetLeft（是具体的值）。若要为div的左边距赋值用：div.style.left="";
（7）js事件冒泡是指鼠标点击里面的元素时也会触发其父元素的一些事件，为了阻止这种情况，应该在里面元素的触发函数里第一行加上:event.stopPropagation();
