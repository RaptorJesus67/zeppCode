# ZEPP CODE
<h4>Convert symbols to string to unique "Zepp Code" to create so-called "pretty-URL's"</h4>
<p>The Zepp "Zeppelin" Code started out as a simple algorithm to switch between strings and symbols. Each symbol would have a string associated with it, as well as a "Zepp Code" counter part using the following syntax "%000#" (minus quotations, of course).</p>

<p>
<h3>Example to examine:</h3>
<strong>Band Name: <span>Scruffy & The Janitors</strong>
</p>

<p>
That '&' is not only ugly in the URL, but it's also reserved! So are #, %, =, etc.
<strong>To fix this, use ZeppCode!</strong>
ZeppCode uses three-way conversion that takes the first parameter and converts it to the second.
The code allows for urls like this <code>example.com/band/scruffyAndTheJanitors</code> instead of this: <br> <code>example.com/index.php?band=Scruffy%20%26%20the%20Janitors</code>

<br>
<h5>Example ZeppCode</h5>
<p><strong>String:</strong> and<br>
   <strong>Zepp:</strong> %001#<br>
   <strong>Symbol:</strong> &<br>
</p>



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
<p>After retrieving item from Database:</p>
<pre>	# POSSIBLY THE VIEW, BUT CAN BE MODEL STILL

	$name = $zepp->zeppCode("zepp", "symbol", $databaseElement);
	
</pre>
