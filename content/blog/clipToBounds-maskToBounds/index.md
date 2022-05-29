---
title: "[UIKit] clipToBounds vs. maskToBounds"
date: "2022-05-28T18:51:00.000Z"
description: clipToBounds 와 maskToBounds 의 차이를 알아보자
estimated: 5 min
tags: iOS
---

clipToBounds vs. maskToBounds

1. 둘은 같다

- 어셈블리 분석 이야기

2. 실제 같은지 테스트한 예제 소개
3. clipToBounds 왜 필요할까?

- UIView 의 역할 소개
- CALayer 역할 및 Container 로써의 UIView
  - 복잡한 UI 설정 기능은 layer 를 통해 접근하게 하고 필요한 것을 제외한 나머지는 감출 의도
- Macos/iOS 의 UIView & NSView & CALayer

### 참고자료

[UIView - Apple Official Document](https://developer.apple.com/documentation/uikit/uiview)
[How does clipsToBounds work?](https://stackoverflow.com/questions/20449256/how-does-clipstobounds-work/20449468#20449468)
[What are the differences between a UIView and a CALayer?](https://stackoverflow.com/questions/7826306/what-are-the-differences-between-a-uiview-and-a-calayer/7827488#7827488)
[How is the relation between UIView's clipsToBounds and CALayer's masksToBounds?](https://stackoverflow.com/questions/1177775/how-is-the-relation-between-uiviews-clipstobounds-and-calayers-maskstobounds/1177978#1177978)
[When to use CALayer on the Mac/iPhone?](https://stackoverflow.com/questions/1447598/when-to-use-calayer-on-the-mac-iphone/1449201#1449201)
