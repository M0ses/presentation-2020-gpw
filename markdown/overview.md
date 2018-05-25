<!-- .slide: data-state="normal" id="overview" data-menu-title="Overview" -->
## Overview

* Kanku Modes
  * Developer Mode
  * Server Mode (Distributed)
* Basic Concepts
  * Jobs
  * Tasks
  * Kanku::Handler
  * Kanku::Utils
* Basic Architecture
  * Daemons / Activities / Components


<!-- .slide: data-state="normal" id="demo-devel-mod" data-menu-title="Demo Developer Mode" -->

<iframe src="http://localhost:8000/demo/devel-mode/demo-devel-mode.html" scrolling="no" frameborder="0"
    style="position: relative; height: 100%; width: 100%;"/>



<!-- .slide: data-state="normal" id="kanku-mode-devel" data-menu-title="Kanku Developer Mode" -->
### Developer Mode
<div style="display: flex;">
  <ul
    style="display:table-cell;vertical-align:top;width:50%;"
  >
    <li>Designed to run on Developers laptop</li>
    <li>Jobs triggered manually (`kanku up`)</li>
    <li>Offline mode (useful while travelling)</li>
    <li>Share project folder with VM</li>
  </ul>
  <div style="display:table-cell;text-align: right;width:50%;">
    <img 
      alt="Kanku Overview Developer Mode" 
      src="images/kanku-logo/kanku-tech-dev-mode.png"
    />
  </div>
</div>


<!-- .slide: data-state="normal" id="kanku-mode-server" data-menu-title="Kanku Server Mode" -->
### Server Mode
<div style="display: flex;">
  <ul
    style="display:table-cell;vertical-align:top;width:50%;"
  >
  <li> Scaleable due to distributed Server concept</li>
  <li> Jobs can either be triggered or scheduled</li>
    <ul>
    <li> triggered by </li>
      <ul>
	<li> kanku-triggerd</li>
	<li> kanku-web</li>
      </ul>
    <li> scheduled by kanku-scheduler</li>
    </ul>
  <li> Generate prepared/tested development VM</li>
  </ul>
  <div style="display:table-cell;text-align: right;width:50%;">
    <img 
      alt="Kanku Overview Developer Mode" 
      src="images/kanku-logo/kanku-tech-server-mode.png"
    />
  </div>
</div>


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
* Will be executed once
* multiple distribution modes 
  * master only
  * worker only
  * all servers


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

