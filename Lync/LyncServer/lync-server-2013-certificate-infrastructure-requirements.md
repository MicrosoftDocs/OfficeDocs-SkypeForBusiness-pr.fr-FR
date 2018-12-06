---
title: Configuration requise pour les infrastructures de certificat Lync Server 2013
TOCTitle: Configuration requise pour les infrastructures de certificat
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398066(v=OCS.15)
ms:contentKeyID: 49296050
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration requise pour les infrastructures de certificat pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Lync Server 2013 requiert une infrastructure à clé publique (PKI, Public Key Infrastructure) pour la prise en charge des connexions PKI et MTLS (Mutual TLS).

Lync Server utilise des certificats dans les cas suivants :

  - Connexions TLS entre client et serveur

  - Connexions MTLS entre serveurs

  - Fédération à l’aide de la découverte automatique de partenaires via le DNS

  - Accès des utilisateurs distants à la messagerie instantanée

  - Accès des utilisateurs externes aux sessions audio/vidéo (A/V), au partage d’application et aux conférences

  - Demandes mobiles utilisant la découverte automatique de services web

Pour Lync Server, les conditions suivantes sont requises :

  - Tous les certificats de serveur doivent prendre en charge l’autorisation serveur (utilisation améliorée de la clé du serveur).

  - Tous les certificats de serveur doivent contenir un point de distribution de liste de révocation de certificats (CDP).

  - Tous les certificats doivent être signés à l’aide de l’algorithme de signature pris en charge par le système d’exploitation. Lync Server 2013 prend en charge SHA-1 et la suite de tailles d’algorithme SHA-2 (224, 256, 384 et 512 bits) et respecte la configuration système requise. Pour plus d’informations sur la prise en charge du système d’exploitation, reporrtez-vous à [http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002).

  - L’inscription automatique est prise en charge pour les serveurs internes exécutant Lync Server.

  - L’inscription automatique n’est pas prise en charge pour les serveurs Edge Lync Server.

  - Pour soumettre une demande de certificat web à une Autorité de certification Windows Server 2003, vous devez utiliser un ordinateur exécutant Windows Server 2003 avec SP2 ou Windows XP.
    
    Notez bien que l’article de la Base de connaissances Microsoft KB922706 indique comment résoudre les problèmes relatifs à l’inscription de certificats web lors d’une inscription avec les services de certificat Windows Server 2003, il n’est pas possible d’utiliser Windows Server 2008, Windows Vista ou Windows 7 pour demander un certificat auprès d’une Autorité de certification Windows Server 2003.

  - Les longueurs de clé de chiffrement 1024, 2048 et 4096 sont prises en charge. Les longueurs de clé supérieures ou égales à 2048 sont recommandées.

  - L’algorithme digest, ou de signature de hachage, par défaut est RSA. Les algorithmes ECDH\_P256, ECDH\_P384 et ECDH\_P521 sont également pris en charge. 

## Dans cette section

  - [Exigences de certificat pour les serveurs internes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Certificats requis pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Certificats requis pour le serveur de conversation permanente dans Lync Server 2013](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [Exigences relatives aux certificats pour la mobilité dans Lync Server 2013](lync-server-2013-certificate-requirements-for-mobility.md)

