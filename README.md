# ansible-ws-garr-2019

Questo repository contiene ricette Ansible utili al conseguimento del Corso per i Service Provider tenuto al Workshop GARR 2019 il 7 Ottobre 2019

## Requisiti

Installare Ansible sulla propria macchina virtuale:

1. Accedere alla propria VM con l'username e la password dati:
   * `ssh debian@sp-<NUM>.aai-test.garr.it`

2. Installare i pacchetti necessari all'esecuzione delle ricette Ansible:
   * `sudo apt-get install --yes vim git python3-dev python3-pip python3-setuptools build-essential bash-completion --no-install-recommends`

4. Abilitare il completamento dei comandi nella Bash shell:
   * `sudo printf "\nif [ -f /etc/bash_completion ]; then\n . /etc/bash_completion\nfi" >> /etc/profile`
   
5. Installare Ansible su Python 3:
   * `sudo pip3 install --upgrade pip setuptools ansible`
   
6. Scaricare il repository GIT delle ricette:
   * `sudo git clone https://github.com/ConsortiumGARR/ansible-ws-garr-2019.git /opt/ansible-ws-garr-2019`

## Configurare Ansible

1. Sostituire i valori compresi nelle parentesi angolari `<`,`>` nel file `/opt/ansible-ws-garr-2019/inventories/mediawiki_01/host_vars/localhost.yml`

2. Aggiungere/Rimuovere il commento agli steps come segue nel file `/opt/ansible-ws-garr-2019/mediawiki_01.yml`:
   * `A_step_01`,`A_step_02`,`A_step_03`,`A_step_04` (per allinearsi sulla primo modulo del corso)

3. Modificare `/opt/ansible-ws-garr-2019/site.yml` per abilitare/disabilitare i moduli verso cui allinearsi.

4. Eseguire `cd /opt/ansible-ws-garr-2019 ; ansible-playbook site.yml -i /opt/ansible-ws-garr-2019/inventories/ws_garr_19/wsgarr19.ini` per eseguire le ricette e configurare la propria macchina.
