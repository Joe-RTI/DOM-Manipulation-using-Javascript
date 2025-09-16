# https://roadmap.sh/projects/simple-tabs
# DOM-Manipulation-using-Javascript
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Tabs Project</title>
  <style>
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: linear-gradient(135deg, #74ebd5 0%, #9face6 100%);
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      margin: 0;
    }

    .container {
      background: #fff;
      border-radius: 15px;
      box-shadow: 0 8px 20px rgba(0,0,0,0.15);
      max-width: 600px;
      width: 100%;
      overflow: hidden;
    }

    .tabs {
      display: flex;
      border-bottom: 2px solid #eee;
      background: #f9f9f9;
    }

    .tab {
      flex: 1;
      padding: 12px;
      cursor: pointer;
      border: none;
      background: transparent;
      transition: all 0.3s ease;
      font-weight: 500;
      font-size: 16px;
      color: #555;
    }

    .tab:hover {
      background: #e6f0ff;
      color: #007bff;
    }

    .tab.active {
      background: #007bff;
      color: #fff;
      font-weight: bold;
      border-bottom: 3px solid #0056b3;
    }

    .tab-content {
      display: none;
      padding: 25px;
      animation: fadeIn 0.4s ease;
      font-size: 18px;
      color: #333;
    }

    .tab-content.active {
      display: block;
    }

    @keyframes fadeIn {
      from {opacity: 0; transform: translateY(10px);}
      to {opacity: 1; transform: translateY(0);}
    }
  </style>
</head>
<body>

  <div class="container">
    <!-- Tabs -->
    <div class="tabs">
      <button class="tab active" data-tab="tab1">First tab</button>
      <button class="tab" data-tab="tab2">Second tab</button>
      <button class="tab" data-tab="tab3">Third tab</button>
      <button class="tab" data-tab="tab4">Fourth tab</button>
    </div>

    <!-- Tab contents -->
    <div id="tab1" class="tab-content active">
      <p>💻 Joseph and Maryam love coding</p>
    </div>
    <div id="tab2" class="tab-content">
      <p>🎨 Sumayya loves designing</p>
    </div>
    <div id="tab3" class="tab-content">
      <p>🏢 RTI is a nice place</p>
    </div>
    <div id="tab4" class="tab-content">
      <p>🍔 Lets go to the canteen</p>
    </div>
  </div>

  <script>
    const tabs = document.querySelectorAll(".tab");
    const contents = document.querySelectorAll(".tab-content");

    tabs.forEach(tab => {
      tab.addEventListener("click", () => {
        tabs.forEach(t => t.classList.remove("active"));
        contents.forEach(c => c.classList.remove("active"));

        tab.classList.add("active");
        document.getElementById(tab.dataset.tab).classList.add("active");
      });
    });
  </script>

</body>
</html>
