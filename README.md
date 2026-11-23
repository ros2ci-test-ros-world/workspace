# workspace (test)

Repos files for testing an experimental ROS 2 build system.

**This is a test project. It is not an official ROS project, and nothing here
is connected to official ROS infrastructure.** The files only name the public
ROS 2 source repositories, which the build system reads and never writes to.

| File | What it is |
|---|---|
| `core.repos` | The ROS 2 core workspace: a copy of `ros2.repos` from the `rolling` branch of ros2/ros2. |
| `small.repos` | The 13 repositories needed to build and test `rcpputils` and everything under it: 55 packages. Small enough for a Raspberry Pi, and it still has C++, Python, linters and launch tests. |

Build `small.repos` up to `rcpputils`:

```
vcs import --input small.repos src
colcon build --packages-up-to rcpputils
```
