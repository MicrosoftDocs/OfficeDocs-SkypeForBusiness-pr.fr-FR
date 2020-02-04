---
title: 'Lync Server 2013 : Prise en charge de la messagerie unifiée Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange Unified Messaging (UM) support
ms:assetid: 0da62b8d-7416-4fb8-a405-381ca805c53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398179(v=OCS.15)
ms:contentKeyID: 48183405
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8925bd8a07693800c49ff2d818d3677b33452b97
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a>Prise en charge de la messagerie unifiée Exchange dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Lync Server 2013 prend en charge l’intégration à la messagerie unifiée Exchange pour combiner la boîte vocale et la messagerie électronique en une seule infrastructure de messagerie. Dans Exchange 2013, la messagerie unifiée Exchange est composée du service de messagerie unifiée Exchange qui est installé et s’exécute sur le serveur de boîtes aux lettres et sur le routeur d’appel de MU qui est installé et s’exécute sur le serveur d’accès client. Pour les déploiements de la voix entreprise de Lync Server 2013, la messagerie UNIFIÉe Exchange combine la messagerie vocale et la messagerie électronique dans un magasin unique accessible à partir d’un téléphone (Outlook Voice Access) ou d’un ordinateur. Exchange UM et Lync Server 2013 collaborent de manière à fournir des réponses aux appels, à Outlook Voice Access et aux services de standard automatique aux utilisateurs d’Enterprise Voice.

Outre la prise en charge de l’intégration avec des déploiements de messagerie unifiée Exchange, Lync Server 2013 prend en charge l’intégration à la messagerie unifiée Exchange hébergée. Cela vous permet de fournir une boîte vocale à vos utilisateurs si vous migrez tout ou partie de ces éléments vers un fournisseur de services Exchange hébergé tel que Microsoft Exchange Online.

Lync Server 2013 prend en charge les versions suivantes :

  - Microsoft Exchange 2013

  - Microsoft Exchange Server 2010 (requis) ou avec le dernier Service Pack (recommandé)

  - Microsoft Exchange Server 2007 avec Service Pack 1 (SP1) (requis) ou le dernier Service Pack (recommandé)

Vous ne pouvez pas collocate Exchange UM avec Lync Server 2013 ou une base de données Lync Server 2013. Vous pouvez installer Exchange UM et Lync Server 2013 dans des forêts distinctes.

<div>


> [!NOTE]  
> Exchange UM ne peut pas être requis pour les déploiements vocaux d’entreprise ayant déployé un système PBX, car le système PBX peut continuer à fournir des messages vocaux et des services associés à tous les utilisateurs. Si vous avez finalement désactivé le PBX (par exemple, si vous déployez le trunking SIP pour une connectivité PSTN), vous devez reconfigurer la messagerie UNIFIÉe Exchange pour fournir la messagerie vocale aux utilisateurs qui ont utilisé le système de messagerie vocale PBX.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Composants et topologies de la messagerie unifiée locale dans Lync Server 2013](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [Prise en charge de l’intégration de la messagerie unifiée Exchange hébergée dans Lync Server 2013](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

