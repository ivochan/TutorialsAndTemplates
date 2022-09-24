## TP Link Wireless USB



### Caratteristiche del dispositivo

Questo dispositivo consiste in una scheda wireless, provvista di adattatore USB e dal design compatto, progettata per collegare i dispositivi cablati al network wireless.

Inoltre, è conforme allo standard wireless 802.11 b/g/n e consente di raggiungere una velocità di trasmissione dati fino a 300 Mbps. 

Il modello della pennina, compatibile con sistemi Windows, MAC OS e Linux, è **TL-WN823N**.



### Configurazione del driver

Il driver che questo dispositivio dovrebbe utilizzare è 8192eu, presente già nel kernel Linux.

Tuttavia, se la pennina non viene comunque riconosciuta, il motivo potrebbe essere che quella presente nel sistema sia un'implementazione di questo driver purtroppo malfunzionante.

Allora sarà necessario disabilitarlo digitando, da terminale, il comando:

```bash
echo "blacklist rtl8xxxu" | sudo tee /etc/modprobe.d/blacklistrtl.conf
```



Ed applicare delle ottimizzazioni, che verranno eseguite, all'azione di montaggio del dispositivo, come delle opzioni di Network Manager e dello stesso driver.

Per quanto riguarda il software dedito alla gestione della scheda di rete occorrerà digitare:

```bash
echo -e "[device]\nwifi.scan-rand-mac-address=no" | sudo tee /etc/NetworkManager/conf.d/disable-random-mac.conf
```



Per specificare le opzioni del driver in questione, invece, si dovrà digitare il comando seguente:

```bash
echo "options 8192eu rtw_power_mgnt=0 rtw_enusbss=0" | sudo tee /etc/modprobe.d/8192eu.conf
```



A questo punto è necessario installare il driver adeguato, ovvero **8192eu**.

Su ArchLinux si procede clonando, quindi, il relativo repository e compilando il pacchetto:

```bash
git clone https://aur.archlinux.org/8192eu-dkms-git 8192eu
cd 8192eu
makepkg -si 
```

Oppure, se si utilizza un AUR-helper, si può scrivere come segue:

```bash
<nomeAURhelper> -S 8192eu-dkms-git
```



Infine, bisognerà riavviare il sistema.
