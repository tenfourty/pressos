
### Agile, DevOps, Continuous Delivery and Lean - How do you tie it all together in GCloud?
#### Red Hat Breakout, Think GCloud March 2014
Jeremy Brown - Head of Middleware UK&I, Red Hat

[@tenfourty] [1]
[1]: http://twitter.com/tenfourty/ "@tenfourty"
<jeremy@redhat.com>

---

## Let's TALK about the RED HAT model...

--

## Many variations vendors take on open source

* Some enable optimizations for their hardware <!-- .element: class="fragment" data-fragment-index="1" -->
* Some use open-core to upsell proprietary add-ons <!-- .element: class="fragment" data-fragment-index="2" -->
* Some invest in focused areas <!-- .element: class="fragment" data-fragment-index="3" -->
* Some contribute little and soley ship and support <!-- .element: class="fragment" data-fragment-index="4" -->

--

## AND SOME...
# GO ALL IN <!-- .element: class="fragment" data-fragment-index="1" -->

--

![Red Hat Leads Through Open Innovation](/content/RedHatModel/img/rht-lifecycle.png) <!-- .element: class="noshadow" fullscreen-size="contain" -->

--

## Shadowman update
### Reached $1.33B in FY13 <!-- .element: class="fragment highlight-red" -->

![10 Years of RHEL](/content/RedHatThinkGCloud2014/img/RHEL_10year-02.png) <!-- .element: class="noshadow" -->

--

## Is Open Source a Business Model?

* No <!-- .element: class="fragment" data-fragment-index="1" -->
* But it is the best DEVELOPMENT model on the planet <!-- .element: class="fragment" data-fragment-index="2" -->
* Enables collaboration <!-- .element: class="fragment" data-fragment-index="3" -->
* Gives users flexibility to consume on their terms <!-- .element: class="fragment" data-fragment-index="4" -->

---

## Recap - Why are we doing this cloud thing anyway?

* Save money
* Agility - turn our infrastructure into a PAYG utility model
* Lock in
* What else?

Note: "IT is changing dramatically, which is not to say there won't be some IT organizations 20 years from now that look like IT organizations did 20 years ago.

But when I think about the changes, increasingly the basic functions that IT organizations spent 70 percent of their time delivering — compute, storage, and networking — can be purchased, and they can be purchased from third parties. This is utility computing. So the organizations that figure that out and start to purchase those at commodity rates rather than continuing to generate custom solutions themselves will position themselves to get ahead.

--

## Now we need some buzzwords
### these are key themes that have influenced my thinking <!-- .element: class="fragment" data-fragment-index="1" -->

--

## [Pets vs Cattle] [1]

* Pets are given names like pussinboots.cern.ch <!-- .element: class="fragment" data-fragment-index="1" -->
* The are unique, lovingly hand raised and cared for <!-- .element: class="fragment" data-fragment-index="1" -->
* When they get ill, you nurse them back to health <!-- .element: class="fragment" data-fragment-index="1" -->
* Cattle are given numbers like vm0042.cern.ch <!-- .element: class="fragment" data-fragment-index="2" -->
* They are almost identical to other cattle <!-- .element: class="fragment" data-fragment-index="2" -->
* When they get ill, you get another one <!-- .element: class="fragment" data-fragment-index="2" -->

![Pet](/content/DevOps/img/pet.png) <!-- .element: class="fragment" data-fragment-index="1" --> ![Cattle](/content/DevOps/img/cattle.png) <!-- .element: class="fragment" data-fragment-index="2" -->

Future application architectures should use Cattle but Pets with strong configuration management are viable and still needed <!-- .element: class="fragment" data-fragment-index="3" -->

[1]: http://www.slideshare.net/gmccance/cern-data-centre-evolution

--

## Continuous Delivery

![Continous Delivery Process Diagram](/content/DevOps/img/Continuous_Delivery_process_diagram.png) <!-- .element: class="noshadow" -->

https://en.wikipedia.org/wiki/Continuous_delivery

--

## DevOps

* Where Developers and Operations meet - DevOps
* But it's much more than that!
    * DevOps is about the business <!-- .element: class="fragment highlight-red" data-fragment-index="1" -->
    * You can't write code with agile and deploy waterfall! <!-- .element: class="fragment highlight-red" data-fragment-index="1" -->

![DevOps Diagram](/content/DevOps/img/Devops.svg) <!-- .element: class="noshadow" -->

https://en.wikipedia.org/wiki/DevOps

--

## Lean Startup
##### It's not just for startups, it's a cultural pattern

![Lean Methodology Diagram](/content/DevOps/img/lean_methodology_diagram.jpg) <!-- .element: class="noshadow" -->

#### Lets ship the MVP (Minimum Viable Product)!

http://theleanstartup.com/principles

--

## Infrastructure as Code

The implication of Continuous Deployment, DevOps and Lean is that we need to start treating infrastructure as code

* This will allow us to reduce cycle time
* And version our infrastructure

---

## Customer's Vision

Red Hat Strategic Advisory Board meeting with CIOs from several of our top customers:

> "They want to describe and automate all their systems and applications fully with software, from hardware up through complex, multi-tier apps and services.

> They want to provision and manage the lifecycle of everything (Linux and Windows, private and public clouds) in an automated fashion.

> Several said this was the holy grail for them" <!-- .element: class="fragment highlight-red" data-fragment-index="1" -->

---


## Meanwhile... 
## up in the G-Clouds

* We have many G-Clouds
* Clouds have different security classifications
* Clouds have different APIs - tied to the cloud provider so our apps are not portable

---

## Customer's Problem

Red Hat Strategic Advisory Board meeting with CIOs from several of our top customers:

> "One of the problems they have is that everyone is defining APIs for their own platforms, but they can’t take workloads from one to another because the APIs they use for orchestration are different."

---

## Tying it all together

* How do we "plumb" an application together that has different bits in different clouds?
	* My data might be in one cloud
	* My main application(s) are in a different cloud
	* I might have a REST API exposed that runs in a third cloud

---

## Future: Vision

* Top-level application stack “manifest”
    * defines configuration and relationships of all services which comprise an application
    * cross-service (e.g. {NW,St,DB,I,aP,xP,LB,DNS}aaS)
    * defines how to create/update/delete the entire application, perhaps even suspend/resume
* Enables efficient automatic application creation and deletion
    * Relevant across dev, QA, prod
* An enabler for DevOps
* Defrag the Data Centre - free up resources

---

## Future: go “meta”

* Application stack templates
* Example: “give me a disaster resilient JEE app with a preconfigured database”

* App manifests move from Word documents to become machine-processable
    * Automatic reasoning about application estates (auto-scaling, capacity management, DR analysis, etc.)
    * Simplification, standardisation and efficiency gains across the board

---

## Let me introduce you to an idea
### This might be pie in the sky but there is real code!<!-- .element: class="fragment" data-fragment-index="1" -->

--

## OpenStack Heat

Inspired by (and compatible with) Amazon Cloud Formations

Mission:
> The mission of the OpenStack Orchestration program is to create human and machine-accessible services for managing the entire lifecycle of infrastructure and applications within OpenStack clouds.



https://wiki.openstack.org/wiki/Heat

--

## How it works

* A Heat template describes the infrastructure for a cloud application in a text file that is readable and writable by humans, and can be checked into version control, diffed etc.
* Heat also provides an autoscaling service, so you can include a scaling group as a resource in a template.
* Templates can also specify the relationships between resources (e.g. this volume is connected to this server).
* Heat manages the whole lifecycle of the application - when you need to change your infrastructure, simply modify the template and use it to update your existing stack. Heat knows how to make the necessary changes. It will delete all of the resources when you are finished with the application, too.
* It has a pluggable resource adapter framework - plugins are easy to write for your own cloud

--

## Oh and it's open source and has a strong community

* OpenStack Havana Release
    * 837 commits and 67 unique technical authors
* OpenStack Icehouse Release
    * 499 commits and 71 unique technical authors

--

## Caveat: the project is just focused on OpenStack
### For now...

---

## To Summarise

* We have a problem with each cloud provider having a different API, so our applications are still stuck and we can't treat our infrastructure as code
* If we can't treat our infrastructure as code we can't do real DevOps, Continuous Delivery and Lean
* We need an open standard and a project that we rally around for application orchestration
    * Is this Heat in the OpenStack project?
    * A Heat resource adapter for every G-Cloud?
* Come and join the discussion, we are a community!
    * email me - <jeremy@redhat.com>

---

## What do these have in common?
* Linux
* OpenStack
* Hadoop
* Rails
* MongoDB
* Git
* Cassandra

--

## What do these have in common?
* They are all open source
* They are all examples of next-generation IT solutions
* They were started by users and developers, not companies

--

## Cloud without open source software?
* No Amazon
* No Rackspace
* No Google
* No Yahoo!
* No Salesforce.com
* No LinkedIn
* No Pandora
* No Twitter
* No Facebook

---

## Thank you
This [presentation] [1] is running on [OpenShift] [2],

the source code is on [GitHub] [3]

and it was developed in HTML5 with [reveal.js] [4]

Jeremy Brown [@tenfourty] [5]

[1]: http://pressos-runningonthe.rhcloud.com/theRedHatModel.html
[2]: http://www.openshift.com/ "OpenShift"
[3]: https://github.com/tenfourty/pressos
[4]: https://github.com/hakimel/reveal.js "reveal.js"
[5]: http://twitter.com/tenfourty/ "@tenfourty"
<jeremy@redhat.com>

![Red Hat](/content/common/img/Red_Hat_RGB.png) <!-- .element: class="noshadow" -->

