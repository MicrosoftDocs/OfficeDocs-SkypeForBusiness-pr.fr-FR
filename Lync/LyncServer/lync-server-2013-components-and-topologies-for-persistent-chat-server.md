---
title: "Lync Server 2013 : Composants et topo. utilisés pour le serv. de conv. Perm."
TOCTitle: Composants et topologies utilisés pour le serveur de conversation permanente
ms:assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398500(v=OCS.15)
ms:contentKeyID: 49297502
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Composants et topologies utilisés pour le serveur de conversation permanente dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-05_

Le serveur de conversations permanentes prend en charge les configurations à serveur unique et celles à plusieurs serveurs. Le serveur de conversations permanentes peut également s’exécuter sur un serveur Standard EditionLync Server 2013. Ces configurations incluent les topologies et composants suivants du serveur de conversations permanentes.

## Composants du serveur de conversations permanentes

L’installation de la dernière version du serveur de conversations permanentes nécessite les composants suivants :

  - Un ou plusieurs ordinateurs exécutant serveur de conversations permanentes et fournissant les services suivants :
    
      - Service de conversation permanente
    
      - Service de conformité, activé si la conformité est activée
    
    > [!IMPORTANT]  
    > Dans Lync Server 2013, les services web de conversation permanente pour le téléchargement de fichier sont à présent colocalisés avec le serveur frontalLync Server 2013.<br />
    Les services web de conversation permanente pour la gestion des salles de conversation sont à présent colocalisés avec le serveur frontalLync Server 2013.

  - Un ou plusieurs serveurs (plusieurs serveurs en cas d’utilisation de la mise en miroir) qui hébergent la base de données principale SQL Server pour l’hébergement de la base de données de contenu de conversation permanente où sont stockés le contenu de la salle de conversation, les salles et les catégories.
    
    > [!NOTE]  
    > La base de données principale stocke les données de l’historique de conversation, dont des informations sur les catégories et les salles de conversation permanente créées.

  - Si la conformité a été activée, un ou plusieurs serveurs (plusieurs serveurs en cas d’utilisation de la mise en miroir) qui hébergent la base de données principale SQL Server pour l’hébergement de la base de données de conformité de conversation permanente où sont stockés les événements de conformité et le contenu des conversations à des fins de conformité.

Pour administrer le serveur de conversations permanentes à partir d’un ordinateur distinct (par exemple, une console d’administration), utilisez le Panneau de configuration Lync Server sur l’ordinateur. Cet ordinateur doit alors être déployé dans un domaine services de domaine Active Directory, avec au moins un serveur de catalogue global à la racine de la forêt.

Pour plus d’informations sur la configuration matérielle et logicielle requise pour le serveur de conversations permanentes, reportez-vous à [Configuration technique requise pour le serveur de conversation permanente dans Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [Matériel pris en charge pour Lync Server 2013](lync-server-2013-supported-hardware.md) et [Prise en charge des infrastructures et des logiciels de serveur dans Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) dans la documentation de prise en charge.

## Colocalisation prise en charge

Lync Server 2013 prend en charge divers scénarios de colocalisation, ce qui vous permet d’économiser des coûts de matériel en exécutant plusieurs composants sur un serveur physique (si votre entreprise est de petite taille) ou d’exécuter des composants distincts sur différents serveurs (si votre entreprise de taille plus grande a des besoins plus importants en termes d’extensibilité et de performances). Vous devez considérer les facteurs d’extensibilité avant de décider si vous allez colocaliser des composants.

Le service de conformité conversation permanente, si la conformité est activée, est colocalisée avec le serveur frontalLync Server 2013.

Le serveur de conversations permanentes peut être déployé sur le serveur Standard Edition. Le serveur principal du serveur de conversations permanentes et la base de données de conformité de conversation permanente peuvent être colocalisés sur le serveur Standard Edition sur le serveur principalSQL Server Express local. Pour plus d’informations sur les composants qui peuvent être colocalisés à cet endroit, reportez-vous à [Colocalisation de serveur prise en charge dans Lync Server 2013](lync-server-2013-supported-server-collocation.md) dans la documentation de prise en charge.

Pour Lync Server 2013Enterprise Edition, il est impossible de colocaliser des serveurs de conversations permanentes sur le serveur Enterprise Edition. La base de données SQL Server pour le serveur de conversations permanentes peut être colocalisée avec la base de données du serveur principal d’un pool de serveurs frontauxEnterprise Edition. La base de données SQL Server pour la conformité de la conversation permanente peut aussi être colocalisée avec la base de données du serveur principal d’un pool Enterprise Edition.

> [!IMPORTANT]  
> Le serveur qui héberge la base de données de conversation permanente peut héberger d’autres bases de données. Cependant, lorsque vous envisagez de colocaliser la base de données de conversation permanente avec d’autres bases de données, sachez que si vous stockez les messages d’un certain nombre d’utilisateurs, les besoins en espace disque de la base de données de conversation permanente peuvent devenir très importants. Pour cette raison, nous ne recommandons pas de colocaliser la base de données de conversation permanente avec la base de données principale.

Si vous colocalisez la base de données de conversation permanente avec la base de données principale, vous pouvez soit utiliser une instance unique de SQL Server pour une partie ou la totalité des bases de données, soit utiliser une instance distincte de SQL Server pour chaque base de données, avec les limitations suivantes :

  - Chaque instance de SQL Server ne peut contenir qu’une seule base de données principale et une base de données de conversation permanente unique.

Pour plus d’informations sur la colocalisation de tous les rôles serveur et de toutes les bases de données, reportez-vous à [Colocalisation de serveur prise en charge dans Lync Server 2013](lync-server-2013-supported-server-collocation.md) dans la documentation de prise en charge.

## Topologies du serveur de conversations permanentes

Le serveur de conversations permanentes prend en charge les topologies suivantes :

  - Serveur unique Lync Server 2013 Enterprise Edition serveur de conversations permanentesserveur frontal

  - Plusieurs serveurs Lync Server 2013 Enterprise Edition serveur de conversations permanentesserveur frontal

  - serveur Standard EditionLync Server 2013 utilisant SQL Server Express

  - serveur Standard EditionLync Server 2013 et serveur de conversations permanentes sur un serveur distinct utilisant le serveur Standard Edition comme serveur du tronçon suivant.

Vous pouvez ajouter un serveur de conversations permanentes à votre déploiement Lync Server 2013 à l’aide du Générateur de topologie. Vous pouvez ajouter un pool de serveurs de conversations permanentes à un seul ou plusieurs serveurs à votre topologie.

> [!IMPORTANT]  
> Si vous avez créé un pool de serveurs de conversations permanentes avec un seul serveur à l’aide du Générateur de topologie, vous ne pouvez pas ajouter d’autres serveurs au pool.

## Topologie à serveur unique

La configuration minimale et le déploiement le plus simple pour le serveur de conversations permanentes est une topologie avec un serveur frontal de serveur de conversations permanentes unique. Ce déploiement requiert un serveur unique qui exécute le serveur de conversations permanentes (qui exécute éventuellement le service de conformité si la conformité est activée), un serveur qui héberge la base de données SQL Server et, si la conformité est obligatoire, la base de données SQL Server pour stocker les données de conformité.

> [!IMPORTANT]  
> Vous ne pouvez pas ajouter de serveurs supplémentaires à un pool de serveurs de conversations permanentes démarré comme un déploiement à serveur unique dans le Générateur de topologie. Nous vous recommandons d’utiliser la topologie de pool à plusieurs serveurs, même si vous utilisez un seul serveur, de manière à ce que vous puissiez ajouter d’autres serveurs par la suite si nécessaire.

La figure suivante présente tous les composants obligatoires et facultatifs d’une topologie pour un seul serveur frontalserveur de conversations permanentes avec conformité.

**Serveur de conversations permanentes unique**

![Topologie à un serveur avec service de conformité](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologie à un serveur avec service de conformité")

## Topologie à plusieurs serveurs

Pour offrir une capacité et une fiabilité supérieures, vous pouvez déployer une topologie à plusieurs serveurs, comme indiqué dans [Planification du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md). La topologie à plusieurs serveurs peut inclure jusqu’à quatre ordinateurs actifs exécutant le serveur de conversations permanentes (les configurations à haute disponibilité et de récupération d’urgence autorisent jusqu’à huit ordinateurs, mais seuls quatre peuvent être actifs, les quatre autres étant en attente). Chaque serveur peut prendre en charge jusqu’à 20 000 utilisateurs simultanés, pour un total de 80 000 utilisateurs connectés simultanément à un pool de serveurs de conversations permanentes avec 4 serveurs. Une topologie à plusieurs serveurs est identique à une topologie à serveur unique, à la différence près que plusieurs serveurs hébergent le serveur de conversations permanentes et qu’elle offre une extensibilité supérieure. Plusieurs ordinateurs exécutant le serveur de conversations permanentes doivent se trouver dans le même domaine des services de domaine Active Directory que Lync Server et le service de conformité.

L’illustration suivante montre tous les composants d’une topologie à plusieurs serveurs avec plusieurs ordinateurs exécutant un serveur de conversations permanentes, le service de conformité facultatif et une base de données de conformité distincte.

**Plusieurs serveurs de conversation permanente**

![Topologie à plusieurs serveurs](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologie à plusieurs serveurs")

Les topologies à plusieurs serveurs permettent de regrouper les fonctionnalités des serveurs. Dans un pool de serveurs, les services de conversation permanente communiquent et partagent des données. Par exemple, l’historique des conversations qui était initialement publié dans un service de conversation permanente est disponible dans n’importe quel service de conversation permanente du système. Un fichier téléchargé via un service de conversation permanente est accessible à n’importe quel service de conversation permanente. Les utilisateurs peuvent être connectés à différents serveurs frontauxserveur de conversations permanentes et peuvent converser et communiquer entre eux.

Le port par défaut TCP 8011, qui connecte un serveur à un pool de serveurs, est utilisé par le service de conversation permanente pour communiquer entre eux ou à des fins administratives.

