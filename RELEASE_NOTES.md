## YouTube Extractor v0.2.1

### Corrections de bugs & Securite

#### Securite
- Retrait du GitHub PAT du code source (integre via variable d'environnement a la compilation)
- Renforcement du CSP : suppression de `unsafe-eval`
- Limite de 10 Mo sur l'import CSV externe (protection DoS)
- Correction de la validation Ollama (`0.0.0.0` bloque)

#### Corrections
- **Liens sociaux du createur injectes dans les prompts IA** : l'IA utilise desormais les liens du createur associe au projet (pas seulement ceux extraits de la description video)
- **Extraction des liens YouTube** : les liens de chaine au format court (`youtube.com/ta-chaine`) sont maintenant reconnus
- **Extraction Rust des liens sociaux** : ajout de YouTube, Facebook et GitHub dans l'extraction backend
- **Encodage UTF-8** : correction de toutes les chaines corrompues (accents francais et emojis)
- **JSON.parse securise** : remplacement de tous les `JSON.parse` non proteges par `safeParse` avec fallback
- **Tests corriges** : 205/205 tests passent (10 tests etaient en echec avant)
- **React keys stabilisees** : plus de `key={index}` instable

#### Nettoyage
- Suppression du dead code (tooltip inutilise, structs DB orphelins)
- Remplacement de `println!` par les macros `log` (`info!`, `error!`, `debug!`)
- Styles inline convertis en classes Tailwind dans AppHeader
- Correction typage TypeScript (`any` → types corrects)

#### Installeur
- **Migration automatique** : l'ancien modele IA (Qwen3-1.7B) est supprime automatiquement avant l'installation du nouveau (Qwen3.5-4B)

#### Documentation
- ROADMAP, DEVELOPMENT, CONTRIBUTING, CHANGELOG mis a jour
- Cursor rules corrigees (CSP, compteur tests)

### Installation
1. Telecharger `YouTube.Extractor_0.2.1_x64-setup.exe`
2. Lancer l'installeur (le modele IA sera telecharge automatiquement ~2.5 Go)
3. L'acceleration GPU peut etre configuree depuis Parametres > Acceleration GPU

### Configuration requise
- Windows 10/11 (x64)
- 4 Go RAM minimum (8 Go recommande)
- ~2 Go d'espace disque
- Connexion internet pour le premier lancement

### Notes
- Le Smart Screen Windows peut s'afficher (application non signee) : cliquer "Plus d'infos" puis "Executer quand meme"
