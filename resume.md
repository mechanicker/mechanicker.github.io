# Resume

	Name: Dhruva Krishnamurthy
	Email: dhruvakm@gmail.com
	Phone: +1 (408) 623-0605
	Location: California, United States

- Resume: [https://mechanicker.github.io/resume.html](https://mechanicker.github.io/resume.html)
- GitHub profile: [https://github.com/mechanicker](https://github.com/mechanicker)
- LinkedIn profile: [https://www.linkedin.com/in/dhruvakm/](https://www.linkedin.com/in/dhruvakm/)

## Summary

I have a proven track record with 20+ years of professional experience delivering business impact with customer value, developing and optimizing large-scale distributed data-intensive software for performance and cost at the cloud scale, and modernizing legacy systems through progressive decomposition to ensure constant evolution. With a passion for optimization and ensuring maintainable software, I thrive in situations demanding out-of-the-box innovative problem-solving.

## Skills

### **Proficiency**

- Distributed systems, cloud-native data-intensive microservices
- Systems programming, file systems, and storage technologies. Performance optimization, developing and using profilers, multithreading and asynchronous programming.
- Source control management (SCM/VCS) with a focus on [git](https://git-scm.com/) & [libgit2](https://libgit2.org/) internals
- C, C++, Go and Python

------

## Experience

### Principal engineer, [Atlassian](https://www.atlassian.com/)
*Jan 2017 - Current*

#### [Bitbucket](http://bitbucket.org)

Responsible for Bitbucket storage architecture and roadmap focusing on performance and cost optimizations. Drive cross-team initiatives to constantly evolve the Bitbucket data stack, adopting industry-wide best practices for better reliability and resiliency.

- Architected live migrations of multi-peta byte repository storage to realize performance and cost benefits, saving approximately USD 2.5 million per year
- Leading multiple initiatives to improve performance for monorepo and enterprise adoption
- Mentor engineers by identifying opportunities and helping build their technical skills
- Enhancing git and libgit2 to improve Bitbucket's performance and robustness. Improved resiliency and observability for using git over NFS

#### Cross product search

Implemented various cross-product indexing and search components, honoring customer-defined role-based access controls. Designed a multi-region fault-tolerant indexing service using CQRS and event store patterns.


#### Trust & Identity
Designed and implemented a unified role-based access control (RBAC) service for seamless user experience across Atlassian services.

- Implemented and operationalized scalable and resilient data pipeline for ingesting real-time permission data
- Built auto-detection and recovery mechanisms from partial/total data loss in the pipeline due to upstream failures

### Senior engineer, [NetApp](http://netapp.com)
*Feb, 2008 - Jan, 2017*

#### NFSv4 server performance lead
Led NFSv4 performance improvement initiatives and delivered ~40% performance reduction in IO latency. Served as a liaison between NFS and the wider performance engineering team. Delivered ~50% throughput improvements by implementing a client-side library for SAP Hana workloads.

- Developed [IOtrap library](https://github.com/mechanicker/iotrap) to transparently use asynchronous IO to improve performance via IO interception, subsequently incorporated into the SAP Hana core engine
- NetApp published best practices for SAP Hana over NFSv4 ["Configuration of Performance Test Tool"](https://www.netapp.com/media/8991-tr4290.pdf)


#### Scale out NAS storage
A key contributor to the architecture of distributed scale-out NAS storage Infinite Volume. Designed and implemented various aspects of object storage conforming to CDMI specs.

- Implemented file system metadata search using embedded BerkeleyDB along with a multithreaded query execution engine with recursive parallelism based on the Intel TBB library
- Implemented core aspects of distributed file system consistency checker with a stateful file system crawler


### Technical Specialist, [McAfee](http://mcafee.com)
*Feb, 2006 - Feb, 2008*

Started the performance engineering initiative and built a team of 4 engineers to focus on performance engineering. 

- Established performance measuring tools and lab to capture predictable performance profiles and make them accessible to development teams.
- Implemented custom memory allocators to reduce lock contentions in multi-threaded service, resulting in ~25% increase in scan rate. Evaluated and benchmarked custom allocators from MicroQuill and Hoard


### Technical Specialist, HP
*Jan, 2006 - Feb, 2007*

Technical lead CIFS file server on the [VMS](http://vmssoftware.com) operating system, led cross team initiatives porting [Samba](http://samba.org). Implemented missing core POSIX APIs emulation on VMS required for the porting efforts along with porting `cvs` for streamlining maintaining VMS fork of Samba.

### Engineering Manager, [Bosch](https://www.bosch.com)
*Dec 2004 - Dec 2005*

Led cross-site teams developing a navigation point-of-interest data compiler chain for Blaupunkt car navigation systems. Delivered resiliency improvements and cost optimizations to multi-stage navigation data compiler suite.

* Transitioned complex project from parent organization in Germany and delivering under tight timelines. This involved hiring and rapid skill development to work in a large C++ codebase

### Technical Lead, [Delmia (Dassault Systemes)](http://3ds.com)
*Feb 1998 - Dec 2004*

Developed core features in a 3D simulation-based robotics and factory floor simulation software in C++ and cross-platform CATIA CAA V5 architecture.

- Team lead for integrating PLM solution `Process Engineer` and CATIA
- Core engineer developing CATIA V5 Composites
- Designed and implemented bi-directional import/export of DMIS programs for CMM machines with vendor-specific language variants
  - Designed and implemented a module to import DMIS (CMM/CNC programs) and create a 3D simulation model
  - Implemented DMIS program generation from a 3D simulation model
- Ported [LXR](https://lxr.sourceforge.io/en/index.php) to run on Microsoct Windows by using [SWISH-E](https://en.wikipedia.org/wiki/SWISH-E) for free text search. Maintained code search based on the port with custom search result sorting/ranking for internal use


### Production Engineer, Wipro Fluid Power
*Oct 1996 - Feb 1998*

Implemented tools and processes for continuous improvement in assembly line and shop floor.

* Implemented a CNC machine path simulator in `C` using Borland graphics primitives
* Implemented an inventory tracking system in `C` and dBase

------



## Awards and recognition

### [Patent](https://patents.justia.com/inventor/dhruva-krishnamurthy) 10812313 (granted)

[A federated namespace of heterogeneous storage system namespaces](https://patents.justia.com/patent/10812313)

#### Abstract
The patent covers a system and computer-based method for performing a data transaction in a network storage system by offering a federated file system namespace with a [POSIX](https://pubs.opengroup.org/onlinepubs/9699919799/)-compliant file system interface to access data stored across distributed decoupled heterogeneous storage entities along with policy-based data lifecycle management leveraging different storage tiers.

[https://patents.justia.com/patent/10812313](https://patents.justia.com/patent/10812313)

## Education

### Bachelor of Engineering, Mechanical
*08/1992 - 08/1996*

[National Institute of Engineering](https://nie.ac.in),
University of Mysore, Karnataka, India

Implemented generic finite element solver using [Skyline matrix](https://en.wikipedia.org/wiki/Skyline_matrix) in `C` for 2D structures and thermal distribution
