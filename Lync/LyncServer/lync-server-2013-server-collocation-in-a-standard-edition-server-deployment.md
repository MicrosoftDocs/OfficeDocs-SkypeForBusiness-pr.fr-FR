---
title: Colocalisation de serveur Lync Server 2013 lors d’un déploiement de serveur Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server collocation in a Standard Edition server deployment
ms:assetid: 0763ffab-4fd6-463a-8e62-d97876b376d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398131(v=OCS.15)
ms:contentKeyID: 48183314
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 950f2ab06a146ec99ef9ebb2ecbc64c885c82d70
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a>Colocalisation de serveur lors d’un déploiement de serveur Standard Edition pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-01-20_

Cette section décrit les rôles de serveur, les bases de données et les partages de fichiers que vous pouvez collocate dans un déploiement Lync Server 2013 Standard Edition Server.

<div>

## <a name="server-roles"></a>Rôles de serveur

Dans Lync Server 2013, le service de conférence A/V, le service de médiation, la surveillance et l’archivage sont localisés sur le serveur Standard Edition Server, mais une configuration supplémentaire est nécessaire pour les activer. Vous pouvez choisir de déployer le service de médiation sur des serveurs distincts.

Vous pouvez collocate un serveur d’applications de confiance auprès d’un serveur Standard Edition Server.

Les rôles serveur suivants doivent être déployés sur un autre ordinateur:

  - directeur

  - serveur Edge

  - Serveur de médiation (en cas d’absence de colocalisé avec le serveur Standard Edition Server)

  - Office Web Apps Server

</div>

<div>

## <a name="databases"></a>Bases de données

Par défaut, la base de données principale SQL Server Express est colocalisée sur le serveur Standard Edition Server. Vous ne pouvez pas le déplacer vers un autre ordinateur. En revanche, vous ne pouvez pas collocate d’autres bases de données sur un serveur Standard Edition Server. Si vous choisissez de déployer le serveur de chat permanent sur un serveur Standard Edition Server, vous pouvez collocate la base de données de chat permanent et la base de données de conformité des conversations permanentes sur le même serveur Standard Edition Server.

Vous pouvez collocater les bases de données suivantes sur un serveur de base de données unique:

  - base de données de surveillance

  - base de données d’archivage

  - Une base de données principale pour une liste frontale Enterprise Edition

Vous pouvez collocate tout ou partie de ces bases de données dans une instance SQL unique ou utiliser des instances SQL distinctes pour chacune d’elles, avec les limitations suivantes:

  - Chaque instance SQL ne peut contenir qu’une seule base de données principale (pour un pool frontal Enterprise Edition), une base de données de surveillance unique, une base de données d’archivage unique, une base de données de chat permanent unique et une seule base de données de conformité des conversations permanentes.

  - Le serveur de base de données ne peut pas prendre en charge plus d’une liste frontale Enterprise Edition, un serveur exécutant l’archivage, un serveur exécutant la surveillance, une seule base de données de chat permanent et une seule base de données de conformité des conversations permanentes, mais elle peut prendre en charge l’une de chacune d’elles. que les bases de données utilisent ou non la même instance de SQL Server, ou des instances distinctes de SQL Server.

Vous pouvez collocate un partage de fichiers avec les bases de données, comme décrit plus loin dans cette section.

<div>


> [!NOTE]  
> Dans Lync Server 2013, vous avez la possibilité d’intégrer le stockage de la surveillance et de l’archivage avec le stockage Exchange 2013 pour tout ou partie de votre déploiement. Vous ne pouvez pas déployer des serveurs exécutant Lync Server ou des composants sur les mêmes serveurs que le stockage Exchange.



</div>

<div>


> [!IMPORTANT]  
> Même si la colocalisation des bases de données est prise en charge, la taille de celles-ci peut être rapidement augmentée. Par exemple, lorsque vous considérez collocating la base de données d’archivage avec d’autres bases de données, sachez que, si vous archivez les messages de plus de quelques utilisateurs, l’espace disque requis par la base de données d’archivage peut devenir très volumineux. C’est pourquoi nous vous déconseillons de collocating plusieurs bases de données, en particulier de la base de données d’archivage, de la base de données de chat persistant et de la base de données de conformité des conversations permanentes avec la base de données principale d’un pool d’entreprise.



</div>

</div>

<div>

## <a name="file-shares"></a>Partages de fichiers

Le partage de fichiers peut être un serveur distinct ou être colocalisé sur le même serveur que tout ou partie des éléments suivants:

  - Serveur de base de données, y compris le serveur principal d’un pool frontal Enterprise Edition

  - base de données d’archivage

  - base de données de surveillance

  - Base de données de conversation permanente

  - Base de données de compatibilité des conversations permanentes

Un partage de fichiers unique peut être utilisé pour plusieurs listes frontales, serveurs Standard Edition (tous sur le même site).

<div>


> [!NOTE]  
> Dans Lync Server 2013, la surveillance et l’archivage utilisent le partage de fichiers Lync Server comme serveur Standard Edition Server.



</div>

</div>

<div>

## <a name="other-components"></a>Autres composants

Vous ne pouvez pas collocate un serveur proxy inverse, qui n’est pas un composant Lync Server 2013, mais qui est requis dans votre déploiement si vous souhaitez prendre en charge le partage de contenu Web pour les utilisateurs fédérés possédant un rôle Server 2013 serveur Lync. Toutefois, vous pouvez implémenter la prise en charge du proxy inverse pour un déploiement de Lync Server 2013 en configurant le support sur un serveur de proxy inverse existant dans votre organisation qui est utilisé pour d’autres applications.

Vous ne pouvez pas collocate un composant Exchange UM ou un composant SharePoint avec un rôle Lync Server 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

