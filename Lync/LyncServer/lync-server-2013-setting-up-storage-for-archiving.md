---
title: Configuration du stockage pour l’archivage
TOCTitle: Configuration du stockage pour l’archivage
ms:assetid: f751245c-743e-454f-8325-968ae5e3de71
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205392(v=OCS.15)
ms:contentKeyID: 49299364
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration du stockage pour l’archivage

 

_**Dernière rubrique modifiée :** 2016-12-08_

L’archivage du stockage pour Lync Server 2013 inclut les éléments suivants :

  - **Stockage des données**   Le stockage des données est requis pour stocker le contenu de messagerie instantanée.

  - **Stockage de fichiers**   Le stockage de fichiers est requis pour stocker le stockage de données de contenu de la conférence (ou de la réunion) et le stockage des fichiers.

## Configuration du stockage des données

Les conditions requises pour la configuration du stockage des données pour l’archivage dans Lync Server 2013 dépend de la façon dont vous souhaitez stocker les données d’archivage :

  - en intégrant l’archivage de Lync Server 2013 à votre déploiement de Exchange pour stocker les données d’archivage en utilisant le stockage Exchange ;

  - en configurant différents serveurs de bases de données SQL Server pour stocker les données d’archivage.

## Configuration du stockage Exchange pour les données d’archivage

Pour pouvoir configurer Exchange pour le stockage des données d’archivage, votre déploiement Exchange doit exécuter Exchange 2013. De plus, les boîtes aux lettres d’utilisateurs doivent être hébergées sur le serveur Exchange 2013 et placées en Archive permanente. Pour plus d’informations sur la configuration de Exchange 2013, voir la documentation du produit Exchange.

## Configuration des serveurs de base de données SQL Server pour le stockage des données d’archivage

Pour procéder à l’archivage dans Lync Server 2013, le logiciel de base de données SQL Server doit stocker les données archivées, sauf si vous intégrez votre déploiement dans Exchange.

Pour que SQL Server archive les bases de données, vous devez installer SQL Server sur l’ordinateur qui hébergera la base de données d’archivage. Vous pouvez utiliser la même instance SQL que pour la base de données primaire d’un pool frontal. Pour de meilleures performances, nous vous conseillons de déployer la base de données d’archivage sur un ordinateur distinct du magasin de gestion centralisée. Pour plus d’informations sur la colocation des composants Lync Server 2013, voir [Colocalisation de serveur prise en charge dans Lync Server 2013](lync-server-2013-supported-server-collocation.md) dans la documentation relative à la prise en charge.

Chaque serveur de base de données doit être exécuté dans une version de SQL Server prise en charge. Pour plus d’informations sur les versions prises en charge, voir [Configuration technique requise pour l’archivage dans Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) dans la documentation de planification.

Vous devez d’abord configurer les plateformes SQL Server avant de déployer et d’activer l’archivage. Si le compte à utiliser pour la publication de la topologie est doté des droits et autorisations d’administrateur appropriées, vous pouvez créer la base de données d’archivage (LcsLog) lorsque vous publiez votre topologie. Vous pouvez également créer la base de données plus tard, y compris dans le cadre de la procédure d’installation. Pour plus d’informations sur SQL Server, voir le site TechCenter SQL Server à l’adresse [http://go.microsoft.com/fwlink/?linkid=129045\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=129045%26clcid=0x40c).

> [!NOTE]  
> Assurez-vous que le type de démarrage du service d’agent SQL Server est Automatique et que le service d’agent SQL Server est en cours d’exécution pour l’instance SQL qui contient la base de données d’archivage, de sorte que la tâche de maintenance d’archivage par défaut de SQL Server peut s’exécuter selon sa planification sous le contrôle du service d’agent SQL Server.

## Configuration du stockage de fichier

L’archivage utilise le partage de fichiers Lync Server 2013 que vous avez spécifié lorsque vous avez configuré votre pool frontal ou votre serveur Standard Edition. Vous ne pouvez pas modifier le partage de fichiers utilisé pour l’archivage. Pour plus d’informations sur les systèmes de stockage de fichiers pris en charge, voir [Prise en charge du stockage des fichiers dans Lync Server 2013](lync-server-2013-file-storage-support.md) dans la documentation relative à la prise en charge.

