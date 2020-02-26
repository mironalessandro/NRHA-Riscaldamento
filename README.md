Riscaldamento
=============

Gestione del riscaldamento Tramite presenza e DarkSky

### About


Project Dependencies
Each project has its own package.json file that includes a list of node modules the project depends on. The Node-RED editor tracks what nodes you are using in a flow and helps you to keep that list of dependencies up to date.

Requirements
##Variabili input_boolean: finestreaperte - Optional (se non viene gestita eliminare dal flow "Finestre o porte aperte ?" e "Finestre Aperte su OFF")

esempio: input_boolean:finestreaperte

group: famiglia - deve contenere lo stato di tutti i device da considerare

esempio: group.famiglia

input_number

gradi_minimo: temperatura minima quando nessuno è presente in casa. gradi_notte: temperatura durante la notte (Da impostare prima la variabile in arancione con gli orari preferiti) gradi_ok: temperatura comfort gradi_per_temp_min: temperatura impostata quando si raggiunge il minimo.

(Se si vuol gestire le finestre o le porte aperte creare la variabile booleana come da indicazioni che va su on quando una finestra o porta è aperta per un tot di tempo). Ho anche il flow per quello che metterò online presto.

##Componenti

DarkSky con almeno il modulo sensor.meteo_darksky_temperature configurato. Maggiori info: https://www.home-assistant.io/integrations/darksky/

#Istruzioni

Questo flow tiene conto della presenza del group.famiglia e di un terzo esterno chiamato in questo caso "Nonna". Dovete modificare i climate.set_temperature con il nome della vostra entity id.(in questo flow climate.primo_piano e climate.piano_terra). Vengono gestiti 2 termostati Il controllo viene fatto ogni ora o ad ogni cambiamento dei tracker. Inoltre viene fatto un controllo su una temperatura del bagno cosi sotto una certa soglia si può accendere il riscaldamento. Dobbiamo avere un device per leggere la temperatura.