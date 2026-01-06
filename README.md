# AWS Infrastructure :

Cloud computing has transformed how applications are built, deployed, and scaled. At the core of cloud computing lies **infrastructure**, and Amazon Web Services (AWS) is the world’s most widely used cloud infrastructure platform.
This explains AWS infrastructure step by step, starting from basic concepts and moving into virtualization and hypervisors.

---

## 1. What is Infrastructure ?

**Infrastructure** refers to the fundamental components required to run IT systems and applications.

### Traditional Infrastructure Includes:

* Physical servers
* Storage devices (hard disks, SAN, NAS)
* Networking equipment (routers, switches, firewalls)
* Data centers
* Power, cooling, and security

### Cloud Infrastructure (AWS Infra):

In cloud computing, infrastructure is **virtualized and delivered over the internet**.

AWS Infrastructure includes:

* Compute (EC2, Lambda)
* Storage (S3, EBS)
* Networking (VPC, Load Balancers)
* Physical data centers distributed globally

 **Key difference:**
You don’t manage hardware in AWS — AWS manages it for you.

---

## 2. What are AWS Regions?

An **AWS Region** is a **geographical area** where AWS has multiple data centers.

### Key Points About Regions:

* Each region is **physically isolated** from others
* Designed for **fault tolerance and stability**
* You choose a region while creating AWS resources

### Examples of AWS Regions:

* US East (N. Virginia)
* US West (Oregon)
* Asia Pacific (Mumbai)
* Europe (Frankfurt)
* Asia Pacific (Singapore)

### Why Regions Matter:

* **Latency**: Choose a region closer to users
* **Compliance**: Some data must stay in specific countries
* **Cost**: Pricing varies by region
* **Disaster Recovery**: Deploy across multiple regions

---

## 3. What are Availability Zones (AZs)?

An **Availability Zone (AZ)** is **one or more isolated data centers** within a region.

### Structure:

```
Region → Multiple Availability Zones → Data Centers
```

### Example:

**Asia Pacific (Mumbai)** region has:

* ap-south-1a
* ap-south-1b
* ap-south-1c

### Characteristics of AZs:

* Each AZ has **independent power, cooling, and networking**
* Connected via **high-speed, low-latency private links**
* Failures in one AZ **do not affect others**

### Why AZs Are Important:

* High availability
* Fault tolerance
* Load balancing
* Disaster recovery within a region

 **Best practice:** Deploy applications across **multiple AZs**.

---

## 4. How Virtualization Works

### What is Virtualization?

**Virtualization** is the technology that allows **multiple virtual machines (VMs)** to run on a **single physical server**.

Instead of:

```
1 App = 1 Physical Server
```

Virtualization allows:

```
Multiple Apps = Multiple VMs = 1 Physical Server
```

---

### Components Involved:

1. **Physical Hardware**

   * CPU, RAM, Storage, Network

2. **Hypervisor**

   * Software layer that creates and manages VMs

3. **Virtual Machines (VMs)**

   * Independent operating systems sharing hardware

---

### How Virtualization Works (Step-by-Step):

1. A physical server is installed in an AWS data center
2. A hypervisor is installed on that server
3. Hypervisor divides hardware resources:

   * CPU
   * Memory
   * Storage
4. Multiple VMs are created
5. Each VM runs its own OS and applications

 Each VM behaves like a **real computer**, even though hardware is shared.

---

### Benefits of Virtualization:

* Better hardware utilization
* Cost efficiency
* Faster provisioning
* Isolation between workloads
* Scalability

---

## 5. How Hypervisor Works

### What is a Hypervisor?

A **hypervisor** is a software layer that:

* Sits between **hardware and virtual machines**
* Controls access to CPU, memory, and storage
* Ensures isolation between VMs

AWS uses a customized hypervisor called **AWS Nitro System** (earlier Xen).

---

### Types of Hypervisors:

#### 1. Type 1 (Bare-Metal Hypervisor)

* Runs directly on hardware
* More secure and efficient
* Used in cloud platforms

Examples:

* AWS Nitro
* VMware ESXi
* Microsoft Hyper-V

 **AWS uses Type 1 hypervisor**

---

#### 2. Type 2 (Hosted Hypervisor)

* Runs on top of an operating system
* Used mostly for testing or personal use

Examples:

* VirtualBox
* VMware Workstation

---

### How a Hypervisor Works in AWS:

1. Physical server boots with hypervisor
2. Hypervisor:

   * Allocates CPU cores
   * Assigns memory
   * Manages storage access
3. EC2 instances (VMs) are launched
4. Each EC2 instance:

   * Has its own OS
   * Is isolated from others
5. Hardware access is controlled securely

---

### AWS Nitro System (Modern AWS Hypervisor):

Key features:

* Hardware-based virtualization
* Improved performance
* Enhanced security
* Offloads networking and storage to dedicated hardware

 This is why AWS EC2 performance is close to **bare-metal servers**.

---

## Conclusion

AWS Infrastructure is designed to be:

* **Highly available**
* **Secure**
* **Scalable**
* **Cost-efficient**

### Quick Recap:

* **Infrastructure**: Foundation of cloud resources
* **Regions**: Geographical locations
* **Availability Zones**: Isolated data centers within regions
* **Virtualization**: Multiple VMs on one physical server
* **Hypervisor**: Manages and isolates virtual machines

