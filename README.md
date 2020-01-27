# PHP-GET-REQUEST-API-Method-to-Federal-Website-NHTSA-Vehicle-Recall-API
API Get Request to Federal Vehicle Recall Site NHTSA

Using the code NHTSA provides on their website throws a notice error because the variable named postdata is undefined. To resolve this problem you can add an @ symbol in from of the variable, so the variable would be called @$postdata. This will cause the notice error to be ignored. 

However you can also add a line of code that sets the variable to null (which is what I did). Your new line above the $opts variable would be

$postdata = null;

See the code inside.
Tested and working.



