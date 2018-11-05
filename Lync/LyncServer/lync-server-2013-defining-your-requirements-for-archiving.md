---
title: 'Lync Server 2013 : Définition de la configuration requise pour l’archivage'
TOCTitle: Définition de la configuration requise pour l’archivage
ms:assetid: ce0fc0f6-7704-4b80-bf19-a1fa9818fc7a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205276(v=OCS.15)
ms:contentKeyID: 49298895
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Définition de la configuration requise pour l’archivage dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-09_

Si votre entreprise doit respecter des réglementations de conformité, vous devez déployer l’archivage pour activer la prise en charge de l’archivage pour la messagerie instantanée et les conférences (réunions) Lync Server 2013. Pour plus d’informations sur le type de contenu qui peut être archivé, reportez-vous à [Vue d’ensemble de l’archivage dans Lync Server 2013](lync-server-2013-overview-of-archiving.md) dans la documentation de planification.

Pour implémenter l’archivage, vous devez d’abord décider comment satisfaire les conditions requises de votre entreprise en relation avec l’archivage. Cela nécessite de déterminer les aspects suivants :

  - **Quand déployer l’archivage**. Vous pouvez déployer l’archivage dans le cadre de votre déploiement Lync Server 2013 initial ou l’ajouter à un déploiement existant. Vous déployez l’archivage à l’aide du Générateur de topologie pour l’ajouter à votre topologie, puis en publiant la topologie.

  - **Archivage des communications internes ou externes**. Vous pouvez activer l’archivage pour les communications internes (communications entre les utilisateurs internes) et/ou les communications externes (communications incluant au moins un utilisateur externe à votre réseau interne). Vous pouvez spécifier ces options pour l’ensemble de votre organisation, ou pour des sites et pools spécifiques. Par défaut, aucune des ces options n’est activée.
    
    > [!NOTE]  
    > Si vous utilisez l’intégration de Microsoft Exchange pour enregistrer les données archivées, vos paramètres Exchange contrôlent l’archivage des communications Lync. Si votre déploiement comprend plusieurs forêts, vous devez synchroniser les paramètres entre Lync Server et Exchange. Le contrôle de l’archivage pour les communications internes et externes n’est disponible que pour la stratégie Lync. Pour l’archivage intégré à Exchange, les deux types de communications sont soit archivés, soit non archivés.

  - **Pourquoi activer l’archivage**. Vous pouvez activer et désactiver l’archivage pour votre déploiement à un niveau global, ainsi que pour des sites et utilisateurs spécifiques. À chacun de ces niveaux, vous spécifiez l’activation de l’archivage des sessions de messagerie instantanée (P2P) et/ou des conférences (réunions, qui sont des sessions à plusieurs utilisateurs). L’archivage est désactivé par défaut.

  - **Importance de l’archivage pour les utilisateurs de votre organisation**. Si l’archivage est essentiel pour votre organisation, vous pouvez choisir d’exécuter Lync Server 2013 en mode critique, ce qui permet de bloquer les sessions de messagerie instantanée et de conférence en cas d’échec de l’archivage. Par exemple :
    
      - Si le service d’archivage est temporairement dans l’impossibilité d’envoyer un message vers la file d’attente de la base de données ou d’insérer un message dans la base de données, les fonctionnalités de messagerie instantanée et de conférence sont bloquées dans le déploiement jusqu’à ce que la prise en charge de l’archivage soit restaurée.
    
      - Si l’utilisateur d’une conférence télécharge un fichier, mais que le fichier ne peut pas être copié dans le magasin de fichiers de l’archivage, la fonctionnalité de conférence est bloquée dans le déploiement jusqu’à ce que le problème soit résolu, mais la fonctionnalité de messagerie instantanée n’est pas bloquée.
    
    Vous pouvez configurer cette option aux niveaux global, d’un site et d’un pool. Par défaut, le mode critique est désactivé.

  - **Utilisation de l’intégration de Microsoft Exchange**. Cette option intègre le stockage de l’archivage avec votre stockage Exchange 2013 afin que vos données Lync Server et Exchange 2013 archivées soient stockées ensemble dans Exchange. Vous pouvez utiliser l’intégration de Microsoft Exchange pour le stockage des données d’archivage pour les utilisateurs hébergés sur Exchange 2013, si leurs boîtes aux lettres sont en archivage permanent. Si vous n’avez pas de déploiement Exchange 2013 ou que vous ne souhaitez pas effectuer d’intégration avec, ou si des utilisateurs Lync ne sont pas hébergés sur Exchange 2013, vous pouvez déployer différentes bases de données d’archivage à l’aide de SQL Server pour stocker les données archivées des communications Lync. Vous pouvez configurer l’option d’intégration de Microsoft Exchange aux niveau site, pool et global. Par défaut, l’intégration Microsoft Exchange n’est pas activée.

  - **Mode de gestion des données archivées**. La base de données d’archivage n’est pas destinée à la rétention à long terme et Lync Server 2013 ne fournit pas de solution de découverte électronique (recherche) pour les données archivées, aussi les données doivent-elles être déplacées vers un autre stockage. Lync Server ne fournit pas d’outil d’exportation de session permettant d’exporter les données archivées et de créer des transcriptions des données archivées pouvant faire l’objet d’une recherche. Pour la stratégie globale, ainsi que pour chaque stratégie de site et utilisateur que vous créez, vous pouvez activer la purge des données et spécifier une des options suivantes :
    
      - Vider les données d’archivage exportées et enregistrées après un délai maximal (jours). Le nombre de jours minimal que vous pouvez spécifier est 1. Le nombre de jours maximal que vous pouvez spécifier est 2562.
    
      - Vider uniquement les données d’archivage exportées. Cette option supprime tous les enregistrements qui ont été exportés et marqués comme pouvant être supprimés par l’outil d’exportation de sessions.
    
    Vous pouvez configurer cette option aux niveaux global, d’un site et d’un pool. La purge est désactivée par défaut.

Vous contrôlez l’archivage à l’aide d’une des méthodes suivantes :

  - **Stratégies d’archivage**. Vous utilisez une ou plusieurs stratégies d’archivage pour activer ou désactiver l’archivage des communications internes et externes. Par défaut, aucun archivage n’est activé. Vous activez ou désactivez l’archivage pour les communications internes et/ou les communications externes dans votre déploiement en utilisant la stratégie globale par défaut. Il est impossible de supprimer la stratégie globale. Vous pouvez spécifier une ou plusieurs stratégies de site facultatives pour activer ou désactiver l’archivage pour les communications internes et externes pour des sites spécifiques. Vous pouvez également spécifier une ou plusieurs stratégies d’utilisateur pour activer ou désactiver l’archivage pour des utilisateurs et groupes d’utilisateurs spécifiques. Les stratégies de niveau utilisateur remplacent les stratégies de niveau site. Les stratégies de niveau site remplacent les stratégies de niveau global. Les stratégies de niveau utilisateur sont uniquement implémentées pour les utilisateurs spécifiques configurés pour utiliser la stratégie. Les conférences et les messages instantanés de groupe sont uniquement archivés si une stratégie affectée à au moins un des participants est configurée pour activer l’archivage.
    
    > [!NOTE]  
    > Si vous utilisez l’intégration de Microsoft Exchange, les stratégies Exchange 2013 remplacent les stratégies d’archivage Lync Server pour tous les utilisateurs hébergés sur les serveurs Exchange 2013.

  - **Configurations d’archivage**. Vous utilisez une ou plusieurs configurations d’archivage pour spécifier la plupart des options d’archivage décrites plus haut dans cette rubrique, sauf pour l’activation de l’archivage des communications internes et externes (configurée avec les stratégies d’archivage, comme décrit dans le point précédent). Les configurations d’archivage comprennent la configuration globale par défaut et des configuration de site et de pool facultatives. Il est impossible de supprimer la configuration globale. Les configurations de niveau pool remplacent les configurations de niveau site. Les configurations de niveau site remplacent les configurations de niveau global.

Dans le cadre de votre analyse des conditions requises, vous devez déterminer les modalités de configuration de l’archivage global et la stratégie d’archivage globale. Vous devez également déterminer vos conditions requises pour toutes les configurations d’archivage de niveau site et de niveau pool, ainsi que pour toutes les stratégies d’archivage de niveau site et de niveau utilisateur.

Si vous déployez l’archivage pour un pool frontal ou un serveur Standard Edition Server, vous devez également l’activer pour tous les pools frontaux et les serveurs Standard Edition Server dans votre déploiement. Ces tâches sont nécessaires, car les utilisateurs dont les communications doivent être archivées peuvent être invités à une conversation de messagerie instantanée en groupe ou à des réunions hébergées sur un autre pool. Si l’archivage n’est pas activé sur le pool sur lequel la conversation ou la réunion est hébergée, il est possible que toutes les données de conférence ne soient pas archivées. L’archivage fonctionnera toujours pour les utilisateurs activés et les messages instantanés, mais il est possible que le contenu des conférences et les événements ne soient pas archivés.

> [!NOTE]  
> Pour activer la délégation des tâches administratives tout en maintenant les normes de sécurité de votre organisation, Lync Server 2013 utilise le contrôle d’accès basé sur un rôle (RBAC). Dans ce cadre, le privilège administratif est accordé en affectant les utilisateurs à des rôles d’administration prédéfinis. Pour configurer les stratégies et configurations d’archivage de Lync, l’utilisateur doit être affecté au rôle CsArchivingAdministrator (sauf si la configuration est effectuée directement sur le serveur où l’archivage est déployé, plutôt qu’à distance depuis un autre ordinateur). Pour plus d’informations sur RBAC, reportez-vous à <a href="lync-server-2013-planning-for-role-based-access-control.md">Planification du contrôle d’accès basé sur un rôle dans Lync Server 2013</a> dans la documentation de planification. Pour obtenir la liste des droits, autorisations et rôles utilisateur requis pour le déploiement de l’archivage, reportez-vous à <a href="lync-server-2013-deployment-checklist-for-archiving.md">Liste de vérification du déploiement pour l’archivage dans Lync Server 2013</a> dans la documentation de planification et de déploiement.<br />
Si vous utilisez l’intégration de Microsoft Exchange, la configuration des stratégies Exchange nécessite des droits et autorisations d’administrateur appropriés. Pour plus d’informations, reportez-vous à la documentation d’Exchange 2013.
