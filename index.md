<!DOCTYPE html>
<html>
	<head>
    	<script src="https://aframe.io/releases/1.0.4/aframe.min.js"></script>
		<script src="https://raw.githack.com/AR-js-org/AR.js/master/aframe/build/aframe-ar-nft.js"></script>
	</head>
  <a-scene embedded arjs=’sourceType: webcam;’>
      <a-marker preset=’hiro’>
	  	<a-entity gltf-model="https://arjs-cors-proxy.herokuapp.com/https://raw.githack.com/AR-js-org/AR.js/master/aframe/examples/image-tracking/nft/trex/scene.gltf"
       scale="0.1 0.1 0.1"
       position="0 0 0"
       	></a-entity> 
      </a-marker>
  <a-entity camera>
  </a-entity>
  </a-scene>
</html>
