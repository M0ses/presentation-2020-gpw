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

