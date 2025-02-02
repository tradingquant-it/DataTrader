# DataTrader per il Trading Algoritmico Avanzato

DataTrader è una piattaforma open-source di backtesting basato sugli eventi da utilizzare nei mercati azionari. La maggior parte delle strategie descritte nel sito TradingQuant.it (https://www.tradingquant.it) utilizza DataTrader come framework per il backtest.

Il software viene fornito con una licenza open source "MIT" (vedere di seguito).

# Installazione

DataTrader può essere installato su una distribuzione Python completa come Anaconda (https://www.anaconda.com/distribution) o in un ambiente virtuale di Python 3. Consigliamo l'uso di Anaconda poiché semplifica notevolmente il processo di installazione.

DataTrader funziona meglio in un sistema basato su Linux (ad esempio MacOS o Ubuntu) poiché è prevalentemente uno strumento con interfaccia a riga di comando (CLI). Può essere installato anche su Windows, ma richiede [Git] (https://git-scm.com/) per installare la versione richiesta.

## Creazione di un ambiente virtuale Python 3 su Ubuntu

Questa sezione è per coloro che hanno dimestichezza con la riga di comando di Linux, gli ambienti virtuali Python e lo strumento ```virtualenv```. Se non hai esperienza con questi strumenti, il modo migliore per installare DataTrader è tramite una distribuzione Anaconda disponibile gratuitamente (vedi sopra). Se hai un'installazione funzionante di Anaconda, salta questa sezione.

La prima attività è creare una nuova directory per memorizzare un ambiente virtuale. Abbiamo utilizzato ```~/venv/datatrader``` in questa sezione. Se desideri modificare questa directory, rinominala nei seguenti passaggi.

Innanzitutto crea la nuova directory:

```
mkdir -p ~/venv/datatrader
```

Quindi utilizziamo lo strumento ```virtualenv``` per creare un nuovo ambiente virtuale Python in questa directory:

```
virtualenv --no-site-packages -p python3 ~/venv/datatrader
```

Quindi possiamo attivare l'ambiente virtule tramite il seguente comando:

```
source ~/venv/datatrader/bin/activate
```

## Installare Git

DataTrader non è ancora parte di un pacchetto repository di Python. Non può essere installato direttamente tramite il classico approccio ```pip```. Invece può essere installato direttamente da questo repository Git.

Per fare ciò è necessario installare Git sul tuo sistema. Le istruzioni di installazione di Git per vari sistemi operativi possono essere trovate nella [documentazione Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

Per esempio, installando Git su un sistema Linux Ubuntu può essere raggiunto con i seguenti comandi:

```sudo apt-get install git-core```

## Installare DataTrader

Ora che è stato installato un ambiente Python dedicato (Anaconda o un ambiente virtuale) insieme al sistema di controllo della versione Git, è possibile installare DataTrader usando ```pip```.

A questo punto è necessario utilizzare pip per installare DataTrader come una libreria e quindi installare manualmente i pacchetti obbligatori.

I passaggi seguenti richiederanno un po' di tempo (5-10 minuti) poiché DataTrader si basa su NumPy, SciPy, Pandas, Matplotlib e molte altre librerie e quindi dovranno essere tutti compilati:

```
pip install git+https://github.com/tradingquant-it/datatrader.git
```

Se hai installato DataTrader in un nuovo ambiente virtuale (al contrario di Anaconda), dovrai installare il solito set di librerie scientifiche di Python.

L'installazione di queste librerie può essere saltata se hai già un'installazione funzionante di Anaconda poiché fornisce versioni aggiornate delle librerie scientifiche di Python.

Le librerie possono essere installate tramite pip:

```
pip install numpy
pip install scipy
pip install matplotlib
pip install pandas
pip install seaborn
```


Indipendentemente dal tuo ambiente di installazione (Anaconda o virtualenv) dovrai installare le seguenti librerie extra:

```
pip install click
pip install pyyaml
pip install munch
pip install enum34
pip install multipledispatch
```

Per verificare che DataTrader sia stato installato correttamente, apri un terminale Python e importa DataTrader tramite il seguente comando:

```
>>> import datatrader
```

Se non sono presenti messaggi di errore, la libreria è stata installata correttamente.

In caso di problemi con le istruzioni di cui sopra, contattaci all'indirizzo [support@tradingquant.it] (mailto: support@tradingquant.it).


# Esempi


Ora che la libreria stessa e i pacchetti necessari sono stati installati, bisogna creare le directory predefinite per i dati utilizzati nei backtest e per l'output delle simulazioni.

Ad esempio è possibile scaricare i dati necessari e il codice di esempio per eseguire un semplice backtest di una strategia Buy And Hold sull'indice dell'S&P500.

Per prima cosa si creano le specifiche directory:

```
mkdir -p ~/datatrader/examples ~/data ~/out
```

Quindi scaricare qualche esempio dei dati dello SPY:

```
cd ~/data
wget https://raw.githubusercontent.com/tradingquant-it/datatrader/master/data/SPY.csv
```

Quindi scarica lo script di esempio del backtest Buy And Hold:

```
cd ~/datatrader/examples
wget https://raw.githubusercontent.com/tradingquant-it/datatrader/master/examples/buy_and_hold_backtest.py 
```

Infine, possiamo eseguire lo stesso backtest:

```
python buy_and_hold_backtest.py
```

Una volta completato, vedrai un completo "tearsheet" dei risultati, tra cui:

* curva Equity
* curva Drawdown
* heatmap dei rendimenti mensili
* distribuzione dei rendimenti annualizzati
* statistiche a livello di Portfolio
* statistiche a livello di Trade

Il tearsheet si presenta simile al seguente:

![alt tag](https://tradingquant.it/wp-content/uploads/datatrader-buy-and-hold-tearsheet-001.png)

Si può esplorare il file ```buy_and_hold_backtest.py``` per esaminare l'API di DataTrader. Vedrai che è relativamente semplice impostare una strategia semplice ed eseguirla.

In caso di domande sull'installazione o sull'utilizzo degli esempi, non esitare a inviare un'e-mail [support@tradingquant.it](mailto:support@tradingquant.it).

# Termini di Utilizzo

Copyright (c) 2017-2025 TradingQuant.it,

Con la presente viene concessa l'autorizzazione, a titolo gratuito, a chiunque ottenga una copia di questo software e dei file di documentazione associati (il "Software"), di trattare il Software senza restrizioni, inclusi, senza limitazione, i diritti di utilizzo, copia, modifica, unione , pubblicare, distribuire, concedere in licenza e / o vendere copie del Software e consentire alle persone a cui il Software è fornito di farlo, alle seguenti condizioni:

L'avviso di copyright di cui sopra e questo avviso di autorizzazione devono essere inclusi in tutte le copie o parti sostanziali del Software.

IL SOFTWARE VIENE FORNITO "COSÌ COM'È", SENZA GARANZIA DI ALCUN TIPO, ESPLICITA O IMPLICITA, INCLUSE, MA NON SOLO, LE GARANZIE DI COMMERCIABILITÀ, IDONEITÀ PER UNO SCOPO PARTICOLARE E NON VIOLAZIONE. IN NESSUN CASO GLI AUTORI OI TITOLARI DEL COPYRIGHT SARANNO RESPONSABILI PER QUALSIASI RIVENDICAZIONE, DANNO O ALTRA RESPONSABILITÀ, SIA IN UN'AZIONE DI CONTRATTO, TORTO O ALTRIMENTI, DERIVANTE DAL, O IN CONNESSIONE CON IL SOFTWARE O L'USO O ALTRI TRATTAMENTI NEL SOFTWARE.

# Trading Disclaimer

Il trading di azioni a margine comporta un alto livello di rischio e potrebbe non essere adatto a tutti gli investitori. I rendimenti passati non sono indicativi di risultati futuri. L'alto grado di leva finanziaria può funzionare sia contro di te che per te. Prima di decidere di investire in azioni, è necessario considerare attentamente i propri obiettivi di investimento, il livello di esperienza e la propensione al rischio. Esiste la possibilità che tu possa sostenere una perdita di parte o tutto il tuo investimento iniziale e quindi non dovresti investire denaro che non puoi permetterti di perdere. Dovresti essere consapevole di tutti i rischi associati al trading di azioni e chiedere consiglio a un consulente finanziario indipendente in caso di dubbi.
