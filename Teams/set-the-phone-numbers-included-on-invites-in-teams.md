---
title: Définissez le téléphone numéros inclus sur invite dans les équipes Microsoft
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
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtenir les étapes pour créer un numéro de téléphone par défaut pour les appelants à participer à une réunion équipes Microsoft. '
ms.openlocfilehash: 54778aac19d090b4c609da1c5a63da3ba146ae44
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23857446"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Définir le téléphone numéros inclus sur invite dans Microsoft Teams

Services d’audioconférence dans Office 365 permet aux utilisateurs de votre organisation de créer des réunions Microsoft Teams, puis autoriser les utilisateurs à se connecter à ces réunions à l’aide d’un téléphone. Dans Office 365, vous avez la possibilité d’utiliser un pont de conférence audio Microsoft ou un pont de conférence audio tiers qui est hébergé par un fournisseur de services d’audioconférence approuvé (ACP).
  
Un pont de conférence vous offre un ensemble de numéros de téléphone pour votre organisation. Tous les peuvent servir à participer à des réunions créé un organisateur de réunion, mais vous pouvez sélectionner ceux qui doivent être incluses dans les invitations de réunion.
  
> [!NOTE]
> Il peut y avoir un maximum d’un numéro et un numéro de téléphone gratuit sur l’invitation à la réunion pour un organisateur de réunion, mais il existe également un lien situé en bas de chaque invitation à la réunion qui ouvre la liste complète de tous les numéros de téléphone qui peut être utilisé pour participer à une réunion. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>Définir ou modifier le numéro de téléphone de conférence audio par défaut pour un utilisateur ou un organisateur de la réunion

1. Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

    ![Indique de sélectionner des utilisateurs dans le Microsoft Teams et Skype entreprise centre d’administration](media/teamsselectusers.png)

2. En haut de la page, cliquez sur **Modifier**.

    ![Cliquez sur Modifier dans les équipes Microsoft Skype entreprise centre d’administration](media/teamsedituser.png)

3. En regard de **Conférence Audio**, cliquez sur **Modifier**. 
    
    ![Cliquez sur Modifier en regard de conférence Audio](media/teamseditaudioconf.png)

4. Utilisez les champs de **numéro de téléphone payant** ou **numéro d’appel gratuit** pour entrer les numéros pour l’utilisateur.


> [!IMPORTANT]
> Lorsque vous modifiez les paramètres de conférence audio d’un utilisateur, périodiques et futures réunions Teams Microsoft doivent être mis à jour et envoyées aux participants. 

## <a name="want-to-use-windows-powershell"></a>Vous souhaitez utiliser Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Pour plus d’informations sur Windows PowerShell, voir la [référence PowerShell d’équipes Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) pour plus d’informations. 
  
    
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l'audioconférence dans Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
