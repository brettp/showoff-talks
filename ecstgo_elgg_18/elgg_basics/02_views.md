!SLIDE subsection transition=scrollUp
# Views

!SLIDE bullets
# Views are easy!
* Just PHP scripts.
* Output chunks of content.
* Overrideable: replace content of original view.
* Extensible: prepend or append content to original view.

!SLIDE center
![Elgg 1.8](views1.png)

!SLIDE center
![Elgg 1.8](views2.png)

!SLIDE center
![Elgg 1.8](views3.png)

!SLIDE bullets incremental smaller
# Working with views
* View scripts are stored in `views/` dirs.
* View scripts are mapped to view name strings.
* New views use convention: put in `views/` and it Just Works™.
* Extending views use configuration: `elgg_extend_view($view_name, $view_extension_name)`

!SLIDE bullets smallest left
# View locations
## View names are just parts of the file path!
* View:
	<p class="pll blue">page/elements/header_logo</p>
* Core view script:
	<p class="pll">elgg/views/default/<span class="blue">page/elements/header_logo</span>.php</p>

!SLIDE bullets smallest left
# Overriding view locations
## Duplicate the view script directory path structure in a plugin
* View:
	<p class="pll blue">page/elements/header\_logo</p>
* Core view script:
	<p class="pll">elgg/<strong>views/default/<span class="blue">page/elements/header\_logo</span>.php</p></strong>
* Plugin override:
	<p class="pll">elgg/mod/my_theme/<strong>views/default/<span class="blue">page/elements/header\_logo</span>.php</strong></p>
	
!SLIDE bullets smallest left
# Core vs Plugins
## Core:
	elgg/
	└── views/
		└── default/
			└── page/
				└── elements/
					└── header_logo.php
_____

## Plugin:
	elgg/
	└── mod/
	    └── my_theme/
	        └── views/
		        └── default/
		  	        └── page/
		  	 	        └── elements/
		  	 		        └── header_logo.php


!SLIDE bullets most-smallest left
# Overriding view locations
## Overriding views from other plugins.
* View:
	<p class="pll blue">page/elements/header\_logo</p>
* Core view script:
	<p class="pll">elgg/<strong>views/default/<span class="blue">page/elements/header\_logo</span>.php</p></strong>
* Plugin override:
	<p class="pll">elgg/mod/<span class="red">my_theme</span>/<strong>views/default/<span class="blue">page/elements/header\_logo</span>.php</strong></p>
* <strong>Another plugin override:</strong>
	<p class="pll">elgg/mod/<span class="red">special_theme</span>/<strong>views/default/<span class="blue">page/elements/header\_logo</span>.php</strong></p>
* Override priority is determined by plugin load priority in Advanced Plugin section.

!SLIDE bullets smaller left
# Default?
## elgg/views/<strong class="blue">default</strong>/page/elements/header\_logo.php
* Views can output anything! HTML, RSS, JSON, serialized PHP.
* The `default` dir name is the view type.
* View types can be changed on any URL by appending:
	<p class="pll">`?view=<viewtype>`</p>
* RSS view type scripts live in: 
	<p class="pll">elgg/views/<strong class="blue">rss</strong>/page/elements/header\_logo.php</p>
* RSS view type URLs look like:
	<p class="pll">http://www.elggsite.org/activity?<strong class="blue">view=rss</strong></p>
	
!SLIDE
# Questions?