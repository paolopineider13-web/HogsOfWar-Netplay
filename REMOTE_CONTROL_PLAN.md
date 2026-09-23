# Hogs of War Shared Campaign - Remote Control

Obiettivo:
permettere a più giocatori remoti di controllare a turno il Controller 1
dell'host durante la campagna single-player.

Architettura:

HOST
- esegue EmulatorJS
- carica il CHD
- riceve input remoti
- applica gli input sempre al Controller 1

CLIENT
- non esegue la campagna
- invia soltanto i comandi del controller
- può controllare solo quando è il giocatore attivo

SERVER
- mantiene la stanza
- mantiene active_controller
- inoltra gli eventi campaign-input all'host
- permette all'host di cambiare active_controller

Eventi previsti:

campaign-register-host
campaign-register-client
campaign-input
campaign-set-active-controller
campaign-active-controller
campaign-player-list
