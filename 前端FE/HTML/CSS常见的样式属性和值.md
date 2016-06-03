#####目录

|序号|属性类型|
|----|--------|
| 1  |字体属性|
| 2  |颜色属性|
| 3  |背景属性|
| 4  |文本属性|
| 5  |边框属性|
| 6  |列表属性|

#####主要选择器的优先级关系

关联选择器 > ID选择器 > 类选择器 > HTML选择器

######1.字体属性

|属性|描述|属性值|
|----|----|------|
|font-family|字体族科|Times,serif(多个族科用逗号分隔,以防止不存在的字体族科)|
|font-size  |字体大小|可以使用绝对大小,相对大小,长度或百分比|
|font-style |字体风格|normal(普通),italic(斜体),oblique(倾斜)|
|font-weight|字体加粗|normal,bold,bolder,lighter|
|font-variant|字体变形|normal(普通),small-caps(小型大写字母)|

######2.颜色属性

|属性|描述|属性值|
|----|----|------|
|color|颜色|blue;#000080;#0C0;|

######3.背景属性

|属性|描述|属性值|
|----|----|------|
|background-color|背景颜色|green|
|background-image|背景图像|图片URL或none(无)|
|background-repeat|背景重复|repeat,repeat-x,repeat-y,no-repeat|
|background-attachment|背景附件|scroll(滚动)或fixed(固定)|
|background-position|背景位置|横向的关键字(left,center,right),纵向的关键字(top,center,bottom),百分比和长度也可用作安排背景图像的位置|

######4.文本属性

|属性|描述|属性值|
|----|----|------|
|letter-spacing|字母间隔|该值必须符合长度格式,允许使用负值|
|word-spacing|文字间隔|该值必须符合长度格式,允许使用负值|
|text-decoration|文字修饰|underline(下划线),overline(上划线),line-through(删除线),blink(闪烁),默认无|
|text-align|横向排列|left,right,center,justify|
|text-indent|文本缩进|该值必须是一个长度或一个百分比,若为百分比则视上级元素的宽度而定|
|line-height|行高|可以接受一个控制文本基线之间的间隔的值.当值为数字时,行高由元素字体大小的量与该数字相乘所得.百分比的值相对于元素字体的大小而定.不允许使用负值|

######5.边框属性

|属性|描述|属性值|
|----|----|------|
|border-style|边框风格|none,dotted(点线式边框),dashed(破折线式边框),solid(直线式边框),double(双线式边框),groove(槽线式边框),ridge(脊线式边框),inset(内嵌效果的边框),outset(突起效果的边框)|
|border-width|边框宽度|关键字或长度,不允许使用负值长度|
|border-color|边框颜色|green|

######6.列表属性

|属性|描述|属性值|
|----|----|------|
|list-style-type|引导列表项的符号类型|disc,circle,square|
|list-style-image|使用图像作为列表项的符号|URL|
|list-style-position|决定列表项目缩进的程度|长度值|

