---
title: Le panneau de configuration - recherche d’un utilisateur mis à jour
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 7318d37741eba1b75ff930bf6b252fbfbdabf4cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33914043"
---
# <a name="control-panel---updated-user-search"></a>Panneau de configuration - Mise à jour : recherche d’un utilisateur

Vous pouvez utiliser les résultats d’une requête de recherche pour configurer les utilisateurs pour Skype pour Business Server. Vous pouvez rechercher des utilisateurs par nom d’affichage, prénom, nom de famille, nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), adresse SIP ou URI (Uniform Resource Identifier) de ligne. Vous pouvez également rechercher des utilisateurs à partir du Panneau de configuration Lync Server ou du composant Utilisateurs et ordinateurs Active Directory.

## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Recherche d’un utilisateur** du Panneau de configuration, vous pouvez effectuer les tâches suivantes :

- [Search for Lync Server 2010 Users](https://technet.microsoft.com/library/3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5.aspx)

- [Enable or Disable Users for Lync Server 2010](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)

- [Déplacement d’un utilisateur](move-user.md)

- [Déplacement de tous les utilisateurs](move-all-users.md)

- [Assign Policies to Users](https://technet.microsoft.com/library/a4ed0120-d9e5-4eb2-acfd-8de2cb503652.aspx)

- [Enable users for Enterprise Voice in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [Configure Federation, Remote User Access, and Public IM Connectivity for Users](https://technet.microsoft.com/library/736fcaad-9f95-4896-b767-e199d86a00a4.aspx)

- [Configure Telephony for Users](https://technet.microsoft.com/library/4546432e-c839-4517-a2c5-bc0d4d8c6a03.aspx)

Pour plus d’informations sur les différentes procédures que vous pouvez effectuer à l’aide de la Skype pour le panneau de configuration serveur Business, voir [Gérer les Skype pour Business Server 2015](../../manage/manage.md).

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

- **Permettre aux utilisateurs** Cliquez pour ouvrir la [utilisateurs : nouvel utilisateur Lync Server](users-new-lync-server-user.md) boîte de dialogue, où vous pouvez ajouter un nouvel utilisateur à Skype pour Business Server.

    Pour ajouter un nouveau contact, cliquez sur la flèche Bas, puis sélectionnez **Activer les contacts** pour afficher la boîte de dialogue [Users: New Contact Objects](users-new-contact-objects.md).

- **Modifier** Cliquez sur **Modifier** , puis cliquez sur **Afficher les détails** pour afficher les détails de l’utilisateur sélectionné, ou cliquez sur **Sélectionner tous les résultats de recherche** pour sélectionner tous les utilisateurs sont affichés dans le tableau de résultats.

- **Action** Cliquez sur **Action**, puis sélectionnez l’action à effectuer pour les utilisateurs sélectionnés dans les résultats de recherche. Les actions suivantes sont disponibles :

  - **Réactiver pour Lync Server** Active le compte d’utilisateur sélectionné après que qu’il a été désactivé temporairement.

  - **Désactiver temporairement pour Lync Server** Désactive le compte d’utilisateur dans Skype pour Business Server jusqu'à ce que vous réactiviez, sans supprimer le compte d’utilisateur.

  - **Affecter des stratégies** Ouvre le [utilisateurs : attribuer des stratégies](users-assign-policies.md) boîte de dialogue, où vous pouvez configurer les stratégies affectées à l’utilisateur.

  - **Statut du code confidentiel d’affichage** Ouvre le [utilisateurs : afficher l’état de code confidentiel](users-view-pin-status.md) boîte de dialogue qui affiche les données de code confidentiel de l’utilisateur sélectionné.

  - **Définir le code confidentiel** Ouvre la boîte de dialogue [Définir le code confidentiel](set-pin.md) , où vous pouvez définir le code confidentiel de l’utilisateur sélectionné.

  - **Verrouiller le code confidentiel** Verrouille le code confidentiel de l’utilisateur.

  - **Code confidentiel de déverrouillage** Supprime le verrou de code confidentiel de l’utilisateur.

  - **Supprimer de Lync Server** Supprime le compte d’utilisateur Skype pour Business Server. L’utilisateur n’est pas supprimé d’Active Directory.

  - **Supprimer un certificat utilisateur** Supprime tous les certificats accordés à l’utilisateur.

  - **Déplacer les utilisateurs sélectionnés vers le pool** Ouvre la boîte de dialogue [Move User](move-user.md) , dans laquelle vous pouvez sélectionner un pool vers lequel déplacer l’utilisateur sélectionné.

  - **Déplacer tous les utilisateurs vers le pool** Ouvre la boîte de dialogue [Move User](move-user.md) , où vous pouvez sélectionner un pool vers lequel déplacer tous les utilisateurs sélectionnés.


