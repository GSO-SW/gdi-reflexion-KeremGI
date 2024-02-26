[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/OwH8KTXH)
# GDI+
Eine Sammlung von Tipps und Tricks zum Thema Grafikprogrammierung mit GDI+.

## Klassen / Ereignisse
### Timer
Ein Timer führt in regelmäßigen Abständen ein `Tick`-Event aus. Der [`System.Windows.Forms`.`Timer`](https://learn.microsoft.com/de-de/dotnet/api/system.windows.forms.timer?view=windowsdesktop-8.0&viewFallbackFrom=net-6.0) kann über die Toolbox auf die GUI gezogen werden. 

Anschließend können wir 
- die Zeit zwischen jedem `Tick`-Event einstellen (`+ Interval { get; set; }: int`) und
- den Timer starten (`+ Start():void`) oder
- stoppen (`+ Stop():void`) oder
- den Zustand abfragen. (`+ Enabled{ get; set; }: bool`) (Standard ist ausgeschaltet: `enabled = false`)



## Tipps und Tricks
Ergänzen Sie hier die notwendigen Code-Ausschnitte, um zu zeigen, wie man es macht. 
- Sie können [CodeBlöcke mit Syntax-Highlighting](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/creating-and-highlighting-code-blocks#syntax-highlighting) einsetzen
- Wird es zu unübersichtlich? Sie können auch Unterordner mit Beispiel-Code anlegen und auf die entsprechenden Dateien verlinken. [Inspiration](https://github.com/gsoTH/flaskShowcase/tree/master/datenbanken).
- Die folgende Liste kann gerne ergänzt werden :)
- 
## Objekte mit Tasten steuern
- Die Bewegung wird in ein eigenen Event codiert. 
- Aufbau eines Events ist ganz simple
```
private void FrmFrogger_KeyDown(object sender, KeyEventArgs e)
{
}
```  
- In diesem Ereignis wird beschrieben, was während des laufenden Programms mit der Tastatur passiert.
- In unserem Fall wie beim Frogger haben wir verhindert durch if abfragen das der Spieler nicht außerhalb des feldes laufen kann.
```
if(e.KeyCode == Keys.Down) 
{
    if ((spieler.Y - hoeheJeBereich) > -43 && (spieler.Y - hoeheJeBereich) < 252)
    {
        spieler.Y = spieler.Y + hoeheJeBereich;
    }
}
```

### Verhindern, dass ein Spieler aus dem Bild läuft
- In diesem Beispiel wird überprüft das der Spieler nicht außerhalb des Spielfeldes laufen kann bzw. oben und unten.
- Genau in diesem schema braucht man auch weitere für rechts, links und oben.

## (object sender, EventArgs e)
Das erste Argument, das das Objekt des Senders repräsentiert, ist wichtig, weil es dem Event-Handler ermöglicht, zu identifizieren, welches Steuerelement oder welche Komponente das Event ausgelöst hat. Das kann nützlich sein, um spezifische Aktionen basierend auf dem Ursprung des Events durchzuführen.

Das zweite Argument, das EventArgs-Objekt, wird verwendet, um zusätzliche Informationen über das Event zu übermitteln. In einigen Fällen kann dies null sein, wenn keine zusätzlichen Informationen benötigt werden. Aber oft gibt es spezialisierte EventArgs-Klassen, die spezifische Daten über das Event tragen.

## Bewegung animieren

- foreach (Hindernis aktuellesHindernis in alleHindernisse)
- {
    
-     aktuellesHindernis.Move();
- }
- In diesem Beispiel werden die Hindernise gespawnt und bewegen sich durch die Methode.
- In der Klasse Hindernis wird dann genau beschrieben wie und wann das Hindernis sich beweget.

- {
-     if ((spieler.Y - hoeheJeBereich) > -43 && (spieler.Y - hoeheJeBereich) < 252)
-     {
-         spieler.Y = spieler.Y + hoeheJeBereich;
-     }
- }
- Hier wird beschrieben wie der Spieler sich bewegen soll.
### Spiel pausieren

- if(e.KeyCode == Keys.Space)  <--- Tastendruck-Leertaste
- { 
-   if(tmrGameTick.Enabled == true ) <--- Spielzeit == wahrheit 
-   {
-       tmrGameTick.Enabled = false; <--- Spielzeit wird gestoppt 
-       return;
-   }
-   else 
-   {
-       tmrGameTick.Enabled = true;
-   }
       
- }

### Ihr schönstes Ergebnis

- Habe nichts besonderes....




