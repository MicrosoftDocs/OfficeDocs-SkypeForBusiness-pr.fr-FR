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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: cb808cb8271cfb32174106e2692793aa41a64d50
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882112"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a>Définir la liste des numéros de téléphone inclus sur invite dans Skype Entreprise Online

> [!Note]
> Pour plus d’informations sur comment faire des conférences avec des numéros de téléphone inclus sur invite dans Microsoft Teams, voir [Définir les numéros de téléphone inclus sur invite dans les Microsoft Teams](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).

Le service d’audioconférence dans Office 365 permet aux utilisateurs de votre organisation de créer des réunions sur Skype Entreprise, et les autorise à se connecter à ces réunions à l’aide d’un téléphone. Dans Office 365, vous avez la possibilité d’utiliser un pont de conférence audio Microsoft ou un pont de conférence audio tiers qui est hébergé par un fournisseur de services d’audioconférence approuvé (ACP).
  
> [!NOTE]
> Il n'existe pas de ressource qui rassemble tous les numéros de connexion pour l'audioconférence. Si vous souhaitez pour voir s’il existe des numéros de téléphone entrant dans votre région ou le pays/région, utilisez le **Skype pour le centre d’administration de Business** > **vocale** > de**Numéros de téléphone**, cliquez sur **Ajouter** puis **nouveaux numéros de Service **. |||UNTRANSLATED_CONTENT_START|||Use the lists for **Country/Region**, **State/Region** and **City** to filter your search.> Also, if you are looking for toll free service numbers, select **Toll-Free** from the **State/Region** list.|||UNTRANSLATED_CONTENT_END|||
  
Un pont de conférence vous offre un ensemble de numéros de téléphone pour votre organisation. Tous ces ponts peuvent servir à participer à des réunions créées par un organisateur de réunion, mais vous pouvez sélectionner ceux qui doivent être inclus dans les invitations de réunion.
  
> [!NOTE]
> Il peut y avoir au maximum une ligne simple et une ligne de téléphone gratuite dont les numéros apparaissent sur l’invitation à la réunion pour un organisateur de réunion, mais il existe également un lien situé en bas de chaque invitation à une réunion qui ouvre la liste complète de tous les numéros de téléphone qui peuvent être utilisés pour participer à une réunion. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a>Définir le numéro de téléphone par défaut pour un organisateur de réunion

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centres dʼadministration** > **Skype Entreprise**.
    
3. Sélectionnez **Utilisateurs**.
    
    ![Indique les utilisateurs au niveau du centre d'administration Skype Entreprise](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. Choisir les utilisateurs à modifier :
    
  - Pour sélectionner un seul utilisateur, sélectionnez le nom de l’utilisateur.
    
  - Pour sélectionner tous les utilisateurs sur la page, cochez la case à côté de **Afficher le nom** en haut de la liste.
    
  - Pour sélectionner plusieurs utilisateurs, cochez la case en regard de chaque nom d’utilisateur.
    
5. Dans le volet de droite, sélectionnez **Modifier**.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Choisissez **Audioconférence**.
    
7. Dans la page **Propriétés**, dans la liste **Nom du fournisseur**, sélectionnez le fournisseur pour l’utilisateur. Selon le fournisseur, complétez les champs suivants.
    
  - **Microsoft est le fournisseur**: utilisez les listes de **numéro de téléphone payant par défaut** et de **numéro d’appel gratuit par défaut** pour sélectionner les numéros par défaut pour l’utilisateur.
    
    > [!NOTE]
    > Au moins un numéro d’appel gratuit doit être affecté à votre pont de conférence avant qu’il ne puisse être défini comme étant le numéro d’appel gratuit par défaut d’un utilisateur. Pour obtenir un numéro gratuit, voir les [numéros de téléphone de service de mise en route pour Skype pour les entreprises](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md). 
  
  - **Le fournisseur est un tiers**: utiliser les champs de **Numéro de téléphone payant** et de**Numéro d'appel gratuit** pour indiquer les numéros pour l'utilisateur.


## <a name="reset-audio-conferencing-phone-numbers"></a>Réinitialiser les numéros de téléphone des services d’audioconférence

1. Dans la **Skype entreprise centre d’administration**, choisissez **audioconférence**.
    
2. En haut de la page, choisissez **Utilisateurs**.
    
3. Sélectionnez les utilisateurs que vous souhaitez réinitialiser, puis dans le volet Actions, cliquez sur **Effacer**.
    
Par défaut, lorsque vous modifiez les paramètres de conférence d’un utilisateur, un message électronique est envoyé à l’utilisateur. Pour modifier ce paramètre, voir [Activer ou désactiver l’envoi de messages électroniques lors de la modifient des paramètres de conférence Audio](enable-or-disable-sending-emails-when-their-settings-change.md).
  
> [!IMPORTANT]
> Lorsque vous modifiez les paramètres d'audioconférence d’un utilisateur, les réunions Skype Entreprise périodiques et futures doivent être mises à jour et envoyées aux participants. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688).
    
- Utilisez l'applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) pour modifier le numéro payant ou gratuit par défaut pour des utilisateurs spécifiques.
    
    Pour modifier le numéro gratuit par défaut pour un utilisateur, exécutez ce qui suit :
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- Utilisez l'applet de commande **Set-CsOnlineDialInConferencingUserDefaultNumber** pour modifier le numéro gratuit ou payant par défaut des utilisateurs en fonction de leur numéro par défaut d'origine ou de leur emplacement.
    
    > [!NOTE]
    > Pour rechercher la BridgeID, utilisez l’applet de commande **Get-CsOnlineDialInConferencingBridge** .
  
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - Pour définir le numéro d’appel gratuit par défaut pour tous les utilisateurs sans un et +18005551234, exécutez :
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - Pour modifier le numéro gratuit par défaut de tous les utilisateurs qui ont leur numéro gratuit par défaut à +18005551239 +18005551234, exécutez :
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Pour définir le numéro gratuit par défaut de tous les utilisateurs situés à +18005551234 qu’aux États-Unis, exécutez :
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
## <a name="want-to-learn-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?
- Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l'audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
