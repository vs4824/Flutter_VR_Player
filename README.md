# Flutter VR Player

VR Player Plugin for Flutter

## Getting Started

Based on Kaltura Playkit SDK.

The VrPlayer plugin lets you play 360° and VR videos smoothly on Android and iOS platforms, delivering an immersive viewing experience with touch and device motion controls. These types of videos, commonly referred to as immersive, 360, or spherical videos, are captured by utilizing an omnidirectional camera or multiple cameras to record the entire panoramic view simultaneously.

## Usage

   ```
   VrPlayer(
  x: 0,
  y: 0,
  onCreated: onViewPlayerCreated,
  width: playerWidth,
  height: playerHeight,
),
   ```

You must implement onViewPlayerCreated to receive player events.

   ```
   void onViewPlayerCreated(
  VrPlayerController controller
  VrPlayerObserver observer
) {
  this.viewPlayerController = controller;
  /// Receive player state [loading, ready, buffering]
  observer.handleStateChange(this.onReceiveState);
  /// Receive duration in millis
  observer.handleDurationChange(this.onReceiveDuration);
  /// Receive current position in millis
  observer.handlePositionChange(this.onReceivePosition);
  /// Receive when video is finished
  observer.handleFinishedChange(this.onReceiveFinished);
  this.viewPlayerController.loadVideo(
    videoUrl: "https://cdn.bitmovin.com/content/assets/playhouse-vr/m3u8s/105560.m3u8"
  );
}
   ```

### VrPlayerController

The VrPlayerController can be used to change the state of a VrPlayer Note that the methods can only be used after the VrPlayer has been created.
