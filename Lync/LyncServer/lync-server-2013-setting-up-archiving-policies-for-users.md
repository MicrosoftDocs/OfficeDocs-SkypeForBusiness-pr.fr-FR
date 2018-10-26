---
title: Configuration des stratégies d’archivage pour les utilisateurs
TOCTitle: Configuration des stratégies d’archivage pour les utilisateurs
ms:assetid: 1bbb45df-0590-4c66-9d65-d25526f57790
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204722(v=OCS.15)
ms:contentKeyID: 49296413
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des stratégies d’archivage pour les utilisateurs

 

_**Dernière rubrique modifiée :** 2012-10-09_

Vous pouvez activer ou désactiver l’archivage pour des utilisateurs spécifiques en créant et en configurant une stratégie d’archivage pour les utilisateurs, puis en appliquant la stratégie à des utilisateurs spécifiques ou à des groupes d’utilisateurs. Les stratégies utilisateur remplacent les stratégies globales ou de site. Les stratégies d’archivage s’appliquent uniquement si vous n’utilisez pas l’intégration Microsoft Exchange ou si vous utilisez l’intégration Microsoft Exchange mais que d’autres utilisateurs ne sont pas hébergés sur Exchange 2013 et que leur boîte aux lettres a été archivée de manière permanente.

Pour plus d’informations sur les stratégies d’archivage, notamment la hiérarchie des stratégies : globale, de site et utilisateur, voir [Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, dans la documentation de déploiement ou dans la documentation des opérations.

> [!NOTE]  
> Si vous activez l’intégration de Microsoft Exchange pour votre déploiement, des stratégies d’archive permanente Exchange contrôlent si l’archivage est activé pour les utilisateurs qui sont hébergés sur Exchange 2013 et dont les boîtes aux lettres sont placées dans une archive permanente. Pour plus d’informations, voir <a href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configuration des stratégies pour l’archivage lors de l’utilisation de l’intégration Exchange Server</a> dans la documentation de déploiement.<br />
Vous devez spécifier toutes les options appropriées dans les configurations de l’archivage avant d’activer l’archivage des communications internes ou externes dans les stratégies d’archivage. Pour plus d’informations, voir <a href="lync-server-2013-configuring-archiving-options.md">Configuration des options d’archivage</a> dans la documentation de déploiement.

## Dans cette section

  - [Configuration des stratégies d’utilisateur pour l’archivage dans Lync Server](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md)

  - [Configuration des stratégies pour l’archivage lors de l’utilisation de l’intégration Exchange Server](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

