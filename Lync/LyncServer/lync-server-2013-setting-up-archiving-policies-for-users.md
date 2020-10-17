---
title: 'Lync Server 2013 : configuration des stratégies d’archivage pour les utilisateurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Archiving policies for users
ms:assetid: 1bbb45df-0590-4c66-9d65-d25526f57790
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204722(v=OCS.15)
ms:contentKeyID: 48183549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f58d7b149c55d8daac9cb47f5e3ab0e1b4ea0596
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509731"
---
# <a name="setting-up-archiving-policies-for-users-in-lync-server-2013"></a>Configuration des stratégies d’archivage pour les utilisateurs dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-09_

Vous pouvez activer ou désactiver l’archivage pour des utilisateurs spécifiques en créant et en configurant une stratégie d’archivage pour les utilisateurs, puis en appliquant la stratégie à des utilisateurs spécifiques ou à des groupes d’utilisateurs. Les stratégies utilisateur remplacent les stratégies globales ou de site. Les stratégies d’archivage ne s’appliquent que si vous n’utilisez pas l’intégration de Microsoft Exchange ou, si vous utilisez l’intégration de Microsoft Exchange, mais que certains utilisateurs ne sont pas hébergés sur Exchange 2013 et que leurs boîtes aux lettres sont placées en conservation In-Place.

Pour plus d’informations sur le fonctionnement des stratégies d’archivage, notamment la hiérarchie pour les stratégies globale, de site et utilisateur, voir [How Archiving Works dans Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation ou Operations documentation.

<div>


> [!NOTE]  
> Si vous activez l’intégration de Microsoft Exchange pour votre déploiement, les stratégies de blocage Exchange In-Place déterminent si l’archivage est activé pour les utilisateurs hébergés sur Exchange 2013 et que leurs boîtes aux lettres sont placées en conservation In-Place. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configuration des stratégies d’archivage dans Lync Server 2013 lors de l’utilisation de l’intégration d’Exchange Server</A> dans la documentation de déploiement.<BR>Vous devez spécifier toutes les options appropriées dans les configurations de l’archivage avant d’activer l’archivage des communications internes ou externes dans les stratégies d’archivage. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-configuring-archiving-options.md">Configuration des options d’archivage dans Lync Server 2013</A> dans la documentation de déploiement.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configuration des stratégies utilisateur pour l’archivage dans Lync Server 2013](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md)

  - [Configuration des stratégies d’archivage dans Lync Server 2013 lors de l’utilisation de l’intégration d’Exchange Server](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

