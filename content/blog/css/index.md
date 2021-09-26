---
title: CSS display - flex
date: "2022-09-23"
description: "왜 css는 항상 헷갈리는가 "
---

# flex 잘 이용하기
프론트앤드 개발자라면 css, html 은 기본으로 잘 다루어야 한다.  
아직 헷갈리는게 많지만 이번에 개발하면서 flex 를 굉장히 많이 쓰게되어서 그만 헷갈리도록 .. 기초지만 정리를 해보려고 한다.

## Properties for the Parent (container)
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

/*cross axis에 맞게 정렬되는 방식을 정의 */
align-items: stretch | flex-start | flex-end | center | baseline | first baseline | last baseline | start | end | self-start | self-end 

/*cross axis에 여유공간이 있을 때 flex container 를 정렬 */
align-content: flex-start | flex-end | center | space-between | space-around | space-evenly | stretch | start | end | baseline | first baseline | last baseline

/* gap 속성은 flex item 간의 간격을 조절해줌 , item 간의 간격만 조정!! not on the outer edges */
gap : 10px;  /*이런식 */
```

|flex-direction |flex wrap      |
|-------------- |-------------- |
|*row(default)*: left to right |*nowrap(default)* : on one line |
|*row-reverse*: right to left | *wrap*: multiple lines, from top to bottom|
|*column* : top to bottom |*wrap-reverse*: multiple lines, from bottm to top|
|*column-reverse*: bottom to top |

justify-content |align-itmes |
|--------------|-----------|
*flex-start* 는 flex-direction 의 시작방향을 따라 item이 정렬 | *stretch* : 디폴트 값 
*start*는 writing-mode direction 시작방향에 따라 item이 정렬 |

## Properties for the Children (flex items)

```css

/*flex container 순서 조작 , 같은 order인 아이템이 source order로 바뀜?*/
order : 5; /*디폴트 : 0 */

/* flex item to grow , negative numbers are invalid */
flex-grow: 2; /*디폴트 : 0 */

/*flex item to shrink */
flex-shrink: 3; /*디폴트 1 */

/*남은 공간을 배분하기 전에 한 요소가 가지는 기본 크기를 정의 */
flex-basis:  | auto; /* default auto */

/*flex-grow, flex-shrink, flex-basis 합친거  2,3번쨰 param 생략 가능 */
flex: 0 1 auto; /*디폴트값*/

/*정의된 정렬방식을 override할 수 있음 */
align-self: auto | flex-start | flex-end | center | baseline | stretch;
```
*float, clear, vertical-align 은 flex item에 아무 영향을 주지 못한다*

--09.26일 작성완료 