---
title: React 에서 svg 파일 사용하기
date: "2021-09-14"
description: "svg를 컴포넌트화하여 사용할 수 있다."
---

## svg 란?
>svg는 벡터 그래픽 이미지 형식으로 XML을 기반으로 하고 있다.  
>svg :  Scalable Vector Graphics

## React 에서 svg를 사용하기
리액트 아이콘을 어떤식으로 사용할까 고민하다가  svg를 사용해보기로 했다.  
svg를 사용하는 방법에도 여러가지가 있다.

- 이미지 태그에 넣어 사용하기
- 컴포넌트화하여 사용하기
- svg 태그사용하기
- SVGR 사용하기
...etc 

나는 컴포넌트로 svg를 사용하기로 결정했다.(그러면 나중에 커스텀할 때도 편하다고..)  
컴포넌트처럼 사용한는 방법은 간단하다. 원하는 svg 파일을 저장하고 다음과 같이 import 하여 사용한다.
```js
import {ReactComponent as Home} from './home.svg';

<div>
  <Home/>
</div>

```
*create-react-app*에서만 작동한다는 것을 기억하자. *create-react-app* 내부에서 SVGR을 사용하기 때문에 리액트 컴포넌트로 svg를 변형하고 import를 해서 쓰는 것이 가능해진다.

++ 추가 - 2021.09.23  
svg 컴포넌트를 커스텀해서 쓰게 되었다.
svg 파일을 확인해보면, fill, stroke 부분에 색이 들어가 있는걸 볼 수 있는데 이 부분을 ```"current"```로 변경해주고
컴포넌트 사용할때 fill, stroke props에 원하는 색상을 넣어주면 색상을 변경하여 커스텀해서 쓸 수 있다. 