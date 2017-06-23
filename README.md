# VuforiaSampleSwift

Vuforia sample code with SceneKit using Swift.

## Requirement

* Xcode 8.3
* iOS 10.3
* Vuforia SDK for iOS v6.2.9

## Setup

* Download Vuforia SDK for iOS.  
  [Vuforia SDK](https://developer.vuforia.com/downloads/sdk)
* Delete vuforia-sdk-ios-6-2-9  
* Put the SDK on your path as like bellow:  
  `VuforiaSampleSwift/VuforiaSampleSwift/vuforia-sdk-ios-6-2-9`
* If you needs to fix to links to these files and settings in project, fix it.  
  If you failed to build, check `Header Search Paths` and `Libarary Search Paths` in Build Settings.
* Set your `lincenseKey` in ViewController.swift.


## Usage

See ViewController.swift.

``` swift

vuforiaManager = VuforiaManager(licenseKey: "your license key", dataSetFile: "your target xml file")
if let manager = vuforiaManager {
    manager.delegate = self
    manager.eaglView.sceneSource = self
    manager.eaglView.delegate = self
    manager.eaglView.setupRenderer()
    self.view = manager.eaglView
}

vuforiaManager?.prepareWithOrientation(.Portrait)

...

do {
    try vuforiaManager?.start()
}catch let error {
    print("\(error)")
}

```