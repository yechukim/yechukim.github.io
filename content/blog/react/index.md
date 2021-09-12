---
title: 리액트 Composition 
date: "2022-09-06"
description: "패스트 캠퍼스 강의 "
---

# 목차
1. Compositon
2. HOC

## Composition 
- 컴포넌트를 담기 
- typeof -> type check 
- 확장성 -> 다양한 상황을 품을 수 있다. 

## HOC 고차 컴포넌트
: High Order Component

복잡하게 느껴지지만 간단하게 생각하자.
고차 컴포넌트는 컴포넌트를 가져와 새 컴포넌트를 반환하는 함수이다. 
- HOC -> 함수를 받아서 함수를 리턴 

```javascript

import React, { useState, useEffect } from 'react'

//얘는 컴포넌트가 아니라 함수 
export default function withLoading(Component) {// 컴포넌트를 받아서 

  const WithLoadingComponent = (props) => {

    const [loading, setLoading] = useState(true)

    useEffect(() => {
      const timer = setTimeout(() => setLoading(false), 1000)
      return () => clearTimeout(timer)
    }, [])

    return loading ? <p> loading ... </p> : <Component {...props} />
  }
  return WithLoadingComponent
//컴포넌트를 리턴한다.. 
}
```
## Memoization 
: 메모이제이션이란 컴퓨터 프로그램이 동일한 계산을 반복해야 할 떄, 이전에 계산한 값을
메모리에 저장! 함으로써 동일한 계산의 반복 수행을 제거하여 프로그램 실행 속도를
빠르게 하는 기술이다. 

### React.memo
동일한 prop으로 렌더링을 한다면 memo를 사용하여 성능향상
- HOC/ Props 비교해서 메모
- Profiler 리액트 성능 분석 도구
- callback -> 함수를 메모이제이션하고 싶을 떄 useCallback
- value -> 변수를 메모이제이션하고 싶을 때 useMemo

## Context 
- context를 이용하면 일일이 props를 넘겨주지 않고 트리 전체에 데이터를 제공할 수 있다. 
- 전역적인 데이터를 관리할 때 쓰는게 좋다. 