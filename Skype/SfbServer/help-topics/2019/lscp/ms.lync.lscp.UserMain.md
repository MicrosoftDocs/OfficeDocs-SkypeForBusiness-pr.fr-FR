---
title: Panneau de contrôle - Recherche utilisateur mise à jour
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
ROBOTS: NOINDEX, NOFOLLOW
description: Vous pouvez utiliser les résultats d’une requête de recherche pour configurer des utilisateurs pour Skype Entreprise Server. Vous pouvez rechercher des utilisateurs par nom d’affichage, prénom, nom de famille, nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), adresse SIP ou URI (Uniform Resource Identifier) de ligne. Vous pouvez également rechercher des utilisateurs à l’aide du Panneau de contrôle Lync Server ou du logiciel en ligne Utilisateurs et ordinateurs Active Directory.
ms.openlocfilehash: f74c1dfe7f1b8184c59261ff03a01f2f5b39db18
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820244"
---
# <a name="control-panel---updated-user-search"></a>Panneau de configuration - Mise à jour : recherche d’un utilisateur

Vous pouvez utiliser les résultats d’une requête de recherche pour configurer des utilisateurs pour Skype Entreprise Server. Vous pouvez rechercher des utilisateurs par nom d’affichage, prénom, nom de famille, nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), adresse SIP ou URI (Uniform Resource Identifier) de ligne. Vous pouvez également rechercher des utilisateurs à l’aide du Panneau de contrôle Lync Server ou du logiciel en ligne Utilisateurs et ordinateurs Active Directory.

## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Vous pouvez effectuer les tâches suivantes dans la page Panneau de contrôle de recherche **de** l’utilisateur :

- [Rechercher des utilisateurs](https://technet.microsoft.com/library/3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5.aspx)

- [Activer ou désactiver des utilisateurs](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)

- [Déplacement d’un utilisateur](ms.lync.lscp.UserMove.md)

- [Déplacement de tous les utilisateurs](ms.lync.lscp.UserMoveAll.md)

- [Attribuer des stratégies aux utilisateurs](https://technet.microsoft.com/library/a4ed0120-d9e5-4eb2-acfd-8de2cb503652.aspx)

- [Activer les utilisateurs Voix Entreprise dans Skype Entreprise Server](../../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [Configurer la fédération, l’accès des utilisateurs distants et la connectivité DE MESSAGERIE INSTANTANÉE publique pour les utilisateurs](https://technet.microsoft.com/library/736fcaad-9f95-4896-b767-e199d86a00a4.aspx)

- [Configurer la téléphonie pour les utilisateurs](https://technet.microsoft.com/library/4546432e-c839-4517-a2c5-bc0d4d8c6a03.aspx)



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

- **Activer les utilisateurs** Cliquez pour ouvrir la boîte de dialogue Utilisateurs : Nouvel utilisateur [Lync Server,](ms.lync.lscp.UserNew.md) dans laquelle vous pouvez ajouter un nouvel utilisateur à Skype Entreprise Server.

    Pour ajouter un nouveau contact, cliquez sur la flèche vers le bas, puis sélectionnez **Activer les contacts** pour ouvrir la boîte de dialogue [Users: New Contact Objects](ms.lync.lscp.UserNewContact.md).

- **Modifier** Cliquez **sur** Modifier, puis sur Afficher les détails pour afficher  les détails de l’utilisateur sélectionné, ou cliquez sur Sélectionner tous les résultats de recherche pour sélectionner tous les **utilisateurs** affichés dans le tableau des résultats.

- **Action** Cliquez **sur Action,** puis sélectionnez l’action que vous souhaitez effectuer pour les utilisateurs sélectionnés dans les résultats de la recherche. Les actions suivantes sont disponibles :

  - **Ré-activer pour Lync Server** Active le compte d’utilisateur sélectionné après sa désactivation temporaire.

  - **Désactiver temporairement pour Lync Server** Désactive le compte d’utilisateur dans Skype Entreprise Server jusqu’à ce que vous le réactiviez, sans supprimer le compte d’utilisateur.

  - **Attribuer des stratégies** Ouvre la boîte [de dialogue Utilisateurs : Attribuer des](ms.lync.lscp.UserAssignPolicy.md) stratégies, dans laquelle vous pouvez configurer les stratégies affectées à l’utilisateur.

  - **Afficher l’état du code confidentiel** Ouvre la boîte [de dialogue Utilisateurs : Afficher l’état du](ms.lync.lscp.UserViewPin.md) code confidentiel, qui affiche les données de code confidentiel de l’utilisateur sélectionné.

  - **Définir le code confidentiel** Ouvre la boîte [de dialogue Définir le code](ms.lync.lscp.UserSetPin.md) confidentiel, dans laquelle vous pouvez définir le code confidentiel de l’utilisateur sélectionné.

  - **Verrouiller le code confidentiel** Verrouille le code confidentiel de l’utilisateur.

  - **Déverrouiller le code confidentiel** Supprime le verrou sur le code confidentiel de l’utilisateur.

  - **Supprimer de Lync Server** Supprime le compte d’utilisateur de Skype Entreprise Server. L’utilisateur n’est pas supprimé d’Active Directory.

  - **Supprimer un certificat utilisateur** Supprime tous les certificats accordés à l’utilisateur.

  - **Déplacer les utilisateurs sélectionnés vers le pool** Ouvre la boîte de dialogue Déplacer [l’utilisateur,](ms.lync.lscp.UserMove.md) dans laquelle vous pouvez sélectionner un pool vers lequel déplacer l’utilisateur sélectionné.

  - **Déplacer tous les utilisateurs vers le pool** Ouvre la boîte [de dialogue Déplacer l’utilisateur,](ms.lync.lscp.UserMove.md) dans laquelle vous pouvez sélectionner un pool vers lequel déplacer tous les utilisateurs sélectionnés.


