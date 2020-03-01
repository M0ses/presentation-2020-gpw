<!-- .slide: data-state="normal" id="motivation" data-menu-title="Motivation/Goals" -->
## Motivation/Goals
<div style="display: flex;">
<ul
   style="display:table-cell;vertical-align:top;"
>
<li>Easy working with OBS built images</li>
<li>Easy to configure (YAML)</li>
<li>Simple jobs in complex setups</li>
<li>Collaborative working</li>
<li>Scriptable (REST/cli remote client)</li>
</ul>
<div
   style="display:table-cell;vertical-align:top;"
>
<img
   alt="DevOps infinity loop"
   src="images/DevOps-infinity-loop.png"
/>
</div>
</div>

Note:

* changes in OBS appliance images
* No image testing in 2015
* POC for simple testing
* all components ready to replace vagrant
* vagrant -> kanku (Devel mode)


<!-- .slide: data-state="normal" id="getting-started" data-menu-title="Getting started" -->
# Getting started

```
kanku lsi -n Tumb
```

```
kanku init
```

```
kanku up
```


<!-- .slide: data-state="normal" id="just-one-yaml" data-menu-title="Just one YAML" -->

<img
   alt="You said all I needed was a YAML file"
   src="images/You_said_all_I-needed_was_a_YAML_file.jpeg"
/>


<!-- .slide: data-state="normal" id="kankufile" data-menu-title="KankuFile" -->
## KankuFile

<pre>
domain_name: kanku-vm
...

jobs:
 kanku-job:
  -
    use_module: Kanku::Handler::SetJobContext
    options:
      host_interface: eth0
  -
    use_module: Kanku::Handler::OBSCheck
...
  -
    use_module: Kanku::Handler::ImageDownload
  -
    use_module: Kanku::Handler::CreateDomain
...
  -
    use_module: Kanku::Handler::PrepareSSH
  -
    use_module: Kanku::Handler::ExecuteCommandViaSSH
    options:
      commands:
        - echo "my test here"
</pre>
