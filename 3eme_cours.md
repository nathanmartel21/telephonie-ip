## Notes




## Resume :

### 1) Définition et architecture IMS

- - IMS (IP Multimedia Subsystem) : Architecture standardisée, indépendante de l’accès, permettant la fourniture de services multimédias (voix, vidéo, messagerie) sur IP, utilisant des protocoles Internet (principalement SIP).
- - Principaux objectifs :
    - Établir des sessions multimédias sur IP
    - Négocier la qualité de service (QoS)
    - Interconnecter Internet et réseaux à commutation de circuits (PSTN)
    - Permettre le roaming et la création rapide de services.
  - Architecture en couches :
    - Transport : IP, UDP/TCP/SCTP
    - Contrôle : SIP, Diameter
    - Services : Serveurs d’applications (AS), HSS, SLF, etc.
   
### 2) Fonctions principales et entités IMS

- CSCF (Call Session Control Function) : Serveurs SIP au cœur de l’IMS, trois types :
  - P-CSCF (Proxy-CSCF) : Premier contact du terminal, gestion de la sécurité, compression SIP, génération de comptes d’exploitation.
  - I-CSCF (Interrogating-CSCF) : Routage des requêtes entrantes, attribution du S-CSCF, gestion du roaming.
  - S-CSCF (Serving-CSCF) : Gestion de l’enregistrement, routage des sessions, invocation de la logique de service, génération de comptes d’exploitation.
- HSS (Home Subscriber Server) : Base de données centrale pour les informations utilisateur (localisation, sécurité, profils, services activés).
- SLF (Subscriber Location Function) : Localise le HSS pertinent si plusieurs HSS existent.
- Application Servers (AS) : Fournissent des services multimédias avancés (présence, messagerie, etc.).
- MRF (Media Resource Function) : Gère les ressources médias (mélange, transcodage, annonces).
- MGCF/MGW (Media Gateway Control Function / Media Gateway) : Interconnexion avec le PSTN, conversion de protocoles et de médias.
- BGCF (Breakout Gateway Control Function) : Sélection du MGCF pour les appels vers le PSTN.

### 3) Interconnexion et interopérabilité

- Interconnexion avec les réseaux mobiles : IMS s’interface avec les réseaux GSM, UMTS, LTE (VoLTE), Wi-Fi, etc.
- Fonctions de passerelle :
  - SGW (Signaling Gateway) : Conversion des signalisations (ex : SS7 vers IP).
  - MGW (Media Gateway) : Conversion des flux médias (ex : RTP vers PCM).
- Interworking IPv4/IPv6 : IMS-ALG (Application Layer Gateway) et TrGW (Transition Gateway) pour la traduction à la couche signalisation et média.
- SBC (Session Border Controller) : Sécurité, contrôle d’accès, résolution des problèmes NAT, QoS, monitoring pour facturation et conformité réglementaire.

### 4) Protocole Diameter

- Rôle : Protocole AAA (Authentication, Authorization, Accounting), utilisé pour la gestion de la sécurité, de la facturation et de la qualité de service dans IMS.
- Fonctionnalités principales :
  - Authentification : Vérification de l’identité.
  - Autorisation : Décision d’accès aux ressources.
  - Comptabilité : Collecte des informations d’utilisation pour la facturation, l’audit, la planification.
- Avantages par rapport à RADIUS :
  - Utilisation de TCP/SCTP (plus fiable que UDP).
  - Sécurité renforcée (IPsec, TLS).
  - Espace d’adressage plus grand, meilleure gestion des sessions, extensibilité facilitée.
  - Prise en charge des messages initiés par le serveur.
- Interfaces Diameter dans IMS :
  - Cx/Dx : Échange d’informations entre CSCF et HSS/SLF.
  - Sh/Dh : Échanges avec les serveurs d’applications.
  - Rf/Ro : Facturation et contrôle de crédit.

 ### 5) Récap :

- IMS	: Architecture multimédia sur IP, basée sur SIP
- CSCF (P/I/S) :	Serveurs SIP pour le routage, l’enregistrement, la sécurité et la gestion des services
- HSS/SLF	: Bases de données pour les abonnés et leur localisation
- MRF	: Gestion des ressources médias
- MGCF/MGW :	Interconnexion avec le PSTN, conversion de protocoles et de médias
- BGCF :	Sélection de la passerelle pour les appels vers le PSTN
- SBC	: Sécurité, contrôle d’accès, résolution NAT
- Diameter : Protocole AAA pour la sécurité, la facturation et la QoS

### 6) Points à retenir

- IMS est la pierre angulaire de la convergence multimédia sur IP, intégrant voix, vidéo et messagerie sur tous types d’accès.
- Les fonctions CSCF orchestrent la signalisation et la gestion des sessions.
- L’interconnexion avec les réseaux mobiles et le PSTN est assurée par des passerelles (SGW, MGW, MGCF).
- Diameter est essentiel pour la sécurité, la facturation et la gestion de la qualité de service dans IMS.
- Le SBC joue un rôle clé dans la sécurité et la résolution des problèmes liés au NAT et aux pare-feu.





















