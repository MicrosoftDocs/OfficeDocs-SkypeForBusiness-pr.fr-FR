---
title: 'Lync Server 2013 : Vue d’ensemble de l’archivage'
TOCTitle: Vue d’ensemble de l’archivage
ms:assetid: 1e3c2ef1-f561-4f57-8b6a-7d78addc1ed1
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204729(v=OCS.15)
ms:contentKeyID: 49296446
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue d’ensemble de l’archivage dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-09-30_

L’archivage dans Lync Server 2013 vous permet d’archiver les communications envoyées via Lync Server 2013.

Vous pouvez implémenter l’archivage dans le cadre de votre déploiement initial de Lync Server 2013 ou l’ajouter à un déploiement existant. Pour utiliser les bases de données d’archivage Lync Server 2013 (bases de données SQL Server) pour le stockage des données d’archivage, utilisez le Générateur de topologie pour ajouter les bases de données à votre topologie, puis republiez la topologie. Si tous vos utilisateurs sont hébergés sur Exchange 2013 et si leurs boîtes aux lettres sont archivées de manière permanente, vous n’avez pas besoin de mettre à jour votre topologie, mais vous devez simplement activer l’intégration Microsoft Exchange pour stocker les données archivées dans Exchange 2013.

Lorsque vous implémentez l’archivage, vous le configurez de façon à indiquer ce qui est archivé. Par défaut, rien n’est archivé. Le Panneau de configuration Lync Server 2013 vous permet de configurer et de gérer l’archivage. Vous pouvez implémenter l’archivage pour les communications internes, les communications externes ou les deux. Vous pouvez configurer les paramètres d’archivage de toute votre organisation, mais également de certains sites, de pools spécifiques et d’utilisateurs et groupes d’utilisateurs en particulier. Pour plus d’informations sur la définition des options appropriées à votre organisation, reportez-vous à [Définition de la configuration requise pour l’archivage dans Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md) dans la documentation de planification. Pour en savoir plus sur l’implémentation des configurations et des stratégies d’archivage et consulter des détails sur les informations pouvant ou non être archivées, reportez-vous à [Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations.

