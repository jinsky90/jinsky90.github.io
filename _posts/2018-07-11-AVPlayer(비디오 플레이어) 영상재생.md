```swift
import AVKit

if let path = Bundle.main.path(forResource: "videoName", onType: "videoType") {
    let video = AVPlayer(url: URL(fileURLWithPath: path))
    let videoPlayer = AVPlayerViewController() 
    videoPlayer.player = video
    
    present(videoPlayer, animated: true, completion:
    {
        video.play()   
    })
}
```