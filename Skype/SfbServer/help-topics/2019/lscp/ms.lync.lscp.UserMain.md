---
title: Le panneau de configuration - recherche d’un utilisateur mis à jour
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
ROBOTS: NOINDEX, NOFOLLOW
description: Vous pouvez utiliser les résultats d’une requête de recherche pour configurer les utilisateurs pour Skype pour Business Server. Vous pouvez rechercher des utilisateurs par nom d’affichage, prénom, nom de famille, nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), adresse SIP ou URI (Uniform Resource Identifier) de ligne. Vous pouvez également rechercher des utilisateurs à partir du Panneau de configuration Lync Server ou du composant Utilisateurs et ordinateurs Active Directory.
ms.openlocfilehash: 54bb0001352d1232a86b5b289f20829a3f34ba3e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21020223"
---
# <a name="control-panel---updated-user-search"></a>Panneau de configuration - Mise à jour : recherche d’un utilisateur
 
Vous pouvez utiliser les résultats d’une requête de recherche pour configurer les utilisateurs pour Skype pour Business Server. Vous pouvez rechercher des utilisateurs par nom d’affichage, prénom, nom de famille, nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), adresse SIP ou URI (Uniform Resource Identifier) de ligne. Vous pouvez également rechercher des utilisateurs à partir du Panneau de configuration Lync Server ou du composant Utilisateurs et ordinateurs Active Directory.
  
## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Recherche d’un utilisateur** du Panneau de configuration, vous pouvez effectuer les tâches suivantes :
  
- [Rechercher des utilisateurs](http://technet.microsoft.com/library/3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5.aspx)
    
- [Activer ou désactiver des utilisateurs](http://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)
    
- [Déplacement d’un utilisateur](ms.lync.lscp.UserMove.md)
    
- [Déplacement de tous les utilisateurs](ms.lync.lscp.UserMoveAll.md)
    
- [Affecter des stratégies pour les utilisateurs](http://technet.microsoft.com/library/a4ed0120-d9e5-4eb2-acfd-8de2cb503652.aspx)
    
- [Activer les utilisateurs pour Enterprise Voice sur Skype pour Business Server](../../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)
    
- [Configurer la fédération, l’accès des utilisateurs distants et la connectivité PIC pour les utilisateurs](http://technet.microsoft.com/library/736fcaad-9f95-4896-b767-e199d86a00a4.aspx)
    
- [Configuration de la téléphonie pour les utilisateurs](http://technet.microsoft.com/library/4546432e-c839-4517-a2c5-bc0d4d8c6a03.aspx)
    
 
  
## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page **Recherche d’un utilisateur**.
  
### <a name="user-search"></a>Recherche d’un utilisateur

- **Recherche** Rechercher des utilisateurs à la première partie du nom complet, prénom, nom de famille, nom de compte SAM, adresse SIP ou URI du compte d’utilisateur de la ligne.
    
- **Recherche LDAP** Rechercher des utilisateurs en tapant une expression LDAP.
    
- **Zone Rechercher des utilisateurs** Tapez les données utilisateur ou une expression LDAP à rechercher.
    
- **Rechercher** Cliquez ici pour afficher les utilisateurs qui correspondent aux valeurs de recherche que vous avez entré dans la zone et de **Rechercher des utilisateurs** .
    
- **Ouvrir une requête** Cliquez pour ouvrir une requête de recherche enregistrée.
    
- **Enregistrer la requête** Cliquez pour enregistrer une requête de recherche.
    
- **+ Ajouter un filtre** Cliquez sur pour ajouter des critères de recherche supplémentaires.
    
- **Champs de filtre de recherche** Sélectionnez le champ sur lequel vous souhaitez filtrer les résultats de la recherche, sélectionnez un opérateur pour la requête, puis tapez la chaîne à rechercher dans.
    
- **Nombre maximal d’utilisateurs à afficher** Tapez le nombre de résultats de recherche que vous souhaitez afficher ou utilisez les flèches pour spécifier le nombre.
    
Ajoutez un texte descriptif, selon les besoins.
  
### <a name="search-results-menus"></a>Menus de la page Résultats de la recherche

- **Permettre aux utilisateurs** Cliquez pour ouvrir la [utilisateurs : nouvel utilisateur Lync Server](ms.lync.lscp.UserNew.md) boîte de dialogue, où vous pouvez ajouter un nouvel utilisateur à Skype pour Business Server.
    
    Pour ajouter un nouveau contact, cliquez sur la flèche vers le bas et sélectionnez **Activer les contacts** pour ouvrir la [utilisateurs : nouveaux objets Contact](ms.lync.lscp.UserNewContact.md) boîte de dialogue.
    
- **Modifier** Cliquez sur **Modifier** , puis cliquez sur **Afficher les détails** pour afficher les détails de l’utilisateur sélectionné, ou cliquez sur **Sélectionner tous les résultats de recherche** pour sélectionner tous les utilisateurs sont affichés dans le tableau de résultats.
    
- **Action** Cliquez sur **Action**, puis sélectionnez l’action à effectuer pour les utilisateurs sélectionnés dans les résultats de recherche. Les actions suivantes sont disponibles :
    
  - **Réactiver pour Lync Server** Active le compte d’utilisateur sélectionné après que qu’il a été désactivé temporairement.
    
  - **Désactiver temporairement pour Lync Server** Désactive le compte d’utilisateur dans Skype pour Business Server jusqu'à ce que vous réactiviez, sans supprimer le compte d’utilisateur.
    
  - **Affecter des stratégies** Ouvre le [utilisateurs : attribuer des stratégies](ms.lync.lscp.UserAssignPolicy.md) boîte de dialogue, où vous pouvez configurer les stratégies affectées à l’utilisateur.
    
  - **Statut du code confidentiel d’affichage** Ouvre le [utilisateurs : afficher l’état de code confidentiel](ms.lync.lscp.UserViewPin.md) boîte de dialogue qui affiche les données de code confidentiel de l’utilisateur sélectionné.
    
  - **Définir le code confidentiel** Ouvre la boîte de dialogue [Définir le code confidentiel](ms.lync.lscp.UserSetPin.md) , où vous pouvez définir le code confidentiel de l’utilisateur sélectionné.
    
  - **Verrouiller le code confidentiel** Verrouille le code confidentiel de l’utilisateur.
    
  - **Code confidentiel de déverrouillage** Supprime le verrou de code confidentiel de l’utilisateur.
    
  - **Supprimer de Lync Server** Supprime le compte d’utilisateur Skype pour Business Server. L’utilisateur n’est pas supprimé d’Active Directory.
    
  - **Supprimer un certificat utilisateur** Supprime tous les certificats accordés à l’utilisateur.
    
  - **Déplacer les utilisateurs sélectionnés vers le pool** Ouvre la boîte de dialogue [Move User](ms.lync.lscp.UserMove.md) , dans laquelle vous pouvez sélectionner un pool vers lequel déplacer l’utilisateur sélectionné.
    
  - **Déplacer tous les utilisateurs vers le pool** Ouvre la boîte de dialogue [Move User](ms.lync.lscp.UserMove.md) , où vous pouvez sélectionner un pool vers lequel déplacer tous les utilisateurs sélectionnés.
    

