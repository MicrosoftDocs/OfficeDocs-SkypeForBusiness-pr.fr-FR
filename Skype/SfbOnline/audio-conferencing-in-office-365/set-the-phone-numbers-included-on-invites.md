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
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: b7f86f114601bf4e1658a65b5a8d6520c2785e1c
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792152"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a>Définir la liste des numéros de téléphone inclus sur invite dans Skype Entreprise Online

> [!Note]
> Pour plus d’informations sur comment faire des conférences avec des numéros de téléphone inclus sur invite dans Microsoft Teams, voir [Définir les numéros de téléphone inclus sur invite dans les Microsoft Teams](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).

Audio Conferencing in Office 365 enables users in your organization to create Skype for Business meetings, and then allow users to dial in to those meetings using a phone. In Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).
  
> [!NOTE]
> There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing. If you are looking to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add** then **New Service Numbers**. Use the lists for **Country/Region**, **State/Region** and **City** to filter your search.> Also, if you are looking for toll free service numbers, select **Toll-Free** from the **State/Region** list.
  
A conferencing bridge gives you a set of dial-in phone numbers for your organization. All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.
  
> [!NOTE]
> Il peut y avoir au maximum une ligne simple et une ligne de téléphone gratuite dont les numéros apparaissent sur l’invitation à la réunion pour un organisateur de réunion, mais il existe également un lien situé en bas de chaque invitation à une réunion qui ouvre la liste complète de tous les numéros de téléphone qui peuvent être utilisés pour participer à une réunion. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a>Définir le numéro de téléphone par défaut pour un organisateur de réunion

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centres dʼadministration** > **Skype Entreprise**.
    
3. Sélectionnez **Utilisateurs**.
    
    ![Indique les utilisateurs au niveau du centre d’administration Skype Entreprise](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. Sélectionnez les utilisateurs que vous souhaitez modifier:
    
   - Pour sélectionner un seul utilisateur, sélectionnez le nom de l’utilisateur.
    
   - Pour sélectionner tous les utilisateurs sur la page, cochez la case à côté de **Afficher le nom** en haut de la liste.
    
   - Pour sélectionner plusieurs utilisateurs, cochez la case en regard de chaque nom d’utilisateur.
    
5. Dans le volet de droite, sélectionnez **Modifier**.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Choisissez **Audioconférence**.
    
7. On the **Properties** page, in the **Provider name** list, choose the provider for the user. Depending on the provider, complete the following boxes.
    
   - **Microsoft est le fournisseur**: utilisez les listes de **numéro de téléphone payant par défaut** et de **numéro d’appel gratuit par défaut** pour sélectionner les numéros par défaut pour l’utilisateur.
    
     > [!NOTE]
     > At least one toll-free number must be assigned to your conferencing bridge before it can be set as the default toll-free number of a user. To get a toll-free number, see [Getting service phone numbers for Skype for Business](/microsoftteams/getting-service-phone-numbers). 
  
   - **Le fournisseur est un tiers** : utiliser les champs de **Numéro de téléphone payant** et de**Numéro d’appel gratuit** pour indiquer les numéros pour l’utilisateur.


## <a name="reset-audio-conferencing-phone-numbers"></a>Réinitialiser les numéros de téléphone des services d’audioconférence

1. Dans le **Centre d’administration de Skype entreprise**, sélectionnez **audioconférence**.
    
2. En haut de la page, choisissez **Utilisateurs**.
    
3. Sélectionnez les utilisateurs que vous souhaitez réinitialiser, puis dans le volet Actions, cliquez sur **Effacer**.
    
By default, when you change a user's conferencing settings, an email is sent to the user. To change this, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).
  
> [!IMPORTANT]
> Lorsque vous modifiez les paramètres d’audioconférence d’un utilisateur, les réunions Skype Entreprise périodiques et futures doivent être mises à jour et envoyées aux participants. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688).
    
- Utilisez l'applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) pour modifier le numéro payant ou gratuit par défaut pour des utilisateurs spécifiques.
    
    Pour modifier le numéro gratuit par défaut pour un utilisateur, exécutez ce qui suit :
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- Utilisez l'applet de commande **Set-CsOnlineDialInConferencingUserDefaultNumber** pour modifier le numéro gratuit ou payant par défaut des utilisateurs en fonction de leur numéro par défaut d'origine ou de leur emplacement.
    
    > [!NOTE]
    > Pour rechercher le BridgeID, utilisez l’applet **de passe Get-CsOnlineDialInConferencingBridge** .
  
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - Pour définir le numéro gratuit par défaut pour tous les utilisateurs ne disposant pas de l’une de + 18005551234, exécutez:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - Pour modifier le numéro gratuit par défaut de tous les utilisateurs qui disposent de + 18005551234 comme numéro gratuit par défaut de + 18005551239, exécutez la commande suivante:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Pour définir le numéro gratuit par défaut de tous les utilisateurs situés aux États-Unis sur 18005551234, exécutez:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
  ## <a name="want-to-learn-more-about-windows-powershell"></a>Vous voulez en savoir plus sur Windows PowerShell?
- Windows PowerShell permet de gérer les utilisateurs et ce qu’ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l’aide d’un point d’administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois. Learn about these advantages in the following topics:
    
  - [Meilleures méthodes de gestion d’Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Voir aussi

[Tester ou acheter l’audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
