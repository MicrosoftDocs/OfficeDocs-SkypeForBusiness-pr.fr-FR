---
title: Configuration des options d’archivage
TOCTitle: Configuration des options d’archivage
ms:assetid: b2f7f74d-e1ad-494e-9d46-5eb0efe5fb29
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205182(v=OCS.15)
ms:contentKeyID: 49298564
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des options d’archivage

 

_**Dernière rubrique modifiée :** 2012-10-10_

Dans le Panneau de configuration Lync Server 2013, vous utilisez les configurations d’archivage pour spécifier la façon dont l’archivage est implémenté. Les configurations d’archivage sont les suivantes :

  - Configuration globale qui est créée par défaut lorsque vous déployez Lync Server 2013.

  - Configurations facultatives au niveau du site et au niveau du pool que vous pouvez créer et utiliser pour spécifier la manière d’implémenter l’archivage de sites ou de pools spécifiques.

Vous commencez par définir des configurations d’archivage lorsque vous déployez l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations à l’issue du déploiement. Dans le Panneau de configuration Lync Server 2013, vous pouvez utiliser la page **Configuration de l’archivage** du groupe **Archivage et surveillance** pour gérer les configurations au niveau global, au niveau du site et au niveau utilisateur. Pour plus d’informations sur la manière d’implémenter les configurations d’archivage, notamment sur les options que vous pouvez spécifier et la hiérarchie des configurations d’archivage, voir [Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, dans la documentation de déploiement ou dans la documentation des opérations. Pour plus d’informations sur la gestion des configurations après le déploiement, voir [Gestion des options de configuration de l’archivage dans Lync Server 2013 pour votre organisation, vos sites et vos pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) dans la documentation des opérations.

> [!NOTE]  
> Pour utiliser l’archivage, vous devez configurer des stratégies d’archivage afin de spécifier si l’archivage doit être activé pour les communications internes, pour les communications externes, ou pour les deux pour les utilisateurs hébergés sur Lync Server 2013. Par défaut, l’archivage n’est pas activé pour les communications internes ou externes. Avant d’activer l’archivage dans des stratégies, vous devez spécifier les configurations d’archivage appropriées pour votre déploiement et, éventuellement, pour des sites et pools spécifiques, comme décrit dans cette section. Pour plus d’informations sur l’activation de l’archivage, voir <a href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuration et affectation des stratégies d’archivage</a> dans la documentation de déploiement.<br />
Si vous n’utilisez pas l’intégration Microsoft Exchange pour tous les utilisateurs de votre déploiement, vous devez configurer des stratégies d’archivage afin de spécifier si l’archivage doit être activé pour les communications internes, pour les communications externes, ou pour les deux. Par défaut, l’archivage n’est pas activé pour les communications internes ou externes pour l’archivage de données lors de l’utilisation de bases de données d’archivage Lync Server 2013. Avant d’activer l’archivage dans des stratégies, vous devez spécifier les configurations d’archivage appropriées pour votre déploiement et, éventuellement, pour des sites et pools spécifiques, comme décrit dans la section. Pour plus d’informations sur l’activation de l’archivage pour l’utiliser avec des bases de données d’archivage Lync Server 2013, voir <a href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuration et affectation des stratégies d’archivage</a> dans la documentation de déploiement.

## Dans cette section

  - [Configuration des options d’archivage au niveau global](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [Configuration des options d’archivage d’un site](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [Configuration des options d’archivage pour un pool](lync-server-2013-configuring-archiving-options-for-a-pool.md)

