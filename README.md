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

### Animate frame and center properties.

```swift
UIView.animate(withDuration: 5.0) {
    square.center = CGPoint(x: 300, y: 300)
    square.frame = CGRect(x: 100, y: 100, width: 200, height: 200)
    //Take a look how prioritize the origin, 300 vs 100
}
```

# Add a completion Handler

- Similar to animations parameter, completion is also a closure.
- Completion closure is executed after your animations have completed (as the name suggest)

```swift
UIView.animate(withDuration: 5.0, animations: {
    square.backgroundColor = .orange
    square.frame = CGRect(x: 150, y: 150, width: 200, height: 200)
}) { (_) in
    UIView.animate(withDuration: 5.0, animations: {
        square.backgroundColor = .purple
        square.frame = smallFrame
    })
}
```

# Add a delay or custom options

```swift
UIView.animate(withDuration: 5.0, delay: 2.0, options: [.repeat], animations: {
    square.backgroundColor = .orange
    square.frame = CGRect(x: 400, y: 400, width: 100, height: 100)
}, completion: nil)
```

# The Transform Property

- The transform property is an instance of the structure CGAffineTransform.
- It is used to change the scale, rotate or move the view without calculating changes to the view's frame.

### An Affine transform is a 3x3 matrix that maps each point in an untransformed view to another point, resulting in a transformed view.

- You won't need an advanced math degree to use them.






