---
title: Considérations relatives à la coexistence
description: Considérations relatives à la coexistence.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: fd1f9525b37bdee3249e0e47352fdea1bc7f012f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547030"
---
# <a name="coexistence-considerations"></a>Considérations relatives à la coexistence

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-06_

Après la migration, seul un pool de serveurs Lync Server 2013, persistent chat existe et vous pouvez mettre hors service votre déploiement hérité.

Avant la fin de la migration et avant que vous n’ayez désactivé entièrement votre déploiement actuel du serveur de conversation de groupe, vous pouvez avoir l’un des déploiements suivants :

  - Lync Server 2013, pool de serveurs de conversation permanente, qui doit être hébergé sur un pool Lync Server 2013.

  - Lync Server 2010, pool de conversation de groupe, qui doit être hébergé sur un pool Lync Server 2010.

  - Pool de conversation de groupe Office Communications Server 2007 R2, qui doit être hébergé sur un pool Office Communications Server 2007 R2.

Ces déploiements peuvent exister côte à côte. Toutefois, les catégories, les salles et les compléments d’un déploiement n’interagissent pas avec ceux du déploiement associé.

À l’aide de la configuration manuelle, un client hérité (client de conversation de groupe) peut se connecter à un pool à la fois pour Office Communications Server 2007 R2, Lync Server 2010, Group chat ou Lync Server 2013.

Le Lync 2013 (client) ne peut interagir qu’avec le pool de serveurs Lync Server 2013, persistent chat, pas avec les pools de serveurs de conversation de groupe hérités. Pour utiliser la conversation permanente dans un Lync 2013 (client), l’utilisateur doit être hébergé sur Lync 2013 et activé par la stratégie.

</div>

<span> </span>

</div>

</div>

</div>

