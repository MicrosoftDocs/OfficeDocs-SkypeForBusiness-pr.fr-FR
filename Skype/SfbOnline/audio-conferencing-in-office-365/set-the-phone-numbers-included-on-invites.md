---
title: Définir la liste des numéros de téléphone inclus sur invite dans Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: 7136a8108a5ecd9e55d2def1e4cedd1076b270ff
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729053"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a>Définir la liste des numéros de téléphone inclus sur invite dans Skype Entreprise Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Pour plus d’informations sur comment faire des conférences avec des numéros de téléphone inclus sur invite dans Microsoft Teams, voir [Définir les numéros de téléphone inclus sur invite dans les Microsoft Teams](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).

L’audioconférence dans Microsoft 365 ou Office 365 permet aux utilisateurs de votre organisation de créer des réunions Skype Entreprise et d’autoriser les utilisateurs à y composer le numéro à l’aide d’un téléphone. Dans Microsoft 365 et Office 365, vous avez la possibilité d’utiliser un pont d’audioconférence Microsoft ou un pont d’audioconférence tiers hébergé par un fournisseur de services d’audioconférence agréé.
  
> [!NOTE]
> Il n’existe pas de ressource qui contient la liste de tous les numéros de connexion pour l’audioconférence. Si vous cherchez à savoir si des numéros de téléphone à composer sont disponibles dans votre région ou pays/région, utilisez le Centre d’administration **Skype Entreprise** Numéros de téléphone Téléphone, cliquez sur Ajouter puis de nouveaux numéros de  >    >   **service.**  Utilisez les listes de **Pays/région**, **Département/région** et **Ville** pour filtrer votre recherche.  En outre, si vous recherchez des numéros d’appel gratuit, sélectionnez **Numéro gratuit** à partir de la liste **Département/région**.
  
Un pont de conférence vous offre un ensemble de numéros de téléphone pour votre organisation. Tous ces ponts peuvent servir à participer à des réunions créées par un organisateur de réunion, mais vous pouvez sélectionner ceux qui doivent être inclus dans les invitations de réunion.
  
> [!NOTE]
> Il peut y avoir au maximum une ligne simple et une ligne de téléphone gratuite dont les numéros apparaissent sur l’invitation à la réunion pour un organisateur de réunion, mais il existe également un lien situé en bas de chaque invitation à une réunion qui ouvre la liste complète de tous les numéros de téléphone qui peuvent être utilisés pour participer à une réunion. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a>Définir le numéro de téléphone par défaut pour un organisateur de réunion

1. Connectez-vous avec votre compte scolaire ou scolaire.
    
2. Sélectionnez **Centres dʼadministration** > **Skype Entreprise**.
    
3. Sélectionnez **Utilisateurs**.
    
    ![Affiche la sélection d’utilisateurs dans le Skype Entreprise d’administration.](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. Sélectionnez les utilisateurs à modifier :
    
   - Pour sélectionner un seul utilisateur, sélectionnez le nom de l’utilisateur.
    
   - Pour sélectionner tous les utilisateurs sur la page, cochez la case à côté de **Afficher le nom** en haut de la liste.
    
   - Pour sélectionner plusieurs utilisateurs, cochez la case en regard de chaque nom d’utilisateur.
    
5. Dans le volet de droite, sélectionnez **Modifier**.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Choisissez **Audioconférence**.
    
7. Dans la page **Propriétés**, dans la liste **Nom du fournisseur**, sélectionnez le fournisseur pour l’utilisateur. Selon le fournisseur, complétez les champs suivants.
    
   - **Microsoft est le fournisseur**: utilisez les listes de **numéro de téléphone payant par défaut** et de **numéro d’appel gratuit par défaut** pour sélectionner les numéros par défaut pour l’utilisateur.
    
     > [!NOTE]
     > Au moins un numéro d’appel gratuit doit être affecté à votre pont de conférence avant qu’il ne puisse être défini comme étant le numéro d’appel gratuit par défaut d’un utilisateur. Pour obtenir un numéro gratuit, consultez Obtenir des numéros de [téléphone de service pour Skype Entreprise.](/microsoftteams/getting-service-phone-numbers) 
  
   - **Le fournisseur est un tiers** : utiliser les champs de **Numéro de téléphone payant** et de **Numéro d’appel gratuit** pour indiquer les numéros pour l’utilisateur.


## <a name="reset-audio-conferencing-phone-numbers"></a>Réinitialiser les numéros de téléphone des services d’audioconférence

1. Dans le **Skype Entreprise d’administration,** sélectionnez **Audioconférence.**
    
2. En haut de la page, choisissez **Utilisateurs**.
    
3. Sélectionnez les utilisateurs que vous souhaitez réinitialiser, puis dans le volet Actions, cliquez sur **Effacer**.
    
Par défaut, lorsque vous modifiez les paramètres de conférence d’un utilisateur, un message électronique est envoyé à l’utilisateur. Pour modifier ce paramètre, voir Activer ou désactiver l’envoi de courriers électroniques en cas de [modification des paramètres d’audioconférence.](enable-or-disable-sending-emails-when-their-settings-change.md)
  
> [!IMPORTANT]
> Lorsque vous modifiez les paramètres d’audioconférence d’un utilisateur, les réunions Skype Entreprise périodiques et futures doivent être mises à jour et envoyées aux participants. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser).
    
- Utilisez l'applet de commande [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) pour modifier le numéro payant ou gratuit par défaut pour des utilisateurs spécifiques.
    
    Pour modifier le numéro gratuit par défaut pour un utilisateur, exécutez ce qui suit :
    
  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- Utilisez l'applet de commande **Set-CsOnlineDialInConferencingUserDefaultNumber** pour modifier le numéro gratuit ou payant par défaut des utilisateurs en fonction de leur numéro par défaut d'origine ou de leur emplacement.
    
    > [!NOTE]
    > Pour trouver le BridgeID, utilisez l’cmdlet **Get-CsOnlineDialInConferencingBridge.**
  
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - Pour définir sur +18005551234 le numéro gratuit par défaut pour tous les utilisateurs qui n’en ont pas, exécutez :
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - Pour modifier le numéro gratuit par défaut de tous les utilisateurs qui ont le numéro gratuit +18005551234 sur +18005551239, exécutez :
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Pour définir le numéro gratuit par défaut de tous les utilisateurs situés aux États-Unis sur +18005551234, exécutez :
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
  ## <a name="want-to-learn-more-about-windows-powershell"></a>Vous voulez en savoir plus sur Windows PowerShell ?
- Windows PowerShell permet de gérer les utilisateurs et ce qu’ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l’aide d’un point d’administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Raisons pour lesquelles vous devez Microsoft 365 ou Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation de la Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion des Microsoft 365 des Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Sujets associés

[Essayez ou achetez l’audioconférence dans Microsoft 365 ou Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
