# Resume

```
Name: Dhruva Krishnamurthy
Email: dhruvakm@gmail.com
Phone: +1 (408) 623-0605
Location: California, United States
```

- Resume: [https://mechanicker.github.io/resume.html](https://mechanicker.github.io/resume.html)
- GitHub profile: [https://github.com/mechanicker](https://github.com/mechanicker)
- LinkedIn profile: [https://www.linkedin.com/in/dhruvakm/](https://www.linkedin.com/in/dhruvakm/)

## Objective

20+ years of software design & development experience involving cross-site collaboration across multiple technologies and domains, having led numerous initiatives improving the performance of products and services, delivering impactful customer value with tangible cost savings. Thrive in situations demanding innovative, out-of-the-box problem-solving approaches. I am seeking opportunities to leverage my expertise in a dynamic and innovative environment with high customer impact.

## Skills

### Proficiency
- Distributed systems and developing cloud-native backend microservices on [`AWS`](http://aws.amazon.com)
- Design and implement scalable `CI/CD` systems, data pipelines, and data lifecycle management
- File systems and systems programming using the POSIX interface
- System programming, performance troubleshooting, and related tool development on both Unix and Microsoft Windows (`Win32` API)
- Source code management systems, [`git`](https://git-scm.com) and [`libgit2`](https://libgit2.org) internals
- C, C++, Go, Python, and Java
- Troubleshooting and debugging distributed systems, debuggers, and profilers across operating systems

### Working knowledge

- Traditional and NoSQL databases
- Memcached, Redis and BerkeleyDB key/value stores
- [Boost](http://boost.org) C++ library
- Parser development using Lex & Yacc and similar tools

------

## Experience

### Principal engineer, [Atlassian](https://www.atlassian.com/)
*Jan 2017 - Current*

#### [Bitbucket](http://bitbucket.org)

##### Performance and scaling

I have led multiple cross team initiatives to improve Bitbucket performance involving designing and implementing innovative caching solutions to achieve low latency and low contention. The distributed repository storage with concurrent access using stateless NFSv3 at cloud scale makes it challenging.

* Worked across the product to support a very active large-scale `monorepo` by optimizing file storage with custom caching to support high-frequency git operations on a single repository.
* Designed and implemented IO latency based dynamic throttling penalizing excessively active requests based on load patterns. This resulted in better resource utilization under normal loads and faster recovery during overload.
* Designed a novel cache invalidation technique with custom modifications to git.
* Designed and led the implementation of git bundle-uri service for Bitbucket. Resulted in significant reduction in NFS load by serving repository snapshots from AWS S3. This led to overall cost reduction in serving git repositories at scale.
* Evaluated various data storage vendors as part of modernizing repository storage. Leveraged auto tiering built into storage to implement cost optimizations. Architected live data migration for ~2.5 petabytes of data to benefit from redesigned repository storage infrastructure.
* Proposed a novel algorithm to fence writes during git repository migrations. This is a key building block for repository migrations at scale and load based rebalancing of repository storage.
* Implemented custom caching backend for all git operations via `libgit2` using `memcached`. Read-ahead logic based on repository access patterns helps realize better page cache hits by preloading data before access.
* Prototyped consistency hashing based `gRPC` routing service for highly available distributed git repository access.
  - Reduced latency of expensive IO operations through improved `fscache` and page cache hits.

##### Data management

* Leading the design and implementation of unified repository archival, backup and serving archived repositories from cheaper AWS S3 storage tier.
* Architected live git repository migrations with no/minimal customer impact. This is now a critical Bitbucket infrastructure to seamlessly move petabytes of data across a storage vendor-agnostic backend. More details from vendor success story at: https://aws.amazon.com/partners/success/atlassian-netapp/
* Designed and implemented cross region git repository replication with predictable performance and meet SLAs honoring the recovery point objective.

##### Cost optimization

* Prototyped tiered storage for git repositories. Led multiple coordinated efforts to realize cost optimizations based on the prototype. We have successfully moved ~70% of data to a cheaper storage tier with redundancy.
* Implemented repository storage IO offload to AWS S3 and read replica resulting in better resource utilization and cost benefits.
* Scaleout storage for handling large `monorepo` by sharding contents of single repository across multiple storage controllers. This has given us increased throughput to serve extremely active git repositories without maintaining multiple redundant read replicas.

##### Miscellaneous

- Maintainer of Bitbucket fork of git with enhancements to increase robustness in a distributed storage environment.
  * Implemented enhancements to recover from crashes with a reliable cleanup, completely eliminating support requests to recover from corrupt git repositories.
  - Improved observability into problems git operations encounter operating in distributed environments with shared data access.
  - Undertook git upgrade from 2.10.5 version to the current version, designed and implemented progressive rollout support, and streamlined the git upgrade process for Bitbucket.
- Implemented parallel unarchiving tool [`puntar`](https://github.com/mechanicker/puntar) to speed up restoring PostgreSQL database backup archives.
- Submitted patches to upstream libgit2 to improve the performance of repositories accessed over the network file system.
  - Implemented `mmap` emulation to disable operating system provided `mmap` for consistent shared access to git repositories.
- Prototyped non-intrusive crypto mining detection and prevention mechanism for Bitbucket pipelines.

#### Cross product search

As part of implementing GDPR compliance, we decided to consolidate user-identifiable information and enforce tighter access controls. User search is a critical component used across Atlassian services.

- Responsible for the user search data pipeline for ingesting user information and indexing for search.
- Implemented core parts of user search backend services to manage the lifecycle of search data with a denormalized permissions model to support permission-aware search.

#### Trust & Identity

Unified role-based permission model for seamless user experience across Atlassian services.

- Implemented and operationalized a highly scalable and resilient data pipeline for ingesting real-time permission data.
- Built detection and optimal recovery mechanisms during partial/total data loss in the pipeline due to upstream failures.

### Senior engineer, [NetApp](http://netapp.com)

*Feb, 2008 - Jan, 2017*

#### NFSv4 server performance lead
With an open mandate to improve NFSv4 server performance and make NFSv4 a compelling alternative to NFSv3, I worked on streamlining performance testing, followed by implementing performance improvements.

- Established predictable and repeatable baseline performance metrics.
- Identified custom workloads for performance improvements.
- Served as a liaison between NFS and the wider performance engineering team.
- Improved NFSv4 IO performance by ~40% by implementing in-kernel buffer caching.
- Simplified NFSv4 server-side state lifecycle management using C++ `RAII`.

[SAP Hana over NFSv4](https://docs.netapp.com/us-en/netapp-solutions-sap/pdfs/sidebar/SAP_HANA_on_NetApp_FAS_Systems_with_NFS_Configuration_Guide.pdf)
Designed and implemented a client-side performance improvement library to increase overall IO throughput by ~50%, critical for SAP Hana workloads. SAP qualifying NetApp NFSv4 depended on these performance improvements.

- Developed [IOtrap library](https://github.com/mechanicker/iotrap) to transparently use `asyncio` to improve performance via `IO` interception. This was later incorporated into the SAP Hana core engine. SAP Hana now supports configuring `async` IO parameters.
- NetApp published best practices for SAP Hana over NFSv4 ["Configuration of Performance Test Tool"](https://www.netapp.com/media/8991-tr4290.pdf).

#### Scaleout NAS storage

As a core member of the architecture group designing distributed scale-out NAS storage `Infinite Volume`, I played a significant role in developing object storage, cluster-wide file system metadata search, and file system recovery. Infinite Volume allowed NetApp to better compete with other storage vendors ([Isilon](https://www.dellemc.com/content/emc/en-ph/storage/isilon/)).

- Core contributor to distributed search service for file system metadata using NoSQL (BerkeleyDB).
  - Designed and implemented optimized tree-based complex query expression execution engine using Intel TBB (Threading Building Blocks) library based on recursive parallelism.
  - Tuned the query engine and delivered ~5x improvements for complex queries involving multiple fields and logical operators.
  - Prototyped porting BerkeleyDB to kernel space and benchmarked against running search service in user space.
- Designed and implemented various components of CDMI object versioning using NetApp file system technologies.
- `HTTPS` support for CDMI by tunneling from the kernel network layer to external SSL terminating service.
- Led the initiative to implement CDMI conformance and performance testing suite.

#### Storage management

* Implemented statistical methods using C++ Boost libraries for NetApp performance advisor. This enabled the frontend team to implement advanced performance data analytics using the NetApp storage management suite.
* Designed and implemented zero-configuration storage controller discovery in a data center based on ICMP/ICMPv6 packet broadcast/response mechanism.
* Developed a prototype of scaleout distributed storage management to overcome limitations in the storage management suite allowing managing 500+ controllers from 50 with a single clustered installation of the storage management suite.
* Designed and implemented a real-time SQL parser to translate Sybase specific syntax to Oracle.

### Technical Specialist, [McAfee](http://mcafee.com)

*Feb, 2006 - Feb, 2008*

- As a lead performance engineer, built a team of 4 engineers to focus on performance engineering.
- Developed methodologies to measure performance.
- Implemented custom memory allocators to reduce lock contention in multi-threaded service resulting in ~25% increase in scan rate.
  - Evaluated and benchmarked custom allocators from MicroQuill and Hoard.

### Technical Specialist, HP

*Jan, 2006 - Feb, 2007*

- Led initiative to port [Samba](http://samba.org), an open-source CIFS file server on the [VMS](http://vmssoftware.com) operating system.
- Implemented missing core POSIX APIs emulation on VMS required for porting Samba.
- Ported `CVS` source code management tool to VMS and transitioned tracking Samba on VMS to `cvs`.
	- Refactored large parts of scattered VMS-specific changes to reduce merge conflict.
	- This led to the reduction in time to merge upstream changes and made it easier to stay in sync with upstream.

### Engineering Manager, [Bosch](https://www.bosch.com)

*Dec 2004 - Dec 2005*

- Led a cross-site team developing a navigation point-of-interest data compiler chain for Blaupunkt car navigation systems. Improved resiliency of multi-stage compiler and delivered cost optimizations by reducing processing time from multiple weeks to days.
- Team building, requirements gathering, project tracking, and coordination with the team in Germany.
- Transition data compiler pipeline from Sun SPARC servers to SUSE Linux, eliminating expensive annual maintenance contract with Sun Microsystems.

### Technical Lead, [Delmia (Dassault Systemes)](http://3ds.com)

*Feb 1998 - Dec 2004*

Developed core features in a 3D simulation-based robotics and factory floor simulation software in C++ and cross-platform CATIA CAA V5 architecture.

- Team lead for integrating PLM solution `Process Engineer` and CATIA.
- Core engineer developing CATIA V5 Composites.
- Designed and implemented bi-directional import/export of DMIS programs for CMM machines with vendor-specific language variants.
  - Designed and implemented a module to import DMIS (CMM/CNC programs) and create a 3D simulation model.
  - Implemented DMIS program generation from a 3D simulation model.
- Ported [LXR](https://lxr.sourceforge.io/en/index.php) to run on Microsoft Windows by using [SWISH-E](https://en.wikipedia.org/wiki/SWISH-E) for free text search. Maintained code search based on the port with custom search result sorting/ranking for internal use.

### Production Engineer, Wipro Fluid Power

*Oct 1996 - Feb 1998*

Worked in a hybrid environment involving production on the shop floor and automating processes for production. This exposed me to real-world manufacturing problems and an opportunity to solve them using software-based technologies.

* Implemented a CNC machine path simulator in `C` using Borland graphics primitives.
* Implemented an inventory tracking system in `C` and dBase.

------

## Awards and recognition

### [Patent](https://patents.justia.com/inventor/dhruva-krishnamurthy) 10812313 (granted)

[A federated namespace of heterogeneous storage system namespaces](https://patents.justia.com/patent/10812313)

#### Abstract
The patent covers a system and computer-based method for performing a data transaction in a network storage system by offering a federated file system namespace with a [POSIX](https://pubs.opengroup.org/onlinepubs/9699919799/)-compliant file system interface to access data stored across distributed decoupled heterogeneous storage entities along with policy-based data lifecycle management leveraging different storage tiers.

### Recognition at work

- Appreciation and peer bonus for implementing significant performance improvements using ASYNC IO, leading to around $30,000 in savings per month.
- Improved cache utilization leading to cost savings by reducing the fleet of servers required to handle the load.
- Implemented transparent cloud-scale `git` object caching layer to significantly lower NFS IO.
- Secured 2nd place in NetApp-wide `hackathon` (leading to patent filing).
- Recognition and award for implementing search service for file system metadata at NetApp.
- Received employee excellence award for `1999 - 2000` at Delmia.

## Education & certifications

### Bachelor of Engineering, Mechanical
### Intel VTune

Underwent hands-on training on using [Intel VTune](https://software.intel.com/content/www/us/en/develop/tools/oneapi/components/vtune-profiler.html) for troubleshooting performance bottlenecks in performance-critical multi-threaded applications.

- Effectively implemented the learnings to solve performance problems in [McAfee Antivirus](https://www.mcafee.com).
- Applied learnings during the implementation of the search query execution engine at NetApp.

### Unix & C

- 6-month practical training program to learn Unix system programming using `C`.

## Other projects and links to referred articles

- Patent 10812313, "Federated namespace of heterogeneous storage system namespaces": [https://patents.justia.com/patent/10812313](https://patents.justia.com/patent/10812313)
- Parallel unarchive command line tool `puntar`: [https://github.com/mechanicker/puntar](https://github.com/mechanicker/puntar)
- `IOtrap` library for `IO` throughput improvement: [https://github.com/mechanicker/iotrap](https://github.com/mechanicker/iotrap)
- Win32 function call profiler: [https://github.com/mechanicker/cramp](https://github.com/mechanicker/cramp)
- NetApp best practices for SAP Hana using `asyncio`: [https://www.netapp.com/media/8991-tr4290.pdf](https://www.netapp.com/media/8991-tr4290.pdf)
