# Guida introduttiva alla creazione di una React-App su Termux

Questo progetto è stato avviato con [Create React App](https://github.com/facebook/create-react-app).

## Installazione di React-Js su Termux

Aggiorna tutti i pacchetti e le dipendenze installati sul sistema con questo comando.

```
apt update && apt upgrade
```

Ora installeremo node-js con questo comando

```
pkg install nodejs
```

Questo installerà sia node-js che npm.

Puoi testare l'installazione di nodejs controllando la versione di nodejs e npm con i seguenti comandi

```
node -v
```
Per controllare la versione npm, digitare

```
npm -v
```

Dopo aver installato correttamente node-js, esegui il comando seguente per installare react

```
npm i -g create-react-app
```

ora Creeremo un'app di reazione Nello ```storage```.

Per fare ciò digita il comando qui sotto e premi invio, assicurati di essere nello storage

```
npx create-react-app my-app
```

Ho chiamato questo progetto come `my-app`, puoi nominare il tuo progetto in qualsiasi cosa.

Inizierà a installare le dipendenze e creerà una nuova cartella "my-app" nello storage.

## Come cambiare porta LocalHost ReactJs
per cambiare la porta, recati nella cartella `my-app`

Modifica il file **package.json**

```json
{
  "name": "my-app",
  "version": "0.1.0",
  "private": true,
  "dependencies": {
    "@testing-library/jest-dom": "^5.16.5",
    "@testing-library/react": "^13.4.0",
    "@testing-library/user-event": "^13.5.0",
    "boostrap": "^2.0.0",
    "react": "^18.2.0",
    "react-dom": "^18.2.0",
    "react-scripts": "5.0.1",
    "web-vitals": "^2.1.4"
  },
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject"
  },
  "eslintConfig": {
    "extends": [
      "react-app",
      "react-app/jest"
    ]
  },
  "browserslist": {
    "production": [
      ">0.2%",
      "not dead",
      "not op_mini all"
    ],
    "development": [
      "last 1 chrome version",
      "last 1 firefox version",
      "last 1 safari version"
    ]
  }
}
```


Modifica la stringa

```json
"start": "react-scripts start",
```


All'inizio inserisci `PORT=2000`

```json
"scripts": {
  "start": "PORT=2000 react-scripts start",
  "build": "react-scripts build",
  "test": "react-scripts test --env=jsdom",
  "eject": "react-scripts eject"
}
```

la porta può essere cambiata in qualsiasi numero tipo `5000` o `4000` etc

## Script disponibili

Nella directory del progetto `my-app`, puoi eseguire:

### `npm start`

Esegue l'app in modalità sviluppo.\
Apri [http://localhost:3000](http://localhost:3000) per visualizzarlo nel tuo browser.

Appena eseguirai `npm start` Termux potrebbe già proporti di aprire un browser


La pagina si ricaricherà quando apporti modifiche.\
Potresti anche vedere eventuali errori di lanugine nella console.
### `npm test`

Avvia il test runner nella modalità orologio interattivo.\
Per ulteriori informazioni, vedere la sezione sui [test di esecuzione](https://facebook.github.io/create-react-app/docs/running-tests).


### `npm run build`

Crea l'app per la produzione nella cartella `build`.\
 Raggruppa correttamente React in modalità produzione e ottimizza la build per le migliori prestazioni.

 La build viene minimizzata e i nomi dei file includono gli hash.\
 La tua app è pronta per essere distribuita!


Vedi la sezione su [deployment](https://facebook.github.io/create-react-app/docs/deployment) per maggiori informazioni.

### `npm run eject`

**Nota: questa è un'operazione a senso unico.  Una volta "espulso", non puoi tornare indietro!**

 Se non sei soddisfatto dello strumento di compilazione e delle scelte di configurazione, puoi 'espellere' in qualsiasi momento.  Questo comando rimuoverà la singola dipendenza di build dal tuo progetto.

 Invece, copierà tutti i file di configurazione e le dipendenze transitive (webpack, Babel, ESLint, ecc.) direttamente nel tuo progetto in modo da avere il pieno controllo su di essi.  Tutti i comandi tranne "espelli" continueranno a funzionare, ma punteranno agli script copiati in modo da poterli modificare.  A questo punto sei da solo.

 Non devi mai usare `eject`.  Il set di funzionalità curato è adatto per distribuzioni di piccole e medie dimensioni e non dovresti sentirti obbligato a utilizzare questa funzionalità.  Tuttavia, comprendiamo che questo strumento non sarebbe utile se non potessi personalizzarlo quando sei pronto per questo.

## Boostrap Deprecato
> **Warning** : **a tutti gli sviluppatori che utilizzano boostrap all'interno di ReactJs, Questo pacchetto è stato Deprecato a causa di vulnerabilità con npm, il pacchetto è stato ritirato.**

**package.json**

```json
{
  "name": "boostrap",
  "version": "2.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "repository": {
    "type": "git",
    "url": "git+https://github.com/npm/deprecate-holder.git"
  },
  "author": "",
  "license": "ISC",
  "bugs": {
    "url": "https://github.com/npm/deprecate-holder/issues"
  },
  "homepage": "https://github.com/npm/deprecate-holder#readme",
  "dependencies": {}
}
```

Per impostare boostrap nell'app React-Js, installa il package React-Boostrap

```
npm install react-bootstrap bootstrap
```

poi importa react-boostrap all'interno di [App.js](src/App.js), inseriscilo nella prima riga di codice

```js
import 'bootstrap/dist/css/bootstrap.min.css';
```



