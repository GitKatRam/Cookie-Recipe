<!DOCTYPE html> 
<html> 
<head> 
<title>Rick Roll Video</title> 
<style> 
body, html { 
margin: 0; 
padding: 0; 
height: 100%; 
background: #000; 
}.video-container { 
width: 100%; 
height: 100vh; 
display: flex; 
justify-content: center; 
align-items: center; }iframe 
{width: 100%; 
height: 100%; 
border: none;}.
click-prompt 
{position: absolute; 
top: 50%; 
left: 50%; 
transform: translate(-50%, -50%); color: white; 
font-size: 24px; 
cursor: pointer; 
background: rgba(0,0,0,0.7); 
padding: 20px; 
border-radius: 10px;} 
z-index: 10; 

</style> 
</head> 
<body> 
<div class="click-prompt" id="clickPrompt"></div> 
<div class="video-container"> 
<iframe 
id="videoFrame" 
src="https://www.youtube.com/embed/dQw4w9WgXcQ?autoplay=1&mute=0&controls=0&modestbranding=1&rel=0" title="Rick Astley - Never Gonna Give You Up (Official Video) (4K Remaster)" 
frameborder="0" 
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" 
allowfullscreen> 
</iframe> 
</div> 
<script> 
document.addEventListener('click', function() { 
// Hide the click prompt 
document.getElementById('clickPrompt').style.display = 'none'; 
// Get the iframe element 
const iframe = document.getElementById('videoFrame'); 
// Request fullscreen 
if (iframe.requestFullscreen) { 
iframe.requestFullscreen(); 
} else if (iframe.webkitRequestFullscreen) { /* Safari */ 
iframe.webkitRequestFullscreen(); 
} else if (iframe.msRequestFullscreen) { /* IE11 */ 
iframe.msRequestFullscreen(); } 
// Ensure the video is playing (in case autoplay was blocked) iframe.src = iframe.src.replace('?autoplay=0', '?autoplay=1'); }); 
// Handle fullscreen change events 
document.addEventListener('fullscreenchange', exitHandler); document.addEventListener('webkitfullscreenchange', exitHandler); document.addEventListener('mozfullscreenchange', exitHandler); document.addEventListener('MSFullscreenChange', exitHandler); function exitHandler() { 
if (!document.fullscreenElement && 
!document.webkitFullscreenElement && 
!document.mozFullScreenElement && 
!document.msFullscreenElement) { 
// Show prompt again if user exits fullscreen 

} 
} 
document.getElementById('clickPrompt').style.display = 'block'; 

</script> </body> 
</html>
