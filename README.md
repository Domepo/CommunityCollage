# CommunityCollage

Ein Projekt, um alle Frames von allen Statisten aus "Schmeiß mein LEBEN auf den MÜLL - Fynn Kliemann" in eine Collage zupacken.
Das Projekt basiert auf folgenden Verfahren.
1. Video Runterladen
2. Video in Frames unterteilen (FFMPEG)
3. Fynns Frames löschen
4. Alle Frames in das nice tool von delimitry packen<br>
![alt text](https://github.com/Domepo/CommunityCollage/blob/master/UnsortiertCompressed.png)
## Installation
Vielen Dank an delimetry für das coole Tool❤️

```bash
https://github.com/delimitry/collage_maker
```
Python Libary
```bash
pip install pillow
```
Das bash Programm, um das Video in Frames zu splitten.
```bash
https://ffmpeg.org/
```

## Usage
Video in Frames splitten. Hier ein [Tutorial](https://www.youtube.com/watch?v=OyRXay93GVM)
```bash
ffmpeg -i output.mp4 frame%093.png
```
Python Script um eine Collage zu erstellen
```bash
collage_maker.py -f Inputfile\frames\ -o Outputfile\collage.png -w gesamtbreite -i bildhöhe
```

## Seitenverhältnissberchnungsgedöns
Wir haben insgesamt 2907 Frames.<br>
Ich habe einfach mal die Frame höhe auf 250 begrenzt. <br>
Jedes Frame hat durch das Musikvideo ein Seitenverhältnis von 16:9.<br>

```bash
(250/16)*9
= 140.625
```
1. Jetzt wissen wir, das jedes kleine Bild eine Auflösung von 140*250 hat.
2. Da wir auch als Output Format 16/9 haben wollen, rechnen wir mit einem Quadrat, da die kleinen Bilder das Endformat bestimmen.
```bash
sqrt(2907) #Quadratwurzel
= 53.916
```
Die Breite und Höhe werden aus 53 Bildern bestehen.
```bash
53.916 * 140.625 # Die Breite der kleinen Bilder
=7582            # Das tragen wir jetzt bei -w gesamtbreite ein.
```

```bash
collage_maker.py -f Inputfile\frames\ -o Outputfile\collage.png -w 7582 -i 250
```

Es gibt noch den Optionalen Operator : -s <br>
Mit dem kann die Bilder Zufällig anordnen.<br>
Hier die Bilder:<br>
[Sortiert](https://github.com/Domepo/CommunityCollage/blob/master/ColalgeSortitert.png)<br>
[Unsortiert](https://github.com/Domepo/CommunityCollage/blob/master/CollageUnsortiert.png)

