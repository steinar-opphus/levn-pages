# Levn Pages

Offentlig publiseringsrepo for ferdigbygget Quartz-output fra det private Levn-repoet.
Ingen private forskningsnotater, kildekopier eller kilde-repoets Git-historikk hører hjemme her.

`main:site/` inneholder ferdige filer; `.github/workflows/pages.yml` er separat
infrastruktur og skal bevares ved synkronisering. Pages-kilde: **GitHub Actions**.
Workflowen publiserer bare `site/`, ved push til main og manuell kjøring på main.
URL: https://steinar-opphus.github.io/levn-pages/.

En repoavgrenset deploy-nøkkel lar privat Actions oppdatere `site/`.
Nøkkelen heter «levn Actions publication» (ID 168393648).
Privatnøkkelen finnes bare som `LEVN_PAGES_DEPLOY_KEY` i privat repos Actions Secrets.
Tilbakekalling: slett deploy-nøkkelen under Settings → Deploy keys her og slett
secret i privat repo. Ikke legg hemmeligheter i innhold, logger eller issues.

Deploy-workflowen bruker bare contents:read, pages:write og id-token:write.
Generisk klargjøringsside inneholder ingen forskningsdata; senere bygg erstatter
hele `site/` uten å endre workflowen. PR-er publiserer ikke; ingen automatisk merge.
