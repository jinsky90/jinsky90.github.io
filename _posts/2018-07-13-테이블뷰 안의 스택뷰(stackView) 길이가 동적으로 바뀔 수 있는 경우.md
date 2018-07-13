---
layout: post
title: "테이블뷰 안의 스택뷰(stackView) 길이가 동적으로 바뀔 수 있는 경우"
image: 'https://user-images.githubusercontent.com/38024119/42678500-06073b8c-86ba-11e8-8e70-74fab0c1ddb3.jpg'
category: 'blog'
tag:
- iOS
- Swift
- StackView
- TableView
- dynamicStackView
---

![스크린샷 2018-04-16 오후 3.50.28.png](https://user-images.githubusercontent.com/38024119/42680236-5c4f858a-86bf-11e8-9401-53e4e61d1bfd.png)

뷰의 height를 주는 경우라던지, 뷰 안의 프로퍼티들의 height를 잡아서 wrapView의 길이를 잡아주는 경우라던지

공통적으로 줄어드는 뷰의 height constraint의 속성을 줄 때 두가지 방법이 있다

첫번째로는

**- Constant**를 height보다 **작거나 같게**

두번쨰로는

**- priority**를 1000(required)가 아닌 750(high) 혹은 250(low)로 줘야한다

특히 테이블뷰의 셀안에 넣을경우 특히특히특히!!!!!!!!!!!!!조심해야 한다!!!!!!!!!!!꼭 잊지말자
