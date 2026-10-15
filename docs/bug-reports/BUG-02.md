# BUG-02 — Le lancement via Docker Compose échoue sous Windows : docker-entrypoint.sh converti en fins de ligne CRLF

Contexte (OS, navigateur, version, mode de lancement)

Windows, PowerShell, Docker Desktop (WSL2), Git avec les réglages par défaut, clone frais du repo QuickOrder V3.1

Cas de test lié

Aucun — anomalie d'installation constatée hors campagne

Préconditions

Docker Desktop démarré (« Engine running »). Git installé avec les options par défaut (core.autocrlf=true).

Étapes de reproduction

1. git clone https://github.com/amine-el-amrani/quickorder-qa-project.git  
2. cd quickorder-qa-project  
3. docker compose up --build

Résultat attendu

L'application démarre sur le port 5000, comme indiqué dans le README.

Résultat obtenu

exec ./docker-entrypoint.sh: no such file or directory  
Le conteneur s'arrête (exited with code 255) : l'application est inaccessible.

Preuve (fichier, requête / réponse)

Message affiché dans PowerShell :  
quickorder-1 \| exec ./docker-entrypoint.sh: no such file or directory  
quickorder-1 exited with code 255  
Vérification : git ls-files --eol docker-entrypoint.sh affichait w/crlf avant correction.

Sévérité

☐ Critique   ☒ Majeure   ☐ Mineure   ☐ Cosmétique

Priorité

☒ Haute   ☐ Moyenne   ☐ Basse

Fréquence de reproduction

☒ Systématique   ☐ Intermittent

Contournement éventuel

git config core.autocrlf false  
Remove-Item docker-entrypoint.sh puis git checkout -- docker-entrypoint.sh  
docker compose down -v puis docker compose up --build  
Correction proposée : ajouter un fichier .gitattributes forçant les fins de ligne LF sur les scripts .sh
