---
title: "ajaxFunction.html"
date: 2019-1-20 08:26:28 -0400
categories: jekyll update
---
{
function send_data(){

	var hostUrl='[URL]';
	var param1=1;
	var param2=10;

	$.ajax({
		url: hostUrl,
		type: 'POST',
		dataType: 'json',
		data:{
			parameter1 : param1, parameter2 : param2, 
		},
		timeout:3000,

		success:function(data){

			console.log('Success');

		}

	});

}

}
