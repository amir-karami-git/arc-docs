## 1. ROS 2: Your Robot's Operating System

🎯 **Learning Objectives**

- Grasp what ROS2 is and how it enables modular robotics software
- Understand key components like nodes, topics, and services
- Know how data flows between different parts of a robotic system

### What is ROS 2?

ROS 2 (Robot Operating System 2) is a framework that helps different parts of a robot — like sensors, motors, and control systems — talk to each other.

You can think of a robot as a team of people:

- **Sensors** = the eyes and ears
- **Motors** = the arms and legs
- **Control Code** = the brain
  ROS 2 is the language they use to coordinate.

> 📘 Learn more: [ROS 2 Overview](https://docs.ros.org/en/rolling/index.html)

### Key ROS 2 Concepts (with Diagram)

```
+-------------+         +-------------+         +-------------+
|  Sensor     |-------> |   Node A    |-------> |  Motor Cmd  |
| (Camera)    | Topic   | (Talker)    | Topic   | (Listener)  |
+-------------+         +-------------+         +-------------+
```

| Concept    | Description                                                |
| ---------- | ---------------------------------------------------------- |
| Node       | A small program that performs one task                     |
| Topic      | A stream of data (like sensor readings)                    |
| Publisher  | A node that sends messages                                 |
| Subscriber | A node that receives messages                              |
| Service    | A request/response system between nodes                    |
| Action     | A long-running task with feedback (e.g. driving to a goal) |
| Parameter  | A tunable value inside a node                              |

> 📘 Learn more: [Nodes, Topics, Services in ROS 2](https://docs.ros.org/en/rolling/Concepts.html)

### ✅ Good Habits Checklist

- [ ] Use launch files to manage nodes
- [ ] Keep node logic modular and reusable
- [ ] dont forget to source /opt/ros/humble/setup.bash
- [ ] Use `ros2 topic list` and `ros2 topic echo` to debug
- [ ] Comment your node scripts generously

🎥 **Coming Soon:** Visual: Talker and listener node in action

---

## 2. ROS 2 Workspaces and Package Structure

🎯 **Learning Objectives**

- Understand the structure of a ROS 2 workspace
- Learn how to create and build packages inside a workspace
- Build good workspace habits to avoid conflicts and confusion

### What is a Workspace?

A workspace is a directory where you develop and organize your ROS 2 projects.

### Directory Layout

```bash
ros2_ws/        # Your main workspace
├── src/        # Source code of your packages
├── install/    # Install folder created by the build system
├── build/      # Temporary build files
├── log/        # Log files from the build
```

> 📘 Learn more: [Creating a ROS 2 Workspace](https://docs.ros.org/en/rolling/Tutorials/Beginner-Client-Libraries/Creating-A-Workspace/Creating-A-Workspace.html)

### ✅ Good Habits Checklist

- [ ] Use one workspace per project to avoid clutter
- [ ] Rebuild regularly (`colcon build`) after changes
- [ ] Run `colcon clean` if packages act unexpectedly
- [ ] Never add workspace sourcing to `.bashrc`

🎥 **Coming Soon:** Visual: Workspace build from scratch

---

## 3. Creating and Understanding a ROS 2 Package

🎯 **Learning Objectives**

- Learn to create a basic ROS 2 Python package
- Understand the purpose of files like `package.xml` and `setup.py`
- Write and run a simple ROS 2 node

### Creating a Python Package

```bash
cd ~/ros2_ws/src
ros2 pkg create --build-type ament_python my_package --dependencies rclpy std_msgs
cd ~/ros2_ws colcon build
```

> 📘 Learn more: [Creating ROS 2 Python Packages](https://docs.ros.org/en/rolling/Tutorials/Beginner-Client-Libraries/Writing-A-Simple-Py-Publisher-And-Subscriber.html)

### ✅ Good Habits Checklist

- [ ] Use clear package and node names
- [ ] Create separate files for publishers and subscribers
- [ ] Use `entry_points` in `setup.py` for CLI access
- [ ] Update `package.xml` with real descriptions

🎥 **Coming Soon:** Visual: File structure breakdown + node run

---
