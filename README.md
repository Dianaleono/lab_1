<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Криворізька міська рада - VR макет</title>
  <script src="https://aframe.io/releases/1.4.0/aframe.min.js"></script>
</head>
<body>
  <a-scene>
    <!-- Небо -->
    <a-sky color="#87CEEB"></a-sky>
    
    <!-- Основа (земля навколо будівлі) -->
    <a-plane position="0 0 0" rotation="-90 0 0" width="60" height="60" color="#2E7D32"></a-plane>
    
    <!-- Асфальтові доріжки -->
    <a-plane position="0 0.01 -15" rotation="-90 0 0" width="40" height="8" color="#424242"></a-plane>
    <a-plane position="15 0.01 0" rotation="-90 0 90" width="30" height="8" color="#424242"></a-plane>
    <a-plane position="-15 0.01 0" rotation="-90 0 90" width="30" height="8" color="#424242"></a-plane>
    
    <!-- Головна будівля міської ради -->
    <a-entity id="main-building" position="0 0 0">
      
      <!-- Основний корпус (прямокутна частина) -->
      <a-box position="0 4 0" width="20" height="8" depth="12" 
             color="#D4AF37" 
             material="roughness: 0.3">
      </a-box>
      
      <!-- Центральна частина з колонами -->
      <a-box position="0 4 -6.5" width="16" height="8" depth="1" 
             color="#F5DEB3" 
             material="roughness: 0.2">
      </a-box>
      
      <!-- Колони -->
      <a-cylinder position="-6 4 -6.5" radius="0.8" height="8" color="#F5DEB3"></a-cylinder>
      <a-cylinder position="-3 4 -6.5" radius="0.8" height="8" color="#F5DEB3"></a-cylinder>
      <a-cylinder position="0 4 -6.5" radius="0.8" height="8" color="#F5DEB3"></a-cylinder>
      <a-cylinder position="3 4 -6.5" radius="0.8" height="8" color="#F5DEB3"></a-cylinder>
      <a-cylinder position="6 4 -6.5" radius="0.8" height="8" color="#F5DEB3"></a-cylinder>
      
      <!-- Дах основної будівлі -->
      <a-box position="0 8.5 0" width="22" height="1" depth="14" color="#8B4513"></a-box>
      
      <!-- Фронтон -->
      <a-entity position="0 9.5 -6.5">
        <a-triangle position="0 0 0" rotation="0 0 0" 
                   geometry="primitive: triangle" 
                   material="color: #8B4513" 
                   scale="8 3 1">
        </a-triangle>
      </a-entity>
      
      <!-- Головний вхід -->
      <a-box position="0 2 -6.8" width="4" height="4" depth="0.5" color="#654321"></a-box>
      <a-box position="0 1 -7" width="3.5" height="3.5" depth="0.2" color="#2F4F4F"></a-box>
      
      <!-- Сходи -->
      <a-box position="0 0.2 -8" width="6" height="0.4" depth="2" color="#696969"></a-box>
      <a-box position="0 0.4 -8.5" width="6" height="0.4" depth="1" color="#696969"></a-box>
      <a-box position="0 0.6 -9" width="6" height="0.4" depth="1" color="#696969"></a-box>
      
      <!-- Вікна першого поверху -->
      <a-box position="-6 2.5 -6.8" width="2" height="1.5" depth="0.1" color="#87CEEB"></a-box>
      <a-box position="6 2.5 -6.8" width="2" height="1.5" depth="0.1" color="#87CEEB"></a-box>
      
      <!-- Вікна другого поверху -->
      <a-box position="-8 5.5 -6.8" width="1.5" height="1.2" depth="0.1" color="#87CEEB"></a-box>
      <a-box position="-4 5.5 -6.8" width="1.5" height="1.2" depth="0.1" color="#87CEEB"></a-box>
      <a-box position="4 5.5 -6.8" width="1.5" height="1.2" depth="0.1" color="#87CEEB"></a-box>
      <a-box position="8 5.5 -6.8" width="1.5" height="1.2" depth="0.1" color="#87CEEB"></a-box>
      
      <!-- Бокові вікна -->
      <a-box position="-10.2 3 -2" width="0.1" height="1.5" depth="2" color="#87CEEB"></a-box>
      <a-box position="-10.2 3 2" width="0.1" height="1.5" depth="2" color="#87CEEB"></a-box>
      <a-box position="10.2 3 -2" width="0.1" height="1.5" depth="2" color="#87CEEB"></a-box>
      <a-box position="10.2 3 2" width="0.1" height="1.5" depth="2" color="#87CEEB"></a-box>
      
      <!-- Прапор України -->
      <a-entity position="0 12 -3">
        <a-cylinder position="0 0 0" radius="0.1" height="4" color="#8B4513"></a-cylinder>
        <a-plane position="1.5 1 0" width="3" height="2" color="#005BBB">
          <a-plane position="0 -0.5 0.01" width="3" height="1" color="#FFD700"></a-plane>
        </a-plane>
      </a-entity>
      
      <!-- Анімація прапора -->
      <a-plane position="1.5 13 -3" width="3" height="2" color="#005BBB" 
               animation="property: rotation; to: 0 5 0; dur: 3000; dir: alternate; loop: true">
        <a-plane position="0 -0.5 0.01" width="3" height="1" color="#FFD700"></a-plane>
      </a-plane>
      
    </a-entity>
    
    <!-- Адміністративні прибудови -->
    <a-box position="-15 2.5 -5" width="8" height="5" depth="8" color="#CD853F"></a-box>
    <a-box position="15 2.5 -5" width="8" height="5" depth="8" color="#CD853F"></a-box>
    
    <!-- Паркування -->
    <a-plane position="0 0.01 15" rotation="-90 0 0" width="30" height="15" color="#2F2F2F"></a-plane>
    
    <!-- Розмітка паркування -->
    <a-plane position="-8 0.02 15" rotation="-90 0 0" width="0.2" height="12" color="#FFFFFF"></a-plane>
    <a-plane position="-4 0.02 15" rotation="-90 0 0" width="0.2" height="12" color="#FFFFFF"></a-plane>
    <a-plane position="0 0.02 15" rotation="-90 0 0" width="0.2" height="12" color="#FFFFFF"></a-plane>
    <a-plane position="4 0.02 15" rotation="-90 0 0" width="0.2" height="12" color="#FFFFFF"></a-plane>
    <a-plane position="8 0.02 15" rotation="-90 0 0" width="0.2" height="12" color="#FFFFFF"></a-plane>
    
    <!-- Дерева навколо -->
    <a-entity position="-20 0 -10">
      <a-cylinder position="0 2 0" radius="0.5" height="4" color="#8B4513"></a-cylinder>
      <a-sphere position="0 5 0" radius="3" color="#228B22"></a-sphere>
    </a-entity>
    
    <a-entity position="20 0 -10">
      <a-cylinder position="0 2 0" radius="0.5" height="4" color="#8B4513"></a-cylinder>
      <a-sphere position="0 5 0" radius="3" color="#228B22"></a-sphere>
    </a-entity>
    
    <a-entity position="-25 0 10">
      <a-cylinder position="0 2 0" radius="0.5" height="4" color="#8B4513"></a-cylinder>
      <a-sphere position="0 5 0" radius="3" color="#228B22"></a-sphere>
    </a-entity>
    
    <a-entity position="25 0 10">
      <a-cylinder position="0 2 0" radius="0.5" height="4" color="#8B4513"></a-cylinder>
      <a-sphere position="0 5 0" radius="3" color="#228B22"></a-sphere>
    </a-entity>
    
    <!-- Освітлення -->
    <a-light type="ambient" color="#ffffff" intensity="0.6"></a-light>
    <a-light type="directional" position="10 20 10" color="#ffffff" intensity="0.8"></a-light>
    
    <!-- Текст з назвою -->
    <a-text value="КРИВОРІЗЬКА МІСЬКА РАДА" 
            position="0 1 -12" 
            color="#003366" 
            align="center" 
            scale="2 2 2"
            font="dejavu">
    </a-text>
    
    <!-- Камера з можливістю огляду -->
    <a-entity id="rig" position="0 3 25">
      <a-camera look-controls wasd-controls="enabled: true" 
                position="0 0 0"
                animation="property: rotation; to: 0 360 0; dur: 30000; loop: true; easing: linear">
      </a-camera>
    </a-entity>
    
  </a-scene>
</body>
</html>
