---
title: Gérer les comptes d’utilisateur pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: Les sections de cet article décrivent comment activer, désactiver temporairement ou supprimer des utilisateurs Active Directory d’Skype Entreprise Server.
ms.openlocfilehash: a604e08ad23f00f8eaf0342254df4563c0a6b864
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622186"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>Gérer les comptes d’utilisateur pour Skype Entreprise Server

Les sections de cet article décrivent comment activer, désactiver temporairement ou supprimer des utilisateurs Active Directory d’Skype Entreprise Server.

Pour plus d’informations sur la façon d’activer un utilisateur Active Directory, voir [Créer un compte d’utilisateur.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732336(v=ws.11)) Pour plus d’informations sur la suppression d’un utilisateur Active Directory, voir [Supprimer un compte d’utilisateur.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))

Ces procédures doivent être effectuées au cours d’une fenêtre de maintenance, lorsque Skype Entreprise’utilisation est la plus faible. Les besoins de votre organisation déterminent si cette planification est quotidienne ou hebdomadaire.

Cet article contient les procédures suivantes :

- [Pour rechercher un ou plusieurs utilisateurs](user-accounts.md#Search)

- [Ajouter et activer un nouvel utilisateur Skype Entreprise Server utilisateur](user-accounts.md#Add)

- [Désactiver ou réactiver un compte d’utilisateur précédemment activé pour Skype Entreprise Server](user-accounts.md#Disable)

- [Désactiver un utilisateur pour une Voix Entreprise](user-accounts.md#Disable_EV)

- [Supprimer un compte d’utilisateur avec Skype Entreprise Server Management Shell](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a>Pour rechercher un ou plusieurs utilisateurs
<a name="Search"> </a>

Vous pouvez utiliser les résultats d’une requête de recherche pour configurer les utilisateurs Active Directory pour Skype Entreprise Server. Vous pouvez rechercher des utilisateurs par nom d’affichage, prénom, nom de famille, nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), adresse SIP ou URI (Uniform Resource Identifier) de ligne.

Vous pouvez rechercher des utilisateurs à l’aide Skype Entreprise Server Panneau de Skype Entreprise Server ou du logiciel en ligne Utilisateurs et ordinateurs Active Directory. La procédure suivante décrit comment utiliser le Panneau de Skype Entreprise Server pour rechercher des utilisateurs.

> [!NOTE]
> Dans un environnement avec une topologie de forêt centrale, les résultats de la recherche peuvent ne pas être précis lorsque vous recherchez un utilisateur par son adresse e-mail. Au lieu de cela, vous pouvez rechercher des utilisateurs en spécifiant un préfixe d’adresse SIP, par exemple sip:name, ajouter un filtre de recherche et sélectionner une adresse SIP qui contient une adresse de messagerie partielle, ou utiliser l'; 

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.

3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur que vous souhaitez activer, puis cliquez sur **Rechercher**.

5. (Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :

   a. Cliquez sur la flèche déroulante située en haut à droite de l’écran, au-dessus **Résultats de la recherche**, puis sur **Ajouter un filtre**.

   b. Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche dans la liste déroulante.

   c. Dans la liste déroulante **Égal à**, cliquez sur **Égal à** ou **Pas égal à**.

   d. Dans la zone de texte, tapez le critère de recherche selon lequel filtrer les résultats, puis cliquez sur **Rechercher**.

6. les résultats de la recherche apparaissent sous **Résultats de la recherche**. Sélectionnez dans la liste les utilisateurs sur lesquels vous voulez exécuter les tâches de configuration.

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>Ajouter et activer un nouvel utilisateur Skype Entreprise Server utilisateur
<a name="Add"> </a>

Après avoir activé un compte d’utilisateur dans Utilisateurs et ordinateurs Active Directory, vous pouvez utiliser le Panneau de Skype Entreprise Server pour créer et activer de nouveaux comptes d’utilisateurs Skype Entreprise Server en ajoutant un utilisateur Active Directory à Skype Entreprise Server.

Vous pouvez également utiliser une cmdlet, en particulier [Enable-CsUser](/powershell/module/skype/enable-csuser).

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.

3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4. Cliquez sur **Activer les utilisateurs**.

5. Dans la boîte de dialogue **Nouvel utilisateur Lync Server**, cliquez sur **Ajouter**.

6. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom, du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse e-mail, du nom d’utilisateur principal ou le numéro de téléphone du compte d’utilisateur Active Directory souhaité, puis cliquez sur **Rechercher**.

7. Dans le tableau, sélectionnez le compte que vous souhaitez ajouter à Skype Entreprise Server, puis cliquez sur **OK**.

8. Affectez l’utilisateur à un pool, indiquez d’autres détails utiles et affectez les stratégies à l’utilisateur voulu, puis cliquez sur **Activer**.

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a>Désactiver ou réactiver un compte d’utilisateur précédemment activé pour Skype Entreprise Server
<a name="Disable"> </a>

Vous pouvez utiliser la procédure suivante pour désactiver un compte d’utilisateur précédemment activé dans Skype Entreprise Server sans perdre les paramètres de Skype Entreprise Server que vous avez configurés pour le compte d’utilisateur. Étant donné que vous ne perdez pas les paramètres de compte d’utilisateur Skype Entreprise Server, vous pouvez ré-activer un compte d’utilisateur précédemment activé sans avoir à reconfigurer le compte d’utilisateur.

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.

3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez désactiver ou réactiver, puis cliquez sur **Rechercher**.

5. Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez désactiver ou réactiver.

6. Dans le menu **Action**, effectuez l’une des opérations suivantes :

   - Pour désactiver temporairement le compte d’utilisateur pour Skype Entreprise Server, cliquez sur **Désactiver temporairement pour Lync Server.**

   - Pour activer le compte d’utilisateur Skype Entreprise Server, cliquez **sur Ré-activer pour Lync Server.**

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Utiliser Windows PowerShell pour désactiver ou réactiver des comptes d’utilisateurs

Les comptes d’utilisateurs peuvent être temporairement désactivés, puis  réactivés par la suite, à l’aide de l'; Vous pouvez exécuter cette cmdlet à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation des Windows PowerShell distantes pour vous connecter à Skype Entreprise Server, consultez l’article de blog « Démarrage rapide : Gestion de [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)à l’aide de Remote PowerShell ». Le processus est le même dans Skype Entreprise Server.

### <a name="to-disable-a-user-account"></a>Pour désactiver un compte d’utilisateur

- Pour désactiver temporairement un compte d’utilisateur, définissez la valeur de la propriété Enabled sur False ($False). Par exemple :

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a>Pour ré-activer un compte d’utilisateur

- Pour réactiver un compte d’utilisateur désactivé, définissez la valeur de la propriété Enabled sur True ($True). Par exemple :

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

Pour plus d’informations, consultez la rubrique d’aide de [l';Set-CsUser.](/powershell/module/skype/set-csuser)

## <a name="disable-a-user-for-enterprise-voice"></a>Désactiver un utilisateur pour une Voix Entreprise
<a name="Disable_EV"> </a>

Utilisez la procédure suivante pour désactiver la Voix Entreprise d’un compte d’utilisateur activé pour Skype Entreprise Server.

### <a name="to-disable-a-user-account-for-enterprise-voice"></a>Pour désactiver un compte d’utilisateur pour Voix Entreprise

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.

3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez activer, puis cliquez sur **Rechercher**.

5. Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez activer pour Voix Entreprise.

6. Dans le menu **Edition**, cliquez sur **Afficher les détails**.

7. Dans la page **Modifier l’utilisateur Lync Server**, sous **Téléphonie**, cliquez sur l’option de votre choix à l’exception de **Voix Entreprise**.

    > [!NOTE]
    > Pour empêcher un utilisateur d’effectuer des appels audio ou vidéo à l’aide de Lync, sous **Téléphonie,** cliquez sur **Audio/Vidéo désactivé.**

8. Cliquez sur **Valider**.

L’utilisateur ne peut désormais pas utiliser la fonctionnalité Voix Entreprise de l’utilisateur. Informations connexes : <br/>[Voix Entreprise mobilité](/previous-versions/office/lync-server-2013/lync-server-2013-managing-enterprise-voice-for-users)<br/> [Activer les utilisateurs pour Voix Entreprise dans Skype Entreprise Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Skype Entreprise Server Management Shell](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>Supprimer un compte d’utilisateur avec Skype Entreprise Server Management Shell
<a name="Remove"> </a>

Vous pouvez utiliser la procédure suivante pour supprimer un compte d’utilisateur précédemment ajouté dans Skype Entreprise Server.

> [!NOTE]
> La suppression d’un utilisateur entraînera la perte de tous les paramètres associés au compte d’utilisateur. Si vous souhaitez désactiver temporairement un compte d’utilisateur à la place, voir Désactiver ou [réactiver](user-accounts.md#Disable)un compte d’utilisateur précédemment activé pour Skype Entreprise Server .

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.

3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez désactiver ou réactiver, puis cliquez sur **Rechercher**.

5. Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez supprimer.

6. Dans le menu **Action**, sélectionnez **Supprimer de Lync Server** et une boîte de dialogue apparaît.

7. Dans la boîte de dialogue, sélectionnez **OK** pour supprimer l’utilisateur.

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>Supprimer des comptes d’utilisateurs Windows cmdlets PowerShell

Vous pouvez supprimer des comptes d’utilisateurs à l’aide Disable-CsUser cmdlet. Cette cmdlet peut être exécuté à partir de l’Skype Entreprise Server Management Shell ou d’une session distante Windows PowerShell. Pour plus d’informations sur l’utilisation des Windows PowerShell distantes pour vous connecter à Skype Entreprise Server, consultez l’article de blog « Démarrage rapide : Gestion de [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)à l’aide de Remote PowerShell ». Le processus est le même dans Skype Entreprise Server.

### <a name="to-remove-a-user-account"></a>Pour supprimer un compte d’utilisateur
Pour supprimer un compte d’utilisateur, utilisez l’applet de commande Disable-CsUser. Par exemple :

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

Une fois cette commande exécutée, il n’y a aucun moyen de réactiver le compte et ses anciens paramètres. En revanche, vous pouvez utiliser l’applet de commande Enable-CsUser pour créer un tout nouveau compte pour Ken Myer.

Pour plus d’informations, consultez la rubrique d’aide de l';cmdlet [Disable-CsUser.](/powershell/module/skype/disable-csuser)

## <a name="see-also"></a>Voir aussi
<a name="Remove"> </a>

[Enable-CsUser](/powershell/module/skype/enable-csuser)

[Disable-CsUser](/powershell/module/skype/disable-csusers)
