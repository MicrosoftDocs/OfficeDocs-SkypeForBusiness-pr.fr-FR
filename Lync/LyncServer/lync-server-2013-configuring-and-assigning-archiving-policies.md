---
title: 'Lync Server 2013 : configuration et affectation de stratégies d’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and assigning Archiving policies
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205175(v=OCS.15)
ms:contentKeyID: 48185121
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7db876d03f7322fae5f3a55f88708fe4165a20ba
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-and-assigning-archiving-policies-in-lync-server-2013"></a>Configuration et affectation de stratégies d’archivage dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-01_

Dans Lync Server 2013, vous utilisez des stratégies pour activer et désactiver l’archivage pour les communications internes et les communications externes pour les utilisateurs hébergés sur Lync Server 2013. Il s’agit notamment des stratégies d’archivage suivantes :

  - Stratégie globale créée par défaut lorsque vous déployez Lync Server 2013.

  - Stratégies facultatives au niveau site et utilisateur que vous pouvez créer et utiliser pour définir de quelle manière l’archivage est implémenté pour des sites ou utilisateurs spécifiques.

Vous définissez les stratégies d’archivage lors du déploiement initial de l’archivage, mais vous pouvez modifier et supprimer des stratégies existantes, ou en ajouter de nouvelles, à tout moment après le déploiement. Dans le panneau de configuration Lync Server 2013, vous pouvez utiliser la page **stratégie d’archivage** du groupe **archivage et surveillance** pour gérer les stratégies au niveau global, au niveau du site et au niveau de l’utilisateur.

<div>


> [!NOTE]  
> Pour contrôler l’implémentation de l’archivage, vous devez définir certaines options de configuration de l’archivage, notamment spécifier si les messages instantanés ou les conférences doivent être archivés, si le mode critique est utilisé et les options de vidage. Par défaut, aucune option n’est activée dans la configuration de l’archivage global ni dans la configuration de l’archivage de site ou de pool. Vous devez définir toutes les options appropriées dans les configurations de l’archivage avant d’activer l’archivage des communications internes ou externes dans les stratégies d’archivage. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for Your Organization, sites, and pools</A> dans la documentation des opérations.<BR>Si vous intégrez votre stockage Lync Server au stockage Exchange 2013, les stratégies d’utilisateur Exchange prévalent sur les stratégies d’archivage Lync Server 2013, mais uniquement pour les utilisateurs hébergés sur Exchange 2013 dont les boîtes aux lettres ont été placées en conservation inaltérable.



</div>

Pour plus d’informations sur l’implémentation des stratégies, y compris la hiérarchie des stratégies, voir [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations. Pour plus d’informations sur la gestion des stratégies après le déploiement, voir [Managing the Archiving of Internal and External Communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) dans la documentation des opérations.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configuration de la stratégie globale pour l’archivage dans Lync Server 2013](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [Configuration des stratégies de site pour l’archivage dans Lync Server 2013](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [Configuration des stratégies d’archivage pour les utilisateurs dans Lync Server 2013](lync-server-2013-setting-up-archiving-policies-for-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

