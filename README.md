# camQfix
Q camera fix for LG G4
I'm not sure if all these are needed yet, but my camera works:

In CameraWrapper change line 786 to

camera_device->base.common.version = HARDWARE_DEVICE_API_VERSION(3, 2);

In g4.mk under #camera add
line 78 camera.device@3.2-impl \ and
line 82 android.hardware.camera.provider@2.4-imp-legacy\

In BoardConfigCommon.mk
under #camera 
Hashtag out lines 93 nad 94

in #Display also added back these lines105-108

MAX_EGL_CACHE_KEY_SIZE := 12*1024

MAX_EGL_CACHE_SIZE := 2048*1024

NUM_FRAMEBUFFER_SURFACE_BUFFERS := 3

TARGET_USES_ION := true


   
In #shims -change line 214 deleting word "vendor"
to:  /system/vendor/lib/hw/camera.msm8992.so|/system/vendor/lib/libfence_shim.so \

+++that was all it took to get camera working!+++


