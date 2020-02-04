---
title: 'Lync Server 2013 : Composants et topologies de la messagerie unifiée locale'
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
ms.openlocfilehash: 1739dbb7d603f112af72c78032c46b94470302bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-on-premises-unified-messaging-in-lync-server-2013"></a>Composants et topologies de la messagerie unifiée locale dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-25_

Cette rubrique décrit les composants Microsoft Exchange Server 2013 requis pour fournir des fonctionnalités de messagerie unifiée Exchange pour le déploiement de Lync Server 2013. Il décrit également les topologies prises en charge pour l’intégration à la messagerie unifiée Exchange locale.

<div>

## <a name="exchange-server-components"></a>Composants d’Exchange Server

Pour fournir les services et fonctionnalités de messagerie UNIFIÉe Exchange décrits dans les [fonctionnalités de messagerie unifiée et de Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) aux utilisateurs voix entreprise dans votre organisation, vous devez déployer un serveur de boîte aux lettres Microsoft Exchange et un serveur d’accès au client, qui héberge les boîtes aux lettres des utilisateurs et fournit un emplacement de stockage unique pour la messagerie électronique et la messagerie vocale. La messagerie unifiée Exchange s’exécute en tant que service sur les serveurs de boîtes aux lettres Exchange et d’accès client.

Pour plus d’informations sur les composants de messagerie unifiée Exchange dans Microsoft Exchange Server 2007 et Microsoft Exchange Server 2010, voir [déploiement de la messagerie unifiée Exchange locale pour fournir la messagerie vocale Lync Server 2013](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) dans la documentation de déploiement.

</div>

<div>

## <a name="supported-topologies"></a>Topologies prises en charge

Vous pouvez déployer Lync Server 2013 et Exchange Unified Messaging (UM) dans la même forêt ou plusieurs forêts. Si le déploiement s’étend sur plusieurs forêts, vous devez effectuer les étapes d’intégration Exchange pour chaque forêt Exchange UM. Par ailleurs, vous devez configurer chaque forêt Microsoft Exchange pour faire confiance aux forêts Lync Server 2013 et à la forêt Lync Server 2013 pour approuver chaque forêt Exchange UM. Outre cette approbation de forêt, les paramètres de messagerie unifiée Exchange pour tous les utilisateurs doivent être définis sur les objets utilisateur dans la forêt 2013 du serveur Lync.

Lync Server 2013 prend en charge les topologies suivantes pour l’intégration à la messagerie unifiée Exchange :

  - Forêt unique

  - Domaine unique (à savoir, une seule forêt associée à un seul domaine). Lync Server 2013, Microsoft Exchange et les utilisateurs se trouvent tous dans le même domaine.

  - Plusieurs domaines (à savoir, un domaine racine comportant un ou plusieurs domaines enfants). Les serveurs Lync Server 2013 et Microsoft Exchange sont déployés dans différents domaines à partir du domaine dans lequel vous créez des utilisateurs. Les serveurs de messagerie unifiée Exchange peuvent être déployés dans différents domaines à partir du pool Lync Server 2013 pris en charge.

  - Forêts multiples (c’est-à-dire, forêt de ressources). Lync Server 2013 est déployé dans une seule forêt, et les utilisateurs sont répartis entre plusieurs forêts. Les attributs d’Exchange UM des utilisateurs doivent être répliqués dans la forêt Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > Exchange peut être déployé dans plusieurs forêts. Chaque organisation Exchange peut fournir la messagerie unifiée Exchange à ses utilisateurs, ou la messagerie unifiée Exchange peut être déployée dans la même forêt que Lync Server 2013.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

