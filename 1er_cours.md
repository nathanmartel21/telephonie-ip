## Notes

- The Session Initiation Protocol (SIP), couche 7
- SIP sessions
- 3GPP
- IMS (IP Multimedia Subsystem)
- RFC 3261, 2002
- Basé sur HTTP et SMTP, transport protocol neutral (UDP, TCP, SCTP)
- Séparation of signalling and media description
- Extensible
- User plan (RTP, RTCP) et Control plan (SIP, SDP)
- Media Gateway Control Serveur
- VoIP : Master/slave protocole
- H. 323
- Skinny Client Control Protocol (Propriétaire cisco)
- Data encapsulation
- TOS field, Differentiated services
- SIP can repeat his request
- Datagram IP avec le protocole SIP
- SCTP authentic purpose
- SCTP vs TCP
- TCP lié à IPSEC/TLS pour SIP ?
- SCTP : Multihoming (redundancy)
- SBC est le firewall ?
- SigComp, SDP
- SIP Adressing, SIP URL
- SIP : Initiate, modify and tear-down media session. Does not care about established media session
- SIP INVITE, REGISTER, BYE, ACK, re-INVITE, CANCEL, OPTIONS, REFER, SUBSCRIBE, NOTIFY MESSAGE, INFO (compatibility)
- Origine de SMS : c'était que l'opérateur puisse configurer le téléphone en envoyant des SMS
- DTMF SIP

## Resume :

### Qu’est-ce que SIP ?

- Définition : SIP (Session Initiation Protocol) est un protocole de signalisation de la couche application, utilisé pour établir, modifier et terminer des sessions multimédias (appels, vidéoconférences, etc.) sur les réseaux IP.
- Fonctionnement : Il permet la communication unicast ou multicast entre un ou plusieurs participants.
- Utilisation : Principalement utilisé pour la VoIP (Voice over IP) et constitue la base de l’architecture IMS (IP Multimedia Subsystem).

### VoIP et protocoles de signalisation

Protocoles ouverts :

- SIP : Standard ouvert, utilisé pour la plupart des solutions VoIP modernes
- H.323 : Standard ITU-T, anciennement le principal concurrent de SIP.
- H.248/MEGACO : Protocole de contrôle des passerelles multimédias.
- IAX : Protocole open source, principalement utilisé avec Asterisk.

Protocoles propriétaires :

- Skype : Protocole fermé, modèle peer-to-peer avec éléments de contrôle centralisé.
- SCCP (Skinny Client Control Protocol) : Protocole Cisco pour connecter les téléphones VoIP à leur serveur Call Manager, moins fermé que Skype.
- Autres : Beaucoup de constructeurs utilisent leurs propres protocoles pour connecter les terminaux à leur PBX.

### SIP et le modèle TCP/IP

- Positionnement : SIP est un protocole de la couche application du modèle TCP/IP.
- Transport : Utilise les protocoles de transport UDP, TCP ou SCTP pour véhiculer ses messages de signalisation.
- Modèles de référence :

- OSI : SIP se situe à la couche application (couche 7).
- TCP/IP : SIP est un protocole applicatif, au-dessus des couches transport (TCP/UDP/SCTP), réseau (IP) et accès réseau.

### Plan utilisateur vs plan de contrôle

- **Plan utilisateur (User Plane) :** Transfère les données utilisateur (voix, vidéo) et contrôle associé (flux, erreurs). Protocoles typiques : RTP, RTCP.
- **Plan de contrôle (Control Plane) :** Gère l’établissement, la maintenance et la fin des sessions. Protocoles typiques : SIP, SDP.

### Protocoles de transport utilisés par SIP

- UDP (User Datagram Protocol) : Simple, sans garantie de livraison, idéal pour la signalisation VoIP où la rapidité prime sur la fiabilité.
- TCP (Transmission Control Protocol) : Fiabilise la communication, avec gestion de la connexion, du contrôle de flux, etc.
- SCTP (Stream Control Transmission Protocol) : Offre la fiabilité de TCP, mais avec des fonctionnalités avancées comme le multi-homing, le multistreaming et une meilleure résistance aux attaques.

### Encapsulation et fonctionnement réseau

- Encapsulation : Les messages SIP sont encapsulés dans des segments TCP, UDP ou SCTP, eux-mêmes encapsulés dans des paquets IP.
- Qualité de Service (QoS) : Le champ TOS/DSCP dans l’en-tête IP permet de gérer la priorité des paquets pour la qualité de service.

### SCTP : caractéristiques principales

- Fiabilité : Livraison sans erreur, non dupliquée, avec retransmission sélective.
- Multistreaming : Plusieurs flux indépendants dans une même association.
- Multi-homing : Plusieurs interfaces réseau possibles pour une même association.
- Sécurité : Sensible aux attaques MITM, mais peut être sécurisé par IPsec ou TLS.
- Établissement de l’association : Four-way handshake pour une initialisation sécurisée.

### Points à retenir

- SIP est le standard ouvert majeur pour la signalisation VoIP.
- Séparation entre signalisation (SIP) et données utilisateur (RTP).
- Protocoles de transport : UDP (rapide), TCP (fiable), SCTP (avancé).
- Protocoles propriétaires existent, mais moins flexibles et interopérables.
- SCTP offre des avantages pour la signalisation, notamment la fiabilité et la résistance aux attaques.







































































