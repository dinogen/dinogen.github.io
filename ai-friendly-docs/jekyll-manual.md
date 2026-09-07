# Manuale del sito Jekyll

Questo repository contiene il sito personale pubblicato su
`https://dinogen.github.io/`.

## Come funziona

- `contents/` contiene gli articoli canonici.
- `_config.yml` configura Jekyll e la collection `contents`.
- `_layouts/` contiene la struttura HTML delle pagine.
- `assets/css/style.css` contiene lo stile del sito.
- `index.md` è la home page e genera automaticamente l'elenco degli articoli.
- `.github/workflows/pages.yml` costruisce e pubblica il sito.

Jekyll richiede Ruby. Non è però necessario installare Ruby sul computer per
pubblicare: GitHub Actions esegue la build su un runner Linux ogni volta che
fai push sul branch `main`.

## Primo setup su GitHub

1. Crea su GitHub un repository chiamato esattamente `dinogen.github.io`.
2. Dal terminale, nella cartella del progetto, controlla o aggiungi il remote:

   ```powershell
   git remote -v
   git remote add origin https://github.com/dinogen/dinogen.github.io.git
   ```

   Esegui `git remote add` solo se `origin` non esiste già.

3. Salva e pubblica il lavoro:

   ```powershell
   git add .
   git commit -m "Set up Jekyll site"
   git branch -M main
   git push -u origin main
   ```

4. Su GitHub apri **Settings > Pages** e imposta **Source** su **GitHub
   Actions**.
5. Apri la scheda **Actions** e attendi il completamento di **Deploy Jekyll
   site to Pages**.
6. Visita `https://dinogen.github.io/`.

Se il repository appartiene a un account diverso da `dinogen`, sostituisci
`dinogen` nell'URL del remote. Il repository deve comunque avere il nome
`dinogen.github.io` per usare quell'indirizzo come GitHub User Site.

## Scrivere un articolo

Ogni file in `contents/` deve iniziare con il front matter YAML:

```yaml
---
title: "Titolo dell'articolo"
date: 2026-09-07
status: draft
topics:
  - software engineering
format: article
---
```

Esempio di nome file: `contents/il-problema-non-era-il-codice.md`.
L'articolo sarà pubblicato all'indirizzo
`/articles/il-problema-non-era-il-codice/`.

Quando un articolo è pronto, aggiorna `status` a `published`, controlla il
testo e fai push:

```powershell
git add contents/il-problema-non-era-il-codice.md
git commit -m "Publish article about legacy code"
git push
```

## Preview locale

Python e Node.js sono utili per altri strumenti, ma non eseguono Jekyll.
Hai tre possibilità:

- usare direttamente GitHub Actions e controllare il sito dopo il deploy;
- installare Ruby con RubyInstaller for Windows e poi eseguire:

  ```powershell
  bundle install
  bundle exec jekyll serve
  ```

  Il sito sarà disponibile su `http://localhost:4000`;
- usare un container Docker con Ruby/Jekyll, se Docker è già installato.

Per il tuo caso consiglio inizialmente la prima opzione: evita di aggiungere
strumenti locali finché il contenuto è ancora in fase di prova.

## Se il deploy fallisce

1. Apri **Actions** su GitHub e seleziona la run fallita.
2. Leggi il primo errore nel job **build**.
3. Controlla soprattutto front matter YAML, nomi dei file e indentazione.
4. Correggi, fai un nuovo commit e ripeti il push.

I file sotto `generated/`, `ideas/`, `images/` e `scripts/` non vengono
pubblicati come pagine del sito: sono spazi di lavoro per il progetto
editoriale.