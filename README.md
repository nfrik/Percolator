# Percolator
Percolator is a dynamic software tool capable of generating both random and ordered arrangements of geometric entities in 2D and 3D spaces. It leverages the power of a 3D physics engine to accurately determine the coordinates of collision points between objects. The outcome of this collision analysis is visualized in the form of an intricate graph, with nodes and edges enriched by attributes detailing the collision coordinates and the types of objects bridging each node. The user-friendly interface allows for intricate object manipulation, introducing varying degrees of structure and organization.

The overarching goal of Percolator is to elucidate our understanding of percolation and conductivity phenomena occurring within seemingly chaotic nanoscale networks.

Percolator harnesses the Open Dynamic Engine for Java (ODE4j), a sophisticated 3D game engine, to pinpoint collision contact points. Collision coordinates between objects are initially identified through the Axis-Aligned Bounding Boxes (AABB) method. Leveraging the ODE4j engine's unique feature of assigning a virtual bounding box to each object, potential collisions can be swiftly detected by performing a simple logic comparison test on the intersections of the bounding boxes of the 3D objects. If intersecting volumes are discovered, indicating a collision, a more detailed analysis is performed to accurately determine the precise coordinates of contact points on the surface of each colliding object.

![alt text](https://github.com/nfrik/Percolator/blob/main/img/UI-example.jpg?raw=true)

Main features:
1. Generation of random and ordered distributions of cylindrical and spherical objects in 2D and 3D
2. Generation of spaghetti objects with various degrees of curviness
3. Application of periodic boundary condition
4. Simulation of collision repulsion for the hard-core model (works with a small number of particles)
5. Custom proximity shell (pillbox) for each object for soft-core percolation analysis
6. Grouping objects into a specific configuration and generating distribution from the resulting configuration
7. Logging and other useful UI tools

![alt text](https://github.com/nfrik/Percolator/blob/main/img/Connectivity.jpg?raw=true)


The software is available as a binary jar container. For convenience, we provide a Docker file with all necessary dependencies to build the Ubuntu VNC server with the Percolator. For more details on tuning additional features of the Ubuntu-xfce-vnc image, refer to: https://hub.docker.com/r/consol/ubuntu-xfce-vnc/

This project was partially supported by NSF grants no. 1748459, 1608847. We thank Freescale LLC (NC, USA) for providing components for this software.

To build the image:
```docker build . -t vnc_percolator```

To run the container:
```docker run -it -p 8888:6901 vnc_percolator```

Navigate to you web browser and open http://localhost:8888 page:

Once prompted type default password: vncpassword

Percolator can be launched through a desktop icon.


Please cite this software using this DOI: https://doi.org/10.5281/zenodo.4549735

[![DOI](https://zenodo.org/badge/339210670.svg)](https://zenodo.org/badge/latestdoi/339210670)
