!SLIDE subsection transition=scrollUp
# Controllers

!SLIDE bullets incremental smaller left
# Controllers are easy.
* Two controllers:
	<p class="pll">Actions: action/&lt;action&gt;</p>
	<p class="pll">Pages: &lt;handler&gt;/&lt;action&gt;</p>
* Both use configuration:
	<p class="pll">Actions: `elgg_register_action($action_name, $action_script)`</p>
	<p class="pll">Pages: `elgg_register_page_handler($handler_name, $function)`</p>
* Overrideable - Just register again!

!SLIDE bullets smaller left
# Controller locations
* Actions are in `actions` dirs.
* Pages are in `pages` dirs.
* .htaccess + mod\_write used to route to engine.
	<p class="pll">http://elggsite.org/<strong>action/login</strong><br />
	-> http://elggsite.org/<strong>engine/handlers/action\_handler.php?action=login</strong></p>
	<br />
	<p class="pll">http://elggsite.org/<strong>bookmarks/add</strong><br />
	-> http://elggsite.org/<strong>engine/handlers/page_handler.php?handler=bookmarks/add</strong></p>

!SLIDE center
# Questions?