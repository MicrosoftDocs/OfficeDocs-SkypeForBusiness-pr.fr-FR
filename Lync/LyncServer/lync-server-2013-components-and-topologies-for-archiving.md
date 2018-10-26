---
title: 'Lync Server 2013 : Composants et topologies utilisés pour l’archivage'
TOCTitle: Composants et topologies utilisés pour l’archivage
ms:assetid: 5893063d-a44a-4034-aba9-cbe883ecf710
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204916(v=OCS.15)
ms:contentKeyID: 49297307
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Composants et topologies utilisés pour l’archivage dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-09_

Si vous souhaitez archiver le contenu des sessions de messagerie instantanée et de conférence de Lync Server 2013, vous pouvez implémenter l’archivage dans Lync Server.

## Composants d’archivage

La fonctionnalité Archivage inclut les composants suivants :

  - **Argents d’archivage**. Les agents d’archivage (également connus sous le nom d’agents de collecte de données unifiée) sont installés et activés automatiquement sur chaque pool frontal et serveur Standard Edition. Même si les agents d’archivage sont activés automatiquement, aucun message n’est réellement capturé tant que l’archivage n’est pas activé et correctement configuré.

  - **Stockage des données d’archivage**. Les données d’archivage de Lync Server 2013 sont les suivantes :
    
      - Stockage Exchange 2013. Si vous activez l’option d’intégration de Microsoft Exchange, les boîtes aux lettres utilisateurs hébergées sur le serveur Exchange 2013 utilisent le stockage Exchange 2013 pour les données archivées, mais uniquement si ces boîtes aux lettres sont placées en archive permanente.
    
      - Stockage SQL Server. Si des utilisateurs de votre déploiement sont hébergés sur Lync Server 2013, vous pouvez configurer l’archivage des bases de données qui exécutent une version prise en charge de SQL Server afin d’activer l’archivage pour ces utilisateurs.

L’archivage nécessite également le stockage de fichiers. Cependant, l’archivage utilise le même type de stockage de fichiers que les serveurs frontaux ou le serveur Standard Edition.

Pour obtenir une liste des configurations matérielles et logicielles nécessaires à l’archivage, reportez-vous à [Matériel pris en charge pour Lync Server 2013](lync-server-2013-supported-hardware.md) et [Prise en charge des infrastructures et des logiciels de serveur dans Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) dans la documentation de prise en charge.

## Topologies prises en charge

Vous déployez l’archivage dans chaque pool où des utilisateurs ont besoin d’une prise en charge de d’archivage. L’archivage fonctionne sur les serveurs frontaux dans les pools Enterprise Edition et sur n’importe quel serveurs Standard Edition. Le stockage des données d’archivage peut se présenter comme suit :

  - intégré au stockage Exchange 2013 ;

  - déployé à l’aide de bases de données SQL Server distinctes.

Si votre déploiement d’Exchange 2013 n’inclut pas tous les utilisateurs de votre déploiement de Lync Server, vous devez utiliser l’intégration de Microsoft Exchange pour les utilisateurs dont les boîtes aux lettres sont hébergées sur des serveurs Exchange 2013. Par ailleurs, vous devez déployer des bases de données SQL Server distinctes utilisables par les autres utilisateurs Lync pour l’archivage.

## Colocalisation prise en charge

Lync Server 2013 prend en charge divers scénarios de colocalisation, ce qui vous permet d’économiser des coûts de matériel en exécutant plusieurs composants sur un serveur (si votre entreprise est de petite taille) ou d’exécuter des composants individuels sur différents serveurs (si votre entreprise de taille plus grande a des besoins plus importants en termes d’extensibilité et de performances). Vous devez considérer les facteurs d’extensibilité avant de décider si vous allez colocaliser des composants.

L’archivage est déployé sur les serveurs frontaux d’un pool ou sur des serveurs Standard Edition. Pour plus d’informations sur les composants qui peuvent être colocalisés, reportez-vous à [Colocalisation de serveur prise en charge dans Lync Server 2013](lync-server-2013-supported-server-collocation.md) dans la documentation de prise en charge.

Si vous utilisez des bases de données SQL Server distinctes pour l’archivage, à la place ou en plus de l’intégration du stockage au stockage Exchange 2013, vous pouvez colocaliser la base de données d’archivage avec l’un des éléments suivants :

  - base de données de surveillance

  - Base de données principale d’un pool frontal Enterprise Edition

> [!NOTE]  
> Le serveur qui héberge la base de données d’archivage peut également héberger d’autres bases de données. Cependant, quand vous envisagez de colocaliser la base de données d’archivage avec d’autres bases de données, sachez que si vous archivez les messages d’un certain nombre d’utilisateurs, les besoins en espace disque de la base de données d’archivage peuvent devenir très importants. C’est la raison pour laquelle nous vous déconseillons de colocaliser la base de données d’archivage avec la base de données principale.

Si vous colocalisez la base de données d’archivage avec la base de données de surveillance, la base de données principale ou les deux à la fois, vous avez le choix entre utiliser une instance SQL unique pour la ou les bases de données ou utiliser une instance SQL distincte pour chaque base de données, tout en sachant qu’il existe les limitations suivantes :

  - Chaque instance SQL ne peut contenir qu’une seule base de données principale, une base de données de surveillance unique et une base de données d’archivage unique.

Pour plus d’informations sur la colocalisation de tous les rôles serveur et de toutes les bases de données, reportez-vous à [Colocalisation de serveur prise en charge dans Lync Server 2013](lync-server-2013-supported-server-collocation.md) dans la documentation de prise en charge.

