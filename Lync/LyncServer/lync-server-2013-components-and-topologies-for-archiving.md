---
title: 'Lync Server 2013 : composants et topologies pour l’archivage'
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
ms.openlocfilehash: ec153b237df086f3622acc70c104bddc64fef28a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502611"
---
# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a>Composants et topologies pour l’archivage dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-09_

Si vous souhaitez archiver le contenu de messagerie instantanée et de conférence Lync Server 2013, vous pouvez implémenter l’archivage dans Lync Server.

<div>

## <a name="archiving-components"></a>Composants d’archivage

La fonctionnalité Archivage inclut les composants suivants :

  - **Argents d’archivage**. Les agents d’archivage (également connus sous le nom d’agents de collecte de données unifiée) sont installés et activés automatiquement sur chaque pool frontal et serveur Standard Edition. Bien que les agents d’archivage soient activés automatiquement, aucun message n’est réellement capturé tant que l’archivage n’est pas activé et correctement configuré.

  - **Stockage des données d’archivage**. Le stockage de données pour Lync Server 2013 peut être l’un des suivants :
    
      - Stockage Exchange 2013. Si vous activez l’option intégration de Microsoft Exchange, les boîtes aux lettres utilisateur hébergées sur le serveur Exchange 2013 utilisent le stockage Exchange 2013 pour les données archivées, mais uniquement si les boîtes aux lettres ont été placées en conservation In-Place.
    
      - Stockage SQL Server. Si certains de vos utilisateurs sont hébergés sur Lync Server 2013, vous pouvez configurer des bases de données d’archivage qui exécutent une version prise en charge de SQL Server afin d’activer l’archivage pour ces utilisateurs.

L’archivage nécessite également le stockage de fichiers. Toutefois, l’archivage utilise le même type de stockage de fichiers que les serveurs frontaux ou le serveur Standard Edition.

Pour obtenir la liste des configurations matérielle et logicielle requises pour l’archivage, voir [matériel pris en charge pour Lync server 2013](lync-server-2013-supported-hardware.md) et [Server Software and Infrastructure Support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) dans la documentation de prise en charge.

</div>

<div>

## <a name="supported-topologies"></a>Topologies prises en charge

Vous déployez l’archivage dans chaque pool où des utilisateurs ont besoin d’une prise en charge de d’archivage. L’archivage s’exécute sur les serveurs frontaux dans les pools Enterprise Edition et sur les serveurs Standard Edition. Le stockage des données d’archivage peut se présenter comme suit :

  - Intégration avec le stockage Exchange 2013

  - Déploiement à l’aide de bases de données SQL Server distinctes

Si votre déploiement Exchange 2013 n’inclut pas tous les utilisateurs dans votre déploiement Lync Server, vous devez utiliser l’intégration de Microsoft Exchange pour les utilisateurs dont les boîtes aux lettres sont hébergées sur des serveurs Exchange 2013 et vous devez déployer des bases de données SQL Server distinctes pour tous les autres utilisateurs Lync à utiliser pour l’archivage.

</div>

<div>

## <a name="supported-collocation"></a>Colocalisation prise en charge

Lync Server 2013 prend en charge un grand nombre de scénarios de colocalisation, ce qui vous permet d’économiser des coûts matériels en exécutant plusieurs composants sur un seul serveur (si vous avez une petite organisation) ou pour exécuter des composants individuels sur des serveurs différents (si votre organisation est de grande taille qui a besoin d’une évolutivité et de performances). Vous devez considérer les facteurs d’extensibilité avant de décider si vous allez colocaliser des composants.

L’archivage est déployé sur les serveurs frontaux d’un pool ou de serveurs Standard Edition. Pour plus d’informations sur les composants qui peuvent être colocalisés, voir [prise en charge de la colocalisation des serveurs dans Lync server 2013](lync-server-2013-supported-server-collocation.md) dans la documentation de prise en charge.

Si vous utilisez des bases de données SQL Server distinctes pour l’archivage, au lieu ou en plus de l’intégration du stockage au stockage Exchange 2013, vous pouvez colocaliser la base de données d’archivage avec l’un des éléments suivants :

  - Base de données de surveillance

  - Base de données principale d’un pool frontal Enterprise Edition

<div>


> [!NOTE]  
> Le serveur qui héberge la base de données d’archivage peut également héberger d’autres bases de données. Toutefois, quand vous envisagez de colocaliser la base de données d’archivage avec d’autres bases de données, sachez que si vous archivez les messages d’un certain nombre d’utilisateurs, les besoins en espace disque de la base de données d’archivage peuvent devenir très importants. C’est la raison pour laquelle nous vous déconseillons de colocaliser la base de données d’archivage avec la base de données principale.



</div>

Si vous colocalisez la base de données d’archivage avec la base de données de surveillance, la base de données principale ou les deux à la fois, vous avez le choix entre utiliser une instance SQL unique pour la ou les bases de données ou utiliser une instance SQL distincte pour chaque base de données, tout en sachant qu’il existe les limitations suivantes :

  - Chaque instance SQL ne peut contenir qu’une seule base de données principale, une base de données de surveillance unique et une base de données d’archivage unique.

Pour plus d’informations sur la colocalisation de tous les rôles serveur et bases de données, voir [prise en charge de la colocalisation des serveurs dans Lync server 2013](lync-server-2013-supported-server-collocation.md) dans la documentation de prise en charge.

</div>

</div>

<span> </span>

</div>

</div>

</div>

