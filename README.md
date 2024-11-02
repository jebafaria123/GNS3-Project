# GNS3 Project: OSPF and BGP Configuration with Route Reflectors

## Overview
The goal of this project is to design and implement a network topology in GNS3 that uses OSPF for internal routing and iBGP with Route Reflectors to optimize BGP peering across the backbone. Additionally, eBGP is configured between PE (Provider Edge) and CE (Customer Edge) routers to handle external routing for different branches of a simulated bank.

## Key Methodology

### 1. Network Design and Configuration
Setting up a well-structured network topology involves:
- **Backbone Routers (P and PE)**: Configured with OSPF to ensure consistent internal routing across all backbone routers.
- **Route Reflector (RR) Routers**: Two dedicated routers manage iBGP peering efficiently. Route Reflectors are used to avoid the complexity of a full mesh iBGP topology, making the network more scalable and easier to manage.
- **eBGP Connections**: Established between PE routers and CE routers to manage external routing between the service provider and branch networks.

**Configuration Steps**:
1. Configure OSPF across all backbone routers for internal routing.
2. Establish iBGP sessions among all backbone routers, using Route Reflectors to simplify peering.
3. Set up eBGP between PE and CE routers to handle routing between the provider and branch networks.

### 2. OSPF Configuration
- **Purpose**: To enable internal routing and ensure all P and PE routers have full connectivity.
- **Key Commands**: Configuring OSPF areas, advertising networks, and verifying neighbor relationships.

### 3. iBGP with Route Reflectors
- **Objective**: Simplify iBGP peering by using two Route Reflector routers, avoiding the need for a full mesh of iBGP connections.
- **Configuration**: Specify RR clients and establish iBGP sessions across all backbone routers.

### 4. eBGP Configuration
- **Setup**: eBGP is configured between each PE router and its connected CE router.
- **Purpose**: To manage routing between the service provider and external networks.

## Results
The project successfully demonstrates:
- **Internal Routing with OSPF**: Ensures backbone connectivity with efficient route propagation.
- **Simplified BGP Peering**: Using Route Reflectors reduces iBGP complexity and scales the network.
- **Effective eBGP Configuration**: Establishes reliable communication between branches and the core network.

## Configuration Files and Topology
- **Topology Image**: Provides a visual representation of the network setup (`topology.png`).
- **Router Configurations**: `.cfg` files containing the saved configurations for all routers.
- **GNS3 Project File**: Loadable project file for recreating the setup in GNS3.

## Performance Metrics
Evaluation involves verifying:
- **OSPF Neighbor Relationships**: Using `show ip ospf neighbor` to ensure all routers are properly peered.
- **BGP Peering Status**: Using `show ip bgp summary` to check the status of iBGP and eBGP sessions.
- **Connectivity Tests**: Pinging between different parts of the network to confirm end-to-end connectivity.

