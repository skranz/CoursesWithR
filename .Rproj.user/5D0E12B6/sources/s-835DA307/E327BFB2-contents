---
title: "Fragen Stellen"
output:
  html_document:
    highlighter: null
    toc: TRUE
    toc_float: TRUE
    theme: "cosmo"
    code_download: TRUE
---

# Fragen stellen

Bevor Sie eine Frage per Email oder Moodle stellen, schauen Sie sich ihr Problem mit den im Kurs erklärten Hilfen nicht lösen lässt (z. B. schonma im Forum besprochen wurde).

Wenn Sie eine Frage stellen, sollten Sie folgende Punkte beachten, damit Ihnen schnell geholfen werden kann:

- Verwenden Sie einen klaren Titel für ihre Frage, damit sofort klar wird um was es geht.
    - **Überlegung:** Formulieren Sie ihren Titel so, wie wenn Sie eine kurze, klare und prägnante Frage an den CEO von Daimler richten. Je prägnanter und klarer ihre Überschrift, desto höher die Wahrscheinlichkeit, dass Sie schnell eine Antwort bekommen.
- Im Text erläutern Sie kurz und präzise, welches Problem Sie haben und wie es reproduziert werden kann (kurzer Beispielcode).
- Welches Resultat haben Sie erwartet und was sehen Sie anstatt dessen?
- Welche R Version (`version` in R eintippen) benutzen Sie?

Wenn Sie Fragen haben, warum ein bestimmter Fehler auftritt, dann ist es _nicht_ hilfreich nur den Fehler zu nennen.
Sie sollten in diesem Fall ein sogenanntes Minimalbeispiel erstellen, welches von ihren Kommilitonen oder dem Dozenten direkt in R kopiert werden kann und den von Ihnen entdeckten Fehler erzeugt.
Warum sollten Sie dies tun?

1. Dadurch machen Sie sich selbst klar wo genau der Fehler liegt
2. Dadurch stellen Sie sicher, dass Sie schnell eine Antwort bekommen

# Beispiele für geschickte und ungeschickte Fragestellungen im Forum

## Ungeschickter Forumsbeitrag

**Überschift im Forum:** Fehlermeldung

**Im Textfeld dann folgende Frage:**

Ich bekommen folgende Fehlermeldung:

Error in rename(`iris[1:10, ]`, petal_length = Petal.Length) : 
   unbenutztes Argument (petal_length = Petal.Length)
   
Können Sie mir bitte weiterhelfen!

$\Rightarrow$ Bei dieser Frage werden Sie sehr viele Gegenfragen bekommen und der Antwortprozess wird sich lange ziehen.

## Geschickter Forumsbeitrag

**Verbesserte Überschrift im Forum (gleiches Problem wie im vorherigen Beispiel):**
dplyr 0.3.0.2 rename() idiom unstable when reshape package is loaded

Vorteil an dieser Überschrift: Es wird direkt ersichtlich auf was sich die Frage bezieht (dplyr und daraus das reshape Paket)

**Im Textfeld dann folgende Frage:**

Ich erhalte eine Fehlermeldung für das Paket "reshape" zusammen mit dplyr, woran könnte dies liegen? Anbei ein Minimalbeispiel:

```{r, error=TRUE, warning=FALSE, message=FALSE}
library(tidyverse)
version # Dadurch weiß jeder welche R-Version verwendet wurde
#sessionInfo() # Alternative zu version

#Wenn Sie einen Fall haben, wo das Problem noch nicht auftritt, diesen zuerst nennen:
packageVersion("dplyr") # welche Paketversion von dplyr wird verwendet
iris[1:10,] %>% rename(petal_length = Petal.Length) 
library(reshape) # Dieses Paket müssen Sie nicht herunterladen, es dient hier nur als Demonstration
iris[1:10,] %>% rename(petal_length = Petal.Length)
```

$\Rightarrow$ Bei dieser Frage ist für jeden Nutzer nachvollziehbaren was ihr Problem ist und was Sie bereits unternommen haben um diesem Problem zu begegnen. Sie werden auf diese Frage schnell eine zielführende Antwort erhalten.

Diese Frage wurde aus Stackoverflow übernommen. Sie finden die Frage [hier](https://stackoverflow.com/questions/26371279/dplyr-0-3-0-2-rename-idiom-unstable-when-reshape-package-is-loaded). Der Verfasser hat innerhalb von 10 Minuten eine Antwort auf die Frage erhalten.
Bitte lesen Sie sich hierzu die Hinweise von Stackoverflow durch, wie Sie ein [Minimalbeispiel](https://stackoverflow.com/help/mcve) erstellen können.
Wenn Sie Probleme haben einen bestimmten Datensatz einzulesen, welcher zur Bearbeitung des Projekts nötig ist, dann können Sie natürlich ihr Minimalbeispiel auch um diesen Datensatz aufbauen.


