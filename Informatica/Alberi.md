
## Definizione

Un **albero** è una delle strutture dati fondamentali in informatica, utilizzata per organizzare e gestire informazioni in modo gerarchico. Immaginiamolo come un diagramma a forma di albero rovesciato, con un punto di partenza chiaro chiamato **radice**. La radice è il nodo principale, da cui parte tutta la struttura.

Ogni elemento dell’albero, chiamato **nodo**, può essere collegato ad altri nodi tramite dei **rami**, formando così un sistema di relazioni tra **genitori** e **figli**. In un albero, ogni nodo può avere uno o più figli, ma al massimo un solo genitore, tranne la radice, che non ha genitori. Questo crea una gerarchia ordinata e ben definita.

Ci sono anche nodi particolari chiamati **foglie**: sono quei nodi che non hanno figli. Sono, per così dire, i "punti finali" della struttura.

Un albero si caratterizza per alcune proprietà importanti:

- **Ordine**: indica il massimo numero di figli che un nodo può avere.
- **Cardinalità**: è il numero totale di nodi nell’albero.
- **Altezza**: rappresenta la lunghezza del percorso più lungo dalla radice a una foglia.

Il termine **foresta** serve per indicare un insieme di alberi.

Pensiamo a come organizziamo i file in un computer: ci sono le cartelle principali, che contengono sottocartelle o file. Questo è un esempio perfetto di albero.

In sostanza, un albero non è solo una struttura dati, ma un modo di pensare a come organizzare le informazioni in modo efficiente, logico e intuitivo.


![[Pasted image 20250128093747.png]]

**ORDINE: 3
CARDINALITA': 12
ALTEZZA: 3

---
## Operazione con alberi binari

In una **lista** **concatenata**, per cercare un elemento bisogna attraversare i nodi uno alla volta, seguendo i puntatori. Questo significa che la ricerca ha una complessità di **O(n)**, proprio come per un **array** **non** **ordinato**.

Tuttavia, a differenza degli array, non è possibile usare una **[[Ricerca dicotimica]]**  (o ricerca binaria) su una lista concatenata. Questo perché non possiamo accedere direttamente a un elemento specifico, ma dobbiamo sempre partire dall'inizio della lista e seguire i collegamenti.

Gli **alberi** **binari** **di** **ricerca** (**BST**, Binary Search Tree) risolvono questo problema. In un BST:

- La ricerca, l’inserimento e la cancellazione richiedono tempi di **O(log n)**, grazie alla loro struttura gerarchica.
- Inoltre, i BST sono **già ordinati**, quindi possiamo scorrere i valori in ordine in un tempo **O(n)**, che è il massimo risultato possibile per questo tipo di operazione.

In breve, un BST combina l’efficienza nella ricerca e modifica con la possibilità di mantenere i dati ordinati.

### Ricerca
![[Pasted image 20250128102109.png]]
### Visita
![[Pasted image 20250128102121.png]]

---
## Realizzazione in memoria

### Realizzazione di un albero con vettore dei padri

Si supponga che i nodi dell’ albero T siano numerati da 0 a n-1. La più semplice realizzazione utilizza un vettore contenente per ogni nodo i, il cursore al padre.

Con questa realizzazione è facile visitare i nodi lungo percorsi che vadano dal basso verso l’alto, cioè dalle foglie verso la radice. Infatti padre(i, T) ha complessità O(1). Viceversa è costoso passare da un nodo ai suoi figli, individuare il livello di un nodo e inserire e cancellare sottoalberi: nel caso peggiore devo cercare in tutto l’albero: complessità O(n).
![[Pasted image 20250128102706.png]]
  

### Realizzazione di un albero con liste dei figli

In questa rappresentazione dell'albero, ogni nodo ha un vettore che punta a una lista contenente tutti i suoi figli. Questo approccio ha il vantaggio di rendere molto facile e veloce scorrere i figli di un nodo e capire l'ordine tra i fratelli. Tuttavia, presenta anche dei limiti: per trovare il **padre** di un nodo o il **fratello** **successivo**, dobbiamo scorrere tutte le liste dei figli, il che, nel caso peggiore, richiede di esaminare tutti i nodi dell'albero. In altre parole, queste operazioni hanno una complessità di **O(n)**. Pertanto, sebbene sia efficiente per navigare verso il basso nell'albero (dai padri ai figli), diventa meno pratico per operazioni che richiedono di risalire verso l'alto o muoversi tra i fratelli.
![[Pasted image 20250128102756.png]]
  
### Realizzazione di un albero padre/primofiglio/fratello

La rappresentazione di un albero utilizzando liste dei figli presenta delle difficoltà quando si tratta di eseguire operazioni come **PADRE**, **SUCCFRATELLO** o **INSOTTOALBERO**. Per migliorare l'efficienza di queste operazioni, si può modificare la struttura di ogni nodo aggiungendo tre informazioni **chiave**:

- Un campo che punta al **padre** del nodo.
- Un campo che punta al **primo figlio** del nodo.
- Un campo che punta al **fratello successivo** del nodo.

Con questa struttura, ogni nodo avrà tre puntatori: uno che collega il nodo al padre, uno che collega il nodo al suo primo figlio, e uno che collega il nodo al suo fratello successivo. Questo approccio semplifica le operazioni di ricerca del padre, del fratello succesu sivo e la gestione dei sottoalberi, rendendo l'albero più efficiente nelle operazioni.

![[Pasted image 20250128102821.png]]
