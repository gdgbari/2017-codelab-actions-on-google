# Actions on Google codelab

## Prerequisiti
Aver installato ```nodejs``` e ```Firebase Cli``` sul PC.

### NodeJs
#### Windows/Mac OS
Scarica e installa nodejs dalla [pagina di download](https://nodejs.org/en/download/).
#### Linux
A seconda della distribuzione sono disponibili diversi modi per installare node. Una lista dei comandi utili per farlo è [disponibile qui](https://nodejs.org/en/download/package-manager/).

### Firebase-Cli
 1. Apri una shell e digita:
```
npm install -g firebase-tools
```
 2. Effettua il login su Firebase:
```
firebase login
```

## Scarica il progetto
Puoi clonare il progetto con ```git clone git@github.com:gdgbari/2017_codelab_actions_on_google.git``` o scaricare lo [.zip da qui](https://github.com/gdgbari/2017_codelab_actions_on_google/archive/master.zip).

## Importa il progetto su Dialogflow
 * Apri la [Console Action on Google](https://console.actions.google.com/) e aggiungi un nuovo progetto con il nome che vuoi.
 * Fai click sul pulsante **ADD ACTIONS** e scegli **BUILD** sulla scheda **Dialogflow**.
 * Fai click su *Save* e seleziona l'icona con la rotellina delle impostazioni.
 * Seleziona *Export and Import*, poi *Restore from zip*, caricando lo zip che troverai nella cartella del tuo progetto scaricata da GitHub.

## Configura Firebase Functions
 * Apri una shell nella cartella del progetto appena scaricato e digita:
```
firebase init functions
```
Alla richiesta *File functions/package.json already exists. Overwrite?*, rispondi **N.**

* Effettua il Deploy su Firebase:
``` firebase deploy --only functions ```￼

Riceverai come risposta l'endpoint del webhook appositamente configurato su Firebase (esempio: ```    Function URL (factsAboutGoogle): https://${REGION}-${PROJECT}.cloudfunctions.net/factsAboutGoogle```).
* Riapri il progetto su Dialogflow e nella scheda *Fulfillment* sulla sinistra attiva il *Webhook*, inserendo l'url ottenuto prima.

* Seleziona *Integrations* dal menu laterale e apri le Impostazioni per *Actions on Google*.
* Aggiungi i seguenti Intent:
```chose_fact```
```chose_cats```

