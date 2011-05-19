!SLIDE subsection transition=scrollUp
# Elgg plugins
### They don't have to be so ugly!

!SLIDE bullets
# Helpful links
* Code standards - http://el.gg/codestandards
* Code standards checker - http://sniff.elgg.org
* Plugin guidelines - http://el.gg/pluginguidelines

!SLIDE smaller 
# A well-formed plugin is a happy plugin.
	mod/example_plugin/
				actions/
				classes/
				languages/
				lib/
				pages/
				views/
				activate.php
				deactivate.php
				manifest.xml
				start.php
				
!SLIDE smaller 
# A well-formed plugin is a happy plugin.
	mod/example_plugin/		     <-- Dir name is the Plugin ID.
				actions/
				classes/
				languages/
				lib/
				pages/
				views/
				activate.php
				deactivate.php
				manifest.xml     <-- Describes plugin. Required.
				start.php        <-- Inits the plugin. Required.
				
!SLIDE smallest
	@@@ xml
	<?xml version="1.0" encoding="UTF-8"?>
	<plugin_manifest xmlns="http://www.elgg.org/plugin_manifest/1.8">
		<name>Plugin Skeleton</name>
		<author>Any Person</author>
		<version>0.1</version>
		<blurb>A concise description.</blurb>
		<description>A longer, more interesting description.</description>
		<website>http://www.nowhere.org/</website>
		<copyright>(C) No one 2011</copyright>
		<license>GNU Public License version 2</license>

		<requires>
			<type>elgg_version</type>
			<version>2009030802</version>
			<comparison>gt</comparison>
		</requires>
	</plugin_manifest>

!SLIDE tiny
	@@@ php
	elgg_register_event_handler('init', 'system', 'bookmarks_init');
	
	function bookmarks_init() {
		elgg_register_action('bookmarks/save', "$action_path/save.php");
		
		[snip]
	
		// menus
		elgg_register_menu_item('site', $menu_options);
	
		elgg_register_page_handler('bookmarks', 'bookmarks_page_handler');
	
		elgg_extend_view('css/elgg', 'bookmarks/css');
		elgg_extend_view('js/elgg', 'bookmarks/js');
	
		// Register entity type for search
		elgg_register_entity_type('object', 'bookmarks');
	}
	
	function bookmarks_page_handler($page) {
		elgg_push_breadcrumb(elgg_echo('bookmarks'), 'bookmarks/all');
		elgg_push_context('bookmarks');
	
		$pages = dirname(__FILE__) . '/pages/bookmarks';
	
		switch ($page[0]) {
			case "all":
				include "$pages/all.php";
				break;
			
			[snip]
	
			default:
				return false;
		}
	
		elgg_pop_context();
		return true;
	}

!SLIDE subsection transition=scrollUp
# Tour of Bookmarks 1.8
### Speak up!