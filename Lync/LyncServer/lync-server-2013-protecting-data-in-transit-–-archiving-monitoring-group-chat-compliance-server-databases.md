---
title: "LS 2013 : prot. données en transit : BD serv. arch., surv., conf. conv. de gr."
TOCTitle: 'Protection des données en transit : bases de données de serveur d’archivage, de surveillance, de conformité de conversation de groupe dans Lync Server 2013'
ms:assetid: ea219705-1015-43a7-890b-e7e67b451e7c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn518336(v=OCS.15)
ms:contentKeyID: 60484533
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Protection des données en transit : bases de données de serveur d’archivage, de surveillance, de conformité de conversation de groupe dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Le serveur d’archivage et le serveur de surveillance Microsoft Lync Server 2013 utilisent tous deux le service Message Queuing (également appelée « MSMQ ») pour collecter et déplacer de façon fiable les messages du point de collecte vers les serveurs de référentiel. Le service de conformité collecte des données conjointement au serveur de conversation de groupe, qui utilise également Message Queuing.

Dans Lync Server 2013, il n’y a pas de protection interne des données sur le fil. Cependant, s’il est nécessaire de sécuriser ce trafic, le service Message Queuing peut permettre le chiffrement au niveau des messages dans la file d’attente d’envoi des messages. Cette opération est effectuée en utilisant des certificats gérés par les services de domaine Active Directory. Pour plus d’informations, reportez-vous à l’Annexe D : Message Queuing et communication Internet dans Windows Server 2008 sous [http://go.microsoft.com/fwlink/p/?LinkId=145238](http://go.microsoft.com/fwlink/p/?linkid=145238) ou à l’Annexe I : Message Queuing et communication Internet dans Windows Server 2008 V2 sous [http://go.microsoft.com/fwlink/p/?LinkId=211883](http://go.microsoft.com/fwlink/p/?linkid=211883) pour Windows Server 2008 V2.

