---
title: 'Lync Server 2013 : prise en charge de la messagerie unifiée Exchange'
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
ms.openlocfilehash: 0e906b6194572d0ed7f797a2be64c7b66982436b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a>Prise en charge de la messagerie unifiée Exchange dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Lync Server 2013 prend en charge l’intégration à la messagerie unifiée Exchange pour combiner la messagerie vocale et la messagerie électronique dans une infrastructure de messagerie unique. Dans Exchange 2013, la messagerie unifiée Exchange se compose du service de messagerie unifiée Exchange, qui est installé et s’exécute sur le serveur de boîtes aux lettres, et du routeur d’appels de messagerie unifiée, qui est installé et s’exécute sur le serveur d’accès au client. Pour les déploiements de voix entreprise dans Lync Server 2013, la messagerie UNIFIÉe Exchange combine la messagerie vocale et la messagerie électronique dans un magasin unique accessible à partir d’un téléphone (Outlook Voice Access) ou d’un ordinateur. La messagerie unifiée Exchange et Lync Server 2013 collaborent pour fournir des services de répondeur automatique, Outlook Voice Access et de standard automatique aux utilisateurs de voix entreprise.

En plus de la prise en charge de l’intégration avec des déploiements locaux de la messagerie unifiée Exchange, Lync Server 2013 prend en charge l’intégration à la messagerie unifiée Exchange hébergée. Cela vous permet d’offrir la fonctionnalité de messagerie vocale aux utilisateurs si vous procédez à la migration de la totalité des utilisateurs ou de certains d’entre eux vers un fournisseur de service Exchange hébergé tel que Microsoft Exchange Online.

Lync Server 2013 prend en charge les versions suivantes :

  - Microsoft Exchange 2013

  - Microsoft Exchange Server 2010 (requis) ou avec le Service Pack le plus récent (recommandé)

  - Microsoft Exchange Server 2007 avec Service Pack 1 (SP1) (requis) ou le Service Pack le plus récent (recommandé)

Vous ne pouvez pas colocaliser la messagerie unifiée Exchange avec Lync Server 2013 ou une base de données Lync Server 2013. Vous pouvez installer la messagerie unifiée Exchange et Lync Server 2013 dans des forêts distinctes.

<div>


> [!NOTE]  
> Il est possible que la messagerie unifiée Exchange ne soit pas indispensable pour les déploiements de Voix Entreprise intégrant un système PBX, car ce dernier peut continuer à fournir à tous les utilisateurs des services de messagerie vocale et d’autres services connexes. Si vous avez finalement retiré le PBX (par exemple, si vous déployez la jonction SIP pour la connectivité PSTN), vous devez reconfigurer la messagerie UNIFIÉe Exchange pour qu’elle fournisse des messages vocaux aux utilisateurs qui ont utilisé le système de messagerie vocale PBX.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Composants et topologies pour la messagerie unifiée locale dans Lync Server 2013](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [Prise en charge de l’intégration de la messagerie unifiée Exchange hébergée dans Lync Server 2013](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

