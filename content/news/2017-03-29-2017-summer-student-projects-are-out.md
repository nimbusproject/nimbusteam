---
title: "2017 summer student projects are out!"
date: 2017-03-29
aliases: ["/2017/03/29/2017-summer-student-projects-are-out/"]
image: "/images/news/service-thumb-1.jpg"
---

<div class="news-date">Mar 29, 2017</div>

<p>We are looking for summer student to work on three different projects. The work location is the Argonne National Laboratory, near Chicago, Illinois. If you are interested in working with us on any of these, contact <a href="/cdn-cgi/l/email-protection#5e353b3f363b271e333d2d703f303270393128">Kate Keahey</a>.</p>

<p><strong>Investigating Hadoop dynamic scaling</strong></p>

<p>We are creating a platform for running geospatial analysis operations in a scalable manner using cloud computing resources. In order to support large number of users with varying workloads, the platform must dynamically manage deployments of compute resources.</p>

<p>Hadoop is heavily used by applications running on this platform. The purpose of this project is to study scalability patterns of a geospatial analysis application, UrbanFlow, in order to derive scaling policies that will allow to dynamically vary the number of Hadoop workers in the system to provide a good response time. Since data and locality in particular is crucial to Hadoop, this project will evaluate how data placement patterns can help or prevent dynamic scaling.</p>

<p>The objectives of this project are:</p>

<ul class="wp-block-list">
<li>Study data access and computing patterns of UrbanFlow</li>

<li>Propose scaling policies using these patterns that will optimize response time for various workloads</li>

<li>Develop a dynamic scaling engine that can enact such policies</li>
</ul>

<p><strong>Cloud workload trace archive</strong></p>

<p>Traces from existing parallel and distributed computing systems are a useful resource for researchers to replicate real-life workloads for their experiments. However, there is little material available from cloud computing systems. We propose to develop a trace archive that will provide traces from various clouds systems combined with tools to replay them. This effort originally focuses on OpenStack clouds, but would eventually include other cloud technologies.</p>

<p>The objectives of this project are:</p>

<ul class="wp-block-list">
<li>Define a cloud workload trace format after reviewing existing traces format. This format should be flexible enough to support other cloud technologies in the future.</li>

<li>Develop tools to extract workload from OpenStack systems, converting into the chosen trace format.</li>

<li>Develop tools to replay traces on an OpenStack deployments for experimental purposes. We will use the Chameleon testbed as a platform for deploying OpenStack.</li>

<li>Create a platform (potentially reusing existing software) for hosting traces and allowing others to contribute.</li>
</ul>

<p><strong>HPC/Cloud resource balancer</strong></p>

<p>We are working on a platform that seeks to combine two types of scheduling: batch/best-effort scheduling typically used in HPC datacenters and on-demand scheduling available in commercial clouds. This project is developing a meta-scheduler that switches between these different modes of scheduling to ensure meeting both user satisfaction goals (in terms of resource availability) and provider satisfaction (in terms of utilization). The overall objective of this project is to use an existing implementation and a set of traces from on-demand and batch jobs and explore different usage scenarios in this context.</p>

<p>The relevant tasks are as follows:</p>

<ul class="wp-block-list">
<li>Evaluate and potentially enhance existing implementation to add additional features</li>

<li>Define and run experiments evaluating features of the resulting platform</li>

<li>Contrast and compare the work with existing platforms such as Mesos</li>
</ul>
