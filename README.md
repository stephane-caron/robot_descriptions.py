# Robot descriptions in Python

[![Build](https://img.shields.io/github/workflow/status/stephane-caron/robot_descriptions.py/CI)](https://github.com/stephane-caron/robot_descriptions.py/actions)
[![Coverage](https://coveralls.io/repos/github/stephane-caron/robot_descriptions.py/badge.svg?branch=master)](https://coveralls.io/github/stephane-caron/robot_descriptions.py?branch=master)
[![PyPI version](https://img.shields.io/pypi/v/robot_descriptions)](https://pypi.org/project/robot_descriptions/)
![Status](https://img.shields.io/pypi/status/robot_descriptions)
[![Contributing](https://img.shields.io/badge/PRs-welcome-green.svg)](https://github.com/stephane-caron/robot_descriptions.py/tree/master/CONTRIBUTING.md)

Import open source robot descriptions as Python modules. The wrapper automatically downloads and cache files at first import. Most [Awesome Robot Descriptions](https://github.com/robot-descriptions/awesome-robot-descriptions) are available.

## Installation

```console
pip install robot_descriptions
```

## Usage

Import the robot description you are interested in directly as a submodule of ``robot_descriptions``:

```python
from robot_descriptions import my_robot_description
```

The import will automatically download the robot description if you don't have it already, and cache it to a local directory. The submodule then provides the following paths:

<dl>
    <dt>
        <code>URDF_PATH</code>
    </dt>
    <dd>
        Path to the main URDF file of the robot description, if applicable.
    </dd>
    <dt>
        <code>MJCF_PATH</code>
    </dt>
    <dd>
        Path to the main MJCF file of the robot description, if applicable.
    </dd>
    <dt>
        <code>MESHES_PATH</code>
    </dt>
    <dd>
        Path to the "meshes" folder of the robot description, if applicable.
    </dd>
    <dt>
        <code>PACKAGE_PATH</code>
    </dt>
    <dd>
        Path to the root of the robot description.
    </dd>
    <dt>
        <code>REPOSITORY_PATH</code>
    </dt>
    <dd>
        Path to the working directory of the git repository hosting the robot description.
    </dd>
</dl>

Some robot descriptions include additional fields. For instance, the ``iiwa_description`` exports ``URDF_PATH_POLYTOPE_COLLISION`` with more detailed collision meshes.

## Examples

Load a robot description:

- [MuJoCo](https://github.com/stephane-caron/robot_descriptions.py/tree/master/examples/load_in_mujoco.py)
- [Pinocchio](https://github.com/stephane-caron/robot_descriptions.py/tree/master/examples/load_in_pinocchio.py)
- [PyBullet](https://github.com/stephane-caron/robot_descriptions.py/tree/master/examples/load_in_pybullet.py)

Visualize a robot description:

- [MeshCat](https://github.com/stephane-caron/robot_descriptions.py/tree/master/examples/show_in_meshcat.py)
- [MuJoCo](https://github.com/stephane-caron/robot_descriptions.py/tree/master/examples/show_in_mujoco.py)
- [PyBullet](https://github.com/stephane-caron/robot_descriptions.py/tree/master/examples/show_in_pybullet.py)
- [yourdfpy](https://github.com/stephane-caron/robot_descriptions.py/tree/master/examples/show_in_yourdfpy.py)

## Command line tool

The command line tool can be used to visualize any of the robot descriptions below. For example:

```console
robot_descriptions show solo_description
```

## Descriptions

Available robot descriptions ([gallery](https://github.com/robot-descriptions/awesome-robot-descriptions#gallery)) currently include:

| Name                  | Maker                    | Format     | Submodule                     |
|-----------------------|--------------------------|------------|-------------------------------|
| A1                    | UNITREE Robotics         | MJCF, URDF | `a1_description`              |
| Aliengo               | UNITREE Robotics         | MJCF, URDF | `aliengo_description`         |
| Allegro Hand          | Wonik Robotics           | URDF       | `allegro_hand_description`    |
| ANYmal B              | ANYbotics                | MJCF       | `anymal_b_mj_description`     |
| ANYmal B              | ANYbotics                | URDF       | `anymal_b_description`        |
| ANYmal C              | ANYbotics                | MJCF       | `anymal_c_mj_description`     |
| ANYmal C              | ANYbotics                | URDF       | `anymal_c_description`        |
| Atlas DRC (v3)        | Boston Dynamics          | URDF       | `atlas_drc_description`       |
| Atlas v4              | Boston Dynamics          | URDF       | `atlas_v4_description`        |
| Baxter                | Rethink Robotics         | URDF       | `baxter_description`          |
| Bolt                  | ODRI                     | URDF       | `bolt_description`            |
| Cassie                | Agility Robotics         | MJCF       | `cassie_mj_description`       |
| Cassie                | Agility Robotics         | URDF       | `cassie_description`          |
| Crazyflie 2.0         | Bitcraze                 | URDF       | `cf2_description`             |
| Double Pendulum       | N/A                      | URDF       | `double_pendulum_description` |
| e.DO                  | Comau                    | URDF       | `edo_description`             |
| Fetch                 | Fetch Robotics           | URDF       | `fetch_description`           |
| FingerEdu             | N/A                      | URDF       | `finger_edu_description`      |
| Gen2                  | Kinova                   | URDF       | `gen2_description`            |
| Go1                   | UNITREE Robotics         | MJCF, URDF | `go1_description`             |
| HyQ                   | IIT                      | URDF       | `hyq_description`             |
| iCub                  | IIT                      | URDF       | `icub_description`            |
| iiwa                  | KUKA                     | URDF       | `iiwa_description`            |
| JVRC-1                | AIST                     | URDF       | `jvrc_description`            |
| JVRC-1                | AIST                     | MJCF       | `jvrc_mj_description`         |
| Laikago               | UNITREE Robotics         | MJCF, URDF | `laikago_description`         |
| Mini Cheetah          | MIT                      | URDF       | `mini_cheetah_description`    |
| Minitaur              | Ghost Robotics           | URDF       | `minitaur_description`        |
| Panda                 | Franka Emika             | URDF       | `panda_description`           |
| Panda                 | Franka Emika             | MJCF       | `panda_mj_description`        |
| PR2                   | Willow Garage            | URDF       | `pr2_description`             |
| Reachy                | Pollen Robotics          | URDF       | `reachy_description`          |
| Romeo                 | Aldebaran Robotics       | URDF       | `romeo_description`           |
| Simple Humanoid       | N/A                      | URDF       | `simple_humanoid_description` |
| Robotiq 2F-85         | Robotiq                  | URDF       | `robotiq_2f85_description`    |
| Robotiq 2F-85         | Robotiq                  | MJCF       | `robotiq_2f85_mj_description` |
| Shadow Hand           | The Shadow Robot Company | MJCF       | `shadow_hand_mj_description`  |
| Solo                  | ODRI                     | URDF       | `solo_description`            |
| TALOS                 | PAL Robotics             | URDF       | `talos_description`           |
| TIAGo                 | PAL Robotics             | URDF       | `tiago_description`           |
| Upkie                 | Tast's Robots            | URDF       | `upkie_description`           |
| UR10                  | Universal Robots         | URDF       | `ur10_description`            |
| UR3                   | Universal Robots         | URDF       | `ur3_description`             |
| UR5                   | Universal Robots         | URDF       | `ur5_description`             |
| UR5e                  | Universal Robots         | MJCF       | `ur5e_mj_description`         |

New robot descriptions are welcome! Check out the [guidelines](https://github.com/stephane-caron/robot_descriptions.py/tree/master/CONTRIBUTING.md) then open a PR.

## Thanks

Thanks to the maintainers of all the git repositories that made these robot descriptions available.
