---
layout: post
title: "공유하기 뷰 띄우기(UIActivityViewController)"
description: Lorem ipsum dolor sit amet, consectetur adipisicing elit.
image: 'http://res.cloudinary.com/dm7h7e8xj/image/upload/c_scale,w_760/v1504807239/morpheus_xdzgg1.jpg'
category: 'blog'
tag:
- 공유하기
- iOS
- Swift
- UIActivityViewController
twitter_text: Lorem ipsum dolor sit amet, consectetur adipisicing elit.
introduction: Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
---

```swift
  /**------------------------------------------------------------------------------------------
   * @ Method : shareButtonTouched
   * @ Description : 공유하기 버튼 터치시
   * @ Parameters : AnyObject
   * @ Returns : nil
   -------------------------------------------------------------------------------------------*/
  @IBAction func shareButtonTouched(sender: AnyObject) {
    let text = "공유할 내용"
    let textToShare = [text]
    let vc = UIActivityViewController(activityItems: textToShare, applicationActivities: [])
    vc.excludedActivityTypes = [UIActivityTypeAirDrop] // 제외하고 싶은 타입을 설정(optional)

    self.presentVC(vc)
  }
```

윗줄은 못건드리지만 밑에줄은 건들 수 있다.
