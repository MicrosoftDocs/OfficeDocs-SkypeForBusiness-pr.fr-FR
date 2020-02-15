---
title: Gérer les comptes d’utilisateur pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: Les sections de cet article décrivent comment activer, désactiver temporairement ou supprimer des utilisateurs Active Directory de Skype entreprise Server.
ms.openlocfilehash: aa1ed16c39141cbcd6542f2c7e254a278c345826
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009637"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>Gérer les comptes d’utilisateur pour Skype entreprise Server

Les sections de cet article décrivent comment activer, désactiver temporairement ou supprimer des utilisateurs Active Directory de Skype entreprise Server.

Pour plus d’informations sur l’activation d’un utilisateur Active Directory, consultez la rubrique [Create a New User Account](https://technet.microsoft.com/library/cc732336%28v=ws.11%29.aspx). Pour plus d’informations sur la suppression d’un utilisateur Active Directory, voir [Delete a User Account](https://technet.microsoft.com/library/cc753730%28v=ws.11%29.aspx).

Ces procédures doivent être effectuées au cours d’une période de maintenance, lorsque l’utilisation de Skype entreprise est la plus faible. Le choix de la planification quotidienne ou hebdomadaire dépend des besoins de votre organisation.

Cet article contient les procédures suivantes :

- [Pour rechercher un ou plusieurs utilisateurs](user-accounts.md#Search)

- [Ajouter et activer un nouvel utilisateur de Skype entreprise Server](user-accounts.md#Add)

- [Désactivation ou réactivation d’un compte d’utilisateur précédemment activé pour Skype entreprise Server](user-accounts.md#Disable)

- [Désactivation d’un utilisateur pour voix entreprise](user-accounts.md#Disable_EV)

- [Supprimer un compte d’utilisateur avec Skype entreprise Server Management Shell](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a>Pour rechercher un ou plusieurs utilisateurs
<a name="Search"> </a>

Vous pouvez utiliser les résultats d’une requête de recherche pour configurer les utilisateurs d’Active Directory pour Skype entreprise Server. Vous pouvez rechercher des utilisateurs par nom d’affichage, prénom, nom de famille, nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), adresse SIP ou URI (Uniform Resource Identifier) de ligne.

Vous pouvez rechercher des utilisateurs à l’aide du panneau de configuration de Skype entreprise Server ou du composant logiciel enfichable utilisateurs et ordinateurs Active Directory. La procédure suivante explique comment utiliser le panneau de configuration de Skype entreprise Server pour rechercher des utilisateurs.

> [!NOTE]
> Dans un environnement avec une topologie de forêt centrale, les résultats de la recherche peuvent ne pas être précis lorsque vous recherchez un utilisateur à l’aide de son adresse de messagerie. Au lieu de cela, vous pouvez rechercher des utilisateurs en spécifiant un préfixe d’adresse SIP, par exemple, SIP : nom, ajouter un filtre de recherche et sélectionner une adresse SIP qui contient une adresse de messagerie partielle ou utiliser la cmdlet **Get-Csuser** .

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Skype entreprise Server.

3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur que vous souhaitez activer, puis cliquez sur **Rechercher**.

5. (Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :

   a. Cliquez sur la flèche déroulante située en haut à droite de l’écran, au-dessus **Résultats de la recherche**, puis sur **Ajouter un filtre**.

   b. Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche dans la liste déroulante.

   c. Dans la liste déroulante **Égal à**, cliquez sur **Égal à** ou **Pas égal à**.

   d. Dans la zone de texte, tapez le critère de recherche selon lequel filtrer les résultats, puis cliquez sur **Rechercher**.

6. les résultats de la recherche apparaissent sous **Résultats de la recherche**. Sélectionnez dans la liste les utilisateurs sur lesquels vous voulez exécuter les tâches de configuration.

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>Ajouter et activer un nouvel utilisateur de Skype entreprise Server
<a name="Add"> </a>

Après avoir activé un compte d’utilisateur dans utilisateurs et ordinateurs Active Directory, vous pouvez utiliser le panneau de configuration de Skype entreprise Server pour créer et activer de nouveaux comptes d’utilisateurs de Skype entreprise Server en ajoutant un utilisateur Active Directory à Skype entreprise Server.

Vous pouvez également utiliser une cmdlet, spécifiquement [Enable-Csuser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Skype entreprise Server.

3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4. Cliquez sur **Activer les utilisateurs**.

5. Dans la boîte de dialogue **Nouvel utilisateur Lync Server**, cliquez sur **Ajouter**.

6. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom, du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse e-mail, du nom d’utilisateur principal ou le numéro de téléphone du compte d’utilisateur Active Directory souhaité, puis cliquez sur **Rechercher**.

7. Dans le tableau, sélectionnez le compte que vous souhaitez ajouter à Skype entreprise Server, puis cliquez sur **OK**.

8. Affectez l’utilisateur à un pool, indiquez d’autres détails utiles et affectez les stratégies à l’utilisateur voulu, puis cliquez sur **Activer**.

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a>Désactivation ou réactivation d’un compte d’utilisateur précédemment activé pour Skype entreprise Server
<a name="Disable"> </a>

Vous pouvez utiliser la procédure suivante pour désactiver un compte d’utilisateur précédemment activé dans Skype entreprise Server sans perdre les paramètres de Skype entreprise Server que vous avez configurés pour le compte d’utilisateur. Étant donné que vous ne perdez pas les paramètres de compte d’utilisateur Skype entreprise Server, vous pouvez réactiver un compte d’utilisateur précédemment activé sans avoir à reconfigurer le compte d’utilisateur.

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Skype entreprise Server.

3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez désactiver ou réactiver, puis cliquez sur **Rechercher**.

5. Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez désactiver ou réactiver.

6. Dans le menu **Action**, effectuez l’une des opérations suivantes :

   - Pour désactiver temporairement le compte d’utilisateur pour Skype entreprise Server, cliquez sur **désactiver temporairement pour Lync Server**.

   - Pour activer le compte d’utilisateur pour Skype entreprise Server, cliquez sur **réactiver pour Lync Server**.

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Utiliser Windows PowerShell pour désactiver ou réactiver les comptes d’utilisateurs

Les comptes d’utilisateur peuvent être temporairement désactivés, puis réactivés ultérieurement à l’aide de la cmdlet **Set-Csuser** . Vous pouvez exécuter cette cmdlet à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Skype entreprise Server, voir l’article de blog [« démarrage rapide : gestion de Microsoft Lync server 2010 à l’aide de PowerShell à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876). Le processus est le même dans Skype entreprise Server.

### <a name="to-disable-a-user-account"></a>Pour désactiver un compte d’utilisateur

- Pour désactiver temporairement un compte d’utilisateur, définissez la valeur de la propriété Enabled sur False ($False). Par exemple :

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a>Pour réactiver un compte d’utilisateur

- Pour réactiver un compte d’utilisateur désactivé, définissez la valeur de la propriété Enabled sur True ($True). Par exemple :

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Set-Csuser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) .

## <a name="disable-a-user-for-enterprise-voice"></a>Désactivation d’un utilisateur pour voix entreprise
<a name="Disable_EV"> </a>

Utilisez la procédure suivante pour désactiver voix entreprise pour un compte d’utilisateur qui est activé pour Skype entreprise Server.

### <a name="to-disable-a-user-account-for-enterprise-voice"></a>Pour désactiver un compte d’utilisateur pour voix entreprise

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Skype entreprise Server.

3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez activer, puis cliquez sur **Rechercher**.

5. Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez activer pour voix entreprise.

6. Dans le menu **Edition**, cliquez sur **Afficher les détails**.

7. Dans la page **Modifier l’utilisateur Lync Server**, sous **Téléphonie**, cliquez sur l’option de votre choix à l’exception de **Voix Entreprise**.

    > [!NOTE]
    > Pour empêcher un utilisateur d’effectuer des appels audio ou vidéo à l’aide de Lync, sous **téléphonie**, cliquez sur **audio/vidéo désactivé**.

8. Cliquez sur **Valider**.

L’utilisateur ne peut plus utiliser la fonctionnalité voix entreprise. Informations connexes : <br/>[Voix entreprise et mobilité](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [Activer les utilisateurs pour voix entreprise dans Skype entreprise Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Skype Entreprise Server Management Shell](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>Supprimer un compte d’utilisateur avec Skype entreprise Server Management Shell
<a name="Remove"> </a>

Vous pouvez utiliser la procédure suivante pour supprimer un compte d’utilisateur ajouté précédemment dans Skype entreprise Server.

> [!NOTE]
> La suppression d’un utilisateur entraînera la perte de tous les paramètres associés au compte d’utilisateur. Si vous souhaitez désactiver temporairement un compte d’utilisateur, reportez-vous à la rubrique désactiver ou réactiver [un compte d’utilisateur précédemment activé pour Skype entreprise Server](user-accounts.md#Disable).

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Skype entreprise Server.

3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez désactiver ou réactiver, puis cliquez sur **Rechercher**.

5. Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez supprimer.

6. Dans le menu **Action**, sélectionnez **Supprimer de Lync Server** et une boîte de dialogue apparaît.

7. Dans la boîte de dialogue, sélectionnez **OK** pour supprimer l’utilisateur.

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>Supprimer des comptes d’utilisateurs avec des applets de commande Windows PowerShell

Vous pouvez supprimer des comptes d’utilisateurs à l’aide de l’applet de commande Disable-CsUser. Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Skype entreprise Server, voir l’article de blog [« démarrage rapide : gestion de Microsoft Lync server 2010 à l’aide de PowerShell à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876). Le processus est le même dans Skype entreprise Server.

### <a name="to-remove-a-user-account"></a>Pour supprimer un compte d’utilisateur
Pour supprimer un compte d’utilisateur, utilisez l’applet de commande Disable-CsUser. Par exemple :

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Disable-Csuser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) .

## <a name="see-also"></a>Voir aussi
<a name="Remove"> </a>

[Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
