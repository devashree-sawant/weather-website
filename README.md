# weather-website
<!DOCTYPE html>
<html>
<head>
  <title>Simple Weather App</title>
  <style>
    body {
      font-family: Arial;
      background: #f0f8ff;
      text-align: center;
      padding: 50px;
    }
    select, button {
      padding: 10px;
      margin: 10px;
      font-size: 16px;
    }
    .result {
      margin-top: 20px;
      padding: 20px;
      background: #ffffff;
      border-radius: 8px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      display: inline-block;
    }
  </style>
</head>
<body>

  <h2>🌤 Simple Weather App</h2>

  <select id="city">
    <option value="">-- Select City --</option>
    <option value="Mumbai">Mumbai</option>
    <option value="Delhi">Delhi</option>
    <option value="Chennai">Chennai</option>
    <option value="Kolkata">Kolkata</option>
  </select>
  <br>
  <button onclick="showWeather()">Show Weather</button>

  <div class="result" id="output">Weather info will appear here</div>

  <script>
    function showWeather() {
      const city = document.getElementById('city').value;
      const output = document.getElementById('output');

      if (!city) {
        output.textContent = "⚠ Please select a city.";
        return;
      }

      // Simulated temperature and wind
      const temperature = Math.floor(Math.random() * 10) + 25;
      const windSpeed = Math.floor(Math.random() * 10) + 5;

      // Current time
      const now = new Date();
      const time = now.toLocaleTimeString([], { hour: '2-digit', minute: '2-digit', hour12: true });

      output.innerHTML = `
        📍 City: ${city}<br>
        🌡 Temperature: ${temperature}°C<br>
        🌬 Wind Speed: ${windSpeed} km/h<br>
        ⏰ Time: ${time}
      `;
    }
  </script>

</body>
</html>
