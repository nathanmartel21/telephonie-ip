## Notes :

- CSeq



## Resume :

### 1) Opérations avancées SIP

- Mise en attente, transfert, conférence : SIP permet la gestion avancée des appels comme la mise en attente (call hold), le transfert d’appel (attended/unattended), la conférence à trois, le renvoi d’appel inconditionnel, sur occupation ou sur non-réponse.
- Gestion des appels : Fonctions telles que le filtrage d’appels entrants/sortants, le parcage et la reprise d’appel (call park/pickup), la recomposition automatique (automatic redial), et l’intégration avec la messagerie instantanée sont possibles.
- Proxies SIP : Différence entre proxy stateful/stateless, proxy inbound/outbound, serveurs de redirection et serveurs d’enregistrement (registrar).

### 2) SDP (Session Description Protocol)

- Rôle : SDP décrit les paramètres de session multimédia (type, adresse IP, port, codecs, etc.) échangés dans les messages SIP pour établir la communication.
- Structure : Message textuel composé de champs obligatoires et optionnels (v= version, o= origin, s= session, c= connexion, m= média, a= attributs, etc.).
- Exemple :

```
v=0
o=alice 53655765 2353687637 IN IP4 pc33.atlanta.com
s=Session SDP
c=IN IP4 pc33.atlanta.com
t=0 0
m=audio 3456 RTP/AVP 0 1 3 99
a=rtpmap:0 PCMU/8000
```

- Utilisation : L’appelant propose ses capacités médias dans l’INVITE, l’appelé répond dans le 200 OK. SDP peut aussi être utilisé dans UPDATE, PRACK, etc.

### 3) RTP (Real-time Transport Protocol) et RTCP

- RTP : Protocole de transport temps réel pour audio/vidéo, utilisé pour transmettre les flux médias entre les terminaux. Il ne garantit pas la livraison mais permet la détection de pertes, de délais et de désordre des paquets.
- Structure d’un paquet RTP : En-tête IP, UDP, puis en-tête RTP (version, séquence, timestamp, SSRC, CSRC, etc.), puis la charge utile (ex : échantillons audio).
- RTCP : Protocole compagnon de RTP, utilisé pour l’échange de statistiques de qualité (nombre de paquets perdus, gigue, etc.), identification des participants, synchronisation et contrôle de session.

### 4) Sécurité SIP et médias

- Authentification SIP : Basée sur le modèle HTTP Digest (challenge/réponse, hash MD5), avec gestion des nonces, realm, qop, etc.
- Confidentialité et intégrité :
  - S/MIME : Permet de signer et chiffrer le corps des messages SIP pour assurer intégrité et confidentialité de bout en bout, mais pose des problèmes d’interopérabilité avec certains équipements intermédiaires.
  - TLS : Assure la confidentialité et l’intégrité des messages SIP sur chaque saut (hop-by-hop), très utilisé dans les infrastructures actuelles.
- Protection des médias :
  - SRTP (Secure RTP) : Chiffre et authentifie les flux RTP/RTCP pour garantir confidentialité et intégrité des médias.
  - Échange de clés : Plusieurs méthodes existent (SDES, MIKEY, ZRTP, DTLS-SRTP) pour négocier les clés de chiffrement.
  - ZRTP : Protocole d’accord de clé basé sur Diffie-Hellman, sans besoin d’infrastructure PKI, utilisant un SAS (Short Authentication String) pour l’authentification mutuelle.
  - DTLS-SRTP : Extension de DTLS pour négocier les paramètres cryptographiques sur le même port UDP que les médias.

### 5) Principaux risques et protections

- Vol d’identité et d’abonnement : L’usurpation d’identité permet à un attaquant de se faire passer pour un autre utilisateur, recevoir ses appels ou utiliser ses droits.
- Protection de la vie privée : SIP transporte de nombreuses informations personnelles (identité, localisation, équipements, etc.) qu’il est possible de masquer ou de chiffrer selon les besoins.
- Sécurisation des échanges : Les solutions de sécurité doivent minimiser l’impact sur la performance (taille des paquets, latence, compatibilité avec la compression d’en-tête).

### 6) Récap :

- SIP avancé : Gestion d’appels complexes : transfert, conférence, filtrage, parcage, etc.
- SDP : Description textuelle des sessions médias (codecs, ports, adresses, attributs)
- RTP/RTCP : Transport des flux médias en temps réel et contrôle de qualité
- S/MIME : Signature et chiffrement de messages SIP de bout en bout
- TLS : Sécurité des messages SIP entre chaque pair d’équipements
- SRTP : Sécurité des flux médias (audio/vidéo)
- ZRTP/DTLS-SRTP : Protocoles d’échange de clés pour sécuriser SRTP
- Proxies et serveurs SIP : Proxy stateful/stateless, redirect, registrar, outbound/inbound
- Risques sécurité : Usurpation d’identité, vol d’abonnement, atteinte à la vie privée

### 7) Points à retenir

- SIP permet la gestion avancée des appels et l’interopérabilité avec de nombreux services multimédias.
- SDP est essentiel pour la négociation des paramètres médias.
- RTP/RTCP assurent le transport et la supervision des flux temps réel.
- La sécurité SIP repose sur l’authentification, la confidentialité et l’intégrité des messages et des médias, avec plusieurs protocoles complémentaires.
- La protection de la vie privée et la lutte contre l’usurpation d’identité sont des enjeux majeurs dans les architectures VoIP modernes



