<!DOCTYPE html>
<html>
<head>
  <title>Capitale du Pays (Afrique)</title>
  <style>
    body {
      font-family: sans-serif;
      text-align: center;
    }
    #container {
      margin: 50px auto;
      width: 300px;
      padding: 20px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    input[type="text"] {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
      border: 1px solid #ccc;
      border-radius: 3px;
    }
    button {
      background-color: #4CAF50;
      color: white;
      padding: 10px 20px;
      border: none;
      border-radius: 3px;
      cursor: pointer;
    }
    #result {
      margin-top: 20px;
      font-size: 18px;
    }
  </style>
</head>
<body>

  <div id="container">
    <h1>Capitale du Pays (Afrique)</h1>
    <input type="text" id="countryInput" placeholder="Entrez un pays d'Afrique">
    <button id="submitBtn">Rechercher</button>
    <div id="result"></div>
  </div>

  <script>
    const countryInput = document.getElementById('countryInput');
    const submitBtn = document.getElementById('submitBtn');
    const result = document.getElementById('result');
    let capitals = {}; // On initialise un objet vide

    // Données des pays et capitales d'Afrique (intégrées directement dans le code)
    const countryData = {
      "pays": [
        {"nom": "Afrique du Sud", "capitale": "Pretoria"},
        {"nom": "Algérie", "capitale": "Alger"},
        {"nom": "Angola", "capitale": "Luanda"},
        {"nom": "Bénin", "capitale": "Porto-Novo"},
        {"nom": "Botswana", "capitale": "Gaborone"},
        {"nom": "Burkina Faso", "capitale": "Ouagadougou"},
        {"nom": "Burundi", "capitale": "Gitega"},
        {"nom": "Cabo Verde", "capitale": "Praia"},
        {"nom": "Cameroun", "capitale": "Yaoundé"},
        {"nom": "Centrafrique", "capitale": "Bangui"},
        {"nom": "Comores", "capitale": "Moroni"},
        {"nom": "Congo", "capitale": "Brazzaville"},
        {"nom": "Congo (RDC)", "capitale": "Kinshasa"},
        {"nom": "Côte d'Ivoire", "capitale": "Yamoussoukro"},
        {"nom": "Djibouti", "capitale": "Djibouti"},
        {"nom": "Égypte", "capitale": "Le Caire"},
        {"nom": "Érythrée", "capitale": "Asmara"},
        {"nom": "Eswatini", "capitale": "Mbabane"},
        {"nom": "Éthiopie", "capitale": "Addis-Abeba"},
        {"nom": "Gabon", "capitale": "Libreville"},
        {"nom": "Gambie", "capitale": "Banjul"},
        {"nom": "Ghana", "capitale": "Accra"},
        {"nom": "Guinée", "capitale": "Conakry"},
        {"nom": "Guinée-Bissau", "capitale": "Bissau"},
        {"nom": "Kenya", "capitale": "Nairobi"},
        {"nom": "Lesotho", "capitale": "Maseru"},
        {"nom": "Libéria", "capitale": "Monrovia"},
        {"nom": "Libye", "capitale": "Tripoli"},
        {"nom": "Madagascar", "capitale": "Antananarivo"},
        {"nom": "Malawi", "capitale": "Lilongwe"},
        {"nom": "Mali", "capitale": "Bamako"},
        {"nom": "Mauritanie", "capitale": "Nouakchott"},
        {"nom": "Maurice", "capitale": "Port-Louis"},
        {"nom": "Maroc", "capitale": "Rabat"},
        {"nom": "Mozambique", "capitale": "Maputo"},
        {"nom": "Namibie", "capitale": "Windhoek"},
        {"nom": "Niger", "capitale": "Niamey"},
        {"nom": "Nigeria", "capitale": "Abuja"},
        {"nom": "Ouganda", "capitale": "Kampala"},
        {"nom": "Rwanda", "capitale": "Kigali"},
        {"nom": "Sao Tomé-et-Principe", "capitale": "Sao Tomé"},
        {"nom": "Sénégal", "capitale": "Dakar"},
        {"nom": "Seychelles", "capitale": "Victoria"},
        {"nom": "Sierra Leone", "capitale": "Freetown"},
        {"nom": "Somalie", "capitale": "Mogadiscio"},
        {"nom": "Soudan", "capitale": "Khartoum"},
        {"nom": "Soudan du Sud", "capitale": "Juba"},
        {"nom": "Tanzanie", "capitale": "Dodoma"},
        {"nom": "Tchad", "capitale": "N'Djamena"},
        {"nom": "Togo", "capitale": "Lomé"},
        {"nom": "Tunisie", "capitale": "Tunis"},
        {"nom": "Zambie", "capitale": "Lusaka"},
        {"nom": "Zimbabwe", "capitale": "Harare"}
      ]
    };

    // Créer l'objet 'capitals' à partir des données
    for (let i = 0; i < countryData.pays.length; i++) {
      capitals[countryData.pays[i].nom] = countryData.pays[i].capitale;
    }

    // Gestion de la recherche
    submitBtn.addEventListener('click', () => {
      const country = countryInput.value.trim();
      if (country in capitals) {
        result.textContent = `La capitale de ${country} est ${capitals[country]}`;
      } else {
        result.textContent = "non trouvé"; // Affiche "non trouvé" en cas d'erreur
      }
      countryInput.value = ''; // Remettre le champ d'entrée à vide

      // Réactiver le bouton et le champ de saisie après la recherche
      submitBtn.disabled = false;
      countryInput.disabled = false;
    });

    // Gestion des saisies après l'affichage de la réponse
    result.addEventListener('click', () => {
      // Désactiver le bouton et le champ de saisie pour éviter des requêtes multiples
      submitBtn.disabled = true;
      countryInput.disabled = true;
          
      // Attendre un peu avant de réactiver le champ de saisie
      setTimeout(() => {
        countryInput.disabled = false;
        countryInput.focus();
      }, 500);
    });

  </script>

</body>
</html>
