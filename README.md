# SFO
Pure Data program for WFS spatialization. 

SFO

Copyright Baptiste Maffrand 2016

Ce programme est sous license GPLv3

------------------------------------------


LISEZ-MOI

(SOON IN ENGLISH)

------------------------------------------


Ce programme est composé d'un ensemble de patchs Pure Data. Le patch parent est le patch SFO_parent, c'est donc celui là qu'il faut ouvrir pour que cela fonctionne.

SFO utilise trois bibliothèques externes à Pure Data Vanilla : mrpeach (pour l'OSC), mapping (pour [resample]) et cyclone (pour [delay~]).



Dans un premier temps vous n'aurez pas à utiliser l'OSC, vous pouvez le supprimer. La première chose à faire est de rentrer la configuration des haut-parleurs. Veuillez rentrer le nombre de haut-parleur (accessible depuis le patch parent, et l'espace inter-haut-parleur (accessible en entrant dans le patch SFO_config). Puis appuyer sur (configurer).

Monter le volume du sous-patch SFO_master : il contrôle le volume de toutes les sorties. En entrant dans ce patch il est possible de régler chaque volume de sortie séparemment.

Chaque source SFO_source doit être vue comme une tranche de console. Son argument correspond au canal d'entrée de la carte son. Si vous ajoutez des sources, il faut à nouveau appuyer sur (configurer) pour actualiser.

Si vous utilisez l'OSC, attention à régler la cadence des paquets au dessus de 50ms (conseillé) pour ne pas saturer Pure Data de données entrantes. Selon les logiciels la valeur des paramètres changent donc il faut peut être normaliser les données dans l'abstraction [sous_osc].

Si vous voulez conserver l'effet Doppler, il faut remplacer dans les abstractions [SFO_process] l'objet [SFO_retard] par [SFO_retard_doppler].
