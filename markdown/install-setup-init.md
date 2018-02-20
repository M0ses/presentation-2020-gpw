<!-- .slide: data-state="normal" id="kanku-beginning" data-menu-title="Beginning with kanku" -->
## Beginning with kanku

<div
  style="display:flex;"
>
<div
  style="display:table-cell;vertical-align:top;width: 50%;"
>
  <ul>
    <li>Installation</li>
    <li>Setup</li>
    <li>First Project</li>
  </ul>
</div>
<div
  style="display:table-cell;vertical-align:top;width: 50%;text-align: right;"
>
<img 
  alt="Kanku Developer Mode Overview" 
  src="images/kanku-logo/kanku-tech-dev-mode.png"
/>
</div>
</div>


<!-- .slide: data-state="normal" id="kanku-installation" data-menu-title="Kanku Installation" -->
## Installation

### Add repositories

```none
su -
zypper ar obs://home:M0ses:Perl home:M0ses:Perl
zypper ar obs://home:M0ses:kanku home:M0ses:kanku
```

### Refresh local repository cache

```none
zypper ref -s
```

### Install kanku-cli

```none
zypper in kanku-cli sudo
```


<!-- .slide: data-state="normal" id="kanku-setup-devel" data-menu-title="Kanku Setup (Developer Mode)" -->
## Setup Developer Mode

```none
sudo /opt/kanku/bin/kanku setup --devel
sudo reboot
```


<!-- .slide: data-state="normal" id="kanku-init" data-menu-title="Kanku Initialize Project" -->
# Initial setup of your Project

<img 
  alt="Kanku Developer Mode Overview" 
  src="images/developer-mode.svg"
/>

```none
mkdir myNewProject
cd myNewProject
kanku init --memory 1024 --vcpu 1
kanku up
```
