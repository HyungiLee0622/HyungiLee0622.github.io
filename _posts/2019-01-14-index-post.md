---
title: index.html
date: 2019-1-14 08:26:28 -0400
categories: jekyll update
---
/*
비활성화된 버튼을 현재 날짜와 DB에 저장된 날짜를 비교해서 -1인 경우(DB의 데이터가 이전 날짜인 경우), 해당 function을 실행한다.
비활성화된 버튼을 활성화 시키고, 버튼을 클릭할 경우, 파란 버튼으로 만들고 클릭하면 기존의 DB 테이블을 업데이트시킨다. (날짜, 출근/퇴근 타각시간을 NULL로 업데이트)  
*/
function del_btn(event){
			switch(event.target.id){
				case 'attend': case 'leave':
				$('#attend').css('background',[활성화색상]);
				$('#leave').css('background', [활성화색상]);
				break;
			}

			/*DB table update*/
			//DB.SQL table create statement
			//DB.SQL update statement (date update, attendence time and leave time = NULL(Initialization))
}

------------------------------------------------------------------------------------------------------------------------------
/*
  버튼을 클릭시, 화면에 시간표시, 로컬DB에 시간정보 저장 및 버튼 비활성화 
*/

var date=new Date();
			var hour = date.getHours();
			var min = date.getMinutes();
			var att_time='';
			var lea_time='';
      
function time_btn(event){

			switch(event.target.id){
				
        case 'attend':
				$('#att_time').html("<h1>"+hour+":"+min+"</h1>");
        /*
          Initialize attendence date
					att_time='[The value of attendence date]';
				*/
          $('#attend').attr ( 'disabled', 'disabled').css('background', [비활성화색상]);
				  break;

				case 'leave':
				$('#le_time').html("<h1>"+hour+":"+min+"</h1>");
				/* 
          Initialize leave date 
					lea_time='[The value of leave date]';
				*/
				  $('#leave').attr ( 'disabled', 'disabled').css('background', [비활성화색상]); 
			  	break;
			}
		  	/*
          DB table update
				  update [table] set [attendance] = [attendance time], [leave] = [leave time];
		  	*/
		}
  
  ----------------------------------------------------------------------------------------------------------------------------
/*
  미완성 function
*/
    function loc_list(value){

			  alert(value);

		}

		function data_trans(){
			/*
          <a href="javascript:data_trans()">Data Transfor</a>
          
		    	["select" DB query] => Transfer status value check 

			    if([Transfer status]===[false]){
				      //send() 메소드를 써서 전송안된 로컬 데이터 서버에 전송.   
          }    
			*/
		}
    /*현재위치를 알아내는 메서드 넣기*/
		function currentLocation(){


		}
    /*현재위치와 제한범위(50m)내의 위치인지 true, false로 구분해서 반환
		function locationComparision(a,b){

	
		}
   
    -------------------------------------------------------------------------------------------------------------------------
    
		var date=new Date();
		var year = date.getFullYear();
		var month = date.getMonth() ;
		var day = date.getDate();
		var hour = date.getHours();
		var min = date.getMinutes();
		
		$ ( document ). ready ( function () {  
			
			/*
        User 및 Date 정보를 검색해서 변수에 넣어둔다.
      */
      
			if([DB.method == [Auto]){
				$('#attend').attr ( 'disabled', 'disabled').css('background', '#ff0000'); 
				$('#leave').attr ( 'disabled', 'disabled').css('background', '#ff0000'); 	
			}
     
      if([GPS Location Comparision] === true){
        
      }
			
			//Dummy 테이블 생성으로 테이블의 생성을 확인

			//만약 테이블이 존재하지 않는다면, 데이터 테이블을 생성하고 동시에 기본 데이터(NOT NULL)를 초기화 시킨다.(유저 및 현재 날짜정보)
			if([Table]===null){
				
				//DB.SQL 테이블 생성(create) statement

				//DB.SQL 데이터 입력(insert) statement/(user, date)
			}
		});	
    
  ----------------------------------------------------------------------------------------------------------------------------
  /*
			Returns a number: cresult
			-1 if a < b 로컬 DB의 날짜 정보가 현재날짜보다 늦은 경우, 
			0 if a = b
			1 if a > b
	*/
  var dates = {
			convert:function(d) {
			        return (
            				d.constructor === Date ? d :
           				d.constructor === Array ? new Date(d[0],d[1],d[2]) :
            				d.constructor === Number ? new Date(d) :
            				d.constructor === String ? new Date(d) :
            				typeof d === "object" ? new Date(d.year,d.month,d.date) :NaN
        				);
    			},
			    compare:function(a,b) {
			        return (isFinite(a=this.convert(a).valueOf()) &&isFinite(b=this.convert(b).valueOf()) ?(a>b)-(a<b) :NaN);
    			}
   };
   /*
      dbDate에서 월 부분을 -1로 설정해서 초기화시켜준다.
      var result = str.substring(0, 3); 두번째 인수값은 자르고자하는 위치+1이다. DB테이블의 날짜 정보 초기화시 사용
   */
   var dbDate = new Date(2018,12,14);
	 var prstDate=new Date(year,month,day);
	 var cresult=dates.compare(dbDate, prstDate);
  /*
    두 날짜정보를 비교하여, 같으면 '0', 현재날짜보다 데이터베이스 날짜가 빠른경우, -1을 반환
  */
   
   if(cresult===-1){

			$('#attend').attr ( 'disabled', false).css('background', [비활성화색상]); 
			$('#leave').attr ( 'disabled', false).css('background', [비활성화색상]); 
			
			$('#attend').on('click', del_btn);
			$('#leave').on('click', del_btn);

		}else{

			$('#attend').on('click', time_btn);
			$('#leave').on('click', time_btn);
			
		}
  ---------------------------------------------------------------------------------------------------------------------------
