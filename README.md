#Equal Column Heights with Javascript & jQuery

Author: Carlos Maldonado @choquo | License: MIT 

**Require jQuery**

This approach let you resize columns inside different parent rows, see the image below.

	<script>
	$(function(){
	    /** Equal columns height by @choquo 
         *  Set the same height of child columns in a defined parent
         */
		var parent_class = '.equal-parent';
		var child_class  = '.equal-child';
		//Do Resize
	    $(parent_class).each(function(){
	    	var array_diff_heights = [];
	        $(this).find(child_class).each(function(){ array_diff_heights.push(  $(this).height() ); }); //Store heights of current parent
	        var max_height = Math.max.apply(Math, array_diff_heights );	//Get child max height of current parent
		    $(this).find(child_class).each(function(){ $(this).css({'min-height' : max_height }); }); //Apply same height to childs of current parent
		    array_diff_heights = []; //Restart array if need to equalize another elements (parents).
	    });
    });
	</script>


![](screen.png)