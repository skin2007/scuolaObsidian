

La **ricorsione** consiste nell'invocare un metodo all'interno dello stesso metodo. Il metodo che ne fa uso si chiama metodo ricorsivo, quando viene chiamato, Java si comporta come se fosse un metodo come gli altri, quindi sospenderà l'esecuzione del metodo invocante per eseguire il metodo invocato fino alla fine, per poi riprendere l'esecuzione del metodo invocante dal punto in cui era stato sospeso. Nello stack si crea quindi una pila di record di attivazione che si allunga e si accorcia fino a estinguersi.

- **pro:** la ricorsione permette di suddividere il problema iniziale in sotto problemi più semplici, a volte semplificando la scrittura del codice.
- **contro:** un algoritmo ricorsivo, se gestito male potrebbe riempire la memoria di record di attivazione causando malfunzionamenti alla macchina.

Ogni metodo ricorsivo **deve rispettare queste regole:**
- deve avere un caso base, una condizione che se verificata, restituisce un valore invece di ricorrere ad una chiamata ricorsiva.
- deve avvenire su un caso semplificato, poiché l’obiettivo è analizzare un problema sempre più semplice, arrivando prima o poi al caso base

---
## Esercizi

### 1. Determinare in modo ricorsivo il massimo in un array di interi dato
```java
public static int findMax(int[] v, int p) {
    if (p == v.length - 1) {
        return v[p]; // Caso base: restituisci l'ultimo elemento
    }

    int maxRest = findMax(v, p + 1); // Trova il massimo nel resto dell'array

    if (v[p] > maxRest) {
        return v[p]; // Se l'elemento corrente è maggiore, restituiscilo
    } else {
        return maxRest; // Altrimenti, restituisci il massimo trovato nel resto
    }
}
```
### 2. Realizzare la somma degli elementi di un array di interi in modo ricorsivo
```java
public static int somma(int[] v, int p) {
    if (p == v.length) {
        return 0;
    }
    return v[p] + somma(v, p + 1);
}
```
### 3. Trovare la somma dei numeri dispari contenuti nell'intervallo 0..$N$
```java
public static int sommaDispari(int N) {
    // Caso base: se N è 0, la somma è 0
    if (N == 0) {
        return 0;
    }
    // Se N è negativo, passa al numero successivo (N + 1)
    if (N < 0) {
        return sommaDispari(N + 1);
    }
    // Se N è dispari, aggiungilo alla somma dei numeri dispari fino a N-1
    if (N % 2 == 1) {
        return N + sommaDispari(N - 1);
    }
    // Se N è pari, passa a N-1 senza aggiungere nulla
    else {
        return sommaDispari(N - 1);
    }
}
```

### 4. Dire quante volte un numero è divisibile per un altro (resto = 0)
```java
public static int contaDivisioni(int numero, int divisore) {
    if (numero < divisore) {
        return 0;
    }
    return 1 + contaDivisioni(numero / divisore, divisore);
}
```

### 5. Converti un numero binario in forma decimale

### 6. Converti un numero decimale in binario

### 7. Scrivere una funzione ricorsiva che calcola, dati due numeri interi $M$ ed $N$, la potenza $M^N$

### 8. Si risolva ricorsivamente il seguente problema: data una frase verificare se è palindroma

### 9. Scrivere una stringa all’incontrario

### 10. Scrivi una funzione che inverte un numero naturale