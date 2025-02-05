### **Summary of the Project**

This project is a demonstrator for the use of distributed computing for physics simulations by connecting four Jetson Nano devices via a network switch and leveraging **Dask** to distribute computational loads. 

![Jetsons]([Home Made Jetson Cluster.jpg](https://github.com/Msapkas/Distributed-Computing-for-Physics-Simulation-and-Computation/blob/main/Home%20Made%20Jetson%20Cluster.jpg))
![Jetsons2]([Home Made Jetson Cluster2.jpg](https://github.com/Msapkas/Distributed-Computing-for-Physics-Simulation-and-Computation/blob/main/Home%20Made%20Jetson%20Cluster2.jpg))

Two simulations were implemented:

1. **2D Ising Model:** The simulation models the evolution of a spin lattice using the Metropolis algorithm, where multiple grids are distributed across multiple computing nodes, enabling parallel updates.
2. **1D Particle Chain:** A thermodynamic simulation of a 1D chain of particles, where various physical properties (e.g., energy and entropy) are computed in parallel.

_________

### **Methods Used**
#### **Hardware & Software**
- **Hardware:** Four Jetson Nano boards connected through a switch.
- **Software:** Dask for parallel computing, NumPy for numerical operations.

#### **Parallelization with Dask**
- **Client-Worker Setup:** Dask's distributed scheduler was used, with Jetson Nanos acting as worker nodes.
- **Task Distribution:** The computational load is split among nodes, each handling part of the evolution.
- **Data Management:** Dask arrays were used to manage distributed data efficiently.

![Jetsons2]([Jetsons Running.png](https://github.com/Msapkas/Distributed-Computing-for-Physics-Simulation-and-Computation/blob/main/Jetsons%20Running.png))

#### **2D Ising Model Simulation**
- Implemented using the **Metropolis algorithm** to model spin state changes.
- The grid was copied 10 times, each processed independently in parallel.
- The lowest energy update gets picked at each step allowing for faster convergence time.

#### **1D Particle Chain Simulation**
- The system modeled interactions between particles using thermodynamic principles.
- Dask was used to distribute the calculations across multiple nodes by splitting the 1D chain into multiple sub-chains.
- Energy, and other thermodynamic quantities were computed.

#### **Limitations** 
- Edge devices are not apropriate for this task due to memory limitations.
- Nevertheless this was a demo project to grasp the pronciplesof distributed computing.
