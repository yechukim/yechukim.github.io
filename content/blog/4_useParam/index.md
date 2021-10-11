---
title: useParam을 사용하여 param 값을 바라보기 
date: "2021-09-13"
description: "어제 해결했다고 생각했던 문제가 해결되지 않았던 것이었다."
---

## 왜 useParams ?

오늘 업무를 하다가 useLocation이 내가 원하는 작업이 아니라는 것을 깨닫고, 
useParams으로 다시 코드를 작성했다. 어떤 부분이 달랐는지 적어보려 한다.

### useLocation 을 사용했을 때
먼저 내가 작업했던 코드는 하단에 탭 메뉴가 있고, 각 탭 클릭시, routes.js 에 정의된 해당 경로로 이동한다 

여기서 1번째 탭을 클릭했을 때 리스트 화면이 나온다.
해당 리스트를 클릭하면 해당 아이템의 화면이 뜬다. 
여기서 route 에는 해당 아이템의 id가 추가된다.  
어제는 items(lists) -> an item 으로 이동할 때 history로 push를 하면서 state를 넣어준 후, 이동한 페이지에서 useLocation()을 사용하여 state를 받아왔다.  

하지만 이 방법은 문제가 있는 것이, 아이템 페이지 안에 또 다른 페이지로 이동하는 경우, 그 페이지로 이동했다가 아이템 페이지로 이동하면 state를 받아오지 못했고, 페이지 이동시마다 state를 넣어주어야 하는 번거로움이 있었다.

또한, 모든 페이지를 routes.js 에 정의해주었기 때문에 저렇게 할 필요도 없기도 했다... 
방법을 찾아보니 ```useParams()```이라는 것이 있었다.

### useParams 사용하기
> useParams 는 URL 파라미터의 key/value 객체를 리턴한다.
> 현재 <Route> 의 match.params에 접근하기 위해 사용한다.

즉, routes.js 에는 각각의 페이지에 대한 경로가 정의되어 있으니, 경로에 param을 잘 설정해주고,
이동할 페이지에서 ```useParams()```를 사용하여 URL 의 파라미터를 가져올 수 있다.  
지금보니 어제작성한 코드는 삽질처럼 보이지만 확실히 하나 배우게 되었다. :fire: :blush:

#### example 

```js
 const params = useParams() 
//userId를 body에 넣어 호출해야 하는 경우 
//userId는 URL에 있을 것이기 때문에 이것만 바라보면 된다 
//아마 아이디는 암호화 해야겠지만..
 dispatch(getUsers.call({ userId: params.userId }))

```
