
## Differenza tra eccezioni ed errore

### Errore

- **Definizione**: Un errore è un problema che si verifica durante l'esecuzione di un programma e che, nella maggior parte dei casi, non può essere gestito direttamente dal programma stesso.
- **Cause**: Gli errori sono spesso causati da problemi gravi, come mancanza di memoria, crash del sistema, o problemi hardware.
- **Esempi**: 
  - `OutOfMemoryError`: si verifica quando la JVM (Java Virtual Machine) non ha più memoria disponibile.
  - `StackOverflowError`: si verifica quando la memoria dello stack è esaurita, tipicamente a causa di una ricorsione infinita.
- **Gestione**: Gli errori sono considerati **irrecuperabili** e non dovrebbero essere catturati o gestiti dal programma. Sono problemi che richiedono un intervento esterno (ad esempio, riavviare l'applicazione o il sistema).

### Eccezione

- **Definizione**: Un'eccezione è un evento anomalo che si verifica durante l'esecuzione di un programma, ma che può essere gestito dal programma stesso per evitare che il programma si interrompa bruscamente.
- **Cause**: Le eccezioni sono causate da situazioni impreviste ma gestibili, come input non validi, file non trovati, o divisioni per zero.
- **Esempi**:
  - `NullPointerException`: si verifica quando si tenta di accedere a un oggetto nullo.
  - `ArithmeticException`: si verifica quando si tenta di dividere un numero per zero.
  - `FileNotFoundException`: si verifica quando si tenta di aprire un file che non esiste.
- **Gestione**: Le eccezioni sono **recuperabili** e possono essere gestite utilizzando meccanismi come `try-catch` per evitare che il programma si interrompa.

---
## Gestione delle eccezioni in java

Java fornisce un meccanismo strutturato per la gestione delle eccezioni, che consente di separare la logica del programma dalla gestione degli errori. Questo meccanismo si basa su tre componenti principali: **try**, **catch** e **finally**.

### 1. Costrutto Try-Catch
Il costrutto `try-catch` permette di monitorare una porzione di codice e gestire eventuali eccezioni che si verificano al suo interno.

```java
try {
    // Codice che potrebbe generare un'eccezione
    int risultato = 10 / 0; // Questo genererà un'eccezione ArithmeticException
} catch (ArithmeticException e) {
    // Gestione dell'eccezione
    System.out.println("Errore: divisione per zero!");
}
```

- **Try**: Il blocco `try` contiene il codice che potrebbe generare un'eccezione.
- **Catch**: Il blocco `catch` cattura l'eccezione e permette di gestirla. È possibile avere più blocchi `catch` per gestire diversi tipi di eccezioni.

### 2. Clausola Finally
La clausola `finally` viene eseguita sempre, indipendentemente dal fatto che si sia verificata un'eccezione o meno. È utile per rilasciare risorse o chiudere file.

```java
try {
    // Codice che potrebbe generare un'eccezione
} catch (Exception e) {
    // Gestione dell'eccezione
} finally {
    // Codice eseguito sempre
    System.out.println("Esecuzione del blocco finally.");
}
```

### 3. Eccezioni Checked e Unchecked
- **Eccezioni Checked**: Sono eccezioni che il compilatore obbliga a gestire. Devono essere dichiarate con `throws` o gestite con `try-catch`. Esempi includono `IOException` e `SQLException`.
- **Eccezioni Unchecked**: Non è obbligatorio gestirle. Sono solitamente sottoclassi di `RuntimeException`. Esempi includono `NullPointerException` e `ArithmeticException`.

### 4. Comando Throw
Il comando `throw` permette di lanciare un'eccezione manualmente. Può essere usato all'interno di un metodo per segnalare situazioni anomale.

```java
public void preleva(int somma) throws IllegalParameterException {
    if (somma > saldo) {
        throw new IllegalParameterException("Saldo insufficiente");
    }
    // Altro codice
}
```

### 5. Gerarchia delle Eccezioni
In Java, le eccezioni sono organizzate in una gerarchia:
- **Error**: Indica problemi gravi, come mancanza di memoria. Non è recuperabile.
- **Exception**: Indica situazioni recuperabili, come errori di input o accesso a file inesistenti.

---
## Conclusione

La gestione delle eccezioni in Java è un meccanismo potente che consente di gestire situazioni impreviste durante l'esecuzione del programma. Utilizzando i costrutti `try-catch`, `finally` e il comando `throw`, è possibile creare programmi robusti e affidabili, in grado di gestire errori senza interrompere l'esecuzione.

- **Errore**: Problema grave e irrecuperabile (es. `OutOfMemoryError`).
- **Eccezione**: Situazione anomala ma gestibile (es. `NullPointerException`, `ArithmeticException`).

La gestione delle eccezioni permette di separare la logica del programma dalla gestione degli errori, rendendo il codice più leggibile e mantenibile.