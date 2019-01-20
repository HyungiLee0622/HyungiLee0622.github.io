---
title: "callbackFunction.html"
date: 2019-1-20 08:26:28 -0400
categories: jekyll update
---


{
$( document ). ready ( function () { 
  
	console.log('Start');
	number();

});

function number(){

	number_callback("A");

}


function number_callback(result){

	console.log("Result : "+result);

	if(result=="A"){

		$("#attend").prop("disabled", true);

	}
}
}
