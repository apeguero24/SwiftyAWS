# SwiftyAWS
A swifty wrapper around the AWS S3 framework that will make storing files (images, videos, etc) easier. 

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Support](#support)
- [Contributing](#contributing)

## Installation

Using Cocoapods:

```
pod 'SwiftyAWS', :git => 'https://github.com/apeguero24/SwiftyAWS.git'
```

## Usage

SwiftyAWS is a simple to use wrapper library around the iOS native AWS SDK. One of the main issues found when using the AWS SDK out of the box is the obvious divergence from modern swift best practices and conventions. 

***Singleton Usage:***

```swift
SwiftyAWS.main.upload(image: image, type: .png, name: .effient, permission: .publicReadWrite) { (path, error) in
    if error != nil {
        print(error!)
        return
    }
}
```
***UIImage Extension Usage:***

```swift
let image = UIImage(named: "lion.jpg")
image?.s3.upload(type: .png, name: .effient, permission: .publicReadWrite, completionHandler: { (path, error) in
    if error != nil {
        print(error!)
        return
    }
})
```

***File Types:***
At the moment SwiftyAWS only supports PNGs and JPEGs, adding more file formats in the near future (pull requests would be appreciated):
```swift
.png
.jpeg

```

## Support

Please [open an issue](https://github.com/apeguero24/SwiftyAWS/issues/new) for support.

## Contributing

Please contribute using [Github Flow](https://guides.github.com/introduction/flow/). Create a branch, add commits, and [open a pull request](https://github.com/apeguero24/SwiftyAWS/compare/).
