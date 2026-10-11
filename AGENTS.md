# Procedure di Deploy e Git (Risparmio Crediti Netlify)

1. **Modifiche e Push su Git (Default - 0 crediti Netlify):**
   - Tutte le modifiche ordinarie vanno salvate, committate e pushate su Git (`origin/main`) **senza** attivare il deploy su Netlify.
   - Ogni commit ordinario deve includere `[skip netlify]` nel messaggio (il git hook `.git/hooks/commit-msg` lo aggiunge automaticamente se non è presente `[deploy]` o `[netlify]`).
   - L'anteprima del sito viene verificata in locale aprendo `index.html`.

2. **Deploy su Netlify (Solo su richiesta esplicita dell'utente):**
   - Pubblica su Netlify **solo** quando l'utente lo chiede esplicitamente (es. *"pubblica su netlify"*, *"fai il deploy su netlify"*).
   - Per attivare la pubblicazione su Netlify, includi il tag `[deploy]` nel messaggio di commit (es. `git commit -m " descrizione [deploy]"` oppure, se le modifiche sono già state committate con `[skip netlify]`, esegui `git commit --allow-empty -m "Pubblica su Netlify [deploy]" && git push`).
