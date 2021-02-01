<!DOCTYPE html>
<html>
<head>
<style>
body {
  margin: 0px 0px 0px 0px;
  padding: 0;
}
dir {
  margin: 0px 0px 0px 0px;
  padding: 0;
}
img {
  margin: 0px 0px 0px 0px;
  padding: 0;
}
.under{
        position:absolute;
    }
.over{
    position: relative;
    }
</style>
</head>
<body onmousemove="pressA(event)">
<dir id="imageScary" class="under">
<img src='align.png' alt='placehold' class='under'>
<img src='placeholder.gif' alt=placeholder' class='over'>
</dir>
	<dir id="eyes">

	</dir>
<script>
var w = window.innerWidth;
var h = window.innerHeight;
var currentFrame = 1;
var el;
var er;
var ti;
function setFrame(num) {
if(num<=38){
	//document.getElementById("imageScary").innerHTML = "<img src='./gifFrames/_a_frm"+num+",20.png' width='"+(w-4)+"' height='"+(h-4)+"'>";
	document.getElementById("imageScary").innerHTML = "<img src='./gifFrames/_a_frm"+(num-1)+",20.png' alt='placehold' class='under' width='"+(w-4)+"' height='"+(h-4)+"'><img src='./gifFrames/_a_frm"+num+",20.png' alt='placeholder' class='over'width=' "+(w-4)+"' height='"+(h-4)+"'> "
	currentFrame++;
	} else {
		if(num==39) {
			document.getElementById("imageScary").innerHTML = "<img src='stares.jpg' width='"+(w-4)+"' height='"+(h-4)+"'>";
			document.getElementById("eyes").innerHTML = "<img src='eyeL.png' alt='place' id='eyeLeft' class='over'><img src='eyeR.png' alt='pl' id='eyeRight' class='over'>"
			el = document.getElementById("eyeLeft");
			er = document.getElementById("eyeRight");
			ti = document.getElementById("imageScary");
			el.style.width = ((w/418)*36)+"px"
			el.style.height = ((h/215)*35)+"px"
			er.style.width = ((w/418)*36)+"px"
			er.style.height = ((h/215)*35)+"px"

			el.style.top = (0.22*h)+"px"
			el.style.left = (0.22*w)+"px"
			er.style.top = (0.22*h)+"px"
			er.style.left = (0.6*w)+"px"
			currentFrame++
		} else {
		return
		}
	}
}

function pressA(e) {
if(num=39) {
el.style.left = (e.clientX-((w/418)*18))+"px"
el.style.top = (e.clientY)-((h/215)*17.5)+"px"

er.style.left = (e.clientX-((w/418)*54))+"px"
er.style.top = (e.clientY)-((h/215)*17.5)+"px"

	if(e.clientX/w>0.29) {
		el.style.left = ((w*0.29)-((w/418)*18))+"px"
	}
	if(e.clientX/w<0.23) {
		el.style.left = ((w*0.23)-((w/418)*18))+"px"
	}
	if(e.clientY/h>0.34) {
		el.style.top = ((h*0.34)-((h/215)*17.5))+"px"
	}
	if(e.clientY/h<0.26) {
		el.style.top = ((h*0.26)-((h/215)*17.5))+"px"
	}
	
	if(e.clientX/w>0.76) {
		er.style.left = ((w*0.76)-((w/418)*54))+"px"
	}
	if(e.clientX/w<0.7) {
		er.style.left = ((w*0.7)-((w/418)*54))+"px"
	}
	if(e.clientY/h>0.34) {
		er.style.top = ((h*0.34)-((h/215)*17.5))+"px"
	}
	if(e.clientY/h<0.26) {
		er.style.top = ((h*0.26)-((h/215)*17.5))+"px"
	}
	}
}

document.getElementById("imageScary").innerHTML = "<img src='./gifFrames/_a_frm0,20.png' width='"+(w-4)+"' height='"+(h-4)+"'>";

setInterval(function(){ setFrame(currentFrame) }, 25);
</script>
</body>
</html>
