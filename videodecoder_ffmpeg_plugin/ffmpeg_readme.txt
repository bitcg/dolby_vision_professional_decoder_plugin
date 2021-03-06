Building the sample FFmpeg decoder plug-in

Before you build the plug-in, check out the Dolby GitHub repository at https://github.com/
DolbyLaboratories/dolby_vision_professional_decoder_plugin. The FFmpeg files you need are contained in
the hevc_ffmpeg_plugin directory.

1.1 Building the plug-in on Microsoft Windows
These steps describe how to build a decoder plug-in on Microsoft Windows.

Prerequisites
Before you begin building the sample FFmpeg decoder, download the FFmpeg source files and build the binaries.
CMake version 3.5 or higher is required for the following building steps.

Procedure
	1. inside the 'dolbyvision_professional_decoder\videodecoder_ffmpeg_plugin' folder create a new directory .\ffmpeg 
	2. For every C header and library file in the FFmpeg package, copy files from FFmpeg to this directory as shown:
		• ffmpeg\lib\avcodec.lib
		• ffmpeg\lib\avutil.lib
        • ffmpeg\lib\avformat.lib
		• ffmpeg\include\libavcodec	
		• ffmpeg\include\libavformat
		• ffmpeg\include\libavutil
	3. In the 'dolbyvision_professional_decoder\videodecoder_ffmpeg_plugin', create a 'build' directory.
	4. Change to the build directory and open a command-line window.
	5. Use CMake to build the files. Specify the platform and toolchain. This example uses a Microsoft Visual Studio 2017 toolchain and x64 architecture.

		cmake .. -A x64 -T v141

	6. Build the sample plug-in using either the command line or an integrated development environment.
		• On the command line, specify either a debug version or a release version.
			cmake --build . --config Debug
			cmake --build . --config Release
		• In the integrated development environment, open the FFmpegVideoDecPlugin.sln solution file and build the sample plug-in there.

Two video decoder plugin shared library files are created. 
		- FFmpegAvcPlugin.dll
		- FFmpegHevcPlugin.dll


1.2 Building the plug-in on Linux
These steps describe how to build a decoder plug-in on Linux.

Procedure
	1. Install libavformat-dev development libraries on your system by using your favourite package manager (e.g. on Ubuntu 16.04 LTS: 'sudo apt install libavformat-dev')
	3. In the ./dolby_vision_professional_decoder_plugin-master/videodecoder_ffmpeg_plugin directory, create a build directory.
	4. Change to the build directory and open a command-line window.
	5. Use CMake to build the files. Specify the build type.
		• cmake .. -DCMAKE_BUILD_TYPE=Debug
		• cmake .. -DCMAKE_BUILD_TYPE=Release
	6. Then build the sample plug-in files.

		cmake --build .
		
	Two video decoder plugin shared library files are created. 
		- libFFmpegAvcPlugin.so
		- libFFmpegHevcPlugin.so
		
		
1.3 Building the plug-in on MacOS
These steps describe how to build a decoder plug-in on MacOS.

Procedure
	0. Prerequisites
		• install homebrew
	1. Install ffmpeg:
		• brew install ffmpeg
	3. In the ./dolby_vision_professional_decoder_plugin-master/videodecoder_ffmpeg_plugin directory, create a build directory.
	4. Change to the build directory and open a command-line window.
	5. Use CMake to build the files. Specify the build type.
		• cmake .. -DCMAKE_BUILD_TYPE=Debug
		• cmake .. -DCMAKE_BUILD_TYPE=Release
	6. Then build the sample plug-in files.

		cmake --build .
		
	Two video decoder plugin shared library files are created. 
		- libFFmpegAvcPlugin.dylib
		- libFFmpegHevcPlugin.dylib