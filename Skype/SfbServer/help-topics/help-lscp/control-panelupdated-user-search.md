---
title: Panneau de configuration-recherche d’utilisateur mise à jour
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/21/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
description: Vous pouvez utiliser les résultats d’une requête de recherche pour configurer les utilisateurs de Skype entreprise Server. Vous pouvez rechercher des utilisateurs par nom d’affichage, prénom, nom de famille, nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), adresse SIP ou URI (Uniform Resource Identifier) de ligne. Vous pouvez également rechercher des utilisateurs à partir du Panneau de configuration Lync Server ou du composant Utilisateurs et ordinateurs Active Directory.
ms.openlocfilehash: 7b6b72275ffd5dfe8c03b41d4da2ca8ee6f40a3a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285999"
---
# <a name="control-panel---updated-user-search"></a>Panneau de configuration - Mise à jour : recherche d’un utilisateur

Vous pouvez utiliser les résultats d’une requête de recherche pour configurer les utilisateurs de Skype entreprise Server. Vous pouvez rechercher des utilisateurs par nom d’affichage, prénom, nom de famille, nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), adresse SIP ou URI (Uniform Resource Identifier) de ligne. Vous pouvez également rechercher des utilisateurs à partir du Panneau de configuration Lync Server ou du composant Utilisateurs et ordinateurs Active Directory.

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

Pour plus d’informations sur les différentes procédures que vous pouvez effectuer à l’aide du panneau de configuration Skype entreprise Server, reportez-vous à la rubrique [gestion de Skype entreprise server 2015](../../manage/manage.md).

## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page **Recherche d’un utilisateur**.

### <a name="user-search"></a>Recherche d’un utilisateur

- **Effectuer une recherche** Recherchez des utilisateurs en fonction de la première partie du nom d’affichage, prénom, nom, nom du compte SAM, adresse SIP ou URI de ligne du compte d’utilisateur.

- **Recherche LDAP** Recherchez des utilisateurs en entrant une expression LDAP.

- **Champ Rechercher des utilisateurs** Tapez les données utilisateur ou l’expression LDAP pour lesquelles vous souhaitez recherche.

- **Recherchez** Cliquez pour afficher les utilisateurs qui correspondent aux valeurs de recherche que vous avez entrées dans les zones **Rechercher les utilisateurs** et.

- **Ouvrir la requête** Cliquez pour ouvrir une requête de recherche enregistrée.

- **Enregistrer la requête** Cliquez sur pour enregistrer une requête de recherche.

- **+ Ajouter un filtre** Cliquez pour ajouter d’autres critères de recherche.

- **Champs de filtre de recherche** Sélectionnez le champ pour lequel vous voulez filtrer les résultats de recherche, sélectionnez un opérateur pour la requête, puis tapez la chaîne dans laquelle vous souhaitez effectuer une recherche.

- **Nombre maximal d’utilisateurs à afficher** Tapez le nombre de résultats de recherche que vous voulez afficher, ou utilisez les flèches haut et bas pour spécifier le numéro.

Ajoutez un texte descriptif, selon les besoins.

### <a name="search-results-menus"></a>Menus de la page Résultats de la recherche

- **Permettre aux utilisateurs** Cliquez pour ouvrir la boîte de dialogue [utilisateurs: nouveau serveur Lync Server](users-new-lync-server-user.md) , dans lequel vous pouvez ajouter un nouvel utilisateur à Skype entreprise Server.

    Pour ajouter un nouveau contact, cliquez sur la flèche Bas, puis sélectionnez **Activer les contacts** pour afficher la boîte de dialogue [Users: New Contact Objects](users-new-contact-objects.md).

- **Modifier** Cliquez sur **modifier** , puis sur **afficher les détails** pour afficher les détails de l’utilisateur sélectionné ou cliquez sur **Sélectionner tous les résultats** de la recherche pour sélectionner tous les utilisateurs affichés dans le tableau des résultats.

- **Action** Cliquez sur **action**, puis sélectionnez l’action que vous voulez effectuer pour les utilisateurs sélectionnés dans les résultats de la recherche. Les actions suivantes sont disponibles:

  - **Nouvelle activation de Lync Server** Active le compte d’utilisateur sélectionné après son Désactivation temporaire.

  - **Désactiver temporairement pour Lync Server** Désactive le compte d’utilisateur dans Skype entreprise Server jusqu’à ce que vous le réactiviez, sans supprimer le compte d’utilisateur.

  - **Attribuer des stratégies** Ouvre la boîte de dialogue [utilisateurs: affecter des stratégies](users-assign-policies.md) , dans laquelle vous pouvez configurer les stratégies attribuées à l’utilisateur.

  - **Afficher l’État** de la broche Ouvre la boîte de dialogue [utilisateurs: afficher l’État](users-view-pin-status.md) de la broche qui affiche les données de code confidentiel pour l’utilisateur sélectionné.

  - **Définir le code confidentiel** Ouvre la boîte de dialogue [définir le code confidentiel](set-pin.md) , dans laquelle vous pouvez définir le code confidentiel pour l’utilisateur sélectionné.

  - **Verrouiller le code confidentiel** Verrouille le code confidentiel de l’utilisateur.

  - **Déverrouiller le code confidentiel** Supprime le verrou sur le code confidentiel de l’utilisateur.

  - **Supprimer de Lync Server** Supprime le compte d’utilisateur de Skype entreprise Server. L’utilisateur n’est pas supprimé d’Active Directory.

  - **Supprimer un certificat utilisateur** Supprime tous les certificats attribués à l’utilisateur.

  - **Déplacer les utilisateurs sélectionnés vers le pool** Ouvre la boîte de dialogue [déplacer l’utilisateur](move-user.md) , dans laquelle vous pouvez sélectionner un pool dans lequel déplacer l’utilisateur sélectionné.

  - **Déplacer tous les utilisateurs vers le pool** Ouvre la boîte de dialogue [déplacer l’utilisateur](move-user.md) , dans laquelle vous pouvez sélectionner un pool dans lequel déplacer tous les utilisateurs sélectionnés.


