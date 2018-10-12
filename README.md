usb_cam [![Build Status](https://api.travis-ci.org/bosch-ros-pkg/usb_cam.png)](https://travis-ci.org/bosch-ros-pkg/usb_cam)
=======

### **Note about no_jpeg_decompression branch**

#### Difference from other branches
* if ~publish_packet is true, usb_cam_node will enter the packet mode
* in the packet mode, the decompression of packets from the camera, which highly consumes the cpu, will not be performed
* instead of the decompression, raw packets will be published as sensor_msgs/CompressedImage
* the packet topic can be subscribed using the compressed_image_transport if the packet's format is supported by the subscriber

#### Additionally-published topics
**~packet/<user-defined>** (sensor_msgs/CompressedImage)
* streams raw packets from the camera
* published only if the node in the packet mode

#### Additional paramters
**~publish_packet** (bool, default: false)
* the packet mode is enabled if true

**~packet_transport** (string, default: "compressed")
* leaf topic name of packet messages

### A ROS Driver for V4L USB Cameras
This package is based off of V4L devices specifically instead of just UVC.

For full documentation, see [the ROS wiki](http://ros.org/wiki/usb_cam).

[Doxygen](http://docs.ros.org/indigo/api/usb_cam/html/) files can be found on the ROS wiki.

### License
usb_cam is released with a BSD license. For full terms and conditions, see the [LICENSE](LICENSE) file.

### Authors
See the [AUTHORS](AUTHORS.md) file for a full list of contributors.
