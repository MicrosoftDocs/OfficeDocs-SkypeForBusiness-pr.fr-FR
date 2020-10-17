---
title: Colocalisation de serveur Lync Server 2013 dans un déploiement de pool frontal Enterprise Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in an Enterprise Edition Front End pool deployment
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48183287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0162a4338a1504ed425015e5b9391fca9903d4ab
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510281"
---
# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a>Colocalisation des serveurs dans un déploiement de pool frontal Enterprise Edition pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-11_

Cette section décrit les rôles serveur, les bases de données et les partages de fichiers que vous pouvez colocaliser dans un déploiement de pool frontal Lync Server 2013.

<div>

## <a name="server-roles"></a>Rôles serveur

Dans Lync Server 2013, le service de conférence A/V, le service de médiation, la surveillance et l’archivage sont colocalisés sur le serveur frontal, mais une configuration supplémentaire est nécessaire pour les activer. Si vous ne souhaitez pas colocaliser le serveur de médiation avec le serveur frontal, vous pouvez le déployer en tant que serveur de médiation autonome sur un ordinateur distinct.

Vous pouvez colocaliser un serveur d’application approuvées avec le serveur frontal.

Les rôles serveur suivants doivent être individuellement déployés sur un ordinateur distinct :

  - Directeur

  - Serveur Edge

  - Serveur de médiation (s’il n’est pas colocalisé avec le serveur frontal).

  - Office Web Apps Server

Vous ne pouvez pas colocaliser le rôle de serveur de conversation permanente avec le serveur frontal.

</div>

<div>

## <a name="databases"></a>Databases

Vous pouvez colocaliser chacune des bases de données suivantes sur le même serveur de base de données :

  - Base de données principale

  - Base de données de surveillance

  - Base de données d’archivage

  - Base de données de conversation permanente

  - Base de données de conformité de conversation permanente

Vous pouvez colocaliser une partie ou l’ensemble de ces bases de données dans une seule instance de SQL Server ou utiliser une instance distincte de SQL Server pour chacune d’elles, avec les limitations suivantes :

  - Chaque instance de SQL Server ne peut contenir qu’une seule base de données principale, une seule base de données de surveillance, une seule base de données d’archivage, une seule base de données de conversation permanente et une seule base de données de conformité de conversation permanente.

  - Le serveur de base de données ne peut pas prendre en charge plusieurs pools frontaux, un déploiement d’archivage et un déploiement de surveillance, mais il peut prendre en charge l’un d’entre eux, indépendamment du fait que les bases de données utilisent la même instance de SQL Server ou des instances distinctes de SQL Server.

Vous pouvez également colocaliser un partage de fichiers avec les bases de données comme il est indiqué plus loin dans cette section.

<div>


> [!NOTE]  
> Dans Lync Server 2013, vous avez la possibilité d’intégrer le stockage d’archivage au stockage Exchange 2013 pour tout ou partie des utilisateurs de votre déploiement. Vous ne pouvez pas déployer de serveurs exécutant Lync Server ou des composants sur les mêmes serveurs que le stockage Exchange.



</div>

<div>


> [!IMPORTANT]  
> Bien que la colocation des bases de données soit prise en charge, la taille des bases de données peut augmenter rapidement. Par exemple, lorsque vous envisagez de colocaliser la base de données d’archivage avec d’autres bases de données, sachez que si vous archivez les messages d’un certain nombre d’utilisateurs, les besoins en espace disque de la base de données du serveur d’archivage peuvent devenir très importants. Pour cette raison, nous vous déconseillons de colocaliser plusieurs bases de données, notamment la base de données d’archivage, la base de données de conversation permanente ou la base de données de conformité de conversation permanente avec la base de données principale.



</div>

</div>

<div>

## <a name="file-share"></a>Partage de fichiers

Le partage de fichier peut être un serveur distinct ou être colocalisé sur le même serveur que l’un ou l’ensemble des éléments suivants :

  - Serveur de base de données, y compris le serveur principal d’un pool frontal Enterprise Edition

  - Base de données d’archivage

  - Base de données de surveillance

  - Base de données de conversation permanente

  - Base de données de conformité de conversation permanente

Un partage de fichiers unique peut être utilisé pour plusieurs pools frontaux et serveurs Standard Edition (sur le même site).

<div>


> [!NOTE]  
> Dans Lync Server 2013, la surveillance et l’archivage utilisent le partage de fichiers Lync Server comme serveur frontal.



</div>

</div>

<div>

## <a name="other-components"></a>Autres composants

Vous ne pouvez pas colocaliser un serveur proxy inverse, qui n’est pas un composant Lync Server 2013, mais qui est requis dans votre déploiement si vous souhaitez prendre en charge le partage de contenu Web pour les utilisateurs fédérés avec un rôle serveur Lync Server 2013. Toutefois, vous pouvez implémenter la prise en charge du proxy inverse pour un déploiement Lync Server 2013 en configurant la prise en charge sur un serveur proxy inverse existant de votre organisation qui est utilisé pour d’autres applications.

Vous ne pouvez pas colocaliser un composant de messagerie unifiée Exchange ou un composant SharePoint avec un rôle SharePoint Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

