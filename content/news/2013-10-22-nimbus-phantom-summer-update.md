---
title: "Nimbus Phantom summer update"
date: 2013-10-22
aliases: ["/2013/10/22/nimbus-phantom-summer-update/"]
image: "/images/news/service-thumb-1.jpg"
---

<div class="news-date">Oct 22, 2013</div>
<p>Hello Phantom Users!</p>
<p>As the days are getting shorter, and the air is getting cooler, we’d like to take one last look back on the summer and highlight the work we’ve done since we announced the Phantom HTTP API in early July. Some of you might have already noticed them in the interface and maybe even started using them – here’s a quick summary of the changes that already happened and how they fit into our strategy going forward.</p>
<p><strong>Support for Appliances</strong></p>
<p>We added support for appliances in Phantom. An appliance represents an environment that can support the execution of an application (e.g., Ubuntu Linux with MPI installed) and is typically implemented as a virtual machine image. However, since clouds use different virtualization technologies (such as KVM, Xen, or VMware) as well as various cloud-specific adaptations (e.g., a Xen image executing on EC2 may be different than a Xen image executing on a Nimbus cloud) an appliance typically maps to multiple VM images, each guaranteed to work with a different cloud. Working with appliances is simpler than having to remember which VM image works with which cloud and finding those images on all the clouds you wanted to run on.</p>
<p>It used to be that in the Phantom Launch Configuration tab you had to specify a VM image for each cloud. Now, there is an alternative to specify an appliance such that Phantom will automatically find which VM image needs to be used for any particular cloud you might run on. The Phantom installation on FutureGrid offers several pre-configured public appliances. You can also of course use the old method and specify an image per cloud.</p>
<p>The details of the pre-configured public appliances are defined at <a href="https://scienceclouds.org/appliances/">https://scienceclouds.org/appliances/</a>. You can find out what operating system version they support, what tools and libraries are installed, and what applications, or type of applications they were designed to support.</p>
<p>As an example, we have created a chef-server appliance. This appliance allows you to easily deploy the chef server which can be helpful in configuring contextualization services.</p>
<p>For now, only Phantom administrators can create appliances, but we are working on making the creation and sharing of appliances easier. In the meantime, if you have an appliance you&#8217;d like to share with the community, please to email the list and we will be happy to publish the appliance under your name.</p>
<p><strong>Contextualization</strong></p>
<p>Noting that many of our users use contextualization tools, we added support for contextualizing instances using Opscode Chef. Contextualization via a server provides a more flexible and powerful contextualization method than sending data using user-data. Phantom does the hard work of configuring each instance with a Chef Server and running Chef Client. You simply have to provide a list of Chef recipes and a Chef configuration in JSON format, which will be applied to each instance.</p>
<p>This feature requires the use of a Chef Server. You can either run your own with the Chef Server Appliance mentioned above, or Entreprise Chef, which is free for up to 5 nodes. Once you have a Chef Server available, configure your Phantom profile with your Chef credentials, which will enable Phantom to interact with the Chef Server on your behalf.</p>
<p>More information on this feature can be found under the following links:</p>
<ul>
<li style="list-style-type: none;">
<ul>
<li><a href="https://www.nimbusproject.org/doc/phantom/latest/webapp.html#configuring-your-profile">How to configure Chef credentials in your profile</a></li>
</ul>
</li>
</ul>
<ul>
<li style="list-style-type: none;">
<ul>
<li><a href="https://www.nimbusproject.org/doc/phantom/latest/webapp.html#creating-a-launch-configuration">How to configure Chef contextualization</a></li>
</ul>
</li>
</ul>
<p>In the future we are planning to make Chef server deployment ever easier, to provide pre-baked deployment templates for popular constructs such as virtual clusters, and to provide generic mechanisms for contextualizing groups of virtual machines.</p>
<p><strong>SSH key upload</strong></p>
<p>Every cloud user needs an SSH key pair to connect to cloud instances: while the private key stays secure on your own machine, the public key is imported inside your instances. In order to do this, each cloud must know your public key. In the past, unless you were using FutureGrid Nimbus clouds, you had to upload keys manually to each cloud using command line tools. Now you can do it directly from the Phantom web interface, which is much easier!</p>
<p><a href="https://www.nimbusproject.org/doc/phantom/latest/webapp.html#configuring-your-profile">How to add an SSH key</a></p>
<p>We hope you enjoy those new features and please, let us know what you think! We would like to take this opportunity to acknowledge and thank users who shared exceptional insight on Phantom features in the last quarter: Jan Balewski and Pradeep Mantha, and whose comments will shape the service going forward. Stay tuned, we have lots of exciting new things coming up in the fall!</p>
