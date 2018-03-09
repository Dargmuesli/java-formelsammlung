# Java Formelsammlung
Erstellt im ersten Semester des Studiengangs Informatik WS17/18 an der Universität Kassel im Modul **Einführung in die Programmierung** von Marvin Junker und Jonas Thelemann.

```Java
static final int KONSTANTE = <Wert>;
```

## Arrays
```Java
int[] a;                                // Deklaration, [Arrays sind immer Zeiger!]
a = new int[5];                         // Initialisierung mit Standardwert 0
a = new int[] {0, 1, 2, 3, 4};          // Initialisierung mit definierten Werten
int[] a = new int[5];                   // Deklaration und Initialisierung
int[] a = {0, 1, 2, 3, 4};              // Deklaration und Initialisierung mit definierten Werten
a.length;                               // Anzahl von Feldern in a
```

## Mehrdimensionale Array
```Java
int[][] a;                              // Deklaration
a = new int [2][3];                     // Initialisierung
int[][] a = { {0, 1, 2}, {3, 4, 5} };   // Deklaration und Initialisierung mit Inhalt
a.length;                               // Hier: 2
a[0].length;                            // Hier: 3
```

## Zeichen
```Java
Character.isLetter(ch);         // Prüft, ob ch ein Unicode-Buchstabe ist
Character.isDigit(ch);          // Prüft, ob ch eine Ziffer ist
Character.isLetterOrDigit(ch);  // Prüft, ob ch ein Unicode-Buchstabe oder eine Ziffer ist
Character.toUpperCase(ch);      // wandelt ch in einen Großbuchstaben um (falls nötig)
Character.toLowerCase(ch);      // wandelt ch in einen Kleinbuchstaben um (falls nötig)
```

## Strings
```Java
String s = "Mettbroetchen";         // Deklaration und Initialisierung mit Wert [ACHTUNG: "String" groß schreiben!]
s.equals("Mettbroetchen");          // Prüft, ob s = „Mettbrötchen" ist
s.length();                         // Gibt die Länge des Strings zurück [ACHTUNG KLAMMER!]
ch = s.charAt(3);                   // Gibt das dritte Zeichen des Strings als Char zurück
i = s.indexOf("br");                // Gibt die Position von "br" oder -1 zurück
i = s.indexOf("br", 7);             // Gibt die Position von "br" ab Index 7 zurück
i = s.lastIndexOf("br");            // Gibt die letzte Position von "br" zurück, optional mit Startindex wie oben
s2 = s.substring(2);                // Gibt den Teilstring ab Position 2 zurück
s2 = s.substring(3, 6);             // Gibt den Teilstring von (inklusive) 2 bis (exklusive) 6 zurück
s.startsWith("Mett");               // Wahr, wenn s mit "Mett" beginnt
s.endsWith("Mett");                 // Wahr, wenn s mit "Mett" endet
int i = Integer.parseInt("123");    // Erzeugt int aus String
float f = Float.parseFloat("3.14"); // Erzeugt float aus String
String s = String.valueOf(x);       // Erzeugt aus x einen String
char[] ch = s.toCharArray();        // Erzeugt aus s einen Characterarray
```

## StringBuilder
```Java
StringBuilder b = new StringBuilder();  // Erzeugt ein Stringbuilder-Objekt (von einem String in den Klammern)
i = b.length();                         // Liefert die Länge des Strings [ACHTUNG KLAMMER!]
b.append(x);                            // Hängt x an b an. x kann char, int, long, float, double, boolean, String oder char[] sein
b.insert(pos, x);                       // Fügt x an Stelle pos in b ein (Typen wie oben)
b.delete(from, to);                     // Löscht in b von (inklusive) from bis (exklusive) to
b.replace(from, to, "Leberwurst");      // Ersetzt in b von (inklusive) from bis (exklusive) to durch "Leberwurst"
s = b.substring(from, to);              // Gibt den Teilstring von (inklusive) from bis (exklusive) to zurück
ch = b.charAt(pos);                     // Gibt den Character an Stelle pos zurück
```

## Objekte
```Java
Klassenname k = new Klassenname();      // Erzeugt mit Objekt k eine Instanz der Klasse "Klassenname"
Klassenname[] k = new Klassenname[5];   // Erzeugt ein Objektearray k[] vom Typ "Klassenname" mit 5 Einträgen
k[i] = new Klassenname();               // Definiert Objekt am Index i in Objektearray k
k.wert;                                 // Gibt den Wert von "wert" in k zurück
k.methode();                            // Ruft die Methode "methode" in k auf
// Erzeugen vom Klassen ohne Konstruktor: Zahlen = 0; Zeiger = null; Boolean = false;
// "static" gehöhrt zur Klasse und nicht zum Objekt. Ansprechen über Klassenname.methode();
// Nicht-static kann auf static zugreifen, aber nicht umgekehrt!
```

## Vererbung
```Java
super.methode();                // Ruft überschriebene Methode der Oberklasse auf
super();                        // Ruft Konstruktor der Oberklasse auf
Vater vadder = new Sohn();      // Jedes Objekt der Unterklasse ist auch ein Objekt der Oberklasse!
                                // Hier kann man nur auf die Felder von "Vater" zugreifen, die von "Sohn" existieren aber auch
vadder instanceof Sohn;         // Wahr, wenn das Objekt "Vater" eigentlich ein "Sohn"-Objekt ist
Sohn sohnemann = (Sohn) vadder; // Cast von Vater auf Sohn, sodass auf "Sohn"s Felder zugegriffen werden kann
```

## Pakete
```Java
package packageName;            // Steht am Anfang, über Klasse
import packageName.Klasse;      // Importiert "Klasse" aus dem Package "packageName"
packageName.Klasse              // Spezifiziert "Klasse" als Klasse des Pakets "packageName" im Code
public                          // Verfügbar für alle
protected                       // Verfügbar für das Paket
private                         // Verfügbar für die Klasse
                                // Einsetzbar für Klassen, Methoden, Felder und Konstruktoren
static                          // Verfügbarkeit ohne Instantiierung, Importieren mit `import static ...`
final                           // Wert kann nicht geändert werden

// Kompilieren mit javac packageName/Klasse.java
// Starten mit java packageName.Klasse
```

## Math-Funktionen
```Java
Math.random();                          // Zufallszahl als double zwischen 0 und 1
int z = (int) (Math.random() * 6) + 1;  // Zufallszahl als Integer zwischen 1 und 6
Math.pow(x, y);                         // Potenz als double (x^y)
Math.max(x, y);                         // Gibt den größeren Wert zurück
Math.min(x, y);                         // Gibt den kleineren Wert zurück
```

## Codebeispiele
```Java
class Program {
    // Globale Variablen und Konstanten

    public static void main(String[] args) {
        // Dieser Code wird bei Programstart ausgeführt
    }

    // Weitere Methoden
}
```
---
```Java
class Sohn extends Vater {  // Die Klasse Sohn erbt von Vater
    // Code
}
```
---
```Java
abstract class AbstrakteKlasse { // Muss abstrakt sein, wenn eine abstrakte Methode enthalten ist
    // Abstrakte Klassen können (im Gegensatz zu nicht abstrakte Unterklassen) nicht instanziiert werden
    // Der Typ darf dennoch die abstrakte Oberklasse sein: `AbstrakteKlasse a = new NichtAbstrakteUnterkls;`

    abstract void abstrakteMethode();
}
```
---
```Java
interface Interface { // Implementierung durch: `class Klasse implements Interface {}`
    // Alle Methoden sind abstrakt
}
```
---
```Java
try {
    // Code
} catch (Exeption e) {
    // Code
} catch (AnotherException e) {
    // Code
} finally {
    // Wird immer ausgeführt, gut um Streams zu schließen
}
```
---
```Java
import java.io.*;
import java.util.*;

class MyFile {
    public static void main(String[] args) throws FileNotFoundException {
        PrintWriter pw;
        Scanner scanner = new Scanner(System.in);
        String str;
        boolean exists = true;

        do {
            System.out.print("Bitte Dateinamen eingeben: ");
            str = scanner.nextLine();

            if (!(new File(str).exists())) {
                exists = false;
            }
        } while (exists);

        pw = new PrintWriter(str);
        pw.println("Datei erfolgreich angelegt");
        System.out.println("Habe soeben in die Datei geschrieben");
        pw.close();
    }
}
```
---
```Java
class InvalidTimeException extends Exception {
    InvalidTimeException(String msg) {
        super(msg);
    }

    public String toString() {
        return getMessage();
    }
}
```
---
```Java
import java.io.*;
import java.util.*;

class MyNewFile {

    public static void main(String[] args)  throws FileNotFoundException {
        File file;
        String filename;
        Scanner s = new Scanner(System.in);

        do {
            System.out.print("Bitte Dateiname eingeben: ");
            filename = s.nextLine();
        } while ((new File(filename)).exists());

        PrintWriter pw = new PrintWriter(filename);
        pw.println("Datei erfolgreich angelegt");
        System.out.println("Habe soeben in die Datei " + filename + " geschrieben");
        pw.close();
        s.close();
    }
}
```
---
```Java
import java.io.*;

class MyFile {
    public static void main(String[] args) throws FileNotFoundException {
        PrintWriter pw;

        try {
            pw = new PrintWriter(args[0]);
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Aufruf: Simpler Dateiname");
            return;
        }

        pw.println("Datei erfolgreich angelegt");
        System.out.println("Habe soeben in die Datei geschrieben");
        pw.close();
    }
}
```
---
```Java
static int fak(int n){
    if (n > 1){
        return(n * fak(n-1));
    } else {
        return 1;
    }
}
```
---
```Java
static int fibonacci(int n) {
    if (n == 1 || n == 2){
        return 1;
    } else {
        return (fibonacci(a-1) + fibonacci(a-2));
    }
}
```

## Weiteres

### Gleitpunktzahl-Grammatik
```
Ziffer = "0" | "1" | "2" | "3" | "4" | "5" | "6" | "6" | "7" | "8" | "9".
Zahl = Ziffer {Ziffer}.
Gleitkommazahl = Zahl "." Zahl ["E" ["+"|"-"] Zahl].
```

### Speicherverwaltung
- **Method Area**
  - Klassen (inkl. Bytecode der Methoden und Klassenvariablen)
- **Stack**
  - Lokale Variablen
  - Parameter von Methoden
  - Rücksprungadresse
  - Hilfsvariablen der JVM
- **Heap**
  - Arrays
  - Objekte (inkl. Attribute und Klassenverweise)
