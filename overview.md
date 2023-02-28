# Quickstart guide
This quickstart guide will show you how to build and use an OnDemand HPC cluster on Azure thru the deployment of an simple **Azure HPC On-Demand Platform** environment. 
In this light environment, there is no Lustre cluster, no Window Viz nodes. `Az-hop` CentOS 7.9 Azure marketplace images for compute and remote desktop nodes will be 
used.

When provisioning a complete `az-hop` environment a deployer VM and a bastion will be included. Once deployed, a cloud init script is run from the deployer VM to 
install and configure all components needed using Ansible playbooks. This second step is longer as it needs to install and configure a Domain Control, CycleCloud, 
OpenOndemand, PBS, Grafana and many others things. The use of Ansible will allows this system to be updated and in case of failure the installation to be retried.

# Azure HPC On-Demand Platform, your deployment to be HPC-Ready! 

Azure HPC On-Demand Platform (az-hop), provides the end-to-end deployment mechanism for a base HPC infrastructure on Azure. az-hop delivers a complete HPC cluster solution ready for users to run applications, which is easy to deploy and manage for HPC administrators. az-hop leverages the various Azure building blocks and can be used as-is, or easily customized and extended to meet any uncovered requirements. Industry standard tools like Terraform, Ansible and Packer are used to provision and configure this environment containing :
  - An [HPC OnDemand Portal](https://osc.github.io/ood-documentation) for all user access, remote shell access, remote visualization access, job submission, file access and more,
  - An Active Directory for user authentication and domain control,
  - [Open PBS](https://openpbs.org/) or [SLURM](https://slurm.schedmd.com/overview.html) as a Job Scheduler,
- Dynamic resources provisioning and autoscaling is done by [Azure CycleCloud](https://docs.microsoft.com/en-us/azure/cyclecloud/?view=cyclecloud-8) pre-configured job queues and integrated health-checks to quickly avoid non-optimal nodes,
- A Jumpbox to provide admin access,
- A common shared file system for home directory and applications is delivered by [Azure Netapp Files](https://azure.microsoft.com/en-us/services/netapp/),
- A Lustre parallel filesystem using local NVME for high performance that automatically archives to [Azure Blob Storage](https://azure.microsoft.com/en-gb/services/storage/blobs/) using the [Robinhood Policy Engine](https://github.com/cea-hpc/robinhood) and [Azure Storage data mover](https://github.com/wastore/lemur),
- [Grafana](https://grafana.com/) dashboards to monitor your cluster,
- Remote Visualization with [noVNC](https://novnc.com/info.html) and GPU acceleration with [VirtualGL](https://www.virtualgl.org/).



