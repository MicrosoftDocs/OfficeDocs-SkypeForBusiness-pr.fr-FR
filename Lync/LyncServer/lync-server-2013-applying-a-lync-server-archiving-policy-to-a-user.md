---
title: Application d’une stratégie d’archivage Lync Server à un utilisateur
TOCTitle: Application d’une stratégie d’archivage Lync Server à un utilisateur
ms:assetid: a23e4876-aa8d-4f49-a3bd-3696616e8290
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205143(v=OCS.15)
ms:contentKeyID: 49298369
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Application d’une stratégie d’archivage Lync Server à un utilisateur

 

_**Dernière rubrique modifiée :** 2012-10-10_

Après avoir créé une stratégie utilisateur Lync Server, vous devez l’appliquer à des utilisateurs ou groupes d’utilisateurs spécifiques hébergés sur Lync Server 2013 pour qu’elle prenne effet. Pour plus d’informations sur la création de stratégies utilisateur pour des utilisateurs spécifiques, voir [Création et configuration des stratégies d’utilisateur pour l’archivage dans Lync Server](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md) dans la documentation de déploiement.

Pour plus d’informations sur le fonctionnement des stratégies d’archivage, notamment la hiérarchie des stratégies : globale, de site et utilisateur, voir [Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, dans la documentation de déploiement ou dans la documentation des opérations.

> [!NOTE]  
> Pour configurer et utiliser l’archivage, vous devez tout d’abord déployer cette fonction. Pour plus d’informations, voir <a href="lync-server-2013-deploying-archiving.md">Déploiement de l’archivage dans Lync Server 2013</a> dans la documentation de déploiement.<br />
Si vous avez activé l’intégration de Microsoft Exchange pour votre déploiement, les stratégies d’archive permanente d’Exchange déterminent si l’archivage est activé pour les utilisateurs hébergés sur Exchange 2013 qui disposent de boîtes aux lettres archivées de manière permanente. Pour plus d’informations, voir <a href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configuration des stratégies pour l’archivage lors de l’utilisation de l’intégration Exchange Server</a> dans la documentation de déploiement.<br />
Il est préférable de spécifier toutes les options appropriées dans les configurations de l’archivage avant d’activer l’archivage. Pour plus d’informations, voir <a href="lync-server-2013-configuring-archiving-options.md">Configuration des options d’archivage</a> dans la documentation de déploiement.

## Pour appliquer une stratégie d’archivage Lync Server à un utilisateur

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server 2013. Pour plus d’informations sur les différentes méthodes d’ouverture du Panneau de configuration Lync Server 2013, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.

4.  Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier l’utilisateur Lync Server** sous **Stratégie d’archivage**, sélectionnez la stratégie utilisateur d’archivage que vous souhaitez appliquer.
    
    > [!NOTE]  
    > Les paramètres <strong>&lt;Automatique&gt;</strong> appliquent les paramètres d’installation du serveur par défaut. Ces paramètres sont appliqués automatiquement par le serveur.

6.  Cliquez sur **Valider**.

