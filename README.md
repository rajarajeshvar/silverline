<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Expanding Cards</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: 'Segoe UI', sans-serif;
      background-color: #111;
      color: #fff;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }

    .container {
      display: flex;
      gap: 1rem;
      width: 90vw;
      max-width: 1200px;
      height: 80vh;
    }

    .panel {
      flex: 1;
      background-size: cover;
      background-position: center;
      border-radius: 15px;
      position: relative;
      cursor: pointer;
      transition: flex 0.5s ease-in-out;
      display: flex;
      align-items: flex-end;
      overflow: hidden;
    }

    .panel h3 {
      background: rgba(0, 0, 0, 0.6);
      width: 100%;
      padding: 1rem;
      text-align: center;
      font-size: 1.2rem;
    }

    .panel.active {
      flex: 5;
    }

    .panel:not(.active) {
      flex: 0.5;
    }

    @media (max-width: 768px) {
      .container {
        flex-direction: column;
        height: auto;
      }

      .panel {
        height: 200px;
      }

      .panel.active {
        flex: 1;
        height: 300px;
      }

      .panel:not(.active) {
        flex: 1;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="panel active" style="background-image: url('jikan.png');">
      <h3>Nature</h3>
    </div>
    <div class="panel" style="background-image: url('jikan.png');">
      <h3>City Lights</h3>
    </div>
    <div class="panel" style="background-image: url('jikan.png');">
      <h3>Tech World</h3>
    </div>
    <div class="panel" style="background-image: url('jikan.png');">
      <h3>Outer Space</h3>
    </div>
    <div class="panel" style="background-image: url('https://source.unsplash.com/800x600/?ocean');">
      <h3>Ocean Life</h3>
    </div>
  </div>

  <script>
    const panels = document.querySelectorAll('.panel');

    panels.forEach(panel => {
      panel.addEventListener('click', () => {
        removeActiveClasses();
        panel.classList.add('active');
      });
    });

    function removeActiveClasses() {
      panels.forEach(panel => {
        panel.classList.remove('active');
      });
    }
  </script>
</body>
</html>
