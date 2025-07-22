# whycode-ros2-interfaces

ROS2 interfaces package for the WhyCode localisation system.

## Messages

### `MarkerArray.msg`

| Field     | Type                          | Description               |
|-----------|-------------------------------|---------------------------|
| `header`  | `std_msgs/Header`             | Standard ROS header       |
| `markers` | `whycode_interfaces/Marker[]` | Array of detected markers |

### `Marker.msg`

| Field       | Type                     | Description                            |
|-------------|--------------------------|----------------------------------------|
| `id`        | `int8`                   | Marker ID                              |
| `size`      | `int32`                  | Size in pixels                         |
| `u`         | `float32`                | Image-space X coordinate               |
| `v`         | `float32`                | Image-space Y coordinate               |
| `angle`     | `float32`                | Rotation around the surface normal     |
| `position`  | `geometry_msgs/Pose`     | 3D pose of the marker                  |
| `rotation`  | `geometry_msgs/Vector3`  | Euler angles: roll, pitch, yaw         |

### `Discovery.msg`

| Field   | Type     | Description                                          |
|---------|----------|------------------------------------------------------|
| `data`  | `string` | Not used. Only for presence signaling to the RQt GUI |

## Services

### `SelectMarker.srv`

**Request:**

| Field     | Type                  | Description                       |
|-----------|-----------------------|-----------------------------------|
| `point`   | `geometry_msgs/Point` | Selected point in image (x, y)    |

**Response:**

| Field      | Type  | Description     |
|------------|-------|-----------------|
| `success`  | `bool`| True if handled |

### `SetCalibMethod.srv`

**Request Constants:**

| Name     | Type  | Value | Description           |
|----------|-------|-------|-----------------------|
| `AUTO`   | `int8`| 0     | Automatic calibration |
| `MANUAL` | `int8`| 1     | Manual calibration    |

**Request:**

| Field     | Type   | Description              |
|-----------|--------|--------------------------|
| `method`  | `int8` | Calibration method type  |

**Response:**

| Field      | Type     | Description             |
|------------|----------|-------------------------|
| `success`  | `bool`   | Whether it succeeded    |
| `msg`      | `string` | Optional status message |

### `SetCalibPath.srv`

**Request Constants:**

| Name   | Type  | Value | Description                |
|--------|-------|-------|----------------------------|
| `SAVE` | `int8`| 0     | Save current calibration   |
| `LOAD` | `int8`| 1     | Load calibration from file |

**Request:**

| Field    | Type     | Description           |
|----------|----------|-----------------------|
| `action` | `int8`   | Save or Load action   |
| `path`   | `string` | Path to the YAML file |

**Response:**

| Field     | Type     | Description                  |
|-----------|----------|------------------------------|
| `success` | `bool`   | Whether the action succeeded |
| `msg`     | `string` | Status or error message      |

-----

#### License

The code is avaiable only for non-commercial research and educational purposes only, see the LICENSE file for details. In any other case or when You are not sure about licensing, please, contact us!

If you use this localization system for your research, please don't forget to cite at least one relevant paper below.

#### Where is it described ?

WhyCon was first presented on International Conference on Advanced Robotics 2013, later in the Journal of Intelligent and Robotics Systems and finally at the Workshop on Open Source Aerial Robotics during the International Conference on Intelligent Robotic Systems, 2015.
Its early version was also presented at the International Conference of Robotics and Automation, 2013.
An extension of the system, which used a necklace code to add ID's to the tags, achieved a best paper award at the SAC 2017 conference.
Improved version with the full 6DOF estimation was presented in the Applied Computing Review, 2023.
If you decide to use this software for your research, please cite relevant papers provided below.

#### References

1. J. Ulrich et al.: **[Real time fiducial marker localisation system with full 6 DOF pose estimation](https://dl.acm.org/doi/abs/10.1145/3594264.3594266)**. ACM SIGAPP Applied Computing Review, 2023. [[bibtex](https://gist.github.com/jiriUlr/3f325488596932d784bcff4178c11478)].
1. J. Ulrich et al.: [Towards fast fiducial marker with full 6 DOF pose estimation](https://dl.acm.org/doi/abs/10.1145/3477314.3507043). Symposium on Applied Computing, 2022. [[bibtex](https://gist.github.com/jiriUlr/7d333e90c43e6b41c79e5150c7a59267)].
1. J. Ulrich: [Fiducial marker-based multiple camera localisation system](https://dspace.cvut.cz/bitstream/handle/10467/101526/F3-DP-2022-Ulrich-Jiri-main.pdf). Master's thesis. Czech Technical University in Prague, 2022. [[bibtex](https://gist.github.com/jiriUlr/e8d53c7edd6b14c824e67e60596a489f)].
1. K. Zampachu: [Visual analysis of beehive queen behaviour](https://dspace.cvut.cz/bitstream/handle/10467/101048/F3-BP-2022-Zampachu-Kristi-main.pdf). Bachelor's thesis. Czech Technical University in Prague, 2022. [[bibtex](https://gist.github.com/jiriUlr/eb08ee4b183c615e312ab2db767e9b18)].
1. J. Ulrich: [Fiducial Marker Detection for Vision-Based Mobile Robot Localisation](https://dspace.cvut.cz/bitstream/handle/10467/89879/F3-BP-2020-Ulrich-Jiri-main.pdf). Bachelor's thesis. Czech Technical University in Prague, 2020. [[bibtex](https://gist.github.com/jiriUlr/348d42b7a1cdd08b94953adedc50c5d7)].
1. P. Lightbody, T. Krajník et al.: An Efficient Visual Fiducial Localisation System. Applied Computing Review, 2017.
1. P. Lightbody, T. Krajník et al.: A versatile high-performance visual fiducial marker detection system with scalable identity encoding Symposium on Applied Computing, 2017.
1. M. Nitsche, T. Krajník et al.: WhyCon: An Efficent, Marker-based Localization System. IROS Workshop on Open Source Aerial Robotics, 2015.
1. T. Krajník, M. Nitsche et al.: A Practical Multirobot Localization System. Journal of Intelligent and Robotic Systems (JINT), 2014.
1. T. Krajník, M. Nitsche et al.: External localization system for mobile robotics. International Conference on Advanced Robotics (ICAR), 2013.
1. J. Faigl, T. Krajník et al.: Low-cost embedded system for relative localization in robotic swarms. International Conference on Robotics and Automation (ICRA), 2013.

#### Acknowledgements

The development of this work is currently supported by the EU FET Open programme under grant agreement No.964492 project _RoboRoyale_.
The development of this work was supported by the Czech Science Foundation project 17-27006Y _STRoLL_.
In the past, the work was supported by EU within its Seventh Framework Programme project ICT-600623 _STRANDS_.
The Czech Republic and Argentina have given support through projects 7AMB12AR022, ARC/11/11 and 13-18316P.
