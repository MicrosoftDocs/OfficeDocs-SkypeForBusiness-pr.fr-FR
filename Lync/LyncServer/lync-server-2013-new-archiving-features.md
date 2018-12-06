---
title: 'Lync Server 2013 : Nouvelles fonctionnalités d’archivage'
TOCTitle: Nouvelles fonctionnalités d’archivage
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205225(v=OCS.15)
ms:contentKeyID: 49298709
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Nouvelles fonctionnalités d’archivage dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

La fonctionnalité d’archivage de Lync Server 2013 permet d’archiver les types de contenus suivants :

  - Messages instantanés P2P

  - Conférences (réunions) constituant des messages instantanés entre utilisateurs multiples

  - Contenu de conférence, dont le contenu téléchargé (par exemple, documents) et le contenu lié à l’événement (par exemple, joindre, quitter la réunion, téléchargement de partage et modifications en termes de visibilité)

En outre, la fonctionnalité d’archivage de Lync Server 2013 offre de nouvelles options permettant d’améliorer le déroulement du déploiement et des opérations. Voici ces nouvelles options :

  - **Colocalisation de l’archivage sur les serveurs frontaux.**    Lync Server 2013 ne comporte pas de rôle serveur d’archivage distinct. L’archivage est une fonctionnalité facultative disponible sur tous les serveurs frontaux installés dans un déploiement Enterprise Edition, ainsi que sur les serveurs Standard Edition. Cette fonctionnalité peut être implémentée et configurée pour un pool ou un site spécifique.

  - **Intégration Microsoft Exchange.**  Lorsque vous déployez la fonctionnalité d’archivage, vous pouvez intégrer le stockage des données d’archivage à votre stockage Exchange 2013 existant pour tous les utilisateurs hébergés sur Exchange 2013 disposant de boîtes aux lettres en archivage permanent. Ainsi, vous n’avez pas besoin de déployer certaines bases de données SQL Server pour archiver les données Lync. Si vous n’avez pas de déploiement Exchange 2013 ou que vous ne souhaitez pas effectuer d’intégration avec, ou si des utilisateurs Lync 2013 aux boîtes aux lettres en archivage permanent ne sont pas hébergés sur Exchange 2013, vous pouvez déployer différentes bases de données d’archivage à l’aide de SQL Server pour stocker les données archivées des communications Lync. Vous pouvez utiliser l’intégration Microsoft Exchange et les bases de données d’archivage Lync Server 2013 si vous souhaitez appliquer l’intégration Microsoft Exchange pour certains utilisateurs de votre déploiement. Pour plus d’informations sur l’archivage permanent, reportez-vous à « Archivage permanent » à l’adresse [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500).

  - **Mise en miroir du magasin SQL Server.**   Lorsque vous déployez la fonctionnalité d’archivage, vous pouvez activer la mise en miroir des bases de données SQL Server pour votre base de données d’archivage.

  - **Archivage des tableaux blancs et des sondages.**   Le contenu de conférence archivé inclut maintenant les tableaux blancs et les sondages partagés pendant la réunion.

Les types de contenu suivants ne sont pas archivés :

  - Transferts de fichiers P2P

  - Audio/vidéo pour messages instantanés et conférences P2P

  - Partage d’application pour messages instantanés et conférences P2P

## Voir aussi

#### Autres ressources

[Planification de l’archivage dans Lync Server 2013](lync-server-2013-planning-for-archiving.md)

