>比较 块级元素-行内元素-行内块元素

   |  块级元素   | 行内元素  |  行内块元素 |
   |  :-:  | :-:  | :-:  | 
   |div hn p pre hr|b em i span|input|
   |设置宽高有效|设置宽高无效，宽高靠内容撑开|设置宽高有效||
   |单独成行|其他行内元素和行内块共用一行|其他行内元素和行内块共用一行|
   |默认宽度是父元素100%. 不设置高度,高度靠内容撑开.没有内容且高度为0时,页面上不可见|宽度靠内容撑开|默认自带宽高，但是不同浏览器给的默认值不同|
   |4个方向外边都有效|上下外边距无效|4个方向外边距都有效.改变一个行内块的上下外边距，这个行内块会带着同一行的其他行内元素，行内块元素一起移动|