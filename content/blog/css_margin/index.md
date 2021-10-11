---
title: auto margin의 사용
date: "2021-10-11"
description: "nav bar에서 잘 사용할 수 있겠다."
---
# auto margin 의 사용

navigation bar 에서 흔한 패턴을 생각 해보면, main은 왼쪽, 나머지는 오른쪽에 정렬하는 경우가 있다. 아래의 이미지를 보면 ```justify-self```를 사용한 것이 아닌가 하겠지만, 이렇게 쓴다면 d 뒤에의 e 마저의 정렬까지도 바뀌어버리고 만다.

![auto margin 을 사용하여 정렬](./align7.png)

이 경우 아이템 d에 ```margin-left: auto;```를 주면 된다.  