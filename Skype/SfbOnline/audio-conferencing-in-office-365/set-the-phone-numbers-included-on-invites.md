---
title: "Définir l’invite les inclure sur des numéros de téléphone"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: 8baf3d79b360a5d95da4b9ead6bae12cd488712c
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2018
---
# <a name="set-the-phone-numbers-included-on-invites"></a>Définir l’invite les inclure sur des numéros de téléphone

Conférence audio dans Office 365 permet aux utilisateurs de votre organisation de créer Skype pour les réunions d’entreprise et Teams de Microsoft, puis autorisez les utilisateurs à se connecter à ces réunions à l’aide d’un téléphone. Dans Office 365, vous avez la possibilité d’utiliser un pont de conférence audio de Microsoft ou d’un pont de conférence audio de tiers qui est hébergé par un fournisseur agréé de conférence audio (ACP).
  
> [!NOTE]
> Il n'existe pas de ressource qui rassemble tous les numéros de connexion pour l'audioconférence. Si vous souhaitez pour voir s’il existe les numéros de téléphone disponibles dans votre région ou votre pays/région, utiliser le **Skype pour le centre d’administration Business** > **vocale** > de**Numéros de téléphone**, cliquez sur **Ajouter** puis **de nouveaux numéros de Service **. Utilisez les listes de **Pays/région**, état/région de **** et **Ville** pour filtrer votre recherche. > en outre, si vous recherchez – numéros d’appel gratuit, sélectionnez **numéro gratuit** à partir de l’état/région **** liste.
  
Un pont de conférence vous offre un ensemble de numéros de téléphone d’accès à distance pour votre organisation. Tous les peuvent servir à assister aux réunions créé un organisateur de réunion, mais vous pouvez sélectionner ceux qui est incluses dans les invitations de réunion.
  
> [!NOTE]
> Il peut y avoir un maximum d’un numéro et un numéro d’appel gratuit sur l’invitation pour l’organisateur d’une réunion, mais il existe également un lien situé au bas de chaque invitation à une réunion qui ouvre la liste complète de tous les numéros de téléphone qui peut être utilisé pour joindre une réunion. 
  
## <a name="setting-the-default-dial-in-phone-number-for-a-meeting-organizer"></a>Définir le numéro de téléphone par défaut pour l’organisateur d’une réunion

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centres dʼadministration** > **Skype Entreprise**.
    
3. Sélectionnez **Utilisateurs**.
    
    ![Affiche la sélection des utilisateurs dans le Skype pour le centre d’administration de Business](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. Sélectionnez les utilisateurs que vous souhaitez modifier :
    
  - Pour sélectionner un seul utilisateur, sélectionnez le nom de l’utilisateur.
    
  - Pour sélectionner tous les utilisateurs sur la page, sélectionnez la case en regard du **nom d’affichage** en haut de la liste.
    
  - Pour sélectionner plusieurs utilisateurs, sélectionnez la case en regard de chaque nom de l’utilisateur.
    
5. Dans le volet de droite, sélectionnez **Modifier**.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Choisissez **l’audioconférence**.
    
7. Sur la page de **Propriétés** , dans la liste **nom du fournisseur** , sélectionnez le fournisseur pour l’utilisateur. Selon le fournisseur, complétez les zones suivantes.
    
  - **Microsoft est le fournisseur**: utilisez le **numéro d’appel payant par défaut** et le **numéro d’appel gratuit par défaut** répertorie pour sélectionner les numéros par défaut pour l’utilisateur.
    
    > [!NOTE]
    > Au moins un numéro d’appel gratuit doit être affecté à votre pont de conférence avant elle peut être définie comme le numéro d’appel gratuit par défaut d’un utilisateur. Pour obtenir un numéro d’appel gratuit, voir [numéros de téléphone de service de mise en route pour Skype pour les entreprises et les équipes de Microsoft](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md). 
  
  - **Une tierce partie est le fournisseur**: les champs **– numéro d’appel** et le **numéro d’appel gratuit** permet d’entrer les numéros de l’utilisateur.
    
## <a name="reset-audio-conferencing-phone-numbers"></a>Réinitialiser les numéros de téléphone de conférence audio

1. Dans le **Skype pour le centre d’administration Business**, choisissez **audioconférence**.
    
2. En haut de la page, cliquez sur **utilisateurs**.
    
3. Sélectionnez les utilisateurs que vous souhaitez réinitialiser, puis, dans le volet Actions, cliquez sur **Effacer**.
    
Par défaut, lorsque vous modifiez des paramètres de conférence d’un utilisateur, un e-mail est envoyé à l’utilisateur. Pour modifier ce comportement, voir [Activer ou désactiver l’envoi de messages électroniques lors de la modifient des paramètres d’audioconférence](enable-or-disable-sending-emails-when-their-settings-change.md).
  
> [!IMPORTANT]
> Lorsque vous modifiez des paramètres de conférence audio d’un utilisateur, périodique et futur Skype pour les réunions d’entreprise et Teams de Microsoft doit être mis à jour et envoyée aux participants. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688).
    
- Utilisez l'applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) pour modifier le numéro payant ou gratuit par défaut pour des utilisateurs spécifiques.
    
    Pour modifier le numéro gratuit par défaut pour un utilisateur, exécutez ce qui suit :
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- Utilisez l'applet de commande **Set-CsOnlineDialInConferencingUserDefaultNumber** pour modifier le numéro gratuit ou payant par défaut des utilisateurs en fonction de leur numéro par défaut d'origine ou de leur emplacement.
    
    > [!NOTE]
    > Pour rechercher la BridgeID, utilisez le **Get-CsOnlineDialInConferencingBridge**.
  
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - Pour définir le numéro d’appel gratuit par défaut pour tous les utilisateurs sans une à +18005551234, exécutez la commande :
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - Pour modifier le numéro d’appel gratuit par défaut de tous les utilisateurs qui ont +18005551234 comme leur numéro d’appel gratuit par défaut à +18005551239, exécutez la commande :
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Pour définir le numéro gratuit de la valeur par défaut de tous les utilisateurs situés aux Etats-Unis à +18005551234, exécutez la commande :
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
## <a name="want-to-learn-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?
- Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Rubriques connexes

[Configurer la conférence Audio pour Skype entreprise et Teams Microsoft](set-up-audio-conferencing.md)
  

