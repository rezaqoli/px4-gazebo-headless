# PX4-Gazebo simulator (headless)

### Build the image from this git repository:

```
$ docker build https://github.com/JonasVautherin/docker.git#master:px4-gazebo-headless -t px4-gazebo-headless
```

### Run it in BROADCAST mode:

```
$ docker run --rm -it px4-gazebo-headless
```

`MAV_BROADCAST` is enabled by default, and the second MAVLink interface is not run in "onboard" mode in order to enable the broadcasting. Those changes are made by [edit_iris_config.bash](edit_iris_config.bash).

### Run it with a custom IP for the second mavlink interface

```
$ docker run --rm -it px4-gazebo-headless 192.168.0.12
```

where `192.168.0.12` should be replaced by the IP listening on the API port 14540 (e.g. DroneCore or Mavros).

### Run it with custom IP for both mavlink interfaces

```
$ docker run --rm -it px4-gazebo-headless 192.168.0.10 10.0.0.12
```

where `192.168.0.10` should be replaced by the IP listening on the QGC port (e.g. QGroundControl) and `10.0.0.12` should be replaced by the IP listening on the API port (e.g. DroneCore or Mavros).