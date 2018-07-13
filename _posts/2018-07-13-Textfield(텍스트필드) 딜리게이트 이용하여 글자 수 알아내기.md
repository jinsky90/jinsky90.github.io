---
layout: post
title: "Textfield(텍스트필드) 딜리게이트 이용하여 글자 수 알아내기"
image: 'https://user-images.githubusercontent.com/38024119/42678500-06073b8c-86ba-11e8-8e70-74fab0c1ddb3.jpg'
category: 'blog'
tag:
- iOS
- Swift
- TextField
- UITextFieldDelegate
---

```swift
extension InfoInputViewController: UITextFieldDelegate {
  func textField(_ textField: UITextField, shouldChangeCharactersIn range: NSRange, replacementString string: String) -> Bool {
      let newLength = (self.pwtextfield.text?.utf16.count)! + string.utf16.count - range.length
    }
  }
```

혹은

```swift
        guard let text = textField.text as NSString? else { return false }
        let replacementString = text.replacingCharacters(in: range, with: string)
        guard replacementString.count < 17 else { return false}
```
