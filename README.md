# Beaglebone-black-OpenCV-installation
Installation of OpenCV on Beaglebone black 

Installing Opencv 2.4.10 is not different from normal ubuntu PC.Copy from internel. 

sudo apt-get update
sudo apt-get upgrade

install dependencies:

sudo apt-get install build-essential libgtk2.0-dev libjpeg-dev libtiff4-dev libjasper-dev libopenexr-dev cmake python-dev python-numpy python-tk libtbb-dev libeigen3-dev yasm libfaac-dev libopencore-amrnb-dev libopencore-amrwb-dev libtheora-dev libvorbis-dev libxvidcore-dev libx264-dev libqt4-dev libqt4-opengl-dev sphinx-common texlive-latex-extra libv4l-dev libdc1394-22-dev libavcodec-dev libavformat-dev libswscale-dev default-jdk ant libvtk5-qt4-dev

Download latest OpenCV and extract to PC. Transfer the file to BBB by scp command. 

1 cd opencv
2 mkdir build && cd build
3 cmake -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=/usr/local -D WITH_CUDA=OFF -D WITH_CUFFT=OFF -D WITH_CUBLAS=OFF -D WITH_NVCUVID=OFF -D WITH_OPENCL=OFF -D WITH_OPENCLAMDFFT=OFF -D WITH_OPENCLAMDBLAS=OFF -D BUILD_opencv_apps=OFF -D BUILD_DOCS=OFF -D BUILD_PERF_TESTS=OFF -D BUILD_TESTS=OFF -D ENABLE_NEON=on ..
4 make
5 sudo make install
6 sudo ldconfig
 
 
 For C++ or python programming, Geany is a slim and quick tool. 
 To configure with OpenCV, add the include and link folder to the compile and build settings 
 -I /usr/local/include/opencv -I /usr/local/include/opencv2 -L /usr/local/lib -lopencv_core -lopencv_highgui -lopencv_imgproc 
