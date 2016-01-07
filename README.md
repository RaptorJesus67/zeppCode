# ZEPP CODE
<h4>Convert symbols to string to unique "Zepp Code" to create so-called "pretty-URL's"</h4>
<p>The Zepp "Zeppelin" Code started out as a simple algorithm to switch between strings and symbols. Each symbol would have a string associated with it, as well as a "Zepp Code" counter part using the following syntax "%000#" (minus quotations, of course).</p>
<p>Initiation of the class is straight forward:</p>
<pre>	# CONFIGURATION OR FILE FOR USE
	
	require_once("path/to/file/zeppTranslate.php");
	$zepp = new zeppTranslate;
</pre>
<p>File being used for the database:</p>
<pre>	# CHANCES ARE THE MODEL FILE

	$urlSegment = "scruffyAndTheJanitors";

	// If included in function, either call it new, or don't forget GLOBAL
	$var = $zepp->zeppCode("string", "zepp", $urlSegment);
	
	$sql = "SELECT `col` FROM `table` WHERE `col` = '$urlSegment' OR `col` = '$var'";
	// SQL Process...
</pre>
