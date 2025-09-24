# F1TENTH Tutorial T01: Docker and ROS 2

Welcome to your first F1TENTH tutorial! This version includes embedded good coding habits, checklists, documentation links, upcoming visual demos, and now also outlines clear learning objectives, troubleshooting tips, and ROS 2 graph visualization guidance to support you as a beginner. This guide is built for first-year university students and assumes minimal experience with software development. It introduces two powerful tools used in robotics development: [Docker](https://docs.docker.com/) and [ROS 2](https://docs.ros.org/en/rolling/). You'll learn core concepts, how to apply them, and gain hands-on experience along the way.

> ✅ **Good Habit Reminder**: Always look up official docs before using a command you're unfamiliar with. Bookmark [Docker](https://docs.docker.com/get-started/) and [ROS 2](https://docs.ros.org/en/rolling/) now!

---

## first go to [Docker_Guide](docker.md)

## second go to [ROS_guide](ROS2.md)

## Third Continue this page

## 1. Building and Running Inside Docker

### Sample Dockerfile

````md
```dockerfile
FROM ros:humble
RUN apt update && apt install -y python3-colcon-common-extensions
WORKDIR /ros2_ws
COPY . /ros2_ws
RUN . /opt/ros/humble/setup.sh && colcon build
CMD ["bash"]
```
````

> 📘 Learn more: [Dockerizing ROS 2 Projects](https://docs.ros.org/en/rolling/How-To-Guides/Docker.html)

### ✅ Good Habits Checklist

- [ ] Add a `.dockerignore` file to keep images small
- [ ] Re-tag and version your Docker builds
- [ ] Push only working builds to Docker Hub

🎥 **Coming Soon:** Visual: Docker build + colcon run demo

---

## 2. Final Assignment

### Objective

- Build a containerized ROS 2 workspace
- Create a simple publisher node
- Launch it using Python
- Push your container to Docker Hub
- Submit via GitHub Classroom

> ✅ **Track your changes:** Keep a `CHANGELOG.md` file from the start

---

## 3. Common Mistakes and Pro Tips

| Mistake                         | Fix                                            |
| ------------------------------- | ---------------------------------------------- |
| Not sourcing the setup script   | Run `source install/setup.bash`                |
| Permissions issue on volume     | Add `--user $(id -u):$(id -g)` to `docker run` |
| Dependencies missing in package | Add to `package.xml` and `setup.py`            |

✅ Use `tmux` to keep sessions alive
✅ Use volumes to persist work
✅ Don’t put ROS source commands in `.bashrc` — see [why here](https://docs.ros.org/en/rolling/How-To-Guides/Overriding-Environment-Variables.html)

---

## 3. Resources and What’s Next

### 🔄 Troubleshooting Common ROS 2 Issues

> 🛠️ **Colcon build fails with missing dependencies**
> Check your `package.xml` and `setup.py` to ensure all dependencies are listed. Use `rosdep install --from-paths src --ignore-src -r -y` to auto-install missing ones.

> 🛠️ **Can't find installed packages**
> Make sure to `source install/setup.bash` after building. Never skip this step.

> 🛠️ **Docker can't access local folder**
> Ensure you're using absolute paths with `-v` or `--mount`, and check permissions.

---

### 🧠 Visualize ROS 2 Graph

Run this command to generate a visual diagram of how your nodes and topics are connected:

```bash
rqt_graph
```

Or use:

```bash
ros2 run tf2_tools view_frames
```

This produces an image like the one below that shows your full ROS 2 computation graph.

📷 _(Insert SVG or screenshot of ROS graph visualization here)_

---

### Learn More

- [Official ROS 2 Tutorials](https://docs.ros.org/en/rolling/Tutorials.html)
- [Docker Curriculum](https://docker-curriculum.com/)
- [RoboticsBackend ROS 2 Tutorials](https://roboticsbackend.com/)

### Coming Up

- Writing custom messages and services
- Simulating environments with Gazebo
- Connecting ROS 2 nodes over a network

---

Congratulations! 🎉 You now know how to:

- Use Docker to run isolated robotics environments
- Build ROS 2 packages from scratch
- Launch and test simple nodes
- Submit your containerized project professionally
