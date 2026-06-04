# RaiPlay Sound Feed

Questo repository genera dei feed RSS per i programmi di RaiPlay Sound, e sono generati automaticamente tramite GitHub Actions e GitHub Pages. In modo da potersi abbonare/ascoltare su qualsiasi client podcast  e non esclusivamente tramite l’app RaiPlaySound. 

Questo progetto è una evoluzione di un mio [precedente repository](https://github.com/giuliomagnifico/raiplay-feed),  il quale aveva il problema di non risolvere correttamente la redirect ed era quindi necessario scaricare il file prima di riprodurlo certi podcast. Adesso gli URLs vengono risolti fino alla CDN finale Rai, evitando i problemi causati dai redirect `relinkerServlet.htm` con alcuni client podcast (i.e. [PocketCasts](https://pocketcasts.com/)).


> [!TIP]
> È una versione modificata del repository [frammenti/raiplaysoundrss](https://github.com/frammenti/raiplaysoundrss) costruita per poter funzionare usando solo su GitHub, in modo da essere indipendente da un server esterno. 


## Podcast

| Programma | Feed RSS |
|----------|----------|
| Almeno credo | https://alessandro-massarella.github.io/raiplaysound-feed/rss/programmi/almenocredo.xml |
| America7 | https://alessandro-massarella.github.io/raiplaysound-feed/rss/programmi/america7.xml |
| Artificialintelligence | https://alessandro-massarella.github.io/raiplaysound-feed/rss/programmi/artificialintelligence.xml |
| Battiti | https://alessandro-massarella.github.io/raiplaysound-feed/rss/programmi/battiti.xml |
| Città sonore | https://alessandro-massarella.github.io/raiplaysound-feed/rss/programmi/cittasonore.xml |
| Detectives - Casi risolti e irrisolti | https://alessandro-massarella.github.io/raiplaysound-feed/rss/programmi/detectives-casirisoltieirrisolti.xml |
| Eta Beta | https://alessandro-massarella.github.io/raiplaysound-feed/rss/programmi/etabeta.xml |
| GR Friuli Venezia Giulia | https://alessandro-massarella.github.io/raiplaysound-feed/rss/programmi/grfriuliveneziagiulia.xml |
| GR1 | https://alessandro-massarella.github.io/raiplaysound-feed/rss/programmi/gr1.xml |
| Hollywood Party | https://alessandro-massarella.github.io/raiplaysound-feed/rss/programmi/hollywoodparty.xml |
| Italia 90 - Il rock alternativo | https://alessandro-massarella.github.io/raiplaysound-feed/rss/programmi/italia90-ilrockalternativo.xml |
| L'edicola di Radio1 | https://alessandro-massarella.github.io/raiplaysound-feed/rss/programmi/ledicoladiradio1.xml |
| La Pennicanza | https://alessandro-massarella.github.io/raiplaysound-feed/rss/programmi/lapennicanza.xml |
| Lillo e Greg 610 | https://alessandro-massarella.github.io/raiplaysound-feed/rss/programmi/lilloegreg610.xml |
| Musical Box | https://alessandro-massarella.github.io/raiplaysound-feed/rss/programmi/musicalbox.xml |
| Prima Pagina | https://alessandro-massarella.github.io/raiplaysound-feed/rss/programmi/primapagina.xml |
| Radio anch'io | https://alessandro-massarella.github.io/raiplaysound-feed/rss/programmi/radioanchio.xml |
| Radio2 Social Club | https://alessandro-massarella.github.io/raiplaysound-feed/rss/programmi/radio2socialclub.xml |
| Radio3 Mondo | https://alessandro-massarella.github.io/raiplaysound-feed/rss/programmi/radio3mondo.xml |
| Radio3 Scienza | https://alessandro-massarella.github.io/raiplaysound-feed/rss/programmi/radio3scienza.xml |
| Revolution | https://alessandro-massarella.github.io/raiplaysound-feed/rss/programmi/revolution.xml |
| Setlist | https://alessandro-massarella.github.io/raiplaysound-feed/rss/programmi/setlist.xml |
| Stereonotte | https://alessandro-massarella.github.io/raiplaysound-feed/rss/programmi/stereonotte.xml |
| Tra poco in edicola | https://alessandro-massarella.github.io/raiplaysound-feed/rss/programmi/trapocoinedicola.xml |
| Tutta la città ne parla | https://alessandro-massarella.github.io/raiplaysound-feed/rss/programmi/tuttalacittaneparla.xml |
| Un giorno da pecora | https://alessandro-massarella.github.io/raiplaysound-feed/rss/programmi/ungiornodapecora.xml |
| Zapping | https://alessandro-massarella.github.io/raiplaysound-feed/rss/programmi/zapping.xml |

## Audiolibri

| Audiolibro | Feed RSS |
|------------|----------|
| Arancia meccanica | https://alessandro-massarella.github.io/raiplaysound-feed/rss/audiolibri/aranciameccanica.xml |

## Abbonarsi o aggiungere un feed

Per abbonarsi basta copiare l'URL del feed dalla tabella nel lettore podcast.

Per aggiungere programmi o audiolibri puoi forkare il repository e aggiungere manualmente i feed, oppure aprire una Pull Request modificando [static.ts](https://github.com/giuliomagnifico/raiplaysound-feed/blob/main/src/static.ts), esempio:

```ts
{
  title: 'Radio3 Scienza',
  path: 'programmi/radio3scienza'
}
```

oppure per un audiolibro:

```ts
{
  title: 'Arancia meccanica',
  path: 'audiolibri/aranciameccanica'
}
```

> [!NOTE]
> la tabella con i feeds o audiolibri nuovi si aggiorna  automaticamente con il nuovo feed (in ordine alfabetico) quando viene eseguita la Action, non aggiungere o modificare manualmente la tabella.

## Aggiornamento ogni ora

I feed vengono aggiornati automaticamente tramite GitHub Actions ogni ora e viene controllata la validità degli URL vecchi ogni 14 giorni.
