---
title: "New Phantomize feature: automatic installation of tcollector sensor agent"
date: 2014-07-15
aliases: ["/2014/07/15/new-phantomize-feature-automatic-installation-of-tcollector-sensor-agent/"]
image: "images/news/service-thumb-1.jpg"
---

<div class="news-date">Jul 15, 2014</div>
<p>We are happy to announce &#8220;phantomize&#8221;, a  Phantom feature that will automatically install and run the tcollector  sensor agent on the first boot of your virtual machines thereby  automatically instrumenting your VMs to provide sensor measurements.</p>
<p>Phantom offers autoscaling based on sensor measurements from a  variety of sources, including user&#8217;s virtual machines. To collect these  measurements, Phantom relies on the tcollector sensor agent being  running on each of those virtual machines. Until now, users had to  manually install tcollector in their virtual machines or use an image  provided by us with tcollector already installed. The former requires  extra effort and the latter restricts the user to the types of images  provided by us.</p>
<p>The phantomize feature addresses this problem. To use it, all the  user needs to do is pick the &#8220;phantomize&#8221; contextualization type in  their launch configuration settings. The only requirement is that the  user&#8217;s virtual machine image is capable of downloading and executing the  user-data script on boot.</p>
<p>Phantomize has been tested successfully with Debian, Fedora, and  Ubuntu virtual machines on FutureGrid clouds running Nimbus and OpenStack.</p>
