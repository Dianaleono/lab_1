<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Криворізька міська рада - AR макет</title>
  <script src="https://aframe.io/releases/1.4.0/aframe.min.js"></script>
  <script src="https://raw.githack.com/AR-js-org/AR.js/master/aframe/build/aframe-ar.js"></script>
</head>
<body style="margin: 0; font-family: Arial, sans-serif;">
  <!-- Інструкції для користувача -->
  <div style="position: fixed; top: 10px; left: 10px; z-index: 9999; background: rgba(0,0,0,0.8); color: white; padding: 10px; border-radius: 5px; font-size: 14px; max-width: 300px;">
    <strong>Інструкції:</strong><br>
    1. Роздрукуйте маркер або відкрийте його на іншому пристрої<br>
    2. Наведіть камеру на маркер<br>
    3. Насолоджуйтесь 3D-моделлю міської ради!<br>
    <br>
    <strong>Маркер:</strong> Використовуйте герб Кривого Рогу або створений спеціальний маркер
  </div>

  <!-- Кнопка для створення маркера -->
  <div style="position: fixed; bottom: 10px; right: 10px; z-index: 9999;">
    <a href="https://jeromeetienne.github.io/AR.js/three.js/examples/markertraining/examples/generator.html" 
       target="_blank" 
       style="background: #007bff; color: white; padding: 10px 15px; text-decoration: none; border-radius: 5px; font-size: 14px;">
      Створити маркер
    </a>
  </div>

  <!-- AR сцена -->
  <a-scene 
    embedded 
    arjs="sourceType: webcam; debugUIEnabled: false; detectionMode: mono_and_matrix; matrixCodeType: 3x3;"
    vr-mode-ui="enabled: false"
    loading-screen="enabled: false">
    
    <!-- Попереднє завантаження текстур -->
    <a-assets>
      <img id="brick" src="https://cdn.aframe.io/a-painter/images/brick.jpg">
      <img id="bricks2" src="https://raw.githubusercontent.com/aframevr/sample-assets/master/assets/images/bricks/bricks2.jpg">
      <img id="concrete" src="https://cdn.aframe.io/360-image-gallery-boilerplate/img/city.jpg">
      <img id="grass" src="https://cdn.aframe.io/a-painter/images/grass.jpg">
    </a-assets>
    
    <!-- Маркер Hiro (для тестування) -->
    <a-marker preset="hiro" cursor="rayOrigin: mouse">
      
      <!-- Основа (компактна версія) -->
      <a-plane position="0 0 0" rotation="-90 0 0" width="8" height="8" 
               material="src: #grass; repeat: 2 2"></a-plane>
      
      <!-- Асфальтові доріжки -->
      <a-plane position="0 0.001 -2" rotation="-90 0 0" width="5" height="1" color="#424242"></a-plane>
      <a-plane position="2 0.001 0" rotation="-90 0 90" width="4" height="1" color="#424242"></a-plane>
      <a-plane position="-2 0.001 0" rotation="-90 0 90" width="4" height="1" color="#424242"></a-plane>
      
      <!-- Головна будівля міської ради (масштабована) -->
      <a-entity id="main-building" position="0 0 0" scale="0.3 0.3 0.3">
        
        <!-- Основний корпус -->
        <a-box position="0 1.5 0" width="6" height="3" depth="4" 
               material="src: #bricks2; roughness: 0.8; repeat: 3 1.5; color: #D2B48C">
        </a-box>
        
        <!-- Центральна фасадна частина -->
        <a-box position="0 1.5 -2.1" width="5" height="3" depth="0.2" 
               material="src: #bricks2; roughness: 0.6; repeat: 2.5 1.5; color: #F5DEB3">
        </a-box>
        
        <!-- Колони (3 колони замість 5) -->
        <a-cylinder position="-1.5 1.5 -2.1" radius="0.2" height="3" 
                    material="src: #bricks2; roughness: 0.5; repeat: 1 1.5; color: #F5DEB3"></a-cylinder>
        <a-cylinder position="0 1.5 -2.1" radius="0.2" height="3" 
                    material="src: #bricks2; roughness: 0.5; repeat: 1 1.5; color: #F5DEB3"></a-cylinder>
        <a-cylinder position="1.5 1.5 -2.1" radius="0.2" height="3" 
                    material="src: #bricks2; roughness: 0.5; repeat: 1 1.5; color: #F5DEB3"></a-cylinder>
        
        <!-- Дах основної будівлі -->
        <a-box position="0 3.2 0" width="6.5" height="0.3" depth="4.5" color="#8B4513"></a-box>
        
        <!-- Фронтон -->
        <a-entity position="0 3.8 -2.1">
          <a-cone position="0 0 0" radius-bottom="2.5" radius-top="0" height="1" 
                  rotation="0 0 0" color="#8B4513"></a-cone>
        </a-entity>
        
        <!-- Головний вхід -->
        <a-box position="0 0.75 -2.2" width="1.2" height="1.5" depth="0.1" 
               material="src: #brick; color: #654321"></a-box>
        <a-box position="0 0.75 -2.3" width="1" height="1.2" depth="0.1" color="#2F4F4F"></a-box>
        
        <!-- Сходи -->
        <a-box position="0 0.05 -2.5" width="2" height="0.1" depth="0.5" color="#696969"></a-box>
        <a-box position="0 0.15 -2.7" width="2" height="0.1" depth="0.3" color="#696969"></a-box>
        <a-box position="0 0.25 -2.9" width="2" height="0.1" depth="0.3" color="#696969"></a-box>
        
        <!-- Вікна -->
        <a-box position="-2 1 -2.2" width="0.6" height="0.5" depth="0.05" color="#87CEEB"></a-box>
        <a-box position="2 1 -2.2" width="0.6" height="0.5" depth="0.05" color="#87CEEB"></a-box>
        <a-box position="-1.5 1 -2.2" width="0.4" height="0.5" depth="0.05" color="#87CEEB"></a-box>
        <a-box position="1.5 1 -2.2" width="0.4" height="0.5" depth="0.05" color="#87CEEB"></a-box>
        
        <!-- Вікна другого поверху -->
        <a-box position="-2.5 2 -2.2" width="0.5" height="0.4" depth="0.05" color="#87CEEB"></a-box>
        <a-box position="-1.5 2 -2.2" width="0.5" height="0.4" depth="0.05" color="#87CEEB"></a-box>
        <a-box position="1.5 2 -2.2" width="0.5" height="0.4" depth="0.05" color="#87CEEB"></a-box>
        <a-box position="2.5 2 -2.2" width="0.5" height="0.4" depth="0.05" color="#87CEEB"></a-box>
        
        <!-- Бокові вікна -->
        <a-box position="-3.1 1.2 -0.7" width="0.05" height="0.5" depth="0.8" color="#87CEEB"></a-box>
        <a-box position="-3.1 1.2 0.7" width="0.05" height="0.5" depth="0.8" color="#87CEEB"></a-box>
        <a-box position="3.1 1.2 -0.7" width="0.05" height="0.5" depth="0.8" color="#87CEEB"></a-box>
        <a-box position="3.1 1.2 0.7" width="0.05" height="0.5" depth="0.8" color="#87CEEB"></a-box>
        
        <!-- Задні вікна -->
        <a-box position="-1.5 1.2 2.1" width="0.8" height="0.5" depth="0.05" color="#87CEEB"></a-box>
        <a-box position="0 1.2 2.1" width="0.8" height="0.5" depth="0.05" color="#87CEEB"></a-box>
        <a-box position="1.5 1.2 2.1" width="0.8" height="0.5" depth="0.05" color="#87CEEB"></a-box>
        
        <!-- Прапор України -->
        <a-entity position="0 4.5 -1">
          <a-cylinder position="0 0 0" radius="0.04" height="1.5" color="#8B4513"></a-cylinder>
          <a-plane position="0.5 0.4 0" width="1" height="0.6" color="#005BBB" 
                   animation="property: rotation; to: 0 10 0; dur: 4000; dir: alternate; loop: true">
            <a-plane position="0 -0.15 0.01" width="1" height="0.3" color="#FFD700"></a-plane>
          </a-plane>
        </a-entity>
        
      </a-entity>
      
      <!-- Адміністративні прибудови -->
      <a-box position="-1.8 0.9 -0.8" width="1" height="1.8" depth="1" 
             material="src: #brick; roughness: 0.8; repeat: 1 1; color: #CD853F" scale="0.3 0.3 0.3"></a-box>
      <a-box position="1.8 0.9 -0.8" width="1" height="1.8" depth="1" 
             material="src: #brick; roughness: 0.8; repeat: 1 1; color: #CD853F" scale="0.3 0.3 0.3"></a-box>
      
      <!-- Дахи прибудов -->
      <a-box position="-1.8 1.95 -0.8" width="1.1" height="0.3" depth="1.1" color="#8B4513" scale="0.3 0.3 0.3"></a-box>
      <a-box position="1.8 1.95 -0.8" width="1.1" height="0.3" depth="1.1" color="#8B4513" scale="0.3 0.3 0.3"></a-box>
      
      <!-- Дерева навколо -->
      <a-entity position="-2.5 0 -1.5" scale="0.3 0.3 0.3">
        <a-cylinder position="0 0.8 0" radius="0.2" height="1.5" color="#8B4513"></a-cylinder>
        <a-sphere position="0 1.8 0" radius="1.2" color="#228B22"></a-sphere>
      </a-entity>
      
      <a-entity position="2.5 0 -1.5" scale="0.3 0.3 0.3">
        <a-cylinder position="0 0.8 0" radius="0.2" height="1.5" color="#8B4513"></a-cylinder>
        <a-sphere position="0 1.8 0" radius="1.2" color="#228B22"></a-sphere>
      </a-entity>
      
      <a-entity position="-3 0 1.5" scale="0.3 0.3 0.3">
        <a-cylinder position="0 0.8 0" radius="0.2" height="1.5" color="#8B4513"></a-cylinder>
        <a-sphere position="0 1.8 0" radius="1.2" color="#228B22"></a-sphere>
      </a-entity>
      
      <a-entity position="3 0 1.5" scale="0.3 0.3 0.3">
        <a-cylinder position="0 0.8 0" radius="0.2" height="1.5" color="#8B4513"></a-cylinder>
        <a-sphere position="0 1.8 0" radius="1.2" color="#228B22"></a-sphere>
      </a-entity>
      
      <!-- Текст з назвою -->
      <a-text value="КРИВОРІЗЬКА МІСЬКА РАДА" 
              position="0 0.5 -1.5" 
              color="#003366" 
              align="center" 
              scale="0.8 0.8 0.8"
              font="dejavu">
      </a-text>
      
      <!-- Додаткова анімація для всієї сцени -->
      <a-animation attribute="rotation" 
                  to="0 360 0" 
                  dur="30000" 
                  repeat="indefinite"
                  easing="linear">
      </a-animation>
      
    </a-marker>
    
    <!-- Додатковий маркер для тестування (pattern) -->
    <!-- Розкоментуйте цей блок та додайте свій файл .patt -->
    <!--
    <a-marker type="pattern" url="path/to/your/kryvyi-rih-marker.patt">
      <a-text value="CUSTOM MARKER DETECTED" 
              position="0 1 0" 
              color="#FF0000" 
              align="center" 
              scale="2 2 2">
      </a-text>
    </a-marker>
    -->
    
    <!-- Камера AR -->
    <a-entity camera></a-entity>
    
  </a-scene>

  <script>
    // Додаткова логіка для AR
    window.addEventListener('load', function() {
      console.log('AR сцена завантажена!');
      
      // Відстеження подій маркера
      const marker = document.querySelector('a-marker[preset="hiro"]');
      
      if (marker) {
        marker.addEventListener('markerFound', function() {
          console.log('Маркер знайдено!');
          // Можна додати додаткову логіку при знаходженні маркера
        });
        
        marker.addEventListener('markerLost', function() {
          console.log('Маркер втрачено!');
          // Можна додати додаткову логіку при втраті маркера
        });
      }
      
      // Перевірка підтримки камери
      if (navigator.mediaDevices && navigator.mediaDevices.getUserMedia) {
        navigator.mediaDevices.getUserMedia({video: true})
          .then(function(stream) {
            console.log('Доступ до камери отримано');
            stream.getTracks().forEach(track => track.stop());
          })
          .catch(function(err) {
            console.error('Помилка доступу до камери:', err);
            alert('Для роботи AR потрібен доступ до камери!');
          });
      }
    });
    
    // Обробка помилок
    window.addEventListener('error', function(e) {
      console.error('Помилка:', e);
    });
  </script>
</body>
</html>
