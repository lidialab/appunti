# Connessione SSH da client Windows a server Debian/Ubuntu tramite coppia di chiavi

## Predisponi il server remoto Debian

Nella destinazione installa ```openssh-server```
Nella tua home devono essere presenti la cartella ```.ssh``` e al suo interno il file ```authorized_keys```, se non sono presenti creali tu.

## Se usi il terminale di Windows con Powershell

Genera la coppia di chiavi in Windows tramite terminale Powershell:

```ssh-keygen```

Copia la chiave pubblica dal terminale di Windows alla tua home del pc remoto con:

```scp id_rsa.pub username@remote_ip:```

Nel server remoto accoda la chiave pubblica al file ```authorized_keys``` tramite:

```cat id_rsa.pub >> .ssh/authorized_keys```

NEl client Windows collegati tramite ssh da Powershell:

```ssh username@remote_ip```

## Se usi PuTTY

Puoi scaricare PuTTY da https://www.chiark.greenend.org.uk/~sgtatham/putty/

Genera la coppia di chiavi in Windows tramite PuTTYGen che viene fornito assieme a PuTTY.

Copia la chiave negli appunti di Windows.

Nel server remoto accoda la chiave al file ```authorized_keys``` su un'unica riga incollandolo tra gli apici di echo:

```
echo "ssh-rsa AAAABBBBBBBBBBBBBBBBCCCCCCCCCCCCCC...DDDDDDDDDDDDDDEEEEEEEEEEEEEEEEEEEEE" >> .ssh/authorized_keys
```
Predisponi la sessione in PuTTY:

- Inserisci il nome utente per l'auto login alla voce Connection > Data > Auto-login username 
- Imposta la chiave privata nella sessione di quella connessione alla voce Connection > SSH > Auth > Private key file for authentication
- Modifica a piacere le opzioni di visualizzazione della finestra (dimensione carattere, ...)
- Prova la sessione e se è tutto ok salvala

Quando devi connetterti al server carica la sessione e aprila