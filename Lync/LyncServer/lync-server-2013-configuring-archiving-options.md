---
title: 'Lync Server 2013 : configuration des options d’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options
ms:assetid: b2f7f74d-e1ad-494e-9d46-5eb0efe5fb29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205182(v=OCS.15)
ms:contentKeyID: 48185158
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 243414dea5b7ca411e4511c3a82f269c9981147e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049776"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-in-lync-server-2013"></a>Configuration des options d’archivage dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-10_

Dans le panneau de configuration Lync Server 2013, vous utilisez des configurations d’archivage pour spécifier le mode d’implémentation de l’archivage. Les configurations d’archivage sont les suivantes :

  - Une configuration globale qui est créée par défaut lorsque vous déployez Lync Server 2013.

  - Configurations facultatives au niveau du site et au niveau du pool que vous pouvez créer et utiliser pour spécifier la manière d’implémenter l’archivage de sites ou de pools spécifiques.

Vous commencez par définir des configurations d’archivage lorsque vous déployez l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations à l’issue du déploiement. Dans le panneau de configuration Lync Server 2013, vous pouvez utiliser la page Configuration de l' **archivage** du groupe **archivage et surveillance** pour gérer les configurations au niveau global, au niveau du site et au niveau du pool. Pour plus d’informations sur l’implémentation des configurations d’archivage, notamment les options que vous pouvez spécifier et la hiérarchie des configurations d’archivage, voir [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations. Pour plus d’informations sur la gestion des configurations après le déploiement, voir [Managing Archiving configuration options in Lync Server 2013 for Your Organization, sites, and pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) dans la documentation des opérations.

<div>


> [!NOTE]  
> Pour utiliser l’archivage, vous devez configurer des stratégies d’archivage pour spécifier s’il faut activer l’archivage pour les communications internes, pour les communications externes ou pour les deux pour les utilisateurs hébergés sur Lync Server 2013. Par défaut, l’archivage n’est pas activé pour les communications internes ou externes. Avant d’activer l’archivage dans des stratégies, vous devez spécifier les configurations d’archivage appropriées pour votre déploiement et, éventuellement, pour des sites et pools spécifiques, comme décrit dans cette section. Pour plus d’informations sur l’activation de l’archivage, voir <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving Policies in Lync Server 2013</A> dans la documentation de déploiement.<BR>Si vous n’utilisez pas l’intégration de Microsoft Exchange pour tous les utilisateurs de votre déploiement, vous devez configurer des stratégies d’archivage pour spécifier s’il faut activer l’archivage pour les communications internes, pour les communications externes ou pour les deux. Par défaut, l’archivage n’est pas activé pour les communications internes ou externes pour l’archivage des données lors de l’utilisation des bases de données d’archivage Lync Server 2013. Avant d’activer l’archivage dans des stratégies, vous devez spécifier les configurations d’archivage appropriées pour votre déploiement et, éventuellement, pour des sites et pools spécifiques, comme décrit dans la section. Pour plus d’informations sur l’activation de l’archivage pour une utilisation avec les bases de données d’archivage de Lync Server 2013, reportez-vous à la rubrique <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configuration et affectation de stratégies d’archivage dans Lync server 2013</A> dans la documentation de déploiement.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configuration des options d’archivage au niveau global dans Lync Server 2013](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [Configuration des options d’archivage pour un site dans Lync Server 2013](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [Configuration des options d’archivage pour un pool dans Lync Server 2013](lync-server-2013-configuring-archiving-options-for-a-pool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

