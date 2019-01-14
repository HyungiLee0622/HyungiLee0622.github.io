---
title: "Welcome to Jekyll!"
date: 2019-1-14 08:26:28 -0400
categories: jekyll update
---
/*"properties.js"*/
var locVariable = 
{
 A:'156.1212|167.3232',
 B:'198.2323|201.1212'
};

/*Dropdown List에 속성 자바스크립트 파일 안에 있는 Dictionary변수의 값을 뿌려준다.*/
<script type="text/javascript" src="properties.js"></script>

	<script type="text/javascript">
  
		for(let key in locVariable){
			$('#loc_list').append('<option value='+locVariable[key]+'>'+key+':'+locVariable[key]+'</option>');
		}
	
</script>

------------------------------------------------------------------------------------------------------------------------------

