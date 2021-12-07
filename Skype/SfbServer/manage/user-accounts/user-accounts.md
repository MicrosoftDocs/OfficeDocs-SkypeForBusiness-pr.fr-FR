---
title: Gérer les comptes d’utilisateur pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: Les sections de cet article décrivent comment activer, désactiver temporairement ou supprimer des utilisateurs Active Directory d’Skype Entreprise Server.
ms.openlocfilehash: 39016a83c11553cd39448efa34d61ffbba5045e9
ms.sourcegitcommit: 2aae13454178dc2e2cbc8cca967cd181c5f9d044
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/06/2021
ms.locfileid: "61314212"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>Gérer les comptes d’utilisateur pour Skype Entreprise Server

Les sections de cet article décrivent comment activer, désactiver temporairement ou supprimer des utilisateurs Active Directory d’Skype Entreprise Server.

Pour plus d’informations sur la façon d’activer un utilisateur Active Directory, voir [Créer un compte d’utilisateur.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732336(v=ws.11)) Pour plus d’informations sur la suppression d’un utilisateur Active Directory, voir [Supprimer un compte d’utilisateur.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))

Ces procédures doivent être effectuées au cours d’une fenêtre de maintenance, lorsque Skype Entreprise’utilisation est la plus faible. Les besoins de votre organisation déterminent si cette planification est quotidienne ou hebdomadaire.

Cet article contient les procédures suivantes :

- [Rechercher un ou plusieurs utilisateurs](#search-for-one-or-more-users)

- [Ajouter et activer un nouvel Skype Entreprise Server utilisateur](#add-and-enable-a-new-skype-for-business-server-user)

- [Désactiver ou réactiver un compte d’utilisateur pour Skype Entreprise Server](#disable-or-re-enable-a-user-account-for-skype-for-business-server)

- [Désactiver un utilisateur pour une Voix Entreprise](#disable-a-user-for-enterprise-voice)

- [Supprimer un compte d’utilisateur avec Skype Entreprise Server Management Shell](#remove-a-user-account-with-the-skype-for-business-server-management-shell)

## <a name="search-for-one-or-more-users"></a>Rechercher un ou plusieurs utilisateurs

Vous pouvez utiliser les résultats d’une requête de recherche pour configurer les utilisateurs Active Directory pour Skype Entreprise Server. Vous pouvez rechercher des utilisateurs par nom d’affichage, prénom, nom de famille, nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), adresse SIP ou URI (Uniform Resource Identifier) de ligne.

Vous pouvez rechercher des utilisateurs à l’aide Skype Entreprise Server Panneau de Skype Entreprise Server ou du logiciel en ligne Utilisateurs et ordinateurs Active Directory. La procédure suivante décrit comment utiliser le Panneau de Skype Entreprise Server pour rechercher des utilisateurs.

> [!NOTE]
> Dans un environnement avec une topologie de forêt centrale, les résultats de la recherche peuvent ne pas être précis lorsque vous recherchez un utilisateur par son adresse de messagerie. Au lieu de cela, vous pouvez rechercher des utilisateurs en spécifiant un préfixe d’adresse SIP, par exemple sip:name, ajouter un filtre de recherche et sélectionner une adresse SIP qui contient une adresse de messagerie partielle, ou utiliser l'; 

### <a name="search-for-users-using-the-new-control-panel"></a>Rechercher des utilisateurs à l’aide du nouveau Panneau de contrôle 

1. Ouvrez une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.
 
2. Connectez-vous à l’aide d’un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator.

3. Dans le volet gauche, sélectionnez **Utilisateurs.**

4. Dans la page **Utilisateurs,** dans la zone De recherche, tapez tout ou la première partie du nom complet que vous souhaitez rechercher et appuyez sur **Entrée**. 

5. (Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :

    1. Cliquez sur le bouton de filtre en haut de la **zone** de recherche.

    2. Dans le **panneau Filtre** qui s’affiche, sélectionnez la propriété utilisateur requise en cliquant sur la flèche dans la liste liste.

    3. Cliquez sur la flèche dans la liste d’opérateurs de liste liste, pour sélectionner l’opérateur requis.

    4. Dans la zone de texte, tapez les critères de recherche que vous souhaitez utiliser pour filtrer les résultats de la recherche, puis cliquez sur **OK.**

6. Les résultats de la recherche apparaissent sur la page **Utilisateurs.** Sélectionnez dans la liste les utilisateurs sur lesquels vous voulez exécuter les tâches de configuration.

> [!NOTE]
> Le nouveau Panneau de Skype Entreprise Server 2015 n’est pas disponible.

### <a name="search-for-users-using-the-legacy-control-panel"></a>Rechercher des utilisateurs à l’aide du Panneau de contrôle hérité 

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.

3. Dans le volet gauche, sélectionnez **Utilisateurs.**

4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur que vous souhaitez activer, puis cliquez sur **Rechercher**.

5. (Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :

    1. Cliquez sur la flèche déroulante située en haut à droite de l’écran, au-dessus **Résultats de la recherche**, puis sur **Ajouter un filtre**.

    2. Entrez la propriété utilisateur en la tapant ou en cliquant sur la flèche dans la liste de listes pour sélectionner une propriété utilisateur.

    3. Dans la **liste Égal à,** **sélectionnez Égal à** ou Non égal **à**.

    4. Dans la zone de texte, tapez le critère de recherche selon lequel filtrer les résultats, puis cliquez sur **Rechercher**.

6. les résultats de la recherche apparaissent sous **Résultats de la recherche**. Sélectionnez dans la liste les utilisateurs sur lesquels vous voulez exécuter les tâches de configuration.

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>Ajouter et activer un nouvel Skype Entreprise Server utilisateur

Après avoir activé un compte d’utilisateur dans Utilisateurs et ordinateurs Active Directory, vous pouvez utiliser le Panneau de Skype Entreprise Server pour créer et activer de nouveaux comptes d’utilisateurs Skype Entreprise Server en ajoutant un utilisateur Active Directory à Skype Entreprise Server.

Vous pouvez également utiliser une cmdlet, en particulier [Enable-CsUser](/powershell/module/skype/enable-csuser).

### <a name="add-a-user-using-the-new-control-panel"></a>Ajouter un utilisateur à l’aide du nouveau Panneau de contrôle 

1. Ouvrez une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.
 
2. Connectez-vous à l’aide d’un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator.

3. Accédez à  >  **Utilisateurs Activer les** utilisateurs, puis cliquez sur **Ajouter.**

4. Dans la **zone de** recherche, tapez la première ou la première partie du nom complet, puis cliquez sur **Rechercher.**

5. (Facultatif) Pour spécifier des critères utilisateur supplémentaires, cliquez **sur + Ajouter** un filtre, sélectionnez la propriété utilisateur requise, sélectionnez l’opérateur, puis entrez la valeur. Cliquez sur **Rechercher**.

6. Dans le tableau, sélectionnez le compte que vous souhaitez ajouter à Skype Entreprise Server, puis cliquez sur **OK**.

7. Affectez l’utilisateur à un pool, spécifiez des détails supplémentaires, attribuez les stratégies requises à l’utilisateur, puis cliquez sur **Activer**.

> [!NOTE]
> Le nouveau Panneau de Skype Entreprise Server 2015 n’est pas disponible.

### <a name="add-a-user-using-the-legacy-control-panel"></a>Ajouter un utilisateur à l’aide du Panneau de contrôle hérité 

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.

3. Accédez à **Utilisateurs** Activer les utilisateurs Nouvel  >    >  **utilisateur Lync Server,** puis cliquez sur **Ajouter.**

6. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom, du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse e-mail, du nom d’utilisateur principal ou le numéro de téléphone du compte d’utilisateur Active Directory souhaité, puis cliquez sur **Rechercher**.

7. Dans le tableau, sélectionnez le compte que vous souhaitez ajouter à Skype Entreprise Server, puis cliquez sur **OK**.

8. Affectez l’utilisateur à un pool, indiquez d’autres détails utiles et affectez les stratégies à l’utilisateur voulu, puis cliquez sur **Activer**.

## <a name="disable-or-re-enable-a-user-account-for-skype-for-business-server"></a>Désactiver ou réactiver un compte d’utilisateur pour Skype Entreprise Server

Vous pouvez utiliser la procédure suivante pour désactiver un compte d’utilisateur précédemment activé dans Skype Entreprise Server sans perdre les paramètres de Skype Entreprise Server que vous avez configurés pour le compte d’utilisateur. Étant donné que vous ne perdez pas les paramètres de compte d’utilisateur Skype Entreprise Server, vous pouvez ré-activer un compte d’utilisateur précédemment activé sans avoir à reconfigurer le compte d’utilisateur.

### <a name="disable-or-re-enable-a-user-account-using-the-new-control-panel"></a>Désactiver ou réactiver un compte d’utilisateur à l’aide du nouveau Panneau de contrôle

1. Ouvrez une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.
 
2. Connectez-vous à l’aide d’un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator.

3. Dans le volet gauche, sélectionnez **Utilisateurs.**

4. Dans la page **Utilisateurs,** dans la zone **De** recherche, tapez tout ou la première partie du nom d’affichage et appuyez sur **Entrée**.

5. Dans le tableau, double-cliquez sur le compte d’utilisateur que vous souhaitez désactiver ou réactiver.
    1. Dans le panneau qui s’affiche, pour désactiver temporairement le compte d’utilisateur Skype Entreprise Server, **sélectionnez Désactiver l’utilisateur.** Dans le panneau qui s’affiche, cliquez sur **Enregistrer.**
    2. Pour ré-activer le compte d’utilisateur Skype Entreprise Server, dans le panneau, **sélectionnez Ré-activer l’utilisateur.** Dans le panneau suivant qui s’affiche, cliquez sur **Enregistrer.**

> [!NOTE]
> Le nouveau Panneau de Skype Entreprise Server 2015 n’est pas disponible.

### <a name="disable-or-re-enable-a-user-account-using-the-legacy-control-panel"></a>Désactiver ou réactiver un compte d’utilisateur à l’aide du Panneau de contrôle hérité

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.

3. Dans le volet gauche, sélectionnez **Utilisateurs.**

4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez désactiver ou réactiver, puis cliquez sur **Rechercher**.

5. Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez désactiver ou réactiver.

6. Dans le menu **Action**, effectuez l’une des opérations suivantes :
   1. Pour désactiver temporairement le compte d’utilisateur Skype Entreprise Server, sélectionnez **Temporairement désactiver pour Lync Server.**
   2. Pour activer le compte d’utilisateur Skype Entreprise Server, sélectionnez **Ré-activer pour Lync Server.**
  
### <a name="disable-or-re-enable-user-accounts-using-windows-powershell"></a>Désactiver ou réactiver des comptes d’utilisateur à l’aide Windows PowerShell

Les comptes d’utilisateurs peuvent être temporairement désactivés, puis  réactivés par la suite, à l’aide de l'; Vous pouvez exécuter cette cmdlet à partir de l’Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype Entreprise Server, voir [Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). Le processus est le même dans Skype Entreprise Server.

### <a name="to-disable-a-user-account-using-windows-powershell"></a>Pour désactiver un compte d’utilisateur à l’aide Windows PowerShell

- Pour désactiver temporairement un compte d’utilisateur, définissez la valeur de la propriété activée sur False ($False). Par exemple :

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account-using-windows-powershell"></a>Pour ré-activer un compte d’utilisateur à l’aide Windows PowerShell

- Pour réactiver un compte d’utilisateur désactivé, définissez la valeur de la propriété activée sur True ($True). Par exemple :

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

Pour plus d’informations, consultez la rubrique d’aide de [l';Set-CsUser.](/powershell/module/skype/set-csuser)

## <a name="disable-a-user-for-enterprise-voice"></a>Désactiver un utilisateur pour une Voix Entreprise

Utilisez la procédure suivante pour désactiver la Voix Entreprise d’un compte d’utilisateur activé pour Skype Entreprise Server.

### <a name="disable-a-user-for-enterprise-voice-using-new-control-panel"></a>Désactiver un utilisateur pour une utilisation Voix Entreprise’aide du nouveau Panneau de contrôle

1. Ouvrez une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.
 
2. Connectez-vous à l’aide d’un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator.

3. Dans le volet gauche, cliquez sur **Utilisateurs.**

4. Dans la **zone de** recherche, tapez la première ou la première partie du nom complet, puis cliquez sur **Rechercher.**

5. Dans le tableau, double-cliquez sur le compte d’utilisateur que vous souhaitez désactiver pour Voix Entreprise.

6. Dans le panneau qui s’affiche, cliquez sur l’icône de crayon en face des **stratégies affectées.**

7. Dans le **panneau Stratégies** affectées, sous **Téléphonie,** cliquez sur n’importe quelle option, Voix Entreprise **dans** la liste liste.

8. Cliquez sur **Enregistrer**.

    > [!NOTE]
    > Pour empêcher un utilisateur d’effectuer des appels audio ou vidéo, sous **Téléphonie,** cliquez sur **Audio/Vidéo désactivé.**

L’utilisateur ne peut désormais pas utiliser la fonctionnalité Voix Entreprise’utilisateur. 

> [!NOTE]
> Le nouveau Panneau de Skype Entreprise Server 2015 n’est pas disponible.

### <a name="disable-a-user-account-for-enterprise-voice-using-legacy-control-panel"></a>Désactiver un compte d’utilisateur pour les Voix Entreprise l’aide du Panneau de contrôle hérité

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.

3. Dans le volet gauche, cliquez sur **Utilisateurs.**

4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez activer, puis cliquez sur **Rechercher**.

5. Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez activer pour Voix Entreprise.

6. Dans le menu **Edition**, cliquez sur **Afficher les détails**.

7. Dans la page **Modifier l’utilisateur Lync Server**, sous **Téléphonie**, cliquez sur l’option de votre choix à l’exception de **Voix Entreprise**.

    > [!NOTE]
    > Pour empêcher un utilisateur d’effectuer des appels audio ou vidéo à l’aide de Lync, sous **Téléphonie,** cliquez sur **Audio/Vidéo désactivé.**

8. Cliquez sur **Valider**.

L’utilisateur ne peut désormais pas utiliser la fonctionnalité Voix Entreprise’utilisateur.

Informations connexes : <br/>[Voix Entreprise mobilité](/previous-versions/office/lync-server-2013/lync-server-2013-managing-enterprise-voice-for-users)<br/> [Activer les utilisateurs pour Voix Entreprise dans Skype Entreprise Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Skype Entreprise Server Management Shell](../management-shell.md)

## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>Supprimer un compte d’utilisateur avec Skype Entreprise Server Management Shell

Vous pouvez utiliser la procédure suivante pour supprimer un compte d’utilisateur précédemment ajouté dans Skype Entreprise Server.

> [!NOTE]
> La suppression d’un utilisateur entraînera la perte de tous les paramètres associés au compte d’utilisateur. Si vous souhaitez désactiver temporairement un compte d’utilisateur à la place, voir Désactiver ou [réactiver](#disable-or-re-enable-a-user-account-for-skype-for-business-server)un compte d’utilisateur précédemment activé pour Skype Entreprise Server .

### <a name="remove-a-user-using-the-new-control-panel"></a>Supprimer un utilisateur à l’aide du nouveau Panneau de contrôle

1. Ouvrez une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.
 
2. Connectez-vous à l’aide d’un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator.

3. Dans le volet gauche, sélectionnez **Utilisateurs.**

4. Dans la **zone de** recherche, tapez la première ou la première partie du nom complet, puis cliquez sur **Rechercher.**

5. Dans le tableau, double-cliquez sur le compte d’utilisateur à supprimer.

6. Dans le panneau qui s’affiche, cliquez **sur Supprimer l’utilisateur.** Dans le panneau suivant qui s’affiche, cliquez sur **OK.**

> [!NOTE]
> Le nouveau Panneau de Skype Entreprise Server 2015 n’est pas disponible.

### <a name="remove-a-user-using-the-legacy-control-panel"></a>Supprimer un utilisateur à l’aide du Panneau de contrôle hérité

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.

3. Dans le volet gauche, sélectionnez **Utilisateurs.**

4. Dans  la zone Rechercher des utilisateurs, tapez tout ou la première partie du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur à supprimer, puis cliquez sur **Rechercher.**

5. Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez supprimer.

6. Dans le menu **Action**, sélectionnez **Supprimer de Lync Server** et une boîte de dialogue apparaît.

7. Dans la boîte de dialogue, sélectionnez **OK** pour supprimer l’utilisateur.

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>Supprimer des comptes d’utilisateurs avec Windows PowerShell cmdlets

Vous pouvez supprimer des comptes d’utilisateurs à l’aide Disable-CsUser cmdlet. Cette cmdlet peut être exécuté à partir de l’Skype Entreprise Server Management Shell ou d’une session distante Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype Entreprise Server, voir [Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). Le processus est le même dans Skype Entreprise Server.

Pour supprimer un compte d’utilisateur, utilisez l’applet de commande Disable-CsUser. Par exemple :

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

Une fois cette commande exécutée, il n’y a aucun moyen de réactiver le compte et ses anciens paramètres. En revanche, vous pouvez utiliser l’applet de commande Enable-CsUser pour créer un tout nouveau compte pour Ken Myer.

Pour plus d’informations, consultez la rubrique d’aide de l';cmdlet [Disable-CsUser.](/powershell/module/skype/disable-csuser)

## <a name="see-also"></a>Voir aussi

[Enable-CsUser](/powershell/module/skype/enable-csuser)

[Disable-CsUser](/powershell/module/skype/disable-csuser)
