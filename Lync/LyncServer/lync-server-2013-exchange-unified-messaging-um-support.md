---
title: 'Lync Server 2013 : Prise en charge de la messagerie unifiée Exchange'
TOCTitle: Prise en charge de la messagerie unifiée Exchange
ms:assetid: 0da62b8d-7416-4fb8-a405-381ca805c53a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398179(v=OCS.15)
ms:contentKeyID: 49296246
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prise en charge de la messagerie unifiée Exchange dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-21_

Lync Server 2013 prend en charge l’intégration à la messagerie unifiée Exchange pour associer la messagerie vocale et électronique dans une seule infrastructure de messagerie.Dans Exchange 2013, la messagerie unifiée Exchange est constituée du service de messagerie unifiée Exchange, qui est installé sur le serveur d’accès au client et qui s’exécute sur celui-ci. Pour les déploiements du composant Voix Entreprise de Lync Server 2013, la messagerie unifiée Exchange regroupe la messagerie vocale et la messagerie électronique dans un seul magasin accessible depuis un téléphone (c’est-à-dire, Outlook Voice Access) ou un ordinateur. La messagerie unifiée Exchange et Lync Server 2013 collaborent pour offrir les services de répondeur automatique, de standard automatique et Outlook Voice Access aux utilisateurs de Voix Entreprise.

En plus de l’intégration aux déploiements sur site de la messagerie unifiée Exchange, Lync Server 2013 prend en charge l’intégration à la messagerie unifiée Exchange hébergée. Cela vous permet d’offrir la fonctionnalité de messagerie vocale aux utilisateurs si vous procédez à la migration de la totalité des utilisateurs ou de certains d’entre eux vers un fournisseur de service Exchange hébergé tel que Microsoft Exchange Online.

Lync Server 2013 prend en charge les versions suivantes :

  - Microsoft Exchange 2013

  - Microsoft Exchange Server 2010 (requis) ou avec le tout dernier service pack (recommandé)

  - Microsoft Exchange Server 2007 avec Service Pack 1 (SP1) (requis) ou le tout dernier service pack (recommandé)

Vous ne pouvez pas colocaliser la messagerie unifiée Exchange avec Lync Server 2013 ou une base de données Lync Server 2013. Vous pouvez installer la messagerie unifiée Exchange et Lync Server 2013 dans des forêts distinctes.

> [!NOTE]  
> Il est possible que la messagerie unifiée Exchange ne soit pas indispensable pour les déploiements de Voix Entreprise intégrant un système PBX, car ce dernier peut continuer à fournir à tous les utilisateurs des services de messagerie vocale et d’autres services connexes. Si vous supprimez finalement le système PBX (par exemple, lors du déploiement de l’acheminement SIP pour une connectivité RTC (réseau téléphonique commuté), vous devez reconfigurer la messagerie unifiée Exchange afin qu’elle mette la messagerie vocale à la disposition des utilisateurs ayant auparavant utilisé le système de messagerie vocale PBX.

## Dans cette section

  - [Composants et topologies de la messagerie unifiée locale dans Lync Server 2013](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [Prise en charge de l’intégration de la messagerie unifiée Exchange hébergée dans Lync Server 2013](lync-server-2013-support-for-hosted-exchange-um-integration.md)

