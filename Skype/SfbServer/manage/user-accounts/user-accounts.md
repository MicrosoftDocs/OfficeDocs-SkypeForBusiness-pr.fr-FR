---
title: Gérer les comptes d’utilisateurs pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: Les sections de cet article décrivent l’activation, la désactivation temporaire ou la suppression d’utilisateurs Active Directory de Skype entreprise Server.
ms.openlocfilehash: 45217593dd010c4daf73d6b5edcbf6f5f4e681a5
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992401"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>Gérer les comptes d’utilisateurs pour Skype entreprise Server

Les sections de cet article décrivent l’activation, la désactivation temporaire ou la suppression d’utilisateurs Active Directory de Skype entreprise Server.

Pour plus d’informations sur l’activation d’un utilisateur Active Directory, voir [créer un compte d’utilisateur](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx). Pour plus d’informations sur la suppression d’un utilisateur Active Directory, voir [supprimer un compte d’utilisateur](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).

Ces procédures doivent être effectuées au cours d’une fenêtre de maintenance, lorsque le niveau d’utilisation de Skype entreprise est inférieur. Le mode de planification quotidienne ou hebdomadaire sera déterminé selon les besoins de votre organisation.

Cet article contient les procédures suivantes :

- [Pour rechercher un ou plusieurs utilisateurs](user-accounts.md#Search)

- [Ajout et activation d’un nouvel utilisateur de Skype entreprise Server](user-accounts.md#Add)

- [Désactivation ou réactivation d’un compte d’utilisateur précédemment activé pour Skype entreprise Server](user-accounts.md#Disable)

- [Désactiver un utilisateur pour voix entreprise](user-accounts.md#Disable_EV)

- [Supprimer un compte d’utilisateur avec Skype entreprise Server Management Shell](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a>Pour rechercher un ou plusieurs utilisateurs
<a name="Search"> </a>

Vous pouvez utiliser les résultats d’une requête de recherche pour configurer les utilisateurs Active Directory pour Skype entreprise Server. Vous pouvez rechercher des utilisateurs par nom d’affichage, prénom, nom de famille, nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), adresse SIP ou URI (Uniform Resource Identifier) de ligne.

Vous pouvez rechercher des utilisateurs à l’aide du panneau de configuration Skype entreprise Server ou du composant logiciel enfichable utilisateurs et ordinateurs Active Directory. La procédure suivante vous explique comment utiliser le panneau de configuration Skype entreprise Server pour rechercher des utilisateurs.

> [!NOTE]
> Dans un environnement doté d’une topologie de forêt centrale, il est possible que les résultats de la recherche soient inexacts lorsque vous recherchez un utilisateur à l’aide de son adresse de messagerie. Au lieu de cela, vous pouvez rechercher des utilisateurs en spécifiant un préfixe d’adresse SIP (par exemple, SIP : nom), ajouter un filtre de recherche et sélectionner une adresse SIP contenant une adresse de messagerie partielle ou utiliser l’applet de requête **Get-Csuser** .

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.

3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4. Dans la boîte de **recherche utilisateurs** , entrez tout ou la première partie du nom d’affichage, prénom, nom, nom de compte Sam, adresse SIP ou URI de ligne du compte d’utilisateur que vous souhaitez rechercher, puis cliquez sur **Rechercher**.

5. (Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :

   a. Cliquez sur la flèche de développement située dans le coin supérieur droit de l’écran au-dessus des résultats de la **recherche**, puis cliquez sur **Ajouter un filtre**.

   b. Entrez la propriété User en le tapant ou en cliquant sur la flèche dans la liste déroulante pour sélectionner une propriété d’utilisateur.

   c. Dans la liste **égal à** , cliquez sur **égal à** ou **n’est pas égal à**.

   d. Dans la zone de texte, tapez les critères de recherche que vous voulez utiliser pour filtrer les résultats de recherche, puis cliquez sur **Rechercher**.

6. Les résultats de la recherche apparaissent sous résultats de la **recherche**. Vous pouvez sélectionner tout ou partie des utilisateurs de la liste et effectuer des tâches de configuration pour les utilisateurs sélectionnés.

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>Ajout et activation d’un nouvel utilisateur de Skype entreprise Server
<a name="Add"> </a>

Après avoir activé un compte d’utilisateur dans utilisateurs et ordinateurs Active Directory, vous pouvez utiliser le panneau de configuration Skype entreprise Server pour créer et activer les nouveaux comptes d’utilisateurs Skype entreprise Server en ajoutant un utilisateur Active Directory à Skype entreprise Server.

Vous pouvez également utiliser une applet de cmdlet, en particulier [Enable-Csuser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.

3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4. Cliquez sur **activer les utilisateurs**.

5. Dans la boîte de dialogue **nouveau serveur Lync** , cliquez sur **Ajouter**.

6. Dans la boîte de dialogue **Rechercher des utilisateurs** , tapez tout ou la première partie du nom, le nom d’affichage, le prénom, le nom, le nom du compte Sam (Security Accounts Manager), l’adresse de messagerie, le nom d’utilisateur principal (UPN) ou le numéro de téléphone du compte d’utilisateur Active Directory souhaité, puis cliquez sur **Rechercher**.

7. Dans le tableau, sélectionnez le compte que vous voulez ajouter à Skype entreprise Server, puis cliquez sur **OK**.

8. Affectez l’utilisateur à un pool, spécifiez des détails supplémentaires et attribuez les stratégies à l’utilisateur de votre choix, puis cliquez sur **activer**.

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a>Désactivation ou réactivation d’un compte d’utilisateur précédemment activé pour Skype entreprise Server
<a name="Disable"> </a>

Vous pouvez utiliser la procédure suivante pour désactiver un compte d’utilisateur déjà activé dans Skype entreprise Server sans perdre les paramètres de Skype entreprise Server que vous avez configurés pour le compte d’utilisateur. Étant donné que vous ne perdez pas les paramètres de compte d’utilisateur Skype entreprise Server, vous pouvez réactiver un compte d’utilisateur déjà activé sans avoir à reconfigurer le compte d’utilisateur.

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.

3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4. Dans la boîte de dialogue **Rechercher des utilisateurs** , tapez tout ou la première partie du nom complet, prénom, nom, nom du compte de comptes de sécurité (Sam), adresse SIP ou URI (Uniform Resource Identifier) du compte d’utilisateur que vous souhaitez désactiver ou réactiver, puis cliquez sur **Rechercher**.

5. Dans la table, cliquez sur le compte d’utilisateur que vous souhaitez désactiver ou réactiver.

6. Dans le menu **action** , effectuez l’une des opérations suivantes :

   - Pour désactiver temporairement le compte d’utilisateur Skype entreprise Server, cliquez sur **désactiver temporairement pour Lync Server**.

   - Pour activer le compte d’utilisateur Skype entreprise Server, cliquez sur **réactiver pour Lync Server**.

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Utiliser Windows PowerShell pour désactiver ou réactiver les comptes d’utilisateurs

Pour désactiver temporairement les comptes d’utilisateurs, vous pouvez les réactiver ultérieurement à l’aide de l’applet de dialogue **Set-Csuser** . Vous pouvez exécuter cette applet de commande à partir de Skype entreprise Server Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype entreprise Server, voir l’article sur le blog [« démarrage rapide : gestion de Microsoft Lync Server 2010 à l’aide de Remote PowerShell »](https://go.microsoft.com/fwlink/p/?linkId=255876). Le processus est le même dans Skype entreprise Server.

### <a name="to-disable-a-user-account"></a>Pour désactiver un compte d’utilisateur

- Pour désactiver temporairement un compte d’utilisateur, définissez la valeur de la propriété Enabled sur false ($False). Par exemple :

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a>Pour réactiver un compte d’utilisateur

- Pour réactiver un compte d’utilisateur désactivé, définissez la valeur de la propriété Enabled sur true ($True). Par exemple :

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Set-Csuser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) .

## <a name="disable-a-user-for-enterprise-voice"></a>Désactiver un utilisateur pour voix entreprise
<a name="Disable_EV"> </a>

Utilisez la procédure suivante pour désactiver Enterprise Voice pour un compte d’utilisateur activé pour Skype entreprise Server.

### <a name="to-disable-a-user-account-for-enterprise-voice"></a>Pour désactiver un compte d’utilisateur pour voix entreprise

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.

3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager), de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur à activer, puis cliquez sur **Rechercher**.

5. Dans la table, cliquez sur le compte d’utilisateur que vous souhaitez activer pour voix entreprise.

6. Dans le menu **Edition**, cliquez sur **Afficher les détails**.

7. Dans la page **modifier l’utilisateur de Lync Server** , sous **téléphonie**, cliquez sur une option sauf **entreprise voix**.

    > [!NOTE]
    > Pour empêcher un utilisateur de passer des appels audio ou vidéo à l’aide de Lync, sous **téléphonie**, cliquez sur **audio/vidéo désactivé**.

8. Cliquez sur **Valider**.

L’utilisateur ne peut plus utiliser la fonctionnalité voix entreprise. Informations connexes : <br/>[Voix et mobilité entreprise](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [Activer les utilisateurs pour voix entreprise dans Skype entreprise Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Skype Entreprise Server Management Shell](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>Supprimer un compte d’utilisateur avec Skype entreprise Server Management Shell
<a name="Remove"> </a>

Vous pouvez utiliser la procédure suivante pour supprimer un compte d’utilisateur déjà ajouté dans Skype entreprise Server.

> [!NOTE]
> La suppression d’un utilisateur entraîne la perte des paramètres que vous avez configurés pour le compte d’utilisateur. Si vous voulez désactiver temporairement un compte d’utilisateur, reportez-vous à [la rubrique désactiver ou réactiver un compte d’utilisateur précédemment activé pour Skype entreprise Server](user-accounts.md#Disable).

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.

3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4. Dans la boîte de dialogue **Rechercher des utilisateurs** , tapez tout ou la première partie du nom complet, prénom, nom, nom du compte de comptes de sécurité (Sam), adresse SIP ou URI (Uniform Resource Identifier) du compte d’utilisateur que vous souhaitez désactiver ou réactiver, puis cliquez sur **Rechercher**.

5. Dans la table, cliquez sur le compte d’utilisateur que vous voulez supprimer.

6. Dans le menu **action** , sélectionnez **supprimer de Lync Server**et une boîte de dialogue s’affiche.

7. Dans la boîte de dialogue, sélectionnez **OK** pour supprimer l’utilisateur.

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>Supprimer des comptes d’utilisateurs avec des cmdlets Windows PowerShell

Vous pouvez supprimer des comptes d’utilisateurs à l’aide de l’applet de passe Disable-CsUser. Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou d’une session distante Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype entreprise Server, voir l’article sur le blog [« démarrage rapide : gestion de Microsoft Lync Server 2010 à l’aide de Remote PowerShell »](https://go.microsoft.com/fwlink/p/?linkId=255876). Le processus est le même dans Skype entreprise Server.

### <a name="to-remove-a-user-account"></a>Pour supprimer un compte d’utilisateur
Pour supprimer un compte d’utilisateur, utilisez l’applet de passe Disable-CsUser. Par exemple :

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

Pour plus d’informations, reportez-vous à la rubrique d’aide de l’applet de la cmdlet [Disable-Csuser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) .

## <a name="see-also"></a>Voir aussi
<a name="Remove"> </a>

[Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
