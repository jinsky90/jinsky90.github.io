---
layout: post
title: "테이블뷰 헤더뷰(headerView)/푸터뷰(footerView) 에러"
image: 'https://user-images.githubusercontent.com/38024119/42678500-06073b8c-86ba-11e8-8e70-74fab0c1ddb3.jpg'
category: 'blog'
tag:
- iOS
- Swift
- HeaderView
- TableView
---

테이블뷰의 헤더뷰와 푸터뷰의 길이를 상황별로 바꾸고싶을때 iOS에서는 제대로 동작하지 않는다.

이건 iOS자체 에러이다

이경우 2가지의 해결방법이있다

- 코드로 헤더/푸터뷰의 길이를 주던가

- 셀로 바꾸던가

아래의 코드는 헤더/푸터뷰의 길이를 잡아준 코드이다.

```swift
override func viewDidLayoutSubviews() {
    super.viewDidLayoutSubviews()

    if let headerView = tableView.tableHeaderView {

        let height = headerView.systemLayoutSizeFitting(UILayoutFittingCompressedSize).height
        var headerFrame = headerView.frame

        //Comparison necessary to avoid infinite loop
        if height != headerFrame.size.height {
            headerFrame.size.height = height
            headerView.frame = headerFrame
            tableView.tableHeaderView = headerView
        }
    }
}
```
