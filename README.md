# Custom CML and NDFC Sandbox
## Overview
This repo serves as a document source for a custom CML and NDFC deployment hosted in a dCloud environment.

## Sandbox Access Details
To access the lab environment is limited to those provided access only. 

## Sandbox Overview
The sandbox consists of the following virtual devices that allow access to a instance of CML and a instance of NDFC. The environment is saved to a specific base state to allow for starting out and exploring both applications. 

### Virtual Machines:

| Device Name | IP Address | Username/Password |
| ----- | ---- | ----| 
| cml | 198.18.133.10 | admin/C1sco12345 |
| wkst1 | 198.18.133.11 | admin/C1sco12345 |
| wkst2 | 198.18.133.12 | admin/C1sco12345 |
| ndfc | 198.18.133.100 | admin/C1sco12345 |

## Sandbox Example Topology
Included in the base setup is a Spine-Leaf topology built in CML. The topology consists of 2 spines and 4 leafs along with 2 Ubuntu vitual machines with initial configurations defined for bootstrapping on startup.

To use the example topology access the cml instance use chrome on one of the workstations and use the start button to start the lab. The nodes will boot up over approximately 5 minute period. The devices will come up and are accessible using MPutty found on the desktop of the workstations. Once all nodes are up access Nexus Dashboard from the Chrome bookmark. Using the drop down menu at the top of the ND webpage after login select Fabric controller to access the NDFC service and start discover of the example fabric. 

To discover the fabric use the seed address of: **198.18.1.11** with a username of **automation** and password of **C1sco12345**.

Configure Fabric as desired leaf-1 and leaf-2 are connected and can 
form a VPC peer as well as leaf-3 and leaf-4

![Example Spine-Leaf CML Topology.](/img/sandbox_example_topology.png)
### Example Topology IP addresses:
| Device Name | IP Address | Username/Password |
| ----- | ---- | ----| 
| spine-1 | 198.18.1.11 | cisco/cisco |
| spine-2 | 198.18.1.12 | cisco/cisco |
| leaf-1 | 198.18.1.13 | cisco/cisco |
| leaf-2 | 198.18.1.14 | cisco/cisco |
| leaf-3 | 198.18.1.15 | cisco/cisco |
| leaf-4 | 198.18.1.16 | cisco/cisco |
| server-1 | 198.18.1.17 | cisco/cisco |
| server-2 | 198.18.1.18 | cisco/cisco |

Server-1 and Server-2 use interfaces ens3 and ens4 as bond interfaces to connect using LACP to the upstream switches. In CML review the ***Edit Config*** tab to explore the configurations and edit subnets to match your testing.

## Deploying your own Custom topologies
To deploy your own custom topologies and provide connectivity externally define management addresses in the range of **198.18.1.100-200** and use an External Connectivity cloud in CML with the Configuration edited to use **Bridge 1**. This will allow for connectivity from the workstations or NDFC.

