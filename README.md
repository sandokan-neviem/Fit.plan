<!DOCTYPE html>
<html lang="sk">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Fit plán na mieru</title>

  <link rel="stylesheet" href="style.css">
  

</head>
<body>
  <div class="logo.png"></div>
  <h1>Fit plán na mieru</h1>
  <nav>
    <a href="onas.html">O nás</a>
    <a href="kontakt.html">Kontakt</a>
    <a href="info.html">Bližšie info</a>
  </nav>

  <form id="fitForm">
    <input id="vyska" type="number" placeholder="Výška (cm)" required>
    <input id="vaha" type="number" placeholder="Váha (kg)" required>
    <input id="vek" type="number" placeholder="Vek" required>

    <select id="pohyb" required>
      <option disabled selected>Pohyb</option>
      <option value="1.9">1. Veľmi aktívny</option>
      <option value="1.6">2. Aktívny</option>
      <option value="1.4">3. Nie moc aktívny</option>
      <option value="1.2">4. Neaktívny</option>
    </select>

    <select id="ciel" required>
      <option disabled selected>Cieľ</option>
      <option value="chudnutie">1. Chudnutie</option>
      <option value="naberanie">2. Naberanie</option>
      <option value="udrzanie">3. Zostať v kondícii</option>
    </select>

    <button type="button" onclick="vypocitaj()">Potvrdiť</button>
  </form>

  <div id="vysledok"></div>

  <script>
  function vypocitaj() {
    const vyska = parseFloat(document.getElementById("vyska").value);
    const vaha = parseFloat(document.getElementById("vaha").value);
    const vek = parseFloat(document.getElementById("vek").value);
    const pohyb = parseFloat(document.getElementById("pohyb").value);
    const ciel = document.getElementById("ciel").value;

    if (!vyska || !vaha || !vek || !pohyb || !ciel) {
      alert("Vyplň všetky údaje!");
      return;
    }
    // Uloženie údajov do localStorage
    localStorage.setItem("vyska", vyska);
    localStorage.setItem("vaha", vaha);
    localStorage.setItem("vek", vek);
    localStorage.setItem("pohyb", pohyb);
    localStorage.setItem("ciel", ciel);

    // Presmerovanie na podstránku s tréningami
    window.location.href = "treningy.html";
  }
  </script>
  
  <img src="Galeria/logo.png" alt="." width="225px", height="225px"/>
</body>
</html>
