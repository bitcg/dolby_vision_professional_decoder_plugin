# This repository provides additional code examples for the Dolby Vision professional decoder SIDK
 
 ## FFMPEG based H.265 video decoder plug-in 
The Dolby Vision professional decoder SIDK features a plug-in concept to support third-party video decoders.
The folder 'hevc_ffmpeg_plugin' contains example code for implementing a FFMPEG based H.265 video decoder plug-in.
Please refer to 'ffmpeg_readme.txt' for details on how to build the plug-in.

## Dolby Vision Professional decoder Gstreamer element example
The folder 'gstreamer_example'contains an example for building a Gstreamer element for decoding Dolby Vision video elementary streams.
Dual layer stream support is not implemented. This example may be a good base for adding this feature, however.

