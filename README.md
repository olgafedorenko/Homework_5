# Homework_5
<!DOCTYPE html>
<html lang="en">
<head>

<title>CNIT 133 Homework Assignments #5</title>

    <meta charset="utf-8">
    <meta name="description" content="Fifth homework in CNIT-133 ">
      <link rel="stylesheet" href="hw4.css">
    <link rel="stylesheet" href="https://code.jquery.com/ui/1.11.4/themes/smoothness/jquery-ui.css">
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.1/jquery.min.js"></script>
   <script type="text/javascript" src="http://code.jquery.com/jquery-latest.min.js" charset="utf-8"></script>
    <script src = "https://code.jquery.com/ui/1.10.4/jquery-ui.js"></script>
<script src="https://ajax.aspnetcdn.com/ajax/jquery.validate/1.13.1/jquery.validate.min.js"></script>

     <script> 
$(document).ready(function(){
$("#myform").validate({

   rules: {

          num: {  number: true, min: 1, max: 2},

 },
    messages: { 

 num:  "Please enter a number 1 or 2"

         }
   
});
});

var seats=new Array(10)
var numFirstClass = 0;
var numEconomyClass = 0;
function part_extra(){
  var num = parseInt(document.getElementById("num").value);   
    switch(num){
        case 1:
            First_Class()
            break;
        case 2:
            Economy_Class()
            break;
    }
    }
function First_Class(){
    if (numFirstClass < 5){
    for (var i=0; i<5; i++){
        if(seats[i]!==1){
            seats[i]=1
            numFirstClass =i+ 1
            document.getElementById("name").innerHTML="Your seat number is " + numFirstClass + " have a nice flight";
		return;
        }
            
    }
    }
    else if (numEconomyClass < 10){
            document.getElementById("name").innerHTML="No more 1st class. Press 2 if you would like to book an economy class ticket."
            if(num==2){
              Economy_Class()
            }
    }
    else{
            document.getElementById("name").innerHTML="Sorry all booked..Next flight leaves in 3 hours."
        }
      
        
    }
    
 function Economy_Class(){
     if (numEconomyClass < 10){
    for (var j=5; j<10; j++){
        if(seats[j]!==1){
            seats[j]=1
            numEconomyClass =j+ 1
            document.getElementById("name").innerHTML="Your seat number is " + numEconomyClass + " have a nice flight";
		return;
    
    }
    }        
 }
     else if (numFirstClass < 5){
            document.getElementById("name").innerHTML="No more economy. Press 1 if you would like to book an first class ticket."
            if(num==1){
              First_Class()
            }
    }
    else{
            document.getElementById("name").innerHTML="Sorry all booked..Next flight leaves in 3 hours."
        }
      
        
    }   
            
</script>
<style>
    #name{
            color: #999093;
            font-size: 24px;
            font-style: italic;
            margin-left: 400px;
        }
    .error { font: normal 14px arial; padding: 3px; margin: 3px; color: blue; background-color: #ffc; }
   
    </style>
 </head>

<body>
    <nav>
    <div class="navigation">
        <a class="navigation" href="hw1.html">HW1</a>
        <a class="navigation" href="hw2.html">HW2</a>
         <a class="navigation" href="hw3.html">HW3</a>
        <a class="navigation" href="hw4.html">HW4</a>
        <a class="navigation" href="hw5.html">HW5</a>
        <a class="navigation" href="hw6.html">HW6</a>
        <a class="navigation" href="hw7.html">HW7</a>
        <a class="navigation" href="hw8.html">HW8</a>
        </div>
    </nav>
    <h1> Homework 5 - Array </h1>
  <div id="menu">
     <div id="first">
        <a href="hw5_part_1.html">
        <h3>Part 1 - Input</h3></a>
    </div>
    <div id="second">
        <a href="hw5_part_1b.html">
            <h3>Part 1b - Pulldown menu</h3></a>
    </div>
    <div id="third">
        <a href="hw5_part_2.html">
        <h3>Part 2 - States</h3></a>
    </div>
    <div id="fourth">
        <a href="hw5_part_3.html">
        <h3>Part 3 - Salaries</h3></a>
    </div>
   <div id="fifth">
        <a href="hw5_part_4.html">
        <h3>Part 4 - Numbers</h3></a>
    </div>
      <div id="extra">
        <a href="hw5_extra.html">
        <h3>Extra - Airlines Reservation System</h3></a>
    </div>
    </div>
  <div id="main">  

      <form name="myform" id="myform">
          <table>

         <td>Please type 1 for "First Class" and  type 2 for "Economy". <br><br>
             Choose a class: 

             <input type="text" id="num" name="num"> 
              </td>
          <td>
             <input type="button" value = "Submit" onclick="part_extra()">

             <input type="reset" value="Reset" onclick="window.location.reload();">
              </td>

         </table>
              
          <table id="name" ></table>
    

      </form>

       
    </div>
  
    <div class="footer">
        <a href="https://validator.w3.org/check?uri=referer">
    <img src="icon-validator-v4.jpg"
     alt="html5"></a>

     <a href="https://jigsaw.w3.org/css-validator/check/referer">
     <img src="css.png" alt="css">
    </a>
<p class="footer">
  Copyright &copy;  Olga Fedorenko 2017
</p>

</div>
    </body>
</html>
