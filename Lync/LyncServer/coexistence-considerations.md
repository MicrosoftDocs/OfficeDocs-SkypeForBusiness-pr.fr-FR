---
title: Remarques liées à la coexistence
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Coexistence considerations
ms:assetid: 9d1a3c0f-492a-4e37-bc2f-63509e328785
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205131(v=OCS.15)
ms:contentKeyID: 48184990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e53c57b90a85024ed5375129ce23c6ff0060edc4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="coexistence-considerations"></a>Remarques liées à la coexistence

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-06_

Après la migration, vous n’aurez qu’un seul Lync Server 2013, le pool de serveurs de conversation permanent et vous pourrez désactiver votre déploiement hérité.

Avant la fin de la migration et avant d’avoir désactivé entièrement le déploiement de votre serveur de discussion de groupe actuel, il est possible que vous disposiez de l’un des déploiements suivants :

  - Lync Server 2013, pool de serveurs de chat permanent, qui doit être hébergé sur un pool 2013 serveur Lync.

  - Lync Server 2010, pool de discussion de groupe, qui doit être hébergé sur un pool 2010 serveur Lync.

  - Pool de discussion de groupe Office Communications Server 2007 R2, qui doit être hébergé sur un pool Office Communications Server 2007 R2.

Ces déploiements peuvent exister côte à côte. Toutefois, les catégories, les salles et les compléments dans un seul déploiement n’interagissent pas avec celles du déploiement associé.

À l’aide de la configuration manuelle, un client hérité (client de discussion de groupe) peut se connecter à un pool à la fois pour Office Communications Server 2007 R2, Lync Server 2010, discussion de groupe ou Lync Server 2013.

Le client Lync 2013 (client) peut interagir uniquement avec Lync Server 2013, le pool de serveurs de chat permanent, et non avec les pools de serveurs de chat de groupe hérités. Pour utiliser la conversation permanente dans une 2013 Lync (client), l’utilisateur doit être hébergé sur Lync 2013 et activé par la stratégie.

</div>

<span> </span>

</div>

</div>

</div>

