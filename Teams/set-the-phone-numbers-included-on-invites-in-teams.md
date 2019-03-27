---
title: Définir les numéros de téléphone inclus sur les invitations dans Microsoft Teams.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtenir les étapes pour créer un numéro de téléphone par défaut pour les appelants à participer à une réunion Microsoft Teams. '
ms.openlocfilehash: 890fe76e455d68868b007537eba6084bf32ad4b5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875425"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Définir les numéros de téléphone inclus dans les invitations dans Microsoft Teams

Services d’audioconférence dans Office 365 permet aux utilisateurs de votre organisation de créer des réunions Microsoft Teams, puis autoriser les utilisateurs à se connecter à ces réunions à l’aide d’un téléphone.
  
Un pont de conférence vous offre un ensemble de numéros de téléphone pour votre organisation. Tous ces ponts peuvent servir à participer à des réunions créées par un organisateur de réunion, mais vous pouvez sélectionner ceux qui doivent être inclus dans les invitations de réunion.
  
> [!NOTE]
> Il peut y avoir au maximum une ligne simple et une ligne de téléphone gratuite dont les numéros apparaissent sur l’invitation à la réunion pour un organisateur de réunion, mais il existe également un lien situé en bas de chaque invitation à une réunion qui ouvre la liste complète de tous les numéros de téléphone qui peuvent être utilisés pour participer à une réunion. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a>Invite d’affectation initiale des numéros de téléphone qui sont inclus dans la réunion pour les nouveaux utilisateurs

Les numéros de téléphone incluses dans la réunion invite d’utilisateurs activés pour la conférence Audio sont définies par le numéro d’appel payant conférence par défaut et les paramètres de l’utilisateur par défaut conférence gratuit numéro. Chaque paramètre spécifie le numéro payant et le numéro gratuit seront inclus dans l’invitation à la réunion d’un utilisateur donné. Comme mentionné ci-dessus, chaque invitation à la réunion contient un numéro, un seul numéro gratuit facultatif et un lien qui ouvre la liste complète de tous les numéros de téléphone qui peut être utilisé pour participer à une réunion donnée.

Pour un nouvel utilisateur, les numéros d’appel payant de conférence par défaut sont affectée en fonction du pays est défini dans le profil de l’utilisateur d’Office 365 lorsque l’utilisateur est activé pour le service de conférence Audio. Si le pont de conférence qui correspond à celui de l’utilisateur est un numéro de téléphone payant, ce numéro est automatiquement attribué en tant que le numéro par défaut de l’utilisateur. Si vous n’en est pas, le nombre est défini comme le numéro par défaut du pont de conférence sera assignée comme le numéro par défaut de l’utilisateur.  

Une fois que l’utilisateur est activé pour le service de conférence Audio, le numéro payant par défaut et les numéros de téléphone de l’utilisateur peuvent être modifiés par l’administrateur de clients à partir de leurs valeurs initiales à tout moment.

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>Définir ou modifier le numéro de téléphone de conférence audio par défaut pour un utilisateur ou un organisateur de la réunion

![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft équipes**

1. Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

    ![Affiche la sélection des utilisateurs dans le centre d’administration Microsoft Teams](media/teams-set-phone-numbers-on-invites-image1.png)

2. En haut de la page, cliquez sur **Modifier**.

    ![Cliquez sur Modifier dans le centre d’administration Microsoft Teams](media/teams-set-phone-numbers-on-invites-image2.png)

3. A côté de **Conférence Audio**, cliquez sur **Modifier**. 
    
    ![Cliquez sur Modifier en regard de conférence Audio](media/teams-set-phone-numbers-on-invites-image3.png)

4. Utilisez les champs de **numéro de téléphone payant** ou **numéro d’appel gratuit** pour entrer les numéros pour l’utilisateur.


> [!IMPORTANT]
> Lorsque vous modifiez les paramètres de conférence audio d’un utilisateur, périodiques et futures réunions Teams Microsoft doivent être mis à jour et envoyées aux participants. 

## <a name="want-to-use-windows-powershell"></a>Vous souhaitez utiliser Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleurs moyens de gérer Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps). 
  
    
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l’audioconférence dans Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[Modifier les numéros de téléphone de votre pont d’audioconférence](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
