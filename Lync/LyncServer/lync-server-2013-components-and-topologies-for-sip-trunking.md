---
title: 'Lync Server 2013 : Composants et topologies utilisés pour une jonction SIP'
TOCTitle: Composants et topologies utilisés pour une jonction SIP
ms:assetid: 8ed9a9d0-517e-4f36-a131-22cdafa257fa
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398720(v=OCS.15)
ms:contentKeyID: 49298043
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Composants et topologies utilisés pour une jonction SIP dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-21_

La figure suivante représente la topologie de jonction SIP dans Lync Server.

**Topologie de jonction SIP**

![Topologie de jonction SIP](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "Topologie de jonction SIP")

Comme le montre le diagramme, un réseau privé virtuel (VPN) IP est utilisé pour la connectivité entre le réseau d’entreprise et le fournisseur de services de réseau téléphonique commuté. L’objectif de ce réseau privé est de fournir la connectivité IP, d’améliorer la sécurité et (éventuellement) d’obtenir des garanties de qualité de service. En raison de la nature d’un VPN, vous n’avez pas besoin d’utiliser TLS pour le trafic de signalisation SIP, ni SRTP pour le trafic multimédia. De ce fait, les connexions entre l’entreprise et le fournisseur de services consistent en des connexions TCP ordinaires pour SIP et des connexions RTP ordinaires (avec le protocole UDP) pour les médias traités par tunnel via un réseau VPN IP. Veillez à ce que tous les pare-feu situés entre les routeurs VPN disposent de ports ouverts pour permettre aux routeurs VPN de communiquer. Par ailleurs, les adresses IP des périmètres externes des routeurs VPN doivent être publiquement routables.

> [!IMPORTANT]  
> Contactez votre fournisseur de services pour déterminer s’il fournit la prise en charge pour la disponibilité élevée, notamment le basculement. Si c’est le cas, vous devrez déterminer les procédures pour la configurer. Par exemple, devez-vous configurer une seule adresse IP et une seule jonction SIP sur chaque serveur de médiation, ou configurer plusieurs jonctions SIP sur chaque serveur de médiation ?<br />
Si vous avez plusieurs sites centraux, demandez aussi à votre fournisseur de services s’il a la capacité d’activer les connexions vers et à partir d’un autre site central.

> [!NOTE]  
> Pour les jonctions SIP, nous vous conseillons vivement de déployer des serveurs de médiation autonomes. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Déploiement des serveurs de médiation et définition des homologues dans Lync Server 2013</a> dans la documentation de déploiement.

## Sécurisation du serveur de médiation pour la jonction SIP

Pour des raisons de sécurité, vous devriez configurer un réseau local virtuel (VLAN) pour chaque connexion entre deux routeurs VPN. Le processus courant de configuration d’un VLAN varie d’un fabricant de routeur à l’autre. Pour plus d’informations, contactez le fournisseur de votre routeur.

Nous vous conseillons de suivre les directives suivantes :

  - Configurez un réseau local virtuel (VLAN) entre le serveur de médiation et le routeur VPN dans le réseau de périmètre (appelé également zone DMZ, zone démilitarisée et sous-réseau filtré).

  - N’autorisez pas le transfert des paquets de diffusions ou de multidiffusions entre le routeur et le réseau local virtuel.

  - Bloquez toutes les règles de routage qui acheminent le trafic du routeur vers n’importe où sauf vers le serveur de médiation.

Si vous utilisez un serveur VPN, bous vous conseillons de suivre les directives suivantes :

  - Configurez un réseau local virtuel entre le serveur VPN et le serveur de médiation.

  - N’autorisez pas la transmission des paquets de diffusions ou de multidiffusions du serveur VPN vers le réseau local virtuel.

  - Bloquez toute règle de routage qui achemine le trafic de serveur VPN vers n’importe où sauf vers le serveur de médiation.

  - Chiffrez les données sur le réseau privé virtuel (VPN) à l’aide de l’encapsulation générique de routage (GRE).

