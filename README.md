<!doctype html>
<html lang="fr">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Unité Mobile - Dépannage & Services Mécaniques</title>
  <meta name="description" content="Unité mobile de mécanique : dépannage, remorquage, entretien sur place. Réservez une intervention en quelques clics." />

  <style>
    :root{--accent:#0b79d0;--dark:#0b2440;--muted:#6b7280}
    *{box-sizing:border-box}
    body{font-family:Inter, system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial; margin:0;color:#111}
    header{background:linear-gradient(90deg,var(--accent),#046aa6);color:#fff;padding:24px}
    .container{max-width:1100px;margin:0 auto;padding:18px}
    .brand{display:flex;gap:12px;align-items:center}
    .logo{width:56px;height:56px;border-radius:10px;background:#fff3;padding:6px;display:flex;align-items:center;justify-content:center;color:var(--accent);font-weight:700}
    nav{margin-left:auto}
    nav a{color:rgba(255,255,255,.95);text-decoration:none;margin-left:18px;font-weight:600}

    .hero{display:grid;grid-template-columns:1fr;gap:18px;align-items:center;padding:28px 0}
    .hero h1{font-size:clamp(20px,4vw,34px);margin:0 0 6px}
    .hero p{margin:0 0 12px;color:var(--muted)}
    .cta-row{display:flex;gap:12px;flex-wrap:wrap}
    .btn{background:#cd9a9a;color:var(--accent);padding:10px 16px;border-radius:8px;border:0;font-weight:700;cursor:pointer}
    .btn.secondary{background:transparent;border:2px solid rgba(255, 255, 255, 0.058);color:#fff}

    main{padding:20px 0}
    .grid-3{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:16px}
    .card{border-radius:12px;padding:16px;background:#f8fafc;box-shadow:0 4px 14px rgba(11,37,64,0.06)}
    .card h3{margin:0 0 8px}
    .muted{color:var(--muted)}

    form{background:#535151;padding:16px;border-radius:12px;box-shadow:0 6px 20px rgba(2,6,23,0.06)}
    label{display:block;font-size:13px;margin-top:10px;color:#b93131}
    input[type=text], input[type=tel], input[type=datetime-local], textarea, select{width:100%;padding:10px;border-radius:8px;border:1px solid #36589c;margin-top:6px;font-size:14px}
    textarea{min-height:100px}
    .form-grid{display:grid;grid-template-columns:1fr;gap:12px}
    @media(min-width:760px){.hero{grid-template-columns:1fr 420px}.form-grid{grid-template-columns:1fr 1fr}}

    footer{padding:20px 0;border-top:1px solid #265288;margin-top:30px}
    .small{font-size:13px;color:var(--muted)}

    .phone-bubble{position:fixed;right:18px;bottom:18px;background:var(--accent);color:#924444;padding:12px 14px;border-radius:999px;box-shadow:0 8px 30px rgba(11,37,64,0.18);display:flex;gap:10px;align-items:center;text-decoration:none}

    .map{width:100%;height:220px;border-radius:10px;overflow:hidden;border:1px solid #2852a8}

    .success{background:#2e5040;border:1px solid #3bbb68;color:#93a5a0;padding:12px;border-radius:8px;margin-top:12px}
    .hidden{display:none}
  </style>
</head>
<body>
  <header>
    <div class="container" style="display:flex;align-items:center">
      <div class="brand">
        <div class="logo">UM</div>
        <div>
          <div style="font-weight:700">Unité Mobile Mécanique</div>
          <div style="font-size:13px;color:rgba(207, 30, 30, 0.9)">Dépannage & entretien sur place</div>
        </div>
      </div>
      <nav>
        <a href="#services">Services</a>
        <a href="#demande">Demande</a>
        <a href="#contact">Contact</a>
      </nav>
    </div>
  </header>

  <div class="container">
    <section class="hero">
      <div>
        <h1>On vient où vous êtes — dépannage et entretien mécanique mobile</h1>
        <p class="muted">Appelez ou envoyez une demande en ligne. Nos techniciens se déplacent rapidement pour réparer, entretenir ou remorquer votre véhicule.</p>
        <div class="cta-row">
          <button class="btn" onclick="document.getElementById('demande').scrollIntoView({behavior:'smooth'})">Demander une intervention</button>
          <a href="tel:+212684964452" class="btn secondary">Appeler maintenant</a>
        </div>

        <div style="margin-top:18px;display:grid;grid-template-columns:repeat(auto-fit,minmax(140px,1fr));gap:10px">
          <div class="card">
            <h3>Intervention 24/7</h3>
            <div class="muted">Dépannage, crevaison, panne moteur, batterie</div>
          </div>
          <div class="card">
            <h3>Techniciens qualifiés</h3>
            <div class="muted">Expérience et outillage professionnel</div>
          </div>
        </div>
      </div>

      <aside>
        <div class="card">
          <h3>Demandez une intervention</h3>
          <form id="requestForm" onsubmit="handleSubmit(event)">
            <div class="form-grid">
              <div>
                <label for="name">Nom complet</label>
                <input id="name" name="name" type="text" required placeholder="Anouar...">
              </div>
              <div>
                <label for="phone">Téléphone</label>
                <input id="phone" name="phone" type="tel" required placeholder="06 00 00 00 00">
              </div>
            </div>

            <label for="service">Type de service</label>
            <select id="service" name="service" required>
              <option value="Depannage">Dépannage sur place</option>
              <option value="Remorquage">Remorquage</option>
              <option value="Entretien">Entretien / Vidange</option>
              <option value="Batterie">Remplacement batterie</option>
              <option value="pneumatique">changement de pneu et jantes</option>
            </select>

            <label for="location">Adresse / Position</label>
            <input id="location" name="location" type="text" required placeholder="Rue, ville ou point de repère">

            <label for="datetime">Quand ? (optionnel)</label>
            <input id="datetime" name="datetime" type="datetime-local">

            <label for="notes">Description du problème</label>
            <textarea id="notes" name="notes" placeholder="Ex: la voiture ne démarre pas, signe sonore..."></textarea>

            <button class="btn" type="submit" style="margin-top:12px">Envoyer la demande</button>

            <div id="result" class="success hidden" role="status"></div>
          </form>
        </div>

        <div style="margin-top:12px" class="card">
          <h4>Où nous trouver</h4>
          <div class="map" id="mapPlaceholder">
            <!-- Remplacez l'iframe ci-dessous par une vraie carte Google Maps si vous avez une clé -->
            <iframe title="carte" src="https://maps.google.com/maps?q=Casablanca&t=&z=13&ie=UTF8&iwloc=&output=embed" style="border:0;width:100%;height:100%" loading="lazy"></iframe>
          </div>
        </div>
      </aside>
    </section>

    <main>
      <section id="services">
        <h2>Services</h2>
        <div class="grid-3" style="margin-top:12px">
          <div class="card"><h3>Réparation sur place</h3><div class="muted">Pannes électriques, démarrage, réglages rapides.</div></div>
          <div class="card"><h3>Remorquage</h3><div class="muted">Remorquage sécurisé vers garage partenaire.</div></div>
          <div class="card"><h3>Entretien</h3><div class="muted">Vidange, filtres, vérification sécurité.</div></div>
        </div>
      </section>

      <section id="how" style="margin-top:20px">
        <h2>Comment ça marche</h2>
        <ol style="padding-left:18px">
          <li>Vous remplissez la demande ou appelez.</li>
          <li>Nous confirmons l'heure et l'adresse.</li>
          <li>Le technicien se déplace et effectue l'intervention ou propose le remorquage.</li>
        </ol>
      </section>

      <section id="demande" style="margin-top:20px">
        <h2>Demander une intervention (rapide)</h2>
        <div class="card" style="margin-top:12px">
          <!-- Formulaire de la page principale (même champs) -->
          <form id="quickForm" onsubmit="handleSubmit(event, true)">
            <div class="form-grid">
              <div>
                <label for="qname">Nom</label>
                <input id="qname" name="qname" type="text" required>
              </div>
              <div>
                <label for="qphone">Téléphone</label>
                <input id="qphone" name="qphone" type="tel" required>
              </div>
            </div>
            <label for="qservice">Service</label>
            <select id="qservice" name="qservice">
              <option>Dépannage</option>
              <option>Remorquage</option>
            </select>
            <label for="qlocation">Adresse</label>
            <input id="qlocation" name="qlocation" type="text" required>
            <button class="btn" style="margin-top:12px">Envoyer</button>
            <div id="qresult" class="success hidden" role="status"></div>
          </form>
        </div>
      </section>

      <section id="contact" style="margin-top:20px">
        <h2>Contact</h2>
        <div class="grid-3" style="margin-top:12px">
          <div class="card">
            <strong>Téléphone</strong>
            <div class="muted">+212 684964452</div>
          </div>
          <div class="card">
            <strong>Adresse</strong>
            <div class="muted">isi agadir, ihchach (exemple)</div>
          </div>
          <div class="card">
            <strong>Email</strong>
            <div class="muted">discordanouar652@gmail.com</div>
          </div>
        </div>
      </section>
    </main>

    <footer>
      <div class="container" style="display:flex;justify-content:space-between;align-items:center">
        <div class="small">© 2025 Unité Mobile Mécanique — Tous droits réservés</div>
        <div class="small">Conception rapide • Modèle HTML</div>
      </div>
    </footer>
  </div>

  <a class="phone-bubble" href="tel:+212684964452">
    <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.86 19.86 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6A19.86 19.86 0 0 1 2.08 4.18 2 2 0 0 1 4 2h3a2 2 0 0 1 2 1.72c.12 1.05.36 2.07.72 3.03a2 2 0 0 1-.45 2.11L9.91 10.09a16 16 0 0 0 6 6l1.23-1.23a2 2 0 0 1 2.11-.45c.96.36 1.98.6 3.03.72A2 2 0 0 1 22 16.92z"></path></svg>
    <span>Appeler</span>
  </a>

  <script>
    function handleSubmit(e, quick=false){
      e.preventDefault();
      const form = e.target;
      const result = quick ? document.getElementById('qresult') : document.getElementById('result');
      // Récupération simple des champs communs
      const name = form.querySelector('input[type="text"]')?.value || '—';
      const phone = form.querySelector('input[type="tel"]')?.value || '—';
      const service = form.querySelector('select')?.value || '—';
      // Simulation d'envoi — ici vous devrez appeler votre API back-end

      // Affichage message de succès
      result.textContent = `Demande reçue pour ${name} (${phone}). Service: ${service}. Nous vous contacterons sous peu.`;
      result.classList.remove('hidden');

      // Réinitialiser le formulaire après 1.2s
      setTimeout(()=>{
        form.reset();
      },1200);
    }
  </script>
</body>
</html>
