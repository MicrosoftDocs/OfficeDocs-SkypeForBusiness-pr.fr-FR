---
title: Configuration des stratégies d’utilisateur pour l’archivage dans Lync Server
TOCTitle: Configuration des stratégies d’utilisateur pour l’archivage dans Lync Server
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204742(v=OCS.15)
ms:contentKeyID: 49296522
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des stratégies d’utilisateur pour l’archivage dans Lync Server

 

_**Dernière rubrique modifiée :** 2012-10-10_

L’activation ou la désactivation de l’archivage pour des utilisateurs spécifiques hébergés sur Lync Server 2013 nécessite de créer et de configurer une ou plusieurs stratégies utilisateur, puis d’appliquer la stratégie appropriée à des utilisateurs ou groupes d’utilisateurs spécifiques. Les stratégies utilisateur remplacent les stratégies de site et les stratégies globales, mais uniquement pour les utilisateurs hébergés sur Lync Server 2013.

Les utilisateurs sont toujours hébergés sur Lync Server. Si l’intégration Microsoft Exchange est activée, les utilisateurs dont les boîtes aux lettres se trouvent dans Microsoft Exchange Server 2013 n’ont pas besoin que leur stratégie d’archivage dans Lync Server soit gérée. La fonctionnalité d’archivage de ces utilisateurs sera gérée par l’archive permanente d’Exchange.

Pour plus d’informations sur les stratégies d’archivage, notamment la hiérarchie des stratégies : globale, de site et utilisateur, voir [Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, dans la documentation de déploiement ou dans la documentation des opérations.

> [!NOTE]  
> Si vous avez activé l’intégration de Microsoft Exchange pour votre déploiement, les stratégies d’archive permanente d’Exchange déterminent si l’archivage est activé pour les utilisateurs hébergés sur Exchange 2013. Pour ces utilisateurs, la fonctionnalité d’archivage nécessite que leurs boîtes aux lettres soient placées dans une archive permanente. Pour plus d’informations, voir <a href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configuration des stratégies pour l’archivage lors de l’utilisation de l’intégration Exchange Server</a> dans la documentation de déploiement.<br />
Il est préférable de spécifier toutes les options appropriées dans les configurations de l’archivage avant d’activer cette fonctionnalité. Pour plus d’informations, voir <a href="lync-server-2013-configuring-archiving-options.md">Configuration des options d’archivage</a> dans la documentation de déploiement.

## Dans cette section

  - [Création et configuration des stratégies d’utilisateur pour l’archivage dans Lync Server](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [Application d’une stratégie d’archivage Lync Server à un utilisateur](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

