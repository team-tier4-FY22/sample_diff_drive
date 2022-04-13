# sample_diff_drive

## Source installation

### Prerequisites

- [Ubuntu 20.04](https://releases.ubuntu.com/20.04/)
- [Git](https://git-scm.com/)
  - [Registering SSH keys to GitHub](https://github.com/settings/keys) is preferable.

```bash
sudo apt-get -y update
sudo apt-get -y install git
```

## How to set up a development environment

1. Clone `team-tier4-FY22/sample_diff_drive` and move to the directory.

   ```bash
   git clone https://github.com/team-tier4-FY22/sample_diff_drive.git
   ```

## How to set up a workspace

1. Create the `src` directory and clone repositories into it.
   ```bash
   cd sample_diff_drive
   mkdir src
   vcs import src < sample_diff_drive.repos
   ```

2. Install dependent ROS packages.

   ```bash
   source /opt/ros/galactic/setup.bash
   rosdep install -y --from-paths src --ignore-src --rosdistro $ROS_DISTRO
   ```

3. Build the workspace.

   ```bash
   colcon build --symlink-install --cmake-args -DCMAKE_BUILD_TYPE=Release
   ```


