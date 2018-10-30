---
title: "Gest. de l'arch. des comm. int. et ext. dans Lync Server 2013"
TOCtitle: "Gest. de l'arch. des comm. int. et ext. dans Lync Server 2013"
ms:assetid: 6c2cf941-3204-4f1a-a7e0-416c828056d9
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204977(v=OCS.15)
ms:contentKeyID: 49297518
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Gestion de l'archivage des communications internes et externes dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-09_

Dans Lync Server 2013, vous pouvez utiliser des stratégies d’archivage pour activer ou désactiver l’archivage des communications internes et externes si vous n’utilisez pas l’intégration Microsoft Exchange ou si certains de vos utilisateurs ne sont pas hébergés sur Exchange 2013 avec leurs boîtes aux lettres placées en archive permanente. Il s’agit notamment des stratégies d’archivage suivantes :

  - Stratégie globale créée par défaut lorsque vous déployez Lync Server 2013.

  - Stratégies facultatives au niveau site et utilisateur que vous pouvez créer et utiliser pour définir de quelle manière l’archivage est implémenté pour des sites ou utilisateurs spécifiques.

Vous définissez les stratégies d’archivage lors du déploiement initial de l’archivage, mais vous pouvez modifier et supprimer des stratégies existantes, ou en ajouter de nouvelles, à tout moment après le déploiement. Dans le Panneau de configuration Lync Server 2013, accédez à la page **Stratégie d’archivage** dans le groupe **Archivage et surveillance** pour gérer les stratégies au niveau global, au niveau du site et au niveau utilisateur. Si vous intégrez le stockage Lync Server avec le stockage Exchange 2013, les stratégies utilisateur d’Exchange sont prioritaires sur les stratégies d’archivage de Lync Server 2013.

Pour plus d’informations sur l’implémentation des stratégies, y compris la hiérarchie des stratégies, voir [Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations.

> [!NOTE]  
> Pour contrôler l’implémentation de l’archivage, vous devez définir certaines options de configuration de l’archivage, notamment spécifier si les messages instantanés ou les conférences doivent être archivés, si le mode critique est utilisé et les options de vidage. Par défaut, aucune option n’est activée dans la configuration de l’archivage global ni dans la configuration de l’archivage de site ou de pool. Vous devez définir toutes les options appropriées dans les configurations de l’archivage avant d’activer l’archivage des communications internes ou externes dans les stratégies d’archivage. Pour plus d’informations, voir <a href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Gestion des options de configuration de l’archivage dans Lync Server 2013 pour votre organisation, vos sites et vos pools</a> dans la documentation des opérations.<br />
Si vous activez l’intégration Microsoft Exchange pour votre déploiement, les stratégies d’Exchange déterminent l’activation de l’archivage pour les utilisateurs qui sont hébergés sur Exchange 2013 et dont les boîtes aux lettres sont placées en archive permanente. Pour plus d’informations, voir <a href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configuration des stratégies pour l’archivage lors de l’utilisation de l’intégration Exchange Server</a> dans la documentation de déploiement.

## Dans cette section

  - [Création d’une stratégie d’archivage pour activer ou désactiver l’archivage des communications internes ou externes pour des sites ou utilisateurs spécifiques](lync-server-2013-creating-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-specific-sites-or-users.md)

  - [Modification d’une stratégie d’archivage pour activer ou désactiver l’archivage des communications internes ou externes pour votre organisation, vos sites ou vos utilisateurs](lync-server-2013-changing-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-your-organization-sites-or-us.md)

  - [Application d’une stratégie d’archivage à des utilisateurs](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [Configuration des stratégies pour l’archivage lors de l’utilisation de l’intégration Exchange Server](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [Suppression d’une stratégie d’archivage](lync-server-2013-deleting-an-archiving-policy.md)

