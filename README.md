# CRobLib
Librairie en langage C standard multi-plateforme communs aux différents projets robotique CRLG.

Cette librairie est destinée à être utilisée comme sous-module des projets en langage C sur petits mircrocontrôleurs ou sur LEGO.

Quelques règles :
- Les différents modules logiciels contenus dans ce projet CRobLib doivent être génériques, indépendant de toute plateforme matérielle ou compilateur.

- Lorsqu'un lien avec le hardware est nécessaire, le module fait appel à une fonction externe qui devra être implémentée par le logiciel utilisateur sur la plateforme cible.\
Exemple pour le module xbee souhaitant émettre un octet sur l'UART.\
Déclaration de la fonction externe : extern void xbee_send_uart(unsigned char data);\
Utilisation : xbee_send_uart(0x34);\
Côté applicatif, implémenter la fonction void xbee_send_uart(unsigned char data);

- Un répertoire par module contenant les fichiers sources et headers du module.

- Lorsqu'une version stable est livrée, un tag est posé permettant aux autres projets de pointer dessus.

Projet similaire en C++ : https://github.com/CRLG/CppRobLib
