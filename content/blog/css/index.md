---
title: CSS display - flex
date: "2022-09-23"
description: "왜 css는 항상 헷갈리는가 "
---

# flex 잘 이용하기
프론트앤드 개발자라면 css, html 은 기본으로 잘 다루어야 한다.  
아직 헷갈리는게 많지만 이번에 개발하면서 flex 를 굉장히 많이 쓰게되어서 그만 헷갈리도록 .. 기초지만 정리를 해보려고 한다.

## 아이템을 담고있는 container 스타일 
```css
display: flex; /* 또는 inline-flex */

/*main-axis 정의 */
flex-direction: row | row-reverse | column | column-reverse;

/* flex item은 한줄에 정렬되는 것이 디폴트, 이를 변경하기 위해서 정의*/
flex-wrap: nowrap | wrap | wrap-reverse;

/*flex-direction + flex-wrap 을 한꺼번에 정의할 수 있음 */
flex-flow: column wrap 

/*main axis 에 맞게 정렬되는 방식을 정의*/
justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly |start | end | left | right

```

|flex-direction |flex wrap      |
|-------------- |-------------- |
|*row(default)*: left to right |*nowrap(default)* : on one line |
|*row-reverse*: right to left | *wrap*: multiple lines, from top to bottom|
|*column* : top to bottom |*wrap-reverse*: multiple lines, from bottm to top|
|*column-reverse*: bottom to top |

justify-content |
|  :----:  |
*flex-start* 는 flex-direction 의 시작방향을 따라 item이 정렬 |
*start*는 writing-mode direction 시작방향에 따라 item이 정렬 |