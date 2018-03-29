---
title: Panneau de commande - recherche d’utilisateur mis à jour
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 5/21/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
description: Vous pouvez utiliser les résultats d’une requête de recherche pour configurer les utilisateurs pour Skype pour Business Server. Vous pouvez rechercher des utilisateurs par nom d’affichage, prénom, nom de famille, nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), adresse SIP ou URI (Uniform Resource Identifier) de ligne. Vous pouvez également rechercher des utilisateurs à partir du Panneau de configuration Lync Server ou du composant Utilisateurs et ordinateurs Active Directory.
ms.openlocfilehash: 9cf6384d10cc4b6d2931fb21c75fd09da873d383
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="control-panel---updated-user-search"></a>Panneau de configuration - Mise à jour : recherche d’un utilisateur
 
Vous pouvez utiliser les résultats d’une requête de recherche pour configurer les utilisateurs pour Skype pour Business Server. Vous pouvez rechercher des utilisateurs par nom d’affichage, prénom, nom de famille, nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), adresse SIP ou URI (Uniform Resource Identifier) de ligne. Vous pouvez également rechercher des utilisateurs à partir du Panneau de configuration Lync Server ou du composant Utilisateurs et ordinateurs Active Directory.
  
## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Recherche d’un utilisateur** du Panneau de configuration, vous pouvez effectuer les tâches suivantes :
  
- [Recherche pour les utilisateurs de Lync Server 2010](http://technet.microsoft.com/library/3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5.aspx)
    
- [Activer ou désactiver des utilisateurs pour Lync Server 2010](http://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)
    
- [Déplacer l’utilisateur](move-user.md)
    
- [Déplacer tous les utilisateurs](move-all-users.md)
    
- [Affecter des stratégies à des utilisateurs](http://technet.microsoft.com/library/a4ed0120-d9e5-4eb2-acfd-8de2cb503652.aspx)
    
- [Permettre aux utilisateurs de Voix Entreprise dans Skype pour Business Server 2015](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)
    
- [Configurer la connectivité PIC, fédération et accès des utilisateurs distants pour les utilisateurs](http://technet.microsoft.com/library/736fcaad-9f95-4896-b767-e199d86a00a4.aspx)
    
- [Configurer la téléphonie pour les utilisateurs](http://technet.microsoft.com/library/4546432e-c839-4517-a2c5-bc0d4d8c6a03.aspx)
    
Pour plus d’informations sur les différentes procédures que vous pouvez effectuer à l’aide de la Skype pour Business Server du Panneau de configuration, voir [Gérer les Skype pour Business Server 2015](../../manage/manage.md).
  
## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page **Recherche d’un utilisateur**.
  
### <a name="user-search"></a>Recherche d’un utilisateur

- **Recherche** Rechercher des utilisateurs par la première partie du nom complet, prénom, nom, nom de compte SAM, adresse SIP ou l’URI du compte d’utilisateur de la ligne.
    
- **Recherche LDAP** Rechercher des utilisateurs en tapant une expression LDAP.
    
- **Zone de recherche aux utilisateurs** Tapez les données de l’utilisateur ou d’un expression LDAP à la recherche de.
    
- **Rechercher** Cliquez pour afficher les utilisateurs qui correspondent aux valeurs de recherche que vous avez entré dans la zone et de **Rechercher des utilisateurs** .
    
- **Ouvrir une requête** Cliquez pour ouvrir une recherche enregistrée.
    
- **Enregistrer la requête** Cliquez pour enregistrer une requête de recherche.
    
- **+ Ajouter un filtre** Cliquez pour ajouter des critères de recherche supplémentaires.
    
- **Champs de filtre de recherche** Sélectionnez le champ sur lequel vous souhaitez filtrer les résultats de la recherche, sélectionnez un opérateur pour la requête et puis tapez la chaîne que vous voulez rechercher.
    
- **Nombre maximal d’utilisateurs à afficher** Tapez le nombre de résultats de recherche que vous souhaitez afficher ou utilisez les flèches pour spécifier le nombre.
    
Ajoutez un texte descriptif, selon les besoins.
  
### <a name="search-results-menus"></a>Menus de la page Résultats de la recherche

- **Permettre aux utilisateurs** Cliquez pour ouvrir la [utilisateurs : nouvel utilisateur de serveur Lync](users-new-lync-server-user.md) boîte de dialogue, où vous pouvez ajouter un nouvel utilisateur à Skype pour Business Server.
    
    Pour ajouter un nouveau contact, cliquez sur la flèche vers le bas et sélectionnez **Activer contacts** pour ouvrir la [utilisateurs : nouveaux objets Contact](users-new-contact-objects.md) boîte de dialogue.
    
- **Modifier** Cliquez sur **Modifier** , puis cliquez sur **Afficher les détails** pour afficher les détails de l’utilisateur sélectionné, ou cliquez sur **Sélectionner tous les résultats de la recherche** pour sélectionner tous les utilisateurs affichés dans le tableau de résultats.
    
- **Action** Cliquez sur **Action**, puis sélectionnez l’action à effectuer pour les utilisateurs sélectionnés dans les résultats de recherche. Les actions suivantes sont disponibles :
    
  - **Réactiver pour Lync Server** Active le compte d’utilisateur sélectionné après que qu’il a été temporairement désactivé.
    
  - **Désactiver temporairement pour Lync Server** Désactive le compte d’utilisateur dans Skype pour Business Server jusqu'à ce que vous la réactivez, sans supprimer le compte d’utilisateur.
    
  - **Affecter des stratégies** Ouvre le [utilisateurs : affecter les stratégies](users-assign-policies.md) boîte de dialogue, dans laquelle vous pouvez configurer les stratégies affectées à l’utilisateur.
    
  - **État de la broche de l’affichage** Ouvre le [utilisateurs : afficher l’état de PIN](users-view-pin-status.md) boîte de dialogue qui affiche les données de code PIN pour l’utilisateur sélectionné.
    
  - **Définir code PIN** Ouvre la boîte de dialogue [Définir un code confidentiel](set-pin.md) , où vous pouvez définir le code PIN de l’utilisateur sélectionné.
    
  - **Verrouillage de broche** Verrouille le code confidentiel de l’utilisateur.
    
  - **Déverrouillage de code confidentiel** Supprime le verrou sur le code PIN de l’utilisateur.
    
  - **Supprimer de Lync Server** Supprime le compte d’utilisateur Skype pour Business Server. L’utilisateur n’est pas supprimé d’Active Directory.
    
  - **Supprimer le certificat de l’utilisateur** Supprime tous les certificats accordés à l’utilisateur.
    
  - **Déplacer les utilisateurs sélectionnés au pool** Ouvre la boîte de dialogue [Déplacer un utilisateur](move-user.md) , où vous pouvez sélectionner un pool pour déplacer l’utilisateur sélectionné.
    
  - **Déplacer tous les utilisateurs au pool** Ouvre la boîte de dialogue [Déplacer un utilisateur](move-user.md) , où vous pouvez sélectionner un pool pour déplacer tous les utilisateurs sélectionnés.
    

