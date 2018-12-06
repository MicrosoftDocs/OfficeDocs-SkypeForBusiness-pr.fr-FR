---
title: "Créa. et conf. des stratégies d’utilisateur pour l’archivage dans Lync Server"
TOCtitle: "Créa. et conf. des stratégies d’utilisateur pour l’archivage dans Lync Server"
ms:assetid: 5af0e605-3563-4d6f-a3c6-511d204a3165
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204923(v=OCS.15)
ms:contentKeyID: 49297277
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création et configuration des stratégies d’utilisateur pour l’archivage dans Lync Server

 

_**Dernière rubrique modifiée :** 2012-10-09_

Pour activer ou désactiver l’archivage d’utilisateurs spécifiques hébergés sur Lync Server, vous devez d’abord créer une stratégie utilisateur, puis appliquer la stratégie à un ou plusieurs utilisateurs ou groupes d’utilisateurs. Pour plus d’informations sur l’application de stratégies utilisateur à des utilisateurs et groupes d’utilisateurs spécifiques, voir [Application d’une stratégie d’archivage Lync Server à un utilisateur](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) dans la documentation de déploiement.

Pour plus d’informations sur les stratégies d’archivage, notamment la hiérarchie des stratégies : globale, de site et utilisateur, voir [Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations.

> [!NOTE]  
> Si vous avez activé l’intégration de Microsoft Exchange pour votre déploiement, les stratégies d’archive permanente d’Exchange déterminent si l’archivage est activé pour les utilisateurs hébergés sur Exchange 2013 qui disposent de boîtes aux lettres placées en archive permanente. Pour plus d’informations, voir <a href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configuration des stratégies pour l’archivage lors de l’utilisation de l’intégration Exchange Server</a> dans la documentation de déploiement.<br />
Il est préférable de spécifier toutes les options appropriées dans les configurations de l’archivage avant d’activer l’archivage. Pour plus d’informations, voir <a href="lync-server-2013-configuring-archiving-options.md">Configuration des options d’archivage</a> dans la documentation de déploiement.

## Pour configurer une stratégie d’archivage pour des utilisateurs hébergés sur Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server 2013. Pour plus d’informations sur les différentes méthodes d’ouverture du Panneau de configuration Lync Server 2013, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Stratégie de l’archivage**.

4.  Cliquez sur **Nouvelle**, puis sur **Stratégie utilisateur**.

5.  Dans **Nouvelle stratégie d’archivage**, procédez comme suit :
    
      - Dans **Nom**, spécifiez le nom de la stratégie utilisateur.
    
      - Dans **Description**, entrez des informations décrivant la stratégie utilisateur (par exemple, stratégie utilisateur pour le service juridique).
    
      - Pour contrôler l’archivage des communications internes de la stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications internes**.
    
      - Pour contrôler l’archivage des communications externes de la stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications externes**.

6.  Cliquez sur **Valider**.

Une stratégie utilisateur ne s’applique qu’aux utilisateurs auxquels vous affectez la stratégie. Pour plus d’informations sur l’application d’une stratégie utilisateur à des utilisateurs spécifiques, voir [Application d’une stratégie d’archivage Lync Server à un utilisateur](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) dans la documentation de déploiement.

