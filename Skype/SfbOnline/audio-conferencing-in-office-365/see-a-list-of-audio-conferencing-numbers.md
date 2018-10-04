---
title: Voir la liste des numéros d’audioconférence dans Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 2d6b4ed4-e12b-4691-8405-fae720d69425
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
description: 'Découvrez comment rechercher vos numéros de conférence rendez-vous à partir de Skype pour Business Online. '
ms.openlocfilehash: 557aef5e85cdd176e2d95e1cd946ed23e00764a0
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372886"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>Voir la liste des numéros d’audioconférence dans Skype Entreprise Online

> [!NOTE]
> Pour plus d’informations sur les numéros d’audioconférence dans Microsoft Teams, voir [Afficher la liste des numéros d’audioconférence dans Microsoft Teams](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams).

When you set up Audio Conferencing for Skype for Business users, you can view the phone numbers that are available to them for audio conferencing. This list will have all of the audio conferencing phone numbers that are available to your organization.
  
 **Looking for prices?** See [Pricing for Audio Conferencing](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements).
  
> [!IMPORTANT]
> **There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing.** If you are looking to see if there are dial-in phone numbers available in your area or country/region, go to **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add**, and then click **New Service Numbers**. Use the lists for **Country/Region**, **State/Region**, and **City** to filter your search. Also, if you are looking for toll-free service numbers, select **Toll-Free** from the **State/Region** list.
  
If there is only one phone number available in your organization, it will be used as the default number for all of your users. When multiple phone numbers are available, you can select the default phone number for each user. This default number will be included in Skype for Business meeting invitations.
  
Vous pouvez voir [l’invite inclus sur les numéros de téléphone](set-the-phone-numbers-included-on-invites.md) pour modifier le numéro de téléphone pour un seul utilisateur.
  
> [!NOTE]
> Les numéros d'accès nationaux sont réservés à votre entreprise et sont les seuls à pouvoir être définis comme numéros de téléphone par défaut. En revanche, les numéros d'accès internationaux peuvent être partagés par plusieurs entreprises. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>Pour afficher vos numéros de téléphone des services d’audioconférence

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio** > **Microsoft bridge**, puis :
    
   - Vous pouvez afficher les numéros de téléphone qui sont disponibles pour l’audioconférence.
    
   - Vous pouvez également afficher l’emplacement et les langues principales et secondaires qui seront utilisés par les services d’audioconférence standard automatiquement.
    
> [!NOTE]
> You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number by choosing a new number from the list of available numbers in your organization. See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md). 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Get-⁠CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691).
    
- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleurs moyens de gérer Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l'audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
  
