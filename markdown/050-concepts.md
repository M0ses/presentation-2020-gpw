<!-- .slide: data-state="normal" id="jobs-diagram" data-menu-title="Job (Diagram)" -->
# Jobs / Tasks / Kanku::Handler / Kanku::Utils

<img 
  alt="Kanku Overview Jobs" 
  src="images/Job-diagram.svg" 
  style="height: 75%;"
/>


<!-- .slide: data-state="normal" id="jobs-intro" data-menu-title="Job (Details)" -->
## Jobs

<img
  alt="Job stripped image"
  src="images/job-stripped.svg"
  style="float: right; height: 50%;"
/>

* A set of one or more Tasks
* loose coupling of Tasks
* JobContext for "communication" between Tasks 
  * K::H::OBSCheck -&gt; K::H::ImageDownload (download_url)
  * K::H::ImageDownload -&gt; K::H::CreateDomain (vm_image_file)
  * K::H::PrepareSSH -&gt; K::H::ExecuteCommandViaSSH (ip)


<!-- .slide: data-state="normal" id="tasks-intro" data-menu-title="Job (Tasks Details)" -->
## Tasks

<img
  alt="Job stripped image"
  src="images/job-stripped.svg"
  style="float: right; height: 50%;"
/>

* Uses exactly one Kanku::Handler and defined options
```
  -
    use_module: Kanku::Handler::CreateDomain
    options:
      domain_name: kanku-vm
```
* Will be executed once


<!-- .slide: data-state="normal" id="handler-intro" data-menu-title="Kanku::Handler" -->
## Kanku::Handler classes

<img
  alt="Tasks stripped image"
  src="images/tasks-stripped.svg"
  style="float: right; height: 35%;position: fixed;right: 1%;top: 1%;"
/>

* Requires three methods
  * prepare
  * execute
  * finalize
* Might have getters/setters to modify JobContext
  * Documented in POD
* multiple distribution modes
  * master only
  * worker only
  * all servers

Note:

* distribution mode examples
  * master only - K::H::PortForwarding
  * worker only - K::H::CreateDomain
  * all servers - K::H::RemoveDomain


<!-- .slide: data-state="normal" id="util-intro" data-menu-title="Kanku::Util" -->
## Kanku::Util classes

* Helper classes for Handlers
  * Reduce complexity in Handlers
  * Make functions/methods reusable between Handlers



<!-- .slide: data-state="normal" id="basic-arch" data-menu-title="Basic Architecture" -->
# Basic Architecture

<img
  alt="Tasks stripped image"
  src="images/Server-Distributed.svg"
  style="width: 100%;"
/>

