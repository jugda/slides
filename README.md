# slides
## Info-Folien für Vorträge der JUG Darmstadt

- siehe http://jugda.github.io/slides/
- umgesetzt mit [Remark](https://github.com/gnab/remark/) (Demo: http://remarkjs.com/)
- man kann auf der ersten Folie die Checkbox anhaken für eine Slideshow
- auf der vorletzten Folie gibt es eine einfache Javascript-Verlosung
  - dazu die Teilnehmerliste in das Textarea kopieren
- für Änderungen einfach von Github klonen und einen Pull Request einreichen
  - um es lokal auszuführen, benötigt man einen simplen Webserver
  - z. B. ```ruby -run -ehttpd . -p8000```
  - siehe auch https://gist.github.com/willurd/5720255
- die Namen der Verlosung bekommt man über folgendes Groovy-Skript (xxx ersetzen durch URL mit Type = JSON)

```
def orgas = ['Falk', 'Gerd', 'Jan', 'Jörn', 'Marcel', 'Niko', 'Sebastian']
def registered = new groovy.json.JsonSlurper()
    .parse(new URL('xxx'), "UTF-8")
    .registrations
    .name

(registered - registered.intersect(orgas)).each {
    println it
}

null
```
