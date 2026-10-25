---
layout: page
title: Distributed Storage Systems — Xiaomi
description: Integrating erasure-coded storage, validating correctness and recovery, and tracing performance from coding libraries to file I/O.
img:
importance: 5
category: engineering
---

**Connecting coding performance with system reliability**

At Xiaomi, I worked on the enterprise **NCDSS distributed-storage system**, integrating network- and erasure-coding components and evaluating their behavior from individual coding operations through end-to-end file access and recovery.

**Role:** Research Engineer Intern | Distributed Systems & Cloud Infrastructure.<br>
**Dates:** May–September 2024.<br>
**Location:** Beijing & Shenzhen, China.

## System integration

I deployed and configured the system's database, coordination, coding, and file-system services in a **60-node Linux environment**, validating erasure-coded storage with **K=4, M=2**. This configuration divides data into four data fragments and adds two parity fragments for recovery.

The integration work involved making the services function together, checking process and dependency failures, and validating file access through the mounted distributed file system. I wrote file read/write demos and documented deployment issues and their resolutions.

## A layered reliability workflow

I built a workflow that checks correctness at the coding layer before testing the full storage path. This made it easier to distinguish coding errors from file-I/O and service-level failures.

| Layer             | What I validated                                                                                                                 |
| ----------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| Coding operations | Consistency after encoding, decoding, repair, and update operations, using coding-module demos and validation scripts            |
| Client file I/O   | Read/write, overwrite, and append behavior, including full segments, partial segments, and transitions across segment boundaries |
| Failure recovery  | End-to-end data integrity and recovery under simulated storage failures                                                          |

The workflow covered **50+ client-I/O correctness scenarios** across **2KB–1GB workloads**. Tests compared written data with the data read back, so a completed operation also had to preserve the expected content.

## Performance analysis

I benchmarked distributed coding implementations across **eight baselines and 48 paired tests**. Coding-module benchmarks were considered alongside client upload/download tests and file-system measurements, connecting the performance of individual components with the behavior visible to a storage client.

Source-level inspection and debugging helped trace bottlenecks through coding interfaces, buffer handling, and the I/O path. I used coding demos and client tools for focused comparisons, **fio** for file-system measurements, and **GDB and Valgrind** for debugging and memory analysis.

| Measure                      | Improvement      |
| ---------------------------- | ---------------- |
| Encoding throughput          | **81.5% higher** |
| End-to-end upload throughput | **22% higher**   |
| Recovery latency             | **12% lower**    |

These measurements distinguish component throughput from end-to-end throughput and recovery latency. A faster coding implementation is useful when its benefits carry through to the complete storage workflow.

## My contribution

- Integrated and validated the storage services and coding components in Linux.
- Built validation scripts and client test cases for normal operations, boundary cases, and recovery.
- Compared coding implementations and investigated performance bottlenecks across the storage stack.
- Recorded benchmark results and documented deployment and test procedures.

**Stack:** C/C++, Bash, Linux, NCDSS, erasure coding, fio, GDB, and Valgrind.

[Experience]({{ '/experience/' | relative_url }}) · [All projects]({{ '/projects/' | relative_url }})
