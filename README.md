SNMP Tweet - Gestione di Rete
============

SNMPTweet è un demone che permette di ricevere le trap SNMP, di elaborarle e di pubblicarle sul social network Twitter (http://www.twitter.com). Le trap SNMP, secondo quanto descritto all’interno dell’RFC 1157, rappresentano messaggi asincroni normalmente utilizzati per indicare eventi o errori che si sono manifestati e a cui è necessario prestare attenzione.

L’utente può configurare il proprio agent SNMP per inviare le trap al calcolatore dove è in esecuzione SNMPTweet, il quale elaborerà la coda delle trap ricevute le invierà come Tweet su Twitter, secondo le modalità decise dall’utente nel file di configurazione.

![Diagramma](https://raw.githubusercontent.com/cortinico/gr-snmptweet/master/doc/diagram.png)

## Documentazione

Per comprendere il progetto si puo' leggere la seguente documentazione
* [PDF Relation (in italian)](../../raw/master/doc/tex/document.pdf)
* [JavaDoc Documentation](http://cortinico.github.io/gr-snmptweet/)

## Eseguire il software

Per eseguire il software eseguire i comandi seguenti

```bash
git clone git@github.com:cortico/gr-snmptweet.git
cd gr-snmptweet/
ant jar
java -jar SNMPTweet.jar
```

## File di configurazione

Mediante il file **snmptweet.conf** è possibile impostare i parametri di configurazione del software, ad esempio:

* ```LOG_FILE```: Permette di impostare la posizione del file di log
* ```MIB_DIR```: Permette di impostare la posizione della cartella dei MIBs
* ```PORT```: Permette di impostare la porta in ascolto delle trap
* ```PRIVATE```: Permette di impostare la modalità privata
* ```USER1``` e ```IP1```: Permette di impostare utenti e indirizzi IP a cui inviare i tweet/messaggi privati

Per altre informazioni consultare la relazione finale.

Se viene settato il file di log, verranno registrate tutte le operazioni all'interno del file scelto.

## Librerie esterne

Per realizzare il software sono state utilizzate le seguenti librerie:

* [Java SNMP](http://gicl.cs.drexel.edu/people/sevy/snmp/) - Un'implementazione del protocollo SNMP
* [Twitter4J](http://twitter4j.org/) - Un'implementazione delle API di Twitter
* [Mibble](http://mibble.org/) - Un'implementazione di un semplice parser per i MIBs
* [Log4J](http://logging.apache.org/log4j/) - Strumenti per la gestione del file di log

