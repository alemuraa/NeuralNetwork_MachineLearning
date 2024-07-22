# Reti Neurali in Matlab - Assegnamento

## Descrizione dell'Assegnamento

L'assegnamento consiste in tre compiti:

- **Compito 1:** Reti neurali in Matlab
- **Compito 2:** Reti multi-strato feedforward (percettroni multi-strato)
- **Compito 3:** Autoencoder

### Compito 1: Reti neurali in Matlab

Il primo compito richiede di seguire un tutorial per utilizzare le reti neurali in Matlab. A tal fine, è necessario installare e utilizzare il Deep Learning Toolbox, eseguibile con il comando `nftool`, che apre l'interfaccia del toolbox.

Per risolvere un problema input-output, è necessario caricare un set di dati. Il toolbox fornisce alcuni esempi presi dall'UCI Machine Learning Repository. In questo esempio, viene utilizzato il set di dati sul grasso corporeo. I campioni vengono quindi suddivisi in tre sottoinsiemi:

- Sottoinsieme di addestramento (70% del set totale)
- Sottoinsieme di validazione (15% del set totale)
- Sottoinsieme di test (15% del set totale)

Il set di validazione è utile per verificare che la rete stia generalizzando e per interrompere l'addestramento prima dell'overfitting. Con l'overfitting, la rete è ben addestrata a riconoscere ciò che ha già visto, ma può avere difficoltà a riconoscere dati che non ha mai visto.

Il toolbox addestra quindi una rete neurale ed esamina i risultati, consentendo di tracciare la regressione, le prestazioni, lo stato dell'addestramento e l'istogramma degli errori.

### Compito 2: Reti multi-strato feedforward

Il secondo compito richiede di seguire un tutorial per risolvere un problema di riconoscimento di pattern utilizzando una rete feedforward a due strati. In particolare, lo strato nascosto ha una funzione di trasferimento sigmoide, mentre lo strato di output ha una funzione di trasferimento softmax.

Anche in questo caso, il set di dati è suddiviso in tre sottoinsiemi (con le stesse percentuali del primo compito: 70%, 15%, 15%). Per questo compito, sono stati utilizzati due set di dati di esempio: il set del vetro e il set dell'iris.

Dopo aver selezionato il set, nel toolbox (eseguibile con il comando `nprtool`) è possibile selezionare il numero di neuroni nascosti, ovvero il numero di neuroni dello strato nascosto (il valore predefinito è 10).

Definito il numero di neuroni nascosti, il toolbox crea e addestra una rete neurale con il set di input fornito. Dopo l'esecuzione della rete neurale, il toolbox è in grado di tracciare le matrici di confusione e le curve ROC (Receiving Operating Characteristic).

### Compito 3: Autoencoder

Il terzo compito richiede di implementare un autoencoder in Matlab. Il set di dati utilizzato è il set MNIST, composto da 60.000 cifre scritte a mano (da 0 a 9) memorizzate in immagini in scala di grigi di 28x28 pixel.

Dal set MNIST, è necessario estrarre solo due classi (ovvero cifre) alla volta e fornirle come un unico set di input all'autoencoder. Poiché il set è piuttosto grande, dai due set di classi viene estratto casualmente un numero fisso di osservazioni (il valore predefinito è 250 per ciascun set di classi), per velocizzare l'esecuzione.

Le due classi selezionate non sono casuali. Per questo compito, al fine di evidenziare le prestazioni dell'autoencoder, alcune coppie di cifre sono facilmente distinguibili, mentre altre possono essere molto più difficili. Le coppie di classi sono:
- Classe 1 e Classe 6
- Classe 3 e Classe 8
- Classe 1 e Classe 7
- Classe 5 e Classe 6

  
Un autoencoder può essere inizializzato e addestrato in Matlab utilizzando le funzioni `trainAutoencoder()` e `encode()`. `trainAutoencoder()` richiede come input il set di dati e il numero di nodi nascosti. Per questa simulazione, al fine di ottenere dati visualizzabili, il numero di nodi nascosti è stato impostato a 2. Si noti che il Deep Learning Toolbox utilizza una notazione diversa rispetto al corso di Machine Learning I, quindi è necessario trasporre tutti i dati prima di procedere. La funzione restituisce una variabile autoencoder.

`encode()` viene quindi utilizzato per codificare i dati, in modo che siano pronti per essere tracciati. `encode()` richiede due input: l'autoencoder e il set di dati. Restituisce i dati codificati.

Infine, il programma traccia l'output dei due neuroni nascosti, uno per asse. I dati vengono tracciati utilizzando la funzione `plotcl()`, fornita nel corso di Machine Learning I. La funzione traccia i dati utilizzando forme e colori diversi, che corrispondono alla classe a cui appartiene l'osservazione.

Se i due set di forme e colori diversi sono distanti tra loro, significa che l'autoencoder ha imparato bene. Altrimenti, se i due set sono mescolati, significa che il processo di apprendimento è stato più confuso e le due classi non sono distinguibili.

