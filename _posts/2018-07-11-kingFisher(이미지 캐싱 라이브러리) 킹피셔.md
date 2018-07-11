---
layout: post
title: "kingFisher(이미지 캐싱 라이브러리) 킹피셔"
description: Lorem ipsum dolor sit amet, consectetur adipisicing elit.
image: 'http://res.cloudinary.com/dm7h7e8xj/image/upload/c_scale,w_760/v1504807239/morpheus_xdzgg1.jpg'
category: 'blog'
tag:
- iOS
- Swift
- kingFisher
- 이미지 캐시
- 킹피셔
twitter_text: Lorem ipsum dolor sit amet, consectetur adipisicing elit.
introduction: Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
---

iOS 이미지 캐싱 라이브러리에는 여러가지가 있지만 많이 사용되는 것들로는

- kingFisher(킹피셔)

- sdWebImage

- alamofireImage

등등이 많이 사용되어 진다.

기존에 api 통신 라이브러리로 alamoFire를 사용한다면 alamoFireImage를 사용해도 나쁘지는 않다.

보통 가장 많이 사용되어 지는 라이브러리는 kingFisher이다.

sdWebImage는 kingFisher가 나오기 전에는 많이 사용했지만

KingFisher가 나오면서 기존의 sdWebImage사용자들은 거의 대부분 kingFisher로 바꾸게 되었다.

바꾸게 된 이유는 여러가지가 있다

- kingFisher -\> swift / sdWebImage -\> objective C 로 되어있기 때문에 swift 네이티브로 구현되어 있는 앱은 사용자에겐 kingFisher가 더 빠른 체감을 느끼게 한다.

- 사용자들이 kingFisher를 채용한 가장 큰 이유는 캐싱된 이미지들을 삭제하는 로직자체에서 사이드이슈가 많이 발생해서 kingFisher를 더 많이 사용한다.

빠르고 이슈가 더 적은 kingFisher를 swift개발자들은 사용하지 않을 이유가 없는것이다.

kingFisher는 한번 다운로드 된 이미지는 이미지캐시 / 디스크캐시에 저장해 두었다가 같은 이미지가 불려올 때는 내부적으로 판단하여

이미 다운로드된 이미지를 사용하게 된다.

그리하여 굳이 이미 다운로드 받은 이미지를 데이터를 소비하며 받을 필요가 없는것이다.

보통 사용자나 개발자가 많이 사용되진 않지만 굳이 캐싱되어 있는 이미지를 지우고 싶을 경우 사용하는 메소드를 제공하고 있다.

```swift
// Clear memory cache right away.
cache.clearMemoryCache()

// Clear disk cache. This is an async operation.
cache.clearDiskCache()

// Clean expired or size exceeded disk cache. This is an async operation.
cache.cleanExpiredDiskCache()
```

보통적으로 kingFisher는 메모리 경고를 받으면 메모리 캐시를 제거하고 필요한 경우 만료되고 크기가 초과 된 캐시를 자동으로 정리합니다.

때문에 일반적으로는 캐시를 직접 정리 할 필요가 없습니다.
