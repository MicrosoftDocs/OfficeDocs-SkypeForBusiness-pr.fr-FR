---
title: 'Lync Server 2013 : composants et topologies pour la messagerie unifiée locale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for on-premises Unified Messaging
ms:assetid: 22fc87cf-a7e5-4c8c-bb9b-101e5380cdcf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425711(v=OCS.15)
ms:contentKeyID: 48183619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 543af1cc9b4dbb437b36273945f9f2cb6112c6b6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-on-premises-unified-messaging-in-lync-server-2013"></a>Composants et topologies pour la messagerie unifiée locale dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-25_

Cette rubrique décrit les composants Microsoft Exchange Server 2013 requis pour fournir des fonctionnalités de messagerie unifiée Exchange au déploiement de Lync Server 2013. Il décrit également les topologies prises en charge pour l’intégration de la messagerie unifiée Exchange sur site.

<div>

## <a name="exchange-server-components"></a>Composants d’Exchange Server

Pour fournir les services et fonctionnalités de messagerie unifiée Exchange décrits dans les [fonctionnalités de la messagerie unifiée intégrée et de Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) aux utilisateurs de voix entreprise dans votre organisation, vous devez déployer un serveur de boîtes aux lettres Microsoft Exchange et un serveur d’accès au client, qui héberge les boîtes aux lettres utilisateur et fournit un emplacement de stockage unique pour la messagerie et la messagerie vocale. La messagerie unifiée Exchange s’exécute en tant que service sur les serveurs de boîtes aux lettres et d’accès au client Exchange.

Pour plus d’informations sur les composants de messagerie unifiée Exchange dans Microsoft Exchange Server 2007 et Microsoft Exchange Server 2010, consultez la rubrique [Deploying on-premises Exchange um to Preserver 2013 Voice Mail](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) dans la documentation de déploiement.

</div>

<div>

## <a name="supported-topologies"></a>Topologies prises en charge

Vous pouvez déployer Lync Server 2013 et la messagerie unifiée Exchange dans la même forêt ou plusieurs forêts. Si le déploiement s’étend sur plusieurs forêts, vous devez effectuer les étapes d’intégration d’Exchange pour chaque forêt de messagerie unifiée Exchange. Par ailleurs, vous devez configurer chaque forêt Microsoft Exchange pour qu’elle approuve la forêt Lync Server 2013 et la forêt Lync Server 2013 pour approuver chaque forêt de messagerie unifiée Exchange. En plus de cette approbation de forêt, les paramètres de messagerie unifiée Exchange pour tous les utilisateurs doivent être définis sur les objets utilisateur de la forêt Lync Server 2013.

Lync Server 2013 prend en charge les topologies suivantes pour l’intégration de la messagerie unifiée Exchange :

  - Forêt unique

  - Domaine unique (c’est-à-dire une forêt unique avec un seul domaine). Lync Server 2013, Microsoft Exchange et les utilisateurs résident tous dans le même domaine.

  - Plusieurs domaines (à savoir, un domaine racine comportant un ou plusieurs domaines enfants). Lync Server 2013 et les serveurs Microsoft Exchange sont déployés dans des domaines différents du domaine dans lequel vous créez des utilisateurs. Les serveurs de messagerie unifiée Exchange peuvent être déployés dans différents domaines à partir du pool Lync Server 2013 qu’ils prennent en charge.

  - Forêt multiple (autrement dit, forêt de ressources). Lync Server 2013 est déployé dans une forêt unique, puis les utilisateurs sont répartis entre plusieurs forêts. Les attributs de messagerie unifiée d’Exchange des utilisateurs doivent être répliqués sur la forêt Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > Exchange peut être déployé dans plusieurs forêts. Chaque organisation Exchange peut fournir la messagerie unifiée Exchange à ses utilisateurs, ou le serveur de messagerie unifiée Exchange peut être déployé dans la même forêt que Lync Server 2013.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

