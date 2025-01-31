
## Definizione

L'efficienza di un algoritmo è determinata dal numero di operazioni elementari compiute in funzione della dimensione dell'input, ossia del numero di dati da elaborare. Per misurare correttamente l'efficienza, è fondamentale che questa valutazione sia indipendente dal calcolatore su cui l'algoritmo viene eseguito, altrimenti si rischierebbe di misurare l'efficienza della macchina anziché quella dell'algoritmo.

La funzione F(n), che calcola il numero di operazioni eseguite, è detta complessità computazionale. Di particolare interesse è il comportamento di F(n) al crescere di n, ovvero il suo ordine di infinito.

![[Pasted image 20250128103434.png]]
  

### O grande (O)

Indica un limite massimo alla crescita del tempo di esecuzione di un algoritmo. Ad esempio, se un algoritmo è O(n²), significa che il tempo impiegato aumenta al massimo come il quadrato della dimensione dell’input (n) quando n diventa molto grande. Lascia aperta la possibilità di trovare algoritmi più veloci.

### Omega (Ω)

Indica un limite minimo alla crescita del tempo di esecuzione di un algoritmo. Se un algoritmo è Ω(n log n), vuol dire che impiega almeno quel tempo per valori grandi di n. È utile, ad esempio, per sapere che non si può fare meglio di un certo livello, come nel caso degli algoritmi complessi (es. crittografia).

### Theta (Θ)

Fornisce sia un limite massimo che minimo. Se un algoritmo è Θ(f(n)), il tempo di esecuzione cresce esattamente come f(n), con una costante moltiplicativa, per n grandi. Questo dà una stima precisa della complessità e permette di confrontare meglio le prestazioni di due algoritmi. Se due algoritmi hanno la stessa complessità Θ, si comportano in modo molto simile.

---
## Funzioni di riferimento

![[Pasted image 20250128104324.png]]

---
## Problemi

### 1. Problemi della classe P

I problemi della classe **P** sono quelli che possono essere risolti in un tempo ragionevole, cioè in tempo polinomiale, usando un algoritmo deterministico. Questo significa che, anche se il problema diventa più grande, il tempo necessario per risolverlo non cresce in modo esagerato, rendendolo affrontabile per un computer.

Un esempio semplice è cercare un elemento in un elenco: con la ricerca sequenziale ci vogliono al massimo passaggi, dove è la lunghezza dell’elenco.

Altri esempi includono ordinare un elenco con algoritmi come QuickSort o trovare il percorso più breve in una rete usando l’algoritmo di Dijkstra.

### 2. Problemi della classe NP

I problemi della classe **NP** sono più difficili. Non sappiamo come risolverli in modo efficiente, ma possiamo verificare velocemente se una soluzione proposta è corretta.

Un esempio famoso è il **problema** **del** **commesso** **viaggiatore**: dato un insieme di città e le distanze tra di esse, trovare il percorso più breve che tocca tutte le città una sola volta. Trovarlo è complicato, ma se qualcuno ci mostra un percorso, possiamo verificarne la lunghezza velocemente.

Altri esempi includono problemi come la **colorazione** **dei** **grafi**, il **problema** **dello** **zaino** o la **soddisfacibilità** **booleana** **(SAT)**, che sono fondamentali in campi come l’ottimizzazione e la crittografia.

### 3. Problemi non risolvibili

Non tutti i problemi possono essere risolti con un algoritmo. Alcuni sono **indecidibili**, cioè non esiste un metodo automatico per risolverli in ogni caso.

Un esempio famoso è il **problema** **dell’arresto**: dato un programma e un input, possiamo sapere se il programma terminerà o andrà in loop per sempre? La risposta è no, non possiamo saperlo in generale. Questo problema è legato a limiti fondamentali della matematica e dell’informatica.

Questa idea è importante perché ci fa capire che non tutto ciò che possiamo immaginare è calcolabile.”

---
## Congettura di Goldbach

La **congettura** **di** **Goldbach** è una delle più antiche e affascinanti congetture della matematica. Dice che ogni numero pari maggiore o uguale a 4 può essere scritto come somma di due numeri primi.

Non è stata ancora dimostrata, ma possiamo provare a verificarla per numeri sempre più grandi. Se fosse falsa, troveremmo un controesempio (un numero pari che non si può scrivere come somma di due numeri primi) e il nostro algoritmo si fermerebbe. Se invece è vera, il programma continuerebbe a cercare all’infinito senza mai fermarsi.