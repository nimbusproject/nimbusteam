---
title: "FutureGrid multi-cloud VM image generator now available"
date: 2014-06-04
aliases: ["/2014/06/04/futuregrid-multi-cloud-vm-image-generator-now-available/"]
image: "images/news/service-thumb-1.jpg"
---

<div class="news-date">Jun 04, 2014</div>
<p>We are happy to announce the alpha release of our newest tool for FutureGrid users: a multi-cloud VM image generator.</p>
<p>FutureGrid offers access to multiple clouds based on several different technologies (Nimbus, OpenStack, and Eucalyptus) using different hypervisors (Xen or KVM). Users can also supplement the use of FutureGrid resources by bursting out to commercial clouds such as Amazon EC2. While this allows users to use multiple clouds, such access is often hard to leverage as VM images are generally not portable across different formats and cloud providers.</p>
<p>This presents users with a few problems. First, moving from one cloud to another means creating a new image; this is time-consuming and error-prone. Second, users typically want the VM images to represent a consistent environment independently of what type of cloud the image is deployed on; this is hard to achieve using a manual configuration process as even small differences in configuration can have significant consequences. Third, even if the user does produce a set of images that are initially consistent, as images subsequently evolve it is hard to keep track of which changes were applied to which image. In short, the problem is the lack of traceability and repeatability of VM image customizations.</p>
<p>Our image generator aims to solve these problems by providing an interface to specify a customization script that can be used to generate consistent images for many clouds. The service starts out with a set of consistent images uploaded to several clouds, applies them to those images, and creates a new VM image on each cloud.</p>
