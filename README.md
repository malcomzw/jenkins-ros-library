# Jenkins Shared Library for ROS Pipeline

This shared library provides reusable functions for ROS (Robot Operating System) Jenkins pipelines.

## Structure

```
jenkins-ros-library/
├── src/                 # Java source files
├── vars/               # Groovy script files
│   ├── rosUtils.groovy    # ROS-related utility functions
│   └── pipelineConfig.groovy # Pipeline configuration
└── resources/          # Non-Groovy files
```

## Available Functions

### rosUtils.groovy

1. `buildRosPackage(Map config)`
   - Builds ROS packages using catkin
   - Parameters:
     - dockerImage: Name of the Docker image (default: 'ros-jenkins')
     - buildNumber: Build number (default: env.BUILD_NUMBER)

2. `runRosTests(Map config)`
   - Runs ROS tests and generates reports
   - Parameters:
     - dockerImage: Name of the Docker image (default: 'ros-jenkins')
     - buildNumber: Build number (default: env.BUILD_NUMBER)

3. `runGazeboSimulation(Map config)`
   - Runs Gazebo simulation
   - Parameters:
     - dockerImage: Name of the Docker image (default: 'ros-jenkins')
     - buildNumber: Build number (default: env.BUILD_NUMBER)
     - timeout: Simulation timeout in seconds (default: 300)

### pipelineConfig.groovy

Provides configuration settings for the pipeline:
- Docker image name
- Timeout settings
- ROS configuration
