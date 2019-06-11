---
title: Colocalisation de serveur Lync Server 2013 lors d’un déploiement de pool frontal Enterprise Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server collocation in an Enterprise Edition Front End pool deployment
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48183287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6947d732cf17cc053e48596ffd310f5df3b11636
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a>Colocalisation de serveur lors d’un déploiement de pool frontal Enterprise Edition pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-11-11_

Cette section décrit les rôles de serveur, les bases de données et les partages de fichiers que vous pouvez collocate dans un déploiement de pool frontal Lync Server 2013.

<div>

## <a name="server-roles"></a>Rôles de serveur

Dans Lync Server 2013, le service de conférence A/V, le service de médiation, la surveillance et l’archivage sont localisés sur le serveur frontal, mais une configuration supplémentaire est nécessaire pour les activer. Si vous ne voulez pas que collocate le serveur de médiation du serveur frontal, vous pouvez le déployer en tant que serveur de médiation autonome sur un autre ordinateur.

Vous pouvez collocate un serveur d’applications de confiance auprès du serveur frontal.

Les rôles serveur suivants doivent être déployés sur un autre ordinateur:

  - directeur

  - serveur Edge

  - Serveur de médiation (en cas de non-colocalisé avec le serveur frontal)

  - Office Web Apps Server

Vous ne pouvez pas collocate le rôle serveur de chat permanent avec le serveur frontal.

</div>

<div>

## <a name="databases"></a>Bases de données

Vous pouvez collocater les bases de données suivantes sur le même serveur de base de données:

  - Base de données principale

  - base de données de surveillance

  - base de données d’archivage

  - Base de données de conversation permanente

  - Base de données de compatibilité des conversations permanentes

Vous pouvez collocate tout ou partie de ces bases de données dans une instance unique de SQL Server ou utiliser une instance distincte de SQL Server pour chacune d’elles, avec les limitations suivantes:

  - Chaque instance de SQL Server peut contenir uniquement une seule base de données principale, une base de données de surveillance unique, une base de données d’archivage unique, une seule base de données de chat permanent et une seule et même base de données de conformité des conversations permanentes.

  - Le serveur de base de données ne peut pas prendre en charge plus d’un pool frontal, un déploiement d’archivage et un déploiement de la surveillance, mais il peut prendre en charge l’un de ceux-ci, que les bases de données utilisent ou non la même instance de SQL Server, ou des instances distinctes de SQL Server.

Vous pouvez collocate un partage de fichiers avec les bases de données, comme décrit plus loin dans cette section.

<div>


> [!NOTE]  
> Dans Lync Server 2013, vous avez la possibilité d’intégrer le stockage d’archivage avec le stockage Exchange 2013 pour tout ou partie de votre déploiement. Vous ne pouvez pas déployer des serveurs exécutant Lync Server ou des composants sur les mêmes serveurs que le stockage Exchange.



</div>

<div>


> [!IMPORTANT]  
> Même si la colocalisation des bases de données est prise en charge, la taille de celles-ci peut être rapidement augmentée. Par exemple, lorsque vous considérez collocating la base de données d’archivage avec d’autres bases de données, sachez que, si vous archivez les messages de plus de quelques utilisateurs, l’espace disque requis par la base de données d’archivage peut devenir très volumineux. C’est pourquoi nous vous déconseillons de collocating plusieurs bases de données, en particulier de la base de données d’archivage, de la base de données de chat permanent ou de la base de données de conformité des conversations permanentes avec la base de données principale.



</div>

</div>

<div>

## <a name="file-share"></a>Partage de fichiers

Le partage de fichiers peut être un serveur distinct ou être colocalisé sur le même serveur que tout ou partie des éléments suivants:

  - Serveur de base de données, y compris le serveur principal d’un pool frontal Enterprise Edition

  - base de données d’archivage

  - base de données de surveillance

  - Base de données de conversation permanente

  - Base de données de compatibilité des conversations permanentes

Un partage de fichiers unique peut être utilisé pour plusieurs listes frontales, serveurs Standard Edition (tous sur le même site).

<div>


> [!NOTE]  
> Dans Lync Server 2013, la surveillance et l’archivage utilisent le partage de fichiers Lync Server comme serveur frontal.



</div>

</div>

<div>

## <a name="other-components"></a>Autres composants

Vous ne pouvez pas collocate un serveur proxy inverse, qui n’est pas un composant Lync Server 2013, mais qui est requis dans votre déploiement si vous souhaitez prendre en charge le partage de contenu Web pour les utilisateurs fédérés possédant un rôle Server 2013 serveur Lync. Toutefois, vous pouvez implémenter la prise en charge du proxy inverse pour un déploiement de Lync Server 2013 en configurant le support sur un serveur de proxy inverse existant dans votre organisation qui est utilisé pour d’autres applications.

Vous ne pouvez pas collocate un composant de messagerie unifiée Exchange ou un composant SharePoint avec un rôle serveur SharePoint.

</div>

</div>

<span> </span>

</div>

</div>

</div>

