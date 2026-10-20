# FS Pilot Career · Bridge

Le **Bridge** est le petit programme Windows qui relie **Microsoft Flight Simulator 2020 et 2024** à
[**FS Pilot Career**](https://fspilotcareer.fr), la carrière de pilote de ligne gratuite pour MSFS.

Il lit le simulateur par SimConnect, l'interface officielle livrée avec MSFS : **pas besoin de FSUIPC**.
Chaque vol est enregistré automatiquement, du desserrage au serrage du frein de parc, puis envoyé à votre carrière :
note sur 100, carnet de vol, paie, réputation, suivi en direct.

> Ce dépôt sert uniquement à publier les versions du Bridge et à recevoir vos signalements. Le jeu lui-même se
> joue sur **https://fspilotcareer.fr**.

## Télécharger

**[⬇ Télécharger fspc-bridge.exe](https://fspilotcareer.fr/telecharger)**, toujours la dernière version.

Les fichiers sont aussi dans [Releases › bridge-latest](https://github.com/LamaXticot/FSPilotCareer-Bridge/releases/tag/bridge-latest) :

| Fichier | Pour qui |
|---|---|
| `fspc-bridge.exe` | Tout le monde : il s'ouvre dans votre navigateur, sans fenêtre de commande. |
| `fspc-bridge-console.exe` | Le même programme avec la console, pour les options en ligne de commande et le diagnostic. |

Configuration requise : Windows 10 ou 11 (64 bits), MSFS 2020 ou 2024, et un compte gratuit sur
[fspilotcareer.fr](https://fspilotcareer.fr).

## Installer et lancer

1. **Créez votre compte** sur [fspilotcareer.fr](https://fspilotcareer.fr), si ce n'est pas déjà fait.
2. **Lancez `fspc-bridge.exe`**, sur le PC où tourne MSFS. Aucune installation n'est nécessaire.
   - Si Windows affiche « Windows a protégé votre ordinateur » ou « Éditeur inconnu » : cliquez sur
     *Informations complémentaires*, puis *Exécuter quand même*. Le programme n'est pas encore signé.
3. **Sa page s'ouvre dans votre navigateur** (http://127.0.0.1:47800, visible seulement sur votre PC).
   Connectez-vous avec le **même e-mail et mot de passe** que sur fspilotcareer.fr. Le compte est retenu sur ce PC.
4. **Lancez MSFS**. Le Bridge s'y connecte tout seul, et sa page affiche « MSFS connecté ».
5. **Volez** :
   - au parking, moteurs en marche, **desserrez le frein de parc** : le vol commence (cale-départ) ;
   - décollez, volez, posez-vous ;
   - au parking d'arrivée, **serrez le frein de parc** ou coupez les moteurs : le vol est noté et apparaît dans
     votre carnet.

Pour vérifier que tout est relié, utilisez le bouton **Tester la connexion**, dans l'application › Réglages ›
Connexion au simulateur.

## La page du Bridge

Elle se met à jour chaque seconde et montre :

- **le compte et MSFS** : connecté, en attente du simulateur, connexion perdue ;
- **la position** : avant le départ, le Bridge compare l'aéroport où se trouve votre avion dans MSFS à la position
  de votre pilote dans la carrière, et vous prévient s'ils diffèrent ;
- **le vol en cours** : numéro, départ, arrivée, phase, altitude, vitesse, vario ;
- **le journal**, avec les boutons *Changer de compte* et *Quitter le Bridge*.

Fermer l'onglet n'arrête pas le Bridge : relancer `fspc-bridge.exe` rouvre simplement sa page. Pour l'arrêter,
cliquez sur **Quitter le Bridge**. Le journal est aussi écrit dans `%APPDATA%\FSPC Bridge\bridge.log`.

## Mettre à jour

L'application vous prévient quand une nouvelle version est disponible, avec un bandeau « Nouvelle version du
Bridge ». Pour l'installer :

1. cliquez sur **Quitter le Bridge** dans sa page ;
2. téléchargez la nouvelle version avec le même lien ;
3. lancez-la à la place de l'ancienne.

Votre compte reste retenu.

## Options (version console)

À lancer dans un terminal ouvert dans le dossier du fichier :

| Commande | Effet |
|---|---|
| `fspc-bridge-console.exe --replay demo --speed 40` | Rejoue un vol de démonstration Paris → Barcelone, sans simulateur. Il apparaît ensuite dans votre carnet. |
| `fspc-bridge-console.exe --record` | Enregistre aussi les données brutes du vol, pour un diagnostic. |
| `fspc-bridge-console.exe --remote 192.168.1.20:500` | MSFS tourne sur un autre PC (SimConnect en réseau). |
| `fspc-bridge-console.exe --dry` | N'envoie rien (test hors ligne). |
| `fspc-bridge-console.exe --logout` | Oublie le compte enregistré sur ce PC. |
| `--no-open` / `--no-ui` | Ne pas ouvrir le navigateur / pas de page du tout (console seule). |

## Problèmes fréquents

- **La page ne s'ouvre pas** : tapez http://127.0.0.1:47800 dans votre navigateur.
- **« MSFS en attente » alors que le simulateur tourne** : attendez d'être dans un vol (pas dans le menu
  principal), puis patientez quelques secondes. Le Bridge réessaie toutes les 5 secondes.
- **« Bridge non détecté » dans l'application** : vérifiez que la page du Bridge affiche votre compte, puis
  cliquez sur *Tester la connexion* dans l'application. Un pare-feu d'entreprise peut bloquer la connexion.
- **Le vol ne compte pas pour la compagnie** : il est sans doute parti d'un autre aéroport que la position de
  votre pilote. Le Bridge et l'application le signalent avant le départ.

## Signaler un problème ou proposer une idée

- Depuis l'application : page **Contact** (bug, amélioration ou autre message).
- Ou ici : onglet [Issues](https://github.com/LamaXticot/FSPilotCareer-Bridge/issues). Joignez si possible le
  fichier `%APPDATA%\FSPC Bridge\bridge.log`.
- Par e-mail : contact@fspilotcareer.fr

---

FS Pilot Career est un projet indépendant, sans affiliation avec Microsoft, Asobo Studio ni les compagnies
aériennes citées. Microsoft Flight Simulator est une marque de Microsoft Corporation.
