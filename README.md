# PHP-GET-REQUEST-API-Method-to-Federal-Website-NHTSA-Vehicle-Recall-API
API Get Request to Federal Vehicle Recall Site NHTSA

Using the code NHTSA provides on their website throws a notice error because the variable named postdata is undefined. To resolve this problem you can add a @ symbol in from of the variable, so the variable would be called @$postdata. This will cause the error to be ignored. However you can also add a line of code that sets the variable to null. Your new line above the $opts variable would be
$postdata = null;

NHTSA gives you go following code to use: (See my Updated Code) within here

<?php
	$opts = array('http' =>
		array(
			'method' => 'GET',
			'content' => $postdata
		)
	);
	$apiURL = "https://vpic.nhtsa.dot.gov/api/vehicles/GetModelsForMakeId/440?format=json";
	$context = stream_context_create($opts);
	$fp = fopen($apiURL, 'rb', false, $context);
	if(!$fp)
	{
		echo "in first if";
	}
	$response = @stream_get_contents($fp);
	if($response == false)
	{
		echo "in second if";
	}
	echo $response;
?>
