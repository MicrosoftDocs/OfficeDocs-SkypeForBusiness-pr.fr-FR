---
title: Gérer les comptes d’utilisateurs de Skype pour Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: Les sections de cet article décrivent comment activer, désactiver temporairement ou supprimer des utilisateurs d’Active Directory de Skype pour Business Server 2015.
ms.openlocfilehash: bd09687a6a2d2f3d1e8dcfe13b7f8aa64648e56b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-user-accounts-for-skype-for-business-server-2015"></a>Gérer les comptes d’utilisateurs de Skype pour Business Server 2015
 
Les sections de cet article décrivent comment activer, désactiver temporairement ou supprimer des utilisateurs d’Active Directory de Skype pour Business Server 2015.
  
Pour plus d’informations sur l’activation d’un utilisateur Active Directory, voir [créer un nouveau compte d’utilisateur](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx). Pour plus d’informations sur la façon de supprimer un utilisateur d’Active Directory, voir [suppression d’un compte d’utilisateur](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).
  
Ces procédures doivent être effectuées au cours d’une période de maintenance, lorsque Skype pour l’utilisation d’entreprise est le plus bas. Si cela est effectué sur une planification quotidienne ou hebdomadaire sera déterminé par les besoins de votre organisation. 
  
Cet article contient les procédures suivantes :
  
- [Pour rechercher un ou plusieurs utilisateurs](user-accounts.md#Search)
    
- [Ajouter et activer un nouveau Skype pour l’utilisateur de Business Server 2015](user-accounts.md#Add)
    
- [Désactiver ou réactiver un compte d’utilisateur précédemment activé pour Skype pour Business Server](user-accounts.md#Disable)
    
- [Désactiver un utilisateur de Voix Entreprise](user-accounts.md#Disable_EV)
    
- [Supprimer un compte d’utilisateur avec le Skype pour Business Server Management Shell](user-accounts.md#Remove)
    
## <a name="to-search-for-one-or-more-users"></a>Pour rechercher un ou plusieurs utilisateurs
<a name="Search"> </a>

Les résultats d’une requête de recherche vous permet de configurer des utilisateurs Active Directory pour Skype pour Business Server 2015. Vous pouvez rechercher des utilisateurs par nom d’affichage, prénom, nom de famille, nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), adresse SIP ou URI (Uniform Resource Identifier) de ligne.
  
Vous pouvez rechercher des utilisateurs à l’aide de la Skype pour Business Server du Panneau de configuration ou les utilisateurs Active Directory et le composant logiciel enfichable ordinateurs. La procédure suivante décrit comment utiliser Skype pour le panneau de configuration de Business Server pour rechercher des utilisateurs.
  
> [!NOTE]
> Dans un environnement avec une topologie à forêt centrale, résultats de la recherche soient pas précis lorsque vous recherchez un utilisateur par adresse de messagerie de l’utilisateur. Au lieu de cela, vous pouvez rechercher des utilisateurs en spécifiant un préfixe d’adresse SIP, par exemple sip : nom, ajouter un filtre de recherche et sélectionnez une adresse SIP qui contient une adresse partielle ou utiliser l’applet de commande **Get-CSUser** .
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans la boîte de **recherche utilisateurs** , tapez tout ou la première partie de l’affichage nom, le prénom, le nom, le nom de compte SAM, SIP d’adresse ou ligne URI du compte d’utilisateur que vous souhaitez rechercher, puis cliquez sur **Rechercher**.
    
5. (Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :
    
   a. Cliquez sur le bouton flèche dans le coin supérieur droit de l’écran située au-dessus des **résultats de recherche**, puis cliquez sur **Ajouter un filtre**.
    
   b. Entrez la propriété de l’utilisateur en tapant ou en cliquant sur la flèche dans la liste déroulante pour sélectionner une propriété de l’utilisateur.
    
   c. Dans la liste **égal à** , cliquez sur **égal** ou **non égal à**.
    
   d. Dans la zone de texte, tapez les critères de recherche que vous souhaitez utiliser pour filtrer les résultats de la recherche, puis cliquez sur **Rechercher**.
    
6. Les résultats de la recherche s’affichent sous **Résultats de la recherche**. Vous pouvez sélectionner tout ou partie des utilisateurs dans la liste et effectuer des tâches de configuration sur les utilisateurs que vous sélectionnez.
    
## <a name="add-and-enable-a-new-skype-for-business-server-2015-user"></a>Ajouter et activer un nouveau Skype pour l’utilisateur de Business Server 2015
<a name="Add"> </a>

Après l’activation d’un compte d’utilisateur dans Active Directory utilisateurs et ordinateurs, vous pouvez utiliser Skype pour le panneau de configuration de Business Server pour créer et activer le nouveau Skype pour les comptes d’utilisateur Business Server 2015 en ajoutant un utilisateur Active Directory à Skype pour Business Server 2015.
  
Vous pouvez également utiliser une applet de commande, spécifiquement [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Cliquez sur **Activer les utilisateurs**.
    
5. Dans la boîte de dialogue **Nouvel utilisateur de serveur Lync** , cliquez sur **Ajouter**.
    
6. Dans la boîte de **recherche utilisateurs** , tapez tout ou la première partie du nom, afficher le nom, prénom, nom, nom de compte Gestionnaire de comptes de sécurité (SAM), adresse de messagerie, nom d’utilisateur Principal (UPN) ou numéro de téléphone du compte d’utilisateur Active Directory que vous souhaitez , puis cliquez sur **Rechercher**.
    
7. Dans le tableau, sélectionnez le compte que vous souhaitez ajouter à Skype pour Business Server 2015, puis cliquez sur **OK**.
    
8. Assigner l’utilisateur à un pool, spécifier des détails supplémentaires et affecter à l’utilisateur que vous souhaitez que les stratégies et puis cliquez sur **Activer**.
    
## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a>Désactiver ou réactiver un compte d’utilisateur précédemment activé pour Skype pour Business Server
<a name="Disable"> </a>

Vous pouvez utiliser la procédure suivante pour désactiver un compte d’utilisateur précédemment activé dans Skype pour Business Server sans perdre la Skype pour les paramètres de serveur de l’entreprise que vous avez configurée pour le compte d’utilisateur. Étant donné que vous ne perdez pas le Skype pour les paramètres de compte d’utilisateur Business Server, vous pouvez réactiver un compte d’utilisateur précédemment activé à nouveau sans avoir à reconfigurer le compte d’utilisateur. 
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans la boîte de **recherche utilisateurs** , tapez tout ou la première partie du nom complet, prénom, nom, nom de compte Gestionnaire de comptes de sécurité (SAM), adresse SIP ou ligne identificateur URI (Uniform Resource) du compte d’utilisateur que vous souhaitez désactiver ou réactiver, puis cliquez sur **Rechercher**.
    
5. Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez désactiver ou réactiver.
    
6. Dans le menu **Action** , effectuez l’une des opérations suivantes :
    
   - Pour désactiver temporairement le compte d’utilisateur pour Skype pour Business Server, cliquez sur **désactiver temporairement pour Lync Server**.
    
   - Pour activer le compte d’utilisateur Skype pour Business Server, cliquez sur **réactiver pour Lync Server**.
    
### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Utiliser Windows Powershell pour désactiver ou réactiver les comptes d’utilisateurs

Comptes d’utilisateurs peuvent être temporairement désactivés et puis ensuite réactivés, à l’aide de l’applet de commande **Set-CsUser** . Vous pouvez exécuter cette applet de commande depuis le Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter sur Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876). Le processus est le même dans Skype pour Business Server.
  
### <a name="to-disable-a-user-account"></a>Pour désactiver un compte d’utilisateur

- Pour désactiver temporairement un compte d’utilisateur, la valeur de la propriété Enabled la valeur False ($False). Par exemple :
    
  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a>Pour réactiver un compte d’utilisateur

- Pour réactiver un compte d’utilisateur désactivé, la valeur de la propriété Enabled la valeur True ($True). Par exemple :
    
  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) .
  
## <a name="disable-a-user-for-enterprise-voice"></a>Désactiver un utilisateur de Voix Entreprise
<a name="Disable_EV"> </a>

La procédure suivante permet de désactiver la Voix Entreprise pour un compte d’utilisateur est activé pour Skype pour Business Server 2015.
  
### <a name="to-disable-a-user-account-for-enterprise-voice"></a>Pour désactiver un compte d’utilisateur de Voix Entreprise

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager), de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur à activer, puis cliquez sur **Rechercher**.
    
5. Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez activer pour les Voix Entreprise.
    
6. Dans le menu **Edition**, cliquez sur **Afficher les détails**.
    
7. Dans la page **Modifier l’utilisateur Lync Server** , **téléphonie**, cliquez sur une option autre que la **Voix Entreprise**.
    
    > [!NOTE]
    > Pour empêcher un utilisateur d’effectuer des appels audio ou vidéo à l’aide de Lync, sous **téléphonie**, cliquez sur **Audio/vidéo désactivée**. 
  
8. Cliquez sur **Valider**.
    
L’utilisateur est désormais impossible d’utiliser la fonctionnalité Voix Entreprise. Obtenir des informations connexes : <br/>[Voix Entreprise et la mobilité](http://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [Permettre aux utilisateurs de Voix Entreprise dans Skype pour Business Server 2015](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Skype pour Business Server 2015 Management Shell](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>Supprimer un compte d’utilisateur avec le Skype pour Business Server Management Shell
<a name="Remove"> </a>

Vous pouvez utiliser la procédure suivante pour supprimer un compte d’utilisateur précédemment ajouté dans Skype pour Business Server 2015. 
  
> [!NOTE]
> Suppression d’un utilisateur provoque la perte des paramètres que vous avez configurée pour le compte d’utilisateur. Si vous voulez temporairement désactiver un compte d’utilisateur à la place, consultez [désactiver ou réactiver un compte d’utilisateur précédemment activé pour Skype pour Business Server](user-accounts.md#Disable). 
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans la boîte de **recherche utilisateurs** , tapez tout ou la première partie du nom complet, prénom, nom, nom de compte Gestionnaire de comptes de sécurité (SAM), adresse SIP ou ligne identificateur URI (Uniform Resource) du compte d’utilisateur que vous souhaitez désactiver ou réactiver, puis cliquez sur **Rechercher**.
    
5. Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez supprimer.
    
6. Dans le menu **Action** , sélectionnez **Supprimer de Lync Server**et une boîte de dialogue zone s’affiche.
    
7. À partir de la boîte de dialogue, cliquez sur **OK** pour supprimer l’utilisateur.
    
### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>Supprimer des comptes d’utilisateurs avec les applets de commande Windows Powershell

Vous pouvez supprimer des comptes d’utilisateurs à l’aide de l’applet de commande Disable-CsUser. Cette applet de commande peut être exécuté à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter sur Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876). Le processus est le même dans Skype pour Business Server.
  
### <a name="to-remove-a-user-account"></a>Pour supprimer un compte d’utilisateur
Pour supprimer un compte d’utilisateur, utilisez l’applet de commande Disable-CsUser. Par exemple :
    
  ```
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.
    
Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) .
  
## <a name="see-also"></a>Voir aussi
<a name="Remove"> </a>

#### 

[Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)
  
[Désactiver-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)

