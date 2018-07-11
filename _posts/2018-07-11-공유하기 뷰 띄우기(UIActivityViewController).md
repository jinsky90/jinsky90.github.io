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