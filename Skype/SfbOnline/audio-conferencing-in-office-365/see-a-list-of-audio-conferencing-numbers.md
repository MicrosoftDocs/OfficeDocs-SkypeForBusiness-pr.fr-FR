---
title: See a list of Audio Conferencing numbers
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 2d6b4ed4-e12b-4691-8405-fae720d69425
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to look up your dial-in conferencing numbers from within Skype for Business. '
ms.openlocfilehash: 19bbf38968afb094deaf97ff14a6673b4cfdda48
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2018
---
# <a name="see-a-list-of-audio-conferencing-numbers"></a>See a list of Audio Conferencing numbers

When you set up Audio Conferencing for Skype for Business and Microsoft Teams users, you can view the phone numbers that are available to them for audio conferencing. This list will have all of the audio conferencing phone numbers that are available to your organization.
  
 **Looking for prices?** See [Pricing for Audio Conferencing](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements).
  
> [!IMPORTANT]
> **There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing.** If you are looking to see if there are dial-in phone numbers available in your area or country/region, go to **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add**, and then click **New Service Numbers**. Utilisez les listes **Pays/Région**, **État/Région** et **Ville** pour filtrer votre recherche. Also, if you are looking for toll-free service numbers, select **Toll-Free** from the **State/Region** list.
  
S'il n'existe qu'un numéro de téléphone disponible pour votre organisation, il est utilisé comme numéro par défaut pour tous vos utilisateurs. Lorsque plusieurs numéros de téléphone sont disponibles, vous pouvez sélectionner le numéro de téléphone par défaut pour chaque utilisateur. This default number will be included in Skype for Business and Microsoft Teams meeting invitations.
  
You can see [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md) to change the dial-in phone number for a single user.
  
> [!NOTE]
> Les numéros d'accès nationaux sont réservés à votre entreprise et sont les seuls à pouvoir être définis comme numéros de téléphone par défaut. En revanche, les numéros d'accès internationaux peuvent être partagés par plusieurs entreprises. 
  
## <a name="to-view-your-audio-conferencing-phone-numbers"></a>To view your audio conferencing phone numbers

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**, and then:
    
  - You can view the phone numbers that are available for audio conferencing.
    
  - You can also view the location, and the primary and secondary languages that will be used by the audio conferencing auto attendant.
    
> [!NOTE]
> You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number by choosing a new number from the list of available numbers in your organization. See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md). 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Get-⁠CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691).
    
- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l'audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
  
