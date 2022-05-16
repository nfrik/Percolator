# Percolator
Percolator is a software tool that can generate random and ordered distributions of geometrical objects in 2D and 3D and estimate collision points' coordinates with a 3D physics engine. The object collision analysis result is a graph with node and edge attributes holding the collision coordinates and the type of the object connecting two nodes.  The user interface provides tools for manipulating objects and introduces various degrees of organization. The primary purpose of this tool is to help understanding percolation and conductivity phenomena in random nanoscale networks.

In Percolator, the contact point is estimated via Open Dynamic Engine for Java (ODE4j) 3D game engine (tzaeschke/ode4j). The collision coordinate between two objects is first identified via the axis-aligned bounding boxes method (AABB) (Bergen 1997). Since in the ODE4j engine, each object has a virtual bounding box, the intersection of the bounding boxes of one 3D object with another can be simply calculated with a logic comparison test. If a collision is identified as intersecting volumes, it will be further analyzed to locate the contact points' exact coordinates on each object's surface.

![alt text](https://github.com/nfrik/Percolator/blob/main/img/UI-example.jpg?raw=true)

Main features:
1. Generation of random and ordered distributions of cylindrical and spherical objects in 2D and 3D
2. Generation of spaghetti objects with various degree of curviness
3. Application of periodic boundary condition
4. Simulation of collision repulsion for the hard-core model (works with a small number of particles)
5. Custom proximity shell (pillbox) for each object for soft-core percolation analysis
6. Grouping objects into a specific configuration and generating distribution from the resulting configuration
7. Logging and other useful UI tools

![alt text](https://github.com/nfrik/Percolator/blob/main/img/Connectivity.jpg?raw=true)


The software is available as a binary jar container. For convenience we provide a Docker file all necessary dependencies to build the Ubuntu VNC server with the Percolator. For more details on tuning additional features of the Ubuntu-xfce-vnc image refer to: https://hub.docker.com/r/consol/ubuntu-xfce-vnc/

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
