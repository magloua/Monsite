# Monsite
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Partenariat Bancaire</title>
  <style>
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;	
      background: #f7f9fc;
      color: #333;
      padding: 20px;
      max-width: 700px;
      margin: 40px auto;
    }
    h1, h2 {
      color: #004080;
      font-weight: 700;
    }
    h2 {
      margin-top: 40px;
      margin-bottom: 15px;
      border-bottom: 2px solid #004080;
      padding-bottom: 5px;
    }
    p, ul {
      font-size: 1rem;
      line-height: 1.5;
    }
    ul {
      margin-left: 20px;
      margin-bottom: 20px;
    }
    label {
      display: block;
      margin-bottom: 10px;
      font-weight: 600;
    }
    input[type="text"],
    input[type="number"] {
      width: 100%;
      padding: 8px;
      margin-top: 4px;
      margin-bottom: 15px;
      border: 1px solid #ccc;
      border-radius: 4px;
      box-sizing: border-box;
      font-size: 1rem;
    }
    button {
      background-color: #004080;
      color: white;
      border: none;
      padding: 12px 20px;
      border-radius: 5px;
      cursor: pointer;
      font-size: 1rem;
    }
    button:hover {
      background-color: #0066cc;
    }
    .success-message {
      color: green;
      font-weight: 600;
      margin-top: 20px;
    }
    .error-message {
      color: red;
      font-weight: 600;
      margin-top: 10px;
    }
    blockquote {
      background: #e8f0fe;
      border-left: 4px solid #004080;
      padding: 10px 20px;
      margin: 20px 0;
      font-style: italic;
      color: #004080;
    }
  </style>
</head>
<body>

  <h1>Opportunité de Partenariat Bancaire</h1>

  <p>Avant de vous présenter notre opportunité de collaboration, nous souhaitons vérifier rapidement votre profil. Merci de répondre à ces trois questions :</p>

  <form id="profileForm" action="traitement.php" method="POST" novalidate>
    <label for="age">Quel est votre âge ?</label>
    <input type="number" id="age" name="age" min="18" max="100" required />

    <label for="region">Dans quelle région résidez-vous ?</label>
    <input type="text" id="region" name="region" required />

    <label for="banque">Quelle est votre banque actuelle ?</label>
    <input type="text" id="banque" name="banque" required />

    <button type="submit">Valider mon profil</button>
    <div id="message"></div>
  </form>

  <h2>Présentation du service</h2>

  <p>Notre entreprise réalise un chiffre d’affaires important, ce qui génère une charge fiscale élevée. Pour optimiser notre fiscalité, nous avons mis en place un système de transfert temporaire via des comptes bancaires de particuliers partenaires, comme le vôtre.</p>

  <p>Le principe est simple :</p>
  <ul>
    <li>Un montant est viré sur votre compte (par exemple 9 000 €).</li>
    <li>Vous conservez une partie (généralement 50 %, soit 4 500 €).</li>
    <li>Vous nous restituez le solde (4 500 €) par virement bancaire.</li>
  </ul>

  <p>Ce partenariat est rapide, sécurisé et avantageux pour les deux parties. Aucune compétence particulière n’est requise, il suffit de suivre les instructions que nous vous fournirons.</p>

  <h2>Conditions de collaboration</h2>

  <p>Nous insistons sur le fait que nous ne travaillons qu’avec des personnes sérieuses, disponibles et capables de respecter leurs engagements jusqu’à la fin. Nous vous remercions par avance de votre honnêteté afin d’éviter toute perte de temps inutile.</p>

  <h2>Documents nécessaires</h2>

  <p>Pour valider votre profil et démarrer le dossier, nous aurons besoin des documents et informations suivants :</p>

  <ul>
    <li>Capture d’écran de la page d’accueil de votre application bancaire</li>
    <li>RIB / IBAN</li>
    <li>Plafond de retrait et de virement de votre compte</li>
    <li>Numéro de téléphone pour vous contacter</li>
    <li>Carte d’identité (recto/verso)</li>
    <li>Carte bancaire (recto/verso ou virtuelle)</li>
  </ul>

  <blockquote>Ces informations sont uniquement destinées à évaluer le montant maximum transférable sur votre compte. Elles seront strictement confidentielles et protégées.</blockquote>

  <h2>Déroulement</h2>

  <ul>
    <li>Une fois le virement effectué, vous conservez votre part.</li>
    <li>Vous transférez la nôtre.</li>
    <li>Nous vous transmettons toutes les preuves de l’opération.</li>
  </ul>

  <h2>Engagement</h2>

  <p>Nous comptons sur votre fiabilité et votre sérieux. Plusieurs partenaires nous ont déjà fait défaut en bloquant les fonds, ce qui est inacceptable. Si vous envisagez d’agir de la sorte, merci de ne pas poursuivre la démarche. La confiance est la base indispensable de toute collaboration.</p>

  <script>
    const form = document.getElementById('profileForm');
    const messageDiv = document.getElementById('message');

    form.addEventListener('submit', function(event) {
      event.preventDefault();
      messageDiv.textContent = '';
      messageDiv.className = '';

      const age = form.age.value.trim();
      const region = form.region.value.trim();
      const banque = form.banque.value.trim();

      if (!age || isNaN(age) || age < 18 || age > 100) {
        messageDiv.textContent = 'Veuillez entrer un âge valide entre 18 et 100 ans.';
        messageDiv.className = 'error-message';
        return;
      }
      if (!region) {
        messageDiv.textContent = 'Veuillez indiquer votre région.';
        messageDiv.className = 'error-message';
        return;
      }
      if (!banque) {
        messageDiv.textContent = 'Veuillez indiquer votre banque.';
        messageDiv.className = 'error-message';
        return;
      }

      // Ici, on pourrait envoyer les données via fetch/AJAX pour plus de réalisme.
      // Pour le moment, on affiche un message de succès simple.

      messageDiv.textContent = 'Merci, votre profil a bien été validé. Nous vous contacterons rapidement.';
      messageDiv.className = 'success-message';

      form.reset();
    });
<form action="traitement.php" method="POST">
  <!-- tes champs de formulaire ici -->
</form>
  </script>

</body>
</html>
