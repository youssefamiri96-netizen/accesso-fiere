# 🏟️ ACCESSO FIERE
### Gestionale per Allestitori Fieristici

Gestionale completo per piccole e medie imprese che operano nel settore degli allestimenti fieristici in Italia e all'estero.

---

## ✨ Funzionalità principali

- **Fiere & Stand** — Gestione fiere con padiglione, numero stand, superficie, tipo allestimento
- **Personale** — Dipendenti, presenze, ferie/permessi, cedolini
- **Mezzi & Veicoli** — Parco mezzi con scadenze (revisione, assicurazione, bollo)
- **Clienti & Preventivi** — CRM base con preventivi PDF
- **Documenti** — Gestione documentale con scadenze e alert email
- **PSAF** — Piano di Sicurezza Allestimento Fieristico
- **Multi-tenant SaaS** — Ogni azienda ha il suo database isolato

---

## 🚀 Deploy su Railway

### 1. Fork & Push su GitHub
```bash
git clone https://github.com/TUO-USERNAME/accesso-fiere.git
cd accesso-fiere
git add .
git commit -m "Initial commit - Accesso Fiere v1"
git push origin main
```

### 2. Crea progetto su Railway
1. Vai su [railway.app](https://railway.app) → **New Project**
2. Seleziona **Deploy from GitHub repo**
3. Collega il tuo repo `accesso-fiere`
4. Railway lo rileva automaticamente con Nixpacks

### 3. Aggiungi Volume persistente (IMPORTANTE)
1. Nel progetto Railway → **+ Add Service** → **Volume**
2. Mount path: `/data`
3. Questo mantiene il database tra i deploy

### 4. Variabili d'ambiente (Settings → Variables)
```
SECRET_KEY=cambia-con-stringa-casuale-lunga-sicura
PORT=5000
```

### 5. Accesso iniziale
- URL: il dominio generato da Railway (es. `accesso-fiere-production.up.railway.app`)
- Admin: `admin@accessofiere.it` / password: `admin123`
- ⚠️ **Cambia subito la password dopo il primo accesso!**

---

## 💻 Sviluppo locale

```bash
# 1. Clona il repo
git clone https://github.com/TUO-USERNAME/accesso-fiere.git
cd accesso-fiere

# 2. Crea virtual environment
python3 -m venv venv
source venv/bin/activate   # Windows: venv\Scripts\activate

# 3. Installa dipendenze
pip install -r requirements.txt

# 4. Avvia
python accesso_fiere.py

# Apri: http://localhost:5000
```

---

## 🔐 SuperAdmin (gestione multi-tenant)
- URL: `/superadmin/login`
- Impostare le credenziali tramite variabile d'ambiente:
  ```
  SUPERADMIN_EMAIL=superadmin@accessofiere.it
  SUPERADMIN_PASSWORD=password-sicura
  ```

---

## 📦 Stack tecnologico
- **Backend**: Python 3.11 + Flask
- **Database**: SQLite (multi-tenant, un DB per azienda)
- **Frontend**: HTML/CSS/JS vanilla + Chart.js
- **PDF**: ReportLab
- **Excel**: openpyxl
- **AI**: Claude API (opzionale, per analisi documenti)
- **Deploy**: Railway (Nixpacks)

---

## 📄 Licenza
Sviluppato da Accesso Fiere — tutti i diritti riservati.
