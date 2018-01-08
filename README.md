
<!doctype html>
<html>
<head>
    <title></title>

    <meta charset="utf-8" />
    <meta http-equiv="Content-type" content="text/html; charset=utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <link href="https://fonts.googleapis.com/css?family=Architects+Daughter|Berkshire+Swash" rel="stylesheet">
   
    <style type="text/css">
        
        
        

       html, body { height: 100%; }
body {
    margin: 0;
    background: black;
    overflow: hidden;
    background-image: url("https://www.pexels.com/photo/close-up-of-hand-holding-pencil-over-white-background-316466/")
}

.moving-zone {
    position: absolute;
    top:35%; left:40%;
    width:150px; height:80px;
    margin: -60px 0 0 -150px;
    perspective: 800px;
}
.popup {
    position: relative;
    width:400%;
    padding: 12px;
    box-sizing: border-box;
    border-radius: 20px 0 20px 0;
    cursor: pointer;
    transform-style: preserve-3d;
    color: black;
}
.popup:before {
    content: '';
    position: absolute;
    left:5%; top:5%;
    width:90%; height:90%;
    border-radius: inherit;
    background: rgba(0,0,0,.1);
    box-shadow: 0 0 40px 20px rgba(0,0,0,.1);
    transform: translateZ(-100px);
}
.popup-content {
    background: #444;
    padding: 20px;
    box-sizing: border-box;
    border-radius: 10px 0 10px 0;
}
.popup-text {
    color: white;
   font-family: 'Architects Daughter', cursive;
    font-size: 20px;
    line-height: 30px;
    font-weight: 100;
    text-align: center;
    transform: translateZ(15px);
}
.popup-text b  {
    color: white;
    font-weight: 300;
    font-family: 'Berkshire Swash', cursive;
} 
        #autori {
            
              color: white;
    font-weight: 300;
        }
      
     
        .buttons-coll {
  width: 90%;
  margin: 5px auto;
  text-align: center;
}
button {
  margin: 10px;
}
.custom-btn {
  padding: 10px 25px;
  font-family: 'Roboto', sans-serif;
  font-weight: 800;
  background: transparent;
  outline: none !important;
  cursor: pointer;
  transition: all 0.1s ease;
  position: relative;
  display: inline-block;
}
        
        .btn-4 {
  width: 130px;
  height: 40px;
  line-height: 42px;
  padding: 0;
  border: none;
            float: left;
            color: white;
}
.btn-4 span {
  position: relative;
  display: block;
  width: 100%;
  height: 100%;
}
.btn-4:before, .btn-4:after {
  position: absolute;
  content: "";
  right: 0;
  top: 0;
  background: white;
  transition: all 0.3s ease;
}
.btn-4:before {
  height: 50%;
  width: 2px;
}
.btn-4:after {
  width: 20%;
  height: 2px;
}
.btn-4:hover:before {height: 100%;}
.btn-4:hover:after {width: 100%;}
.btn-4 span:before, .btn-4 span:after {
  position: absolute;
  content: "";
  left: 0;
  bottom: 0;
  background: white;
  transition: all 0.3s ease;
}
.btn-4 span:before {
  width: 2px;
  height: 50%;
}
.btn-4 span:after {
  width: 20%;
  height: 2px;
}
.btn-4 span:hover:before {height: 100%;}
.btn-4 span:hover:after {width: 100%;}
        
        .btn-12 {
  border: 2px solid white;
  z-index: 1;
            float: right;
            color: white;
}
.btn-12:after {
  position: absolute;
  content: "";
  width: 100%;
  height: 0;
  bottom: 0;
  left: 0;
  z-index: -1;
  background: white;
  transition: all 0.3s ease;
}
.btn-12:hover {
  color: #fff;
}
.btn-12:hover:after {
  top: 0;
  height: 100%;
}
.btn-12:active {top: 2px;}
        
     
        
    </style>    
</head>

<body>

   
    
    <div class="moving-zone">
    <div class="popup">
        <div class="popup-content">
            <div class="popup-text" id="output">
            
            </div>
            <div class="popup-text">
            <b id = "autori"></b>
            </div>               

         
            <div id="myBtn" class="buttons-coll">
            
            <button class="custom-btn btn-4" onclick="setRandomColor()"><span>Read More</span></button>
            
            </div>
            
             <div class="buttons-coll">
            <button class="custom-btn btn-12" id="accordion" >Share
           
           <!-- <div id="ikonat">
                
                  <a href="http://www.facebook.com/sharer.php?u=https://simplesharebuttons.com" target="_blank">
        <img src="https://www.gstatic.com/images/icons/material/system/2x/post_facebook_black_24dp.png" alt="Facebook" />
    </a>
                 <a href="https://plus.google.com/share?url=https://simplesharebuttons.com" target="_blank">
        <img src="https://www.gstatic.com/images/icons/material/system/2x/post_gplus_black_24dp.png" alt="Google" />
    </a>
                <a href="https://twitter.com/share?url=https://simplesharebuttons.com&amp;text=Simple%20Share%20Buttons&amp;hashtags=simplesharebuttons" target="_blank">
        <img src="https://www.gstatic.com/images/icons/material/system/2x/post_twitter_black_24dp.png" alt="Twitter" />
    </a>
                 
                 </div> -->
                
               


           
               </button>  
                 
                 

            
            </div>
            <br><br><br>
          </div>
    </div>
</div>
    
    <script
  src="https://code.jquery.com/jquery-3.2.1.js"
  integrity="sha256-DZAnKJ/6XZ9si04Hgrsxu/8s717jcIzLy3oi35EouyE="
            crossorigin="anonymous"></script>
    
    <script src="http://ajax.googleapis.com/ajax/libs/jquery/2.1.4/jquery.min.js"></script>
    
    <script>
        
        
    
    
    var moveForce = 30; 
var rotateForce = 20; 

$(document).mousemove(function(e) {
    var docX = $(document).width();
    var docY = $(document).height();
    
    var moveX = (e.pageX - docX/2) / (docX/2) * -moveForce;
    var moveY = (e.pageY - docY/2) / (docY/2) * -moveForce;
    
    var rotateY = (e.pageX / docX * rotateForce*2) - rotateForce;
    var rotateX = -((e.pageY / docY * rotateForce*2) - rotateForce);
    
    $('.popup')
        .css('left', moveX+'px')
        .css('top', moveY+'px')
        .css('transform', 'rotateX('+rotateX+'deg) rotateY('+rotateY+'deg)');
});
    
   
        
$("#myBtn").click(function(e){
    
    var url = "https://talaikis.com/api/quotes/random/"
            ;
    
    e.preventDefault();
    
  $.ajax({
      
      url:url,
      type:"GET",
      dataType:"json",
      success:function(data){
          
       
          
          console.log(data);
          $.each(data,function(key , index){
              
              var quote = data["quote"];
              
              console.log(key);
              console.log(index);
              
              
            $("#output").html("<br>"+quote);
              
              var autori = data["author"];
              
               $("#autori").html("<br>"+ autori);
             
          })
      }
      
  })
    
})
        
        function getRandomColor() {
  var letters = '0123456789ABCDEF';
  var color = '#';
  for (var i = 0; i < 6; i++) {
    color += letters[Math.floor(Math.random() * 16)];
  }
  return color;
}



function setRandomColor() {
 var ngjyrat = $("body ").css("background" , getRandomColor());
   $(".popup-content").css("background", getRandomColor());
 
   
   
}
        
       
    
    </script>
    
</body>
</html>
