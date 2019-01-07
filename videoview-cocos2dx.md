# Cocos2dxVideoView.java

## [SurfaceView][1]

```java
public class Cocos2dxVideoView extends SurfaceView
...
```

> One of the purposes of this class is to provide a surface in which a secondary thread can render into the screen.

* a *SurfaceView* is a view in your view hierarchy that has its own sperate *Surface*.
* You can draw to *SurfaceView* in a sperate thread.

## [SurfaceHolder.Callback][2]

```java
SurfaceHolder.Callback mSHCallback = new SurfaceHolder.Callback()
    {
        public void surfaceChanged(SurfaceHolder holder, int format,
                                    int w, int h)
        {
            boolean isValidState =  (mTargetState == STATE_PLAYING);
            boolean hasValidSize = (mVideoWidth == w && mVideoHeight == h);
            if (mMediaPlayer != null && isValidState && hasValidSize) {
                if (mSeekWhenPrepared != 0) {
                    seekTo(mSeekWhenPrepared);
                }
                start();
            }
        }

        public void surfaceCreated(SurfaceHolder holder)
        {
            mSurfaceHolder = holder;
            openVideo();
        }

        public void surfaceDestroyed(SurfaceHolder holder)
        {
            // after we return from this we can't use the surface any more
            mSurfaceHolder = null;
            release(true);
        }
    };

    private void initVideoView() {
        ...
        getHolder().addCallback(mSHCallback);
        ...
    }
```

[1]:https://developer.android.com/reference/android/view/SurfaceView "Surface View - Android Docs"
[2]:https://developer.android.com/reference/android/view/SurfaceHolder.Callback "SurfaceHolder.Callback - Android Docs"
[3]:https://developer.android.com/guide/topics/media/mediaplayer "MediaPlayer overview - Android Docs"

## [MediaPlayer State Diagram][4]

![State Diagram](videoview-cocos2dx/mediaplyer_)

[4]:https://developer.android.com/reference/android/media/MediaPlayer#state-diagram "MediaPlayer State Diagram - Android Docs"