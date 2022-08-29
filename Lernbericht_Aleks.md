# Lern-Bericht
Aleksandar Veselinov

## Einleitung

In diesem Projekt/Auftrag, ging es darum mit einer Webapplikation Daten entgegenzunehmen, speichern und mittels den gleich Daten etwas aufrufen. In diesem Beispiel erstellte ich eine Webseite, bei der ein Nutzer ein Pokemon-Charakter erstellen kann, mittels einer Auswahl von Optionen. diese Optionen werden letztendlich im Backing weitergeleitet, gespeichert und wieder aufgerufen, um die Bilder des Charakters dazustellen. Zusätzlich musste noch beachtet werden, dass man immer von eine Seite zur anderen springt, wenn etwas mit dem Button geklickt wurde.

## Was habe ich gelernt?

Ich habe gelernt, wie man Datensätze von einer .xhtml weitergeben kann und in welcher Bean-Variable sie gespeichert werden soll.

## Beschreibung

Auf diesen Code-Ausschnitten kann man sehen, dass es beim xhtml um eine Radio-Button Auswahl geht. Wenn man beim Radio-Button die Augenfarbe auswählt, weiss das Programm automatisch, anhand '#{avatarBean.augenfarbe}', wo es beim Bean weitergegeben werden muss. Wenn die Augenfarbe selektiert wurde, dann wird ein Wert dem Bean 'Augenfarbe' und zu einem späteren Zeitpunkt wieder aufgerufen (Falls blau gewählt wurde, dann gibt es den Wert 'b' weiter). Diese Werte werden später wieder aufgerufen, wenn ein Bild vom Charakter erstellt werden soll --> d.h. wenn die Augenfarbe ausgewählt wurde, dann erscheint die gewünschte Augenfarbe auf der nächsten Seite. Wenn man zum Schluss auf dem Button klickt, dann wird man zur nächsten Seite springen. Im Video kann man es ab 0:13 bis 0:19 sehen.
```XHTML
<h:form>
            <h:graphicImage value="./9954_PokemonBilder/#{avatarBean.hautfarbe}.png"/> <br/>
            <h:outputText value="Wähle mittels RadioButton die Augenfarbe"/> <br/>
            <h:selectOneRadio value = "#{avatarBean.augenfarbe}"> 
                <f:selectItem itemLabel="blau" itemValue="b" />
                <f:selectItem itemLabel="grün" itemValue="g" />
            </h:selectOneRadio>  
            <h:commandButton action="page2.xhtml" value="Augenfarbe auswählen"/>
</h:form>
```
```Java
@Named(value = "avatarBean")
@SessionScoped
public class AvatarBean implements Serializable{
    private char hautfarbe;
    private char augenfarbe;
    private char haarfarbe;

    /**
     * Creates a new instance of AvatarBean
     */
    public AvatarBean() {
    }
    
    public char getHautfarbe() {
        return hautfarbe;
    }

    public void setHautfarbe(char hautfarbe) {
        this.hautfarbe = hautfarbe;
    }
    
    public char getAugenfarbe() {
        return augenfarbe;
    }

    public void setAugenfarbe(char augenfarbe) {
        this.augenfarbe = augenfarbe;
    }

    public char getHaarfarbe() {
        return haarfarbe;
    }

    public void setHaarfarbe(char haarfarbe) {
        this.haarfarbe = haarfarbe;
    }
    
}
```
https://youtu.be/SWzESN2U8a8 Link zum Youtube-Video

## Verifikation

Ich habe gelernt, wie man von Umfragen (bzw. RadioButtons und ScrolldownLists) gewünschte Datensätze an Beans weiterleiten kann.

# Reflektion zum Arbeitsprozess

Bei der Arbeit konnte ich mit den Codes zurecht kommen und wissen, welche Property beim XHTML-Tag benötigt wurde, um die Werte weiterzugeben. Daraus konnte ich sehr schnell und problemlos zum Ziel gelangen.

Grosse Probleme während dem Arbeiten gab es nicht. Es sei nur, dass ich herausfinden musste, wie man von RadioButtons, etc. die Daten weitergeben musste. Es war im Auftrag uns nur erklärt worden, wie man von einem commandLink-Bild die Daten weitergegeben werden sollten.

**VBV**: Als Verbesserung habe ich nichts hinzuzufügen, da ich bereits die Leistung bestmöglich erbracht habe. Nächstes Mal vielleicht beim Auftrag noch die zusätzlichen Weitergabe-Tags spezifizieren bei ScrollDown-Listen, etc. ;)
