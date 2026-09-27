# Migration Marlin 2.1.2.6 vers 2.1.2.8 et bootscreen

Carte : BTT Octopus V1.1, STM32F446ZET6.
Compilation finale : SUCCESS, STM32F446ZE_btt, 16.709 secondes.
Commande : platformio run -e STM32F446ZE_btt
Journal : build-statusscreen.log (aucune erreur ni avertissement du compilateur).
RAM : 12992 / 131072 octets (9.9 %). Flash : 268896 / 491520 octets (54.7 %).

## Modifications exhaustives

- Configuration.h : DEFAULT_bedKp/Ki/Kd deviennent DEFAULT_BED_KP/KI/KD. Valeurs conservees : 56.2100, 5.90, 356.700. PIDTEMPBED reste desactive.
- Configuration.h : SHOW_CUSTOM_BOOTSCREEN active a la demande de l'utilisateur.
- Aucun autre changement dans Configuration.h : comparaison octet par octet apres ces quatre substitutions.
- Configuration_adv.h : strictement identique au fichier ancien.
- platformio.ini : default_envs = STM32F446ZE_btt au lieu de mega2560.
- Marlin/_Statusscreen.h : fourni par l'utilisateur, utilise sans modification.
- Marlin/_Bootscreen.h : fourni par l'utilisateur, utilise sans modification ; bitmap 128 x 64, 1024 octets.
- Numeros de format 02010206 conserves, conformement au code 2.1.2.8.
- FT_MOTION non active. Aucun changement du brochage ni du code source Marlin.

## Verification

Compilation et controles statiques Marlin valides. Aucun flashage ni essai sur imprimante.
Les valeurs en EEPROM ne peuvent pas etre recuperees a partir des fichiers seuls.
Anciennes configurations intactes ; sauvegardes initiales *.before ; comparaisons *.comparison.diff et *.migration.diff.

## Binaire final avec bootscreen

Chemin : C:\Users\yanni\Downloads\Marlin-2.1.2.8\Marlin-2.1.2.8\.pio\build\STM32F446ZE_btt\firmware.bin
Taille : 269500 octets.
SHA256 : 2e651507c716155a65cb056e3cca4a612f604cb2914cd80313d10be62c52f62a

Derniere recompilation : integration du _Statusscreen.h modifie par l'utilisateur, sans modification des configurations par l'assistant.
