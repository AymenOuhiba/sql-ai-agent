# Guide Installation (Francais)

## Prerequis
- Python 3.8+
- Ollama installe
- (Option SQL Server) ODBC Driver 17 + SQL Server local

## 1. Installer les dependances
```bash
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```

## 2. Installer le modele Ollama
```bash
ollama pull llama3.2
```

## 3. Configurer les variables
1. Creer un fichier `.env` a la racine.
2. Copier les valeurs depuis `env.example.txt`.

Exemple minimal:
```env
AYMENOU_LLM_BACKEND=ollama
AYMENOU_OLLAMA_MODEL=llama3.2
AYMENOU_OLLAMA_URL=http://localhost:11434/api/generate
AYMENOU_DB_PATH=data/sample.db
AYMENOU_MAX_QUERY_ROWS=500
AYMENOU_FLASK_DEBUG=0
```

Option SQL Server:
```env
AYMENOU_SQL_SERVER=YOUR_SERVER\SQLEXPRESS
AYMENOU_SQL_DATABASE=YouTubeAnalytics
```

## 4. Lancer l'application

### Option A: Web app generale
```bash
python web_app_v2.py
```
Ouvrir: `http://localhost:5000`

### Option B: Agent YouTube (SQL Server)
```bash
python agent.py
```
Ouvrir: `http://localhost:5001`

### Option C: CLI
```bash
python app.py
```

## 5. Verifier rapidement
1. Poser une question depuis les exemples.
2. Verifier le SQL genere.
3. Verifier le tableau resultat.
4. Tester export `CSV` puis `SQL+Result`.

## Probleme frequents
- `ollama not found`: redemarrer le terminal ou corriger PATH.
- `pyodbc` erreur: `pip install pyodbc`.
- Connexion SQL Server echoue: verifier `AYMENOU_SQL_SERVER`.
- Reponse lente: normal en local CPU (mode offline).
