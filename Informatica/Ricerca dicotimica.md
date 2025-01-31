La **ricerca dicotomica**, detta anche **ricerca binaria**, è un algoritmo efficiente per trovare un elemento in una lista **ordinata**. Si basa sul principio del “dividi et impera”: a ogni passo, dimezza la porzione di lista da analizzare.

## Come funziona

1. Si prende l’elemento centrale della lista.

2. Se è l’elemento cercato, la ricerca termina.

3. Se l’elemento cercato è **minore**, si continua la ricerca nella metà sinistra.

4. Se è **maggiore**, si prosegue nella metà destra.

5. Si ripete il processo fino a trovare l’elemento o a esaurire la lista.

### Esempio


Cerchiamo il numero **7** in questa lista ordinata:

**[1, 3, 5, 7, 9, 11, 13]**

• **Primo passo**: il centro è **7**

Se cercassimo **9**, divideremmo la lista e continueremmo nella metà destra.

**Complessità computazionale**

• **Caso peggiore**: → molto più efficiente della ricerca lineare .

• **Condizione essenziale**: l’array deve essere **ordinato**.
