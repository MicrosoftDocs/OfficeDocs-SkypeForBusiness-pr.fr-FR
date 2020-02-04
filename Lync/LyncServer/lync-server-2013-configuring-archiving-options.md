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
ms.openlocfilehash: 9aa49aceacbd5053ead1af6b881be87c74b2ea30
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734874"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-in-lync-server-2013"></a>Configuration des options d’archivage dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-10_

Dans Lync Server 2013 panneau de configuration, vous utilisez des configurations d’archivage pour spécifier la façon dont l’archivage est implémenté. Cela inclut les configurations d’archivage suivantes :

  - Configuration globale créée par défaut lors du déploiement de Lync Server 2013.

  - Configurations facultatives de niveau de site et de niveau groupe que vous pouvez créer et utiliser pour spécifier la façon dont l’archivage est implémenté pour des sites ou des groupes spécifiques.

Vous définissez initialement des configurations d’archivage lors du déploiement de l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations après le déploiement. Dans Lync Server 2013 panneau de configuration, vous pouvez utiliser la page Configuration de l' **archivage** du groupe **archivage et surveillance** pour gérer les configurations au niveau global, au niveau du site et au niveau du pool. Pour plus d’informations sur l’implémentation des configurations d’archivage, notamment les options que vous pouvez spécifier et la hiérarchie des configurations d’archivage, voir fonctionnement [de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou les opérations. Pour plus d’informations sur la gestion des configurations après le déploiement, reportez-vous à la rubrique [gestion des options de configuration de l’archivage dans Lync Server 2013 pour votre organisation, sites et pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) dans la documentation sur les opérations.

<div>


> [!NOTE]  
> Pour utiliser l’archivage, vous devez configurer des stratégies d’archivage pour spécifier s’il convient d’activer l’archivage pour les communications internes, pour les communications externes ou pour les utilisateurs hébergés sur Lync Server 2013. Par défaut, l’archivage n’est pas activé pour les communications internes et externes. Avant d’activer l’archivage dans toutes les stratégies, vous devez spécifier les configurations d’archivage appropriées pour votre déploiement et, si vous le souhaitez, pour des sites et des groupes spécifiques, comme décrit dans cette section. Pour plus d’informations sur l’activation de l’archivage, voir <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configuration et affectation de stratégies d’archivage dans Lync Server 2013</A> dans la documentation de déploiement.<BR>Si vous n’utilisez pas l’intégration de Microsoft Exchange pour tous les utilisateurs de votre déploiement, vous devez configurer des stratégies d’archivage pour spécifier s’il convient d’activer l’archivage des communications internes, pour les communications externes ou pour les deux. Par défaut, l’archivage n’est pas activé pour les communications internes ou externes lors de l’archivage de données lors de l’utilisation de bases de données d’archivage Lync Server 2013. Avant l’activation de l’archivage dans toutes les stratégies, vous devez spécifier les configurations d’archivage appropriées pour votre déploiement et, si vous le souhaitez, pour des sites et des groupes spécifiques, comme décrit dans cette section. Pour plus d’informations sur l’activation de l’archivage pour une utilisation avec des bases de données d’archivage Lync Server 2013, voir <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configuration et affectation de stratégies d’archivage dans Lync server 2013</A> dans la documentation de déploiement.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configuration des options d’archivage au niveau global dans Lync Server 2013](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [Configuration des options d’archivage d’un site dans Lync Server 2013](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [Configuration des options d’archivage d’un pool dans Lync Server 2013](lync-server-2013-configuring-archiving-options-for-a-pool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

