# Accesso federato per MediaWiki con Shibboleth Service Provider

Questo repository contiene il materiale didattico (vedi `slides`) e le ricette ansible per il corso **Accesso federato per MediaWiki con Shibboleth Service Provider** tenuto al Workshop GARR 2019, vedi https://learning.garr.it/course/view.php?id=87


## Requisiti

Installare Ansible sulla propria macchina virtuale:

1. Accedere alla propria VM con l'username e la password dati:
   * `ssh root@sp-<NUM>.aai-test.garr.it`

2. Installare i pacchetti necessari all'esecuzione delle ricette Ansible:
   * `sudo apt-get install --yes vim git python3-dev python3-pip python3-setuptools build-essential bash-completion --no-install-recommends`

3. Abilitare il completamento dei comandi nella Bash shell:
   * `sudo printf "\nif [ -f /etc/bash_completion ]; then\n . /etc/bash_completion\nfi" >> /etc/profile`
   
4. Installare Ansible su Python 3:
   * `sudo pip3 install --upgrade pip setuptools ansible`
   
5. Scaricare il repository GIT delle ricette:
   * `sudo git clone https://github.com/ConsortiumGARR/ansible-ws-garr-2019.git /opt/ansible-ws-garr-2019`

6. Importare il certificato della CA "[wsgarr-ca.crt](https://github.com/ConsortiumGARR/ansible-ws-garr-2019/blob/master/wsgarr-ca.crt)" tra i certificati delle Autorità permesse dal browser. Vedere i filmati di configurazione per [Google Chrome](https://github.com/ConsortiumGARR/ansible-ws-garr-2019/blob/master/Aggiungere-CA-a-Chrome.mp4) e [Mozilla FireFox](https://github.com/ConsortiumGARR/ansible-ws-garr-2019/blob/master/Aggiungere-CA-a-FireFox.mp4) (da scaricare sul PC)

## Allineamento ai Moduli del Corso

1. Sostituire i valori compresi nelle parentesi angolari `<`,`>` nel file `/opt/ansible-ws-garr-2019/inventories/mediawiki_01/host_vars/localhost.yml`

2. Aggiungere/Rimuovere il commento agli steps come segue nel file `/opt/ansible-ws-garr-2019/mediawiki_01.yml`:
   * `A_step_01`,`A_step_02`,`A_step_03`,`A_step_04` (per allinearsi sulla Modulo 1 del corso)

3. Aggiungere/Rimuovere il commento agli steps come segue nel file `/opt/ansible-ws-garr-2019/shibsp_03.yml`:
   * `C_step_03` (per allinearsi sulla Modulo 3 del corso)

4. Aggiungere/Rimuovere il commento agli steps come segue nel file `/opt/ansible-ws-garr-2019/federa_wiki_04.yml`:
   * `D_step_01`,`D_step_02`,`D_step_03` (per allinearsi sulla Modulo 4 del corso)

5. Eseguire `cd /opt/ansible-ws-garr-2019 ; ansible-playbook site.yml -i /opt/ansible-ws-garr-2019/inventories/ws_garr_19/wsgarr19.ini` per eseguire le ricette e configurare la propria macchina.


N.B.: E' possibile modificare `/opt/ansible-ws-garr-2019/site.yml` per decidere quali moduli abilitare/disabilitare per allinearsi.
