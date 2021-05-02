# AR_Model_Guide
AR 3D Model Guide Files 

The following is a text Guide listing the step by step process of how to make a 2D marker and attach a 3D model to it that is accessible on a custom website.
Files used in the guide:
https://drive.google.com/drive/folders/1xBSB7mSOHDqfcNRlHmxBsX90aas8B7dg?usp=sharing

----------------------------------------------------------

AR Modeling Guide
Abstract:
To show a 3D model with Augmented Reality hosted on to a physical image tag/marker. 


Model requirements
  Software: Blender
  Format: .gltf
Image Requirements
  Files Required: .fset, .fset3, .iset
  File Generator: NFT Marker Creator
  Image File Host: Github
    Github: rahulkerur (github.com)
    Hosting retrieval URL generator : raw.githack.com
Website requirements
  Website host: Neocities.org
  2D Marker
  3D Model
  Code


Model requirements
  Software: Blender
    Open source 3D software - Blender.org
  Format: .gltf
    File > Export > .GLTF
    Source: <a-gltf-model> – A-Frame (aframe.io)

Image Requirements
  Files Required: .fset, .fset3, .iset
    These files need to be created from the marker image in order for the code to know what to recognize.
  File Generator: NFT Marker Creator
    Use NFT Marker 
  Image File Host: Github
    Github: rahulkerur (github.com)
      Repositories > New > Repository Name > Public > Create Repository
      Repositories are like folders in github. Create a new one to hold and host files that can be retrieved by a code for a website. 
    Hosting retrieval URL generator : raw.githack.com
      This is a github file retrieval generator. It creates a URL that accesses the file/files hosted within the pathed github. But the generator doesn’t always create a usable link, so the URL needs to be edited. See below:
        Un-edtied Link: https://raw.githack.com/rahulkerur/AR_Model_Guide/tree/main/Image/NFT_files/Monkey_2D
        Edited Link: https://raw.githubusercontent.com/rahulkerur/AR_Model_Guide/main/Image/NFT_files/Monkey_2D

Website requirements
  Website host: Neocities.org
    Website hosts that allow basic file upload and retrieval are ideal. After the website/account are created the 3D model will need to be uploaded. 
  2D Marker
    Ensure the proper githack edited URL as stated in section Hosting retrieval URL generator : raw.githack.com
  3D Model
    When using a .GLTF 3D model, make sure to use the proper code as stated in 3D Models – A-Frame (aframe.io).
    Ensure that the URL for the source file is active by placing it in the address bar of a browser and testing it. If the file download starts, then the link is working and should work within the code.
    The URL should direct to the location of where the file is uploaded, in this case the Website host’s files. ( gltf-model='https://ar3dmodelguide.neocities.org/Monkey_3D.gltf')
  Code
    Use the code below as a template in order to make your own website that can access a 2D marker and an AR 3D model.
    Note the comments within the code and the following text to ensure a functioning website.


<script src="https://aframe.io/releases/1.0.4/aframe.min.js"></script>

<style>
  .arjs-loader {
    height: 100%;
    width: 100%;
    position: absolute;
    top: 0;
    left: 0;
    background-color: rgba(0, 0, 0, 0.8);
    z-index: 9999;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .arjs-loader div {
    text-align: center;
    font-size: 1.25em;
    color: white;
  }
</style>

<!-- rawgithack development URL -->
<script src='https://raw.githack.com/AR-js-org/AR.js/master/aframe/build/aframe-ar-nft.js'></script>

<body style='margin : 0px; overflow: hidden;'>
   <!-- minimal loader shown until image descriptors are loaded -->
  <div class="arjs-loader">
    <div>Loading Model, Point Camera at Image, please wait...</div> <!--Text that loads before the application is ready-->
  </div>
    <a-scene
        vr-mode-ui="enabled: false;"
        renderer="logarithmicDepthBuffer: true;"
        embedded arjs='trackingMethod: best; sourceType: webcam; debugUIEnabled: false;'
        shadow="autoUpdate: false">
        
        <!-- use rawgithack to retrieve the correct url for nft marker (see 'Monkey_2D' below). Do not paste the link from raw githack directly. make sure to edit it as shown in the guide. Un-edtied Link: https://raw.githack.com/rahulkerur/AR_Model_Guide/tree/main/Image/NFT_files/Monkey_2D
Edited Link: https://raw.githubusercontent.com/rahulkerur/AR_Model_Guide/main/Image/NFT_files/Monkey_2D -->
        <a-nft
            type='nft' url='https://raw.githubusercontent.com/rahulkerur/AR_Model_Guide/main/Image/NFT_files/Monkey_2D' 
            smooth='true' smoothCount='10' smoothTolerance='0.01' smoothThreshold='5'>
           <!--Below is where the 3D models are loaded in. Always ensure to test the proper scale when the 3D model is linked. It can either be too small or too big so test a range of sizes. -->
            <a-entity
                gltf-model='https://ar3dmodelguide.neocities.org/Monkey_3D.gltf'
                scale="50 50 50"
                rotate="0 0 0"
                position="0 100 0"
                
                >
            </a-entity>    
            <!-- Add this to test the marker with a primitive 3D entity. <a-sphere color="yellow" radius="10"></a-sphere> -->
        </a-nft>
		<a-entity camera></a-entity>
    </a-scene>
</body>



2D Marker Image for Guide:
https://drive.google.com/drive/folders/1zqfQ1x5GGNiF1bAWoxM4nQcDiVEf62Gu?usp=sharing

3D Model:
https://drive.google.com/file/d/1nrXvOyMWbxKdXUgvR9DxZh35ARhAS720/view?usp=sharing
