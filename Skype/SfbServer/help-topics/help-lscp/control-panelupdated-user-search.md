---
title: 'Panneau de contrôle : recherche utilisateur mise à jour'
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 5/21/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
description: Vous pouvez utiliser les résultats d’une requête de recherche pour configurer les utilisateurs pour Skype Entreprise Server. Vous pouvez rechercher des utilisateurs par nom d’affichage, prénom, nom de famille, nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), adresse SIP ou URI (Uniform Resource Identifier) de ligne. Vous pouvez également rechercher des utilisateurs à l’aide du Panneau de contrôle Lync Server ou du logiciel en ligne Utilisateurs et ordinateurs Active Directory.
ms.openlocfilehash: 40a1ced2933abe628c7d1e56d9a1a7f66466769e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62388492"
---
# <a name="control-panel---updated-user-search"></a>Panneau de configuration - Mise à jour : recherche d’un utilisateur

Vous pouvez utiliser les résultats d’une requête de recherche pour configurer les utilisateurs pour Skype Entreprise Server. Vous pouvez rechercher des utilisateurs par nom d’affichage, prénom, nom de famille, nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), adresse SIP ou URI (Uniform Resource Identifier) de ligne. Vous pouvez également rechercher des utilisateurs à l’aide du Panneau de contrôle Lync Server ou du logiciel en ligne Utilisateurs et ordinateurs Active Directory.

## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Vous pouvez effectuer les tâches suivantes dans la page Panneau de contrôle de **recherche d’utilisateur** :

- [Rechercher des utilisateurs Lync Server 2010](/previous-versions/office/lync-server-2013/lync-server-2013-search-for-lync-server-users)

- [Activer ou désactiver des utilisateurs pour Lync Server 2010](/previous-versions/office/lync-server-2013/lync-server-2013-disable-or-re-enable-user-account-for-lync-server)

- [Déplacement d’un utilisateur](move-user.md)

- [Déplacement de tous les utilisateurs](move-all-users.md)

- [Attribuer des stratégies aux utilisateurs](/previous-versions/office/lync-server-2013/lync-server-2013-assigning-per-user-policies)

- [Activer les utilisateurs pour Voix Entreprise dans Skype Entreprise Server 2015](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [Configurer la fédération, l’accès des utilisateurs distants et la connectivité DE MESSAGERIE INSTANTANÉE publique pour les utilisateurs](/previous-versions/office/lync-server-2013/lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user)

- [Configurer la téléphonie pour les utilisateurs](/previous-versions/office/lync-server-2013/lync-server-2013-configure-telephony-for-a-user)

Pour plus d’informations sur les différentes procédures que vous pouvez effectuer à l’aide du Panneau de Skype Entreprise Server, voir [Manage Skype Entreprise Server 2015](../../manage/manage.md).

## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes suivantes décrivent les menus, commandes, champs et propriétés de la page **Recherche d’un utilisateur**.

### <a name="user-search"></a>Recherche d’un utilisateur

- **Recherche** Recherchez des utilisateurs par la première partie du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur.

- **Recherche LDAP** Recherchez des utilisateurs en tapant une expression LDAP.

- **Zone Rechercher des utilisateurs** Tapez les données utilisateur ou l’expression LDAP dont vous souhaitez mettre en cache.

- **Rechercher** Cliquez pour afficher les utilisateurs qui correspondent aux valeurs de recherche que vous avez entrées dans la zone Rechercher **des** utilisateurs.

- **Ouvrir une requête** Cliquez pour ouvrir une requête de recherche enregistrée.

- **Enregistrer la requête** Cliquez pour enregistrer une requête de recherche.

- **+ Ajouter un filtre** Cliquez pour ajouter des critères de recherche supplémentaires.

- **Champs de filtre de recherche** Sélectionnez le champ sur lequel vous souhaitez filtrer les résultats de recherche, sélectionnez un opérateur pour la requête, puis tapez la chaîne sur laquelle effectuer la recherche.

- **Nombre maximal d’utilisateurs à afficher** Tapez le nombre de résultats de recherche à afficher ou utilisez les flèches haut et bas pour spécifier le nombre.

Ajoutez un texte descriptif, selon les besoins.

### <a name="search-results-menus"></a>Menus de la page Résultats de la recherche

- **Activer les utilisateurs** Cliquez pour ouvrir la boîte de dialogue Utilisateurs : Nouvel utilisateur [Lync Server](users-new-lync-server-user.md), dans laquelle vous pouvez ajouter un nouvel utilisateur à Skype Entreprise Server.

    Pour ajouter un nouveau contact, cliquez sur la flèche vers le bas, puis sélectionnez **Activer les contacts** pour ouvrir la boîte de dialogue [Users: New Contact Objects](users-new-contact-objects.md).

- **Modifier** Cliquez **sur** Modifier, puis sur Afficher les détails pour afficher les détails de l’utilisateur sélectionné,  ou cliquez sur Sélectionner tous les résultats de recherche pour sélectionner tous les **utilisateurs** affichés dans le tableau des résultats.

- **Action** Cliquez **sur Action**, puis sélectionnez l’action que vous souhaitez effectuer pour les utilisateurs sélectionnés dans les résultats de la recherche. Les actions suivantes sont disponibles :

  - **Ré-activer pour Lync Server** Active le compte d’utilisateur sélectionné après sa désactivation temporaire.

  - **Désactiver temporairement pour Lync Server** Désactive le compte d’utilisateur dans Skype Entreprise Server jusqu’à ce que vous le réactiviez, sans supprimer le compte d’utilisateur.

  - **Attribuer des stratégies** Ouvre la boîte [de dialogue Utilisateurs : Attribuer des](users-assign-policies.md) stratégies, dans laquelle vous pouvez configurer les stratégies affectées à l’utilisateur.

  - **Afficher l’état du code confidentiel** Ouvre la boîte [de dialogue Utilisateurs : Afficher l’état du](users-view-pin-status.md) code confidentiel, qui affiche les données de code confidentiel de l’utilisateur sélectionné.

  - **Définir le code confidentiel** Ouvre la boîte [de dialogue Définir le code](set-pin.md) confidentiel, dans laquelle vous pouvez définir le code confidentiel de l’utilisateur sélectionné.

  - **Verrouiller le code confidentiel** Verrouille le code confidentiel de l’utilisateur.

  - **Déverrouiller le code confidentiel** Supprime le verrou sur le code confidentiel de l’utilisateur.

  - **Supprimer de Lync Server** Supprime le compte d’utilisateur de Skype Entreprise Server. L’utilisateur n’est pas supprimé d’Active Directory.

  - **Supprimer un certificat utilisateur** Supprime tous les certificats accordés à l’utilisateur.

  - **Déplacer les utilisateurs sélectionnés vers le pool** Ouvre la boîte [de dialogue Déplacer l’utilisateur](move-user.md) , dans laquelle vous pouvez sélectionner un pool vers lequel déplacer l’utilisateur sélectionné.

  - **Déplacer tous les utilisateurs vers le pool** Ouvre la boîte [de dialogue Déplacer l’utilisateur](move-user.md) , dans laquelle vous pouvez sélectionner un pool vers lequel déplacer tous les utilisateurs sélectionnés.