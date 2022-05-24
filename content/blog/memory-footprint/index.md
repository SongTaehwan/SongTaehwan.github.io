---
title: "[CS] Memory Footprint 🛠"
date: "2022-05-24T15:45:00.000Z"
description: Footprint 는 메모리(RAM)에서 애플리케이션이 차지하는 크기를 의미한다.
estimated: 1 min
tags: 글조각
---

Footprint 는 메모리(RAM)에서 애플리케이션이 차지하는 크기를 의미한다.

Footprint 의 학술적 정의는 모든 종류의 메모리와 Storage를 포함하고 있지만, 실제로는 대게 Heap(dynamic 메모리) 와 디스크에서 로드된 리소스는 포함하지 않는다.

왜냐하면 Dynamic 메모리 할당은 애플리케이션이나 모듈이 메모리를 어떻게 사용하느냐에 따라 메모리 크기가 달라지기 때문이다. 때문에 `low footprint`, `high footprint` 라는 말의 의미에는 요구되는 메모리 공간이 불변함을 내포한다.

- 높다, 낮다라고 표현하려면 판단할 기준이 필요한데 Footprint 의 크기가 가변적이라면 높낮이의 기준으로 사용되기 어렵다.
- 예를 들어, Heap 을 Footprint 에 포함시킨다면, 이미지 에디터 앱의 footprint 는 애플리케이션에 로드하는 이미지 크기에 따라 완전히 달라진다.

써드 파티 라이브러리의 경우, 라이브러리의 Memory Footprint 최적화를 위해 필요 이상의 코드를 애플리케이션 바이너리에 포함시키않는 방식을 사용한다.

C 언어의 경우, 라이브러리 함수를 별도의 c-file 로 배분(distribute)한다. 대부분의 C Linker 는 개발자가 호출한 함수뿐만아니라 c-file 의 명시된 모든 코드를 애플리케이션에 링킹한다.

c-file 에 하나의 함수만을 명시한다면, linker 는 해당 함수만 애플리케이션에 포함시킨다. 만약 5개의 함수를 c-file 에 명시한다면, 실제로 5개 중 하나만을 사용하더라도 linker 는 5개 모두 애플리케이션에 포함시킨다.

### 참고자료

[What is meaning of small footprint in terms of programming?](https://stackoverflow.com/questions/1618065/what-is-meaning-of-small-footprint-in-terms-of-programming/1618070#1618070)
