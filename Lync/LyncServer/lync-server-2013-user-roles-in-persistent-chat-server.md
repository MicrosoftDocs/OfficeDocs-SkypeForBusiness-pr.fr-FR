---
title: Rôles d’utilisateur dans le serveur de conversation permanente
TOCTitle: Rôles d’utilisateur dans le serveur de conversation permanente
ms:assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ676774(v=OCS.15)
ms:contentKeyID: 49891306
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Rôles d’utilisateur dans le serveur de conversation permanente

 

_**Dernière rubrique modifiée :** 2015-03-19_

Le serveur de conversations permanentes fournit le concept des membres autorisés/refusés, qui s’applique aux catégories de conversation permanente et contrôle qui peut accéder aux salles d’une catégorie spécifique.

> [!IMPORTANT]  
> Le concept des membres autorisés/refusés d’une catégorie n’est pas le même que celui du rôle de <strong>membre</strong>, qui s’applique à une salle de conversation permanente.<br />
Les recherches affichent toutes les salles de conversation ouvertes et fermées pour lesquelles l’utilisateur effectuant la recherche figure dans la liste des membres autorisés/refusés. Les salles secrètes ne sont pas affichées, sauf si l’utilisateur effectuant la recherche en est membre. L’utilisateur peut rechercher seulement les salles dont il est déjà membre, ou celles pour lesquelles il peut demander son appartenance.

La logique principale du concept de membres autorisés/refusés passe par des murs éthiques. Par exemple, il est courant dans les institutions bancaires et financières d’imposer des limites éthiques qui empêchent les courtiers et les analystes de partager des communications quand ils mettent en œuvre des stratégies et des conventions. Pour répondre à cette exigence, un administrateur peut créer des catégories de sorte qu’une seule catégorie autorise la création et l’utilisation des salles par les courtiers, et une autre catégorie autorise la création et l’utilisation des salles par les analystes. Cette contrainte au sein du système interdit l’ajout d’un utilisateur en tant que membre de la salle si la catégorie parente l’en empêche.

Les rôles suivants sont les quatre rôles d’utilisateur du serveur de conversations permanentes:

  - **Créateur** : utilisateurs ayant l’autorisation de créer des salles de conversation. Ces utilisateurs figurent dans la liste de créateurs de certaines catégories : ils peuvent créer des salles de conversation dans cette catégorie et ils peuvent aussi assigner une appartenance selon la catégorie et assigner des responsables pour gérer la salle de conversation. L’utilisateur qui crée une salle de conversation est automatiquement ajouté en tant que responsable de la salle.
    
    > [!NOTE]  
    > Le rôle de créateur se limite à disposer du droit de création des salles de conversation. C’est en réalité la promotion automatique au poste de responsable qui permet au créateur de redéfinir les appartenances, les responsables, etc. sur les services de conversation créés.    
    
    
    Ce rôle existe pour vous donner la possibilité de déterminer qui peut créer des salles de conversation dans votre organisation, en particulier si vous voulez centraliser la gestion de la création de salles de conversation pour appliquer des stratégies et des conventions, et par la suite déléguer la gestion des salles de conversation à d’autres utilisateurs de votre organisation.

  - **Responsable** : utilisateurs gérant les propriétés d’une salle de conversation. Les responsables de salle de conversation peuvent modifier la liste des membres (ajouter et supprimer des membres) et modifier la liste des responsables de la salle de conversation (ajouter et supprimer des responsables). Ils peuvent s’ajouter eux-mêmes à la liste des membres ou des présentateurs (pour les auditoriums) afin de pouvoir participer à la salle de conversation. Les responsables de salle de conversation peuvent aussi désactiver des salles de conversation (les administrateurs peuvent rechercher les salles de conversation désactivées et les supprimer définitivement). Les responsables peuvent modifier toutes les propriétés d’une salle de conversation, à l’exception de sa catégorie. Seul l’administrateur de conversation permanente peut modifier la catégorie après la création d’une salle de conversation.
    
    > [!IMPORTANT]  
    > Si le responsable est aussi le créateur d’une autre catégorie, il peut modifier la catégorie de sorte à pouvoir créer des salles.

  - **Membre** : utilisateurs membres d’une salle de conversation. Ces utilisateurs peuvent voir les salles de conversation dans le répertoire (même si la salle de conversation est secrète), ainsi que s’abonner à la salle de conversation (y compris aux options de métadonnées comme les messages non lus, les filtres Ego et les filtres de mots clés), et participer à la salle de conversation (ils peuvent publier, sauf s’il s’agit d’un auditorium dans lequel seuls les présentateurs peuvent publier, obtenir du contenu et effectuer des recherches). Les utilisateurs non membres de la salle de conversation peuvent rechercher la salle de conversation s’ils figurent dans la liste des membres autorisés de la catégorie, mais ils doivent solliciter l’accès à ces salles de conversation pour pouvoir accéder au contenu. (Aucune demande d’accès ou approbation n’est intégrée au système, ce sont des processus externes effectués par courrier électronique, téléphone ou une autre forme de contact.).

  - **Présentateur** : utilisateurs pouvant publier dans un auditorium.

Les rôles suivants sont les rôles d’administrateur du serveur de conversations permanentes :

  - Administrateur de **conversation permanente (CsPersistentChatAdministrator)** : il s’agit d’un nouveau rôle RBAC (contrôle d’accès basé sur un rôle) permettant d’administrer et de gérer le serveur de conversations permanentes. Les utilisateurs ou les groupes de sécurité désignés en tant que CsPersistentChatAdministrator sont capables d’administrer le serveur de conversations permanentes à l’aide des applets de commande Windows PowerShell à distance (c’est-à-dire à partir d’un ordinateur autre que le serveur de conversations permanentes). Le serveur de conversations permanentes vérifie que l’administrateur de conversation permanente est membre du groupe local d’administration RTC Local sur le serveur frontal du serveur de conversations permanentes.
    
    Le rôle CsPersistentChatAdministrator peut gérer des salles de conversation (modifier toutes les propriétés, y compris l’appartenance, les responsables, les catégories et désactiver des salles), ainsi que créer et gérer des catégories de salle de conversation qui définissent qui peut créer des salles de conversation et y accéder. Les administrateurs peuvent aussi marquer des salles de conversation comme désactivées et effacer celles qui ne sont plus actives. Les administrateurs ne sont pas soumis aux restrictions des créateurs ou des membres autorisés. Ils peuvent créer toutes sortes de salle de conversation et s’ajouter eux-mêmes en tant que membres de n’importe quelle salle de conversation. Les administrateurs peuvent aussi modifier et gérer la configuration de conversation permanente (propriétés du pool, paramètres globaux et configuration de conformité), et ils peuvent également planifier et implémenter la migration d’un ancien déploiement de serveur Group Chat vers un serveur de conversations permanentesLync Server 2013.

  - **Administrateur Lync** : administrateur général de l’entreprise, responsable du déploiement de Lync Server 2013.

  - **Responsable des opérations** : utilisateur responsable de la gestion des opérations quotidiennes.

  - **Développeurs et partenaires tiers** : les développeurs tiers développent le système, en particulier en fournissant une solution de mur éthique pour les conversations de groupe, des outils et un support pour la conformité, des clients web/mobile et une infrastructure pour le développement Bot.

