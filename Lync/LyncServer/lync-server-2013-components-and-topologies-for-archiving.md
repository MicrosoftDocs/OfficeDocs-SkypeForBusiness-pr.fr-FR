---
title: 'Lync Server 2013 : Composants et topologies utilisés pour l’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Archiving
ms:assetid: 5893063d-a44a-4034-aba9-cbe883ecf710
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204916(v=OCS.15)
ms:contentKeyID: 48184213
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3ccb77d8d2d0b7bd7d4d564087a69b7605863fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a>Composants et topologies utilisés pour l’archivage dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-09_

Si vous souhaitez archiver du contenu de messagerie instantanée et de conférences Lync Server 2013, vous pouvez implémenter l’archivage dans Lync Server.

<div>

## <a name="archiving-components"></a>Archivage des composants

La fonctionnalité d’archivage inclut les composants suivants :

  - **Argents d’archivage**. Les agents d’archivage (également appelés agents de collection de données unifiées) sont installés et activés automatiquement sur chaque pool frontal et serveur Standard Edition. Bien que les agents d’archivage soient activés automatiquement, aucun message n’est réellement capturé tant qu’il n’est pas activé et configuré de manière appropriée.

  - **Archivage du stockage des données**. Le stockage de données pour Lync Server 2013 peut être l’un des éléments suivants :
    
      - Stockage 2013 Exchange. Si vous activez l’option d’intégration de Microsoft Exchange, les boîtes aux lettres d’utilisateur hébergées sur le serveur Exchange 2013 utilisent le stockage Exchange 2013 pour les données archivées, mais uniquement si celles-ci sont placées sur le blocage sur place.
    
      - Stockage SQL Server. Si votre déploiement comporte des utilisateurs qui sont hébergés sur Lync Server 2013, vous pouvez configurer des bases de données d’archivage qui exécutent une version prise en charge de SQL Server pour permettre l’archivage de ces utilisateurs.

L’archivage nécessite également le stockage de fichiers, mais l’archivage utilise le même stockage de fichiers que le serveur frontal ou les serveurs Standard Edition.

Pour obtenir la liste des configurations matérielles et logicielles requises pour l’archivage, voir [matériel compatible pour Lync server 2013](lync-server-2013-supported-hardware.md) et les [logiciels et l’infrastructure pris en charge dans Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) dans la documentation sur la prise en charge.

</div>

<div>

## <a name="supported-topologies"></a>Topologies prises en charge

Le déploiement de l’archivage dans chaque liste incluant des utilisateurs nécessitent une prise en charge de l’archivage. L’archivage s’exécute sur les serveurs frontaux dans les groupes Enterprise Edition et sur les serveurs Standard Edition Server. Le stockage des données d’archivage peut être ce qui suit :

  - Intégration avec le stockage 2013 Exchange

  - Déploiement à l’aide de bases de données SQL Server distinctes

Si votre déploiement d’Exchange 2013 n’inclut pas tous les utilisateurs dans le déploiement de Lync Server, vous devez utiliser l’intégration de Microsoft Exchange pour les utilisateurs dont la boîte aux lettres est située sur les serveurs Exchange 2013 et vous devez déployer des bases de données SQL Server distinctes pour toutes les autres. Utilisateurs de Lync à utiliser pour l’archivage.

</div>

<div>

## <a name="supported-collocation"></a>Colocalisation prises en charge

Lync Server 2013 prend en charge un large éventail de scénarios de colocalisation, qui vous permettent de gagner en souplesse en exécutant plusieurs composants sur un serveur (si vous disposez d’une petite organisation) ou pour exécuter des composants individuels sur différents serveurs (si vous avez une plus grande Organisation nécessitant une évolutivité et des performances optimales. Prenez en compte les facteurs d’évolutivité avant de décider de collocater ou non les composants.

L’archivage est déployé sur les serveurs front-end d’une réserve ou d’un serveur Standard Edition Server. Pour plus d’informations sur les composants qui peuvent être colocalisés à partir de cet emplacement, voir [prise en charge de la coexistence du serveur dans Lync server 2013](lync-server-2013-supported-server-collocation.md) dans la documentation de support.

Si vous utilisez des bases de données SQL Server distinctes pour l’archivage, au lieu de ou en plus de l’intégration de stockage avec le stockage 2013 Exchange, vous pouvez collocate la base de données d’archivage de l’une des façons suivantes :

  - Base de données de surveillance

  - Base de données principale d’un pool frontal Enterprise Edition

<div>


> [!NOTE]  
> Le serveur qui héberge la base de données d’archivage peut également héberger d’autres bases de données. Cependant, quand vous envisagez de colocaliser la base de données d’archivage avec d’autres bases de données, sachez que si vous archivez les messages d’un certain nombre d’utilisateurs, les besoins en espace disque de la base de données d’archivage peuvent devenir très importants. C’est la raison pour laquelle nous vous déconseillons de colocaliser la base de données d’archivage avec la base de données principale.



</div>

Si vous collocate la base de données d’archivage avec la base de données de surveillance, la base de données principale, ou les deux, vous pouvez utiliser une instance SQL unique pour tout ou partie des bases de données, ou vous pouvez utiliser une instance SQL distincte pour chaque base de données, comme suit : modér

  - Chaque instance SQL ne peut contenir qu’une seule base de données principale, une base de données de surveillance unique et une seule base de données d’archivage.

Pour plus d’informations sur la colocalisation de tous les rôles de serveur et bases de données, voir [prise en charge de la colocalisation du serveur dans Lync server 2013](lync-server-2013-supported-server-collocation.md) dans la documentation de prise en charge.

</div>

</div>

<span> </span>

</div>

</div>

</div>

