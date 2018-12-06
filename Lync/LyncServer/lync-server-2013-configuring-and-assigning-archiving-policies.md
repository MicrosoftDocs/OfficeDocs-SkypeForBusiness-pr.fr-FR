---
title: Configuration et affectation des stratégies d’archivage
TOCTitle: Configuration et affectation des stratégies d’archivage
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205175(v=OCS.15)
ms:contentKeyID: 49298499
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration et affectation des stratégies d’archivage

 

_**Dernière rubrique modifiée :** 2012-10-01_

Dans Lync Server 2013, vous pouvez utiliser des stratégies pour activer ou désactiver l’archivage des communications internes et des communications externes pour les utilisateurs qui sont hébergés sur Lync Server 2013. Il s’agit notamment des stratégies d’archivage suivantes :

  - Stratégie globale créée par défaut lorsque vous déployez Lync Server 2013.

  - Stratégies facultatives au niveau site et utilisateur que vous pouvez créer et utiliser pour définir de quelle manière l’archivage est implémenté pour des sites ou utilisateurs spécifiques.

Vous définissez les stratégies d’archivage lors du déploiement initial de l’archivage, mais vous pouvez modifier et supprimer des stratégies existantes, ou en ajouter de nouvelles, à tout moment après le déploiement. Dans le Panneau de configuration Lync Server 2013, vous pouvez utiliser la page **Stratégie d’archivage** du groupe **Archivage et surveillance** pour gérer les stratégies au niveau global, au niveau du site et au niveau utilisateur.

> [!NOTE]  
> Pour contrôler l’implémentation de l’archivage, vous devez définir certaines options de configuration de l’archivage, notamment spécifier si les messages instantanés ou les conférences doivent être archivés, si le mode critique est utilisé et les options de vidage. Par défaut, aucune option n’est activée dans la configuration de l’archivage global ni dans la configuration de l’archivage de site ou de pool. Vous devez définir toutes les options appropriées dans les configurations de l’archivage avant d’activer l’archivage des communications internes ou externes dans les stratégies d’archivage. Pour plus d’informations, voir <a href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Gestion des options de configuration de l’archivage dans Lync Server 2013 pour votre organisation, vos sites et vos pools</a> dans la documentation des opérations.<br />
Si vous intégrez votre stockage Lync Server au stockage Exchange 2013, les stratégies utilisateur Exchange ont priorité sur les stratégies d’archivage Lync Server 2013, mais uniquement pour les utilisateurs hébergés sur Exchange 2013 et dont la boîte aux lettres se trouve en archive permanente.

Pour plus d’informations sur l’implémentation des stratégies, y compris la hiérarchie des stratégies, voir [Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de la planification, la documentation du déploiement ou la documentation des opérations. Pour plus d’informations sur la gestion des stratégies après le déploiement, voir [Gestion de l'archivage des communications internes et externes dans Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) dans la documentation des opérations.

## Dans cette section

  - [Configuration de la stratégie globale pour l’archivage](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [Configuration des stratégies de site pour l’archivage](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [Configuration des stratégies d’archivage pour les utilisateurs](lync-server-2013-setting-up-archiving-policies-for-users.md)

