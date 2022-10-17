# Traveling 

I have lucky enough to see a large part of this world and I'd love to share my Experiences with you! I've been to **every European country** and through some of **Latin America!** 

### My Top 3 Countires That I've Visited Are:

- [**Swedan**](https://en.wikipedia.org/wiki/Sweden)
- [**Panama**](https://en.wikipedia.org/wiki/Panama)
- [**Czech Republic**](https://en.wikipedia.org/wiki/Czech_Republic)

## This Past Summer 

Over the summer of 2022, I had the chance to travel to Europe and backpack for just a little over 3 months! Me and three of my best friends started our journey in *Stockholm, Swedan* and ended in *Amsterdam, Neatherlands.* We as a team visted over 20 countries in that short period of time!

## Photo of Us:

![IMG_0948](https://user-images.githubusercontent.com/115883101/196240440-8f53e998-55a9-416b-b9bd-5f7e68031c8d.JPG)

## Coding in Irland 

While I was in Irland, I was talking a Capstone class for my degree in Information Technolgy and we spent sometime making an app to do photogrammetry. The code we used was in Java and looked a little like this:

```
import Cocoa
import AVFoundation

class ViewController: NSViewController {
@IBOutlet weak var camera: NSView!

override func viewDidLoad() {
    super.viewDidLoad()
    camera.layer = CALayer()
    let session:AVCaptureSession = AVCaptureSession()
    session.sessionPreset = AVCaptureSession.Preset.high
    let device:AVCaptureDevice = (AVCaptureDevice.default(for: AVMediaType.video))!
   // let listdevices = (AVCaptureDevice.devices())


do {
    try session.addInput(AVCaptureDeviceInput(device: device))

    //Preview
    let previewLayer:AVCaptureVideoPreviewLayer = AVCaptureVideoPreviewLayer(session: session)
    let myView:NSView = self.view
    previewLayer.frame = myView.bounds
    previewLayer.videoGravity = AVLayerVideoGravity.resizeAspectFill
    self.camera.layer?.addSublayer(previewLayer)
    session.startRunning()

           // print(listdevices)
            // print(device)
    } catch {
         print(device)
            }


}


override var representedObject: Any? {
    didSet {
    // Update the view, if already loaded.
    }
}


 }
```

If you'd like to continue learning about me, reread the page, or go back to the [home page](README.md), please click one!

- [Learn About Me!](AboutMe.md)
- [Learn About My Work!](MyWork.md)
- [Learn About My Travels!](Travels.md)
- [Learn About My Education!](Education.md)
- [Learn About My Interests!](MyInterests.md)
