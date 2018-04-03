### 이슈

---

\* 인디케이터는 NV인디케이터를 사용함
로직은 API통신을 시작할 때와 끝날 때의 시점을 잡아서 true / false값으로 인디케이터를 동작 / 정지 하는 형태로 되어있다.

뷰모델의 isLoading 값

```swift
var isLoading  : Observable<Bool> { return requestId.asObservable().map({ $0 != nil})}
```

뷰컨트롤러의 인디케이터 동작로직

```swift
func initIsLoading() {
self.viewModel.isLoading.bindOnMain { [weak self] (isLoading) in
if isLoading {
self?.startAnimating()
if let valueIsEmpty = self?.viewModel.cellTypes.value.isEmpty {
if valueIsEmpty {
self?.tableView?.tableFooterView?.isHidden = true
}
}
} else {
self?.stopAnimating()
self?.tableView?.tableFooterView?.isHidden = false
}
}.disposed(by: disposeBag)
}
```

이슈의 발생지점은 viewDidLoad()에서 뷰모델에 있는 API통신하는 함수를 직접 호출하면서 시작됬다.

다른 경우에는 API통신 함수를 직접 호출하여도 정상적으로 블락(인디케이터)가 동작하였지만

\* 이 뷰의 경우에는 네비가 달려있는 뷰 계층구조에 프레젠트 방식으로 네비를 하나 더 달고 뿌려지는 방식이었다.

그래서 인디케이터 뷰가 정상적으로 현재뷰에 안붙고 이전뷰에 붙거나 현재뷰에 붙으면 붙자마자 사라지는 이슈가 발생했다.

RX를 쓰기때문에 데이터바인딩이 너무 빨리 끝나버려서 생기는 이슈였다.

### 해결방법

---

뷰모델에 있는 API통신하는 함수를 직접 호출하지 않고

```swift
let sequence: BehaviorRelay<Int?>  = BehaviorRelay<Int?>(value: nil)
```

```swift
func initSequenceObservable() {
self.viewModel.sequence.bindOnMain { [weak self] _ in
self?.viewModel.loadDetailData()
}.disposed(by: disposeBag)
}
```

시퀀스를 옵져버해서 값이 accept되면 API통신을 하게 수정하니 해결되었다.

