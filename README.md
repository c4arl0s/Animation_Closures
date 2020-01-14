# Animation_Closures
Animation_Closures

```swift
UIView.animate(withDuration: TimeInterval, animations: () -> Void)
UIView.animate(withDuration: TimeInterval, animations: () -> Void, completion: ((Bool) -> Void)?((Bool) -> Void)?(Bool) -> Void)
UIView.animate(withDuration: TimeInterval, delay: TimeInterval, options: UIView.AnimationOptions, animations: () -> Void, completion: ((Bool) -> Void)?)
```

# UIView

Properties you can animate on UIView class

- frame
- bounds
- center
- transform
- alpha
- backgroundColor

# Animate with duration

```swift
import UIKit
import PlaygroundSupport

let liveViewFrame = CGRect(x: 0, y: 0, width: 500, height: 500)
let liveView = UIView(frame: liveViewFrame)
liveView.backgroundColor = .white
PlaygroundPage.current.liveView = liveView

let smallFrame = CGRect(x: 0, y: 0, width: 100, height: 100)
let square = UIView(frame: smallFrame)
square.backgroundColor = .purple
liveView.addSubview(square)

UIView.animate(withDuration: 5.0) {
    square.backgroundColor = .orange
}
```


