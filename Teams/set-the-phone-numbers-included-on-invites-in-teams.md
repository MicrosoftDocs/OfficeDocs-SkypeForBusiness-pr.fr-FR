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
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Découvrez les étapes nécessaires pour créer un numéro de téléphone par défaut permettant aux appelants de participer à une réunion Microsoft Teams. '
ms.openlocfilehash: edaed53ddd25dee875753b76bb612888ebb45cef
ms.sourcegitcommit: 15fe483079847d24869e325eead35f252da8c7dd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "37571281"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Définir les numéros de téléphone inclus dans les invitations dans Microsoft Teams

L’audioconférence dans Office 365 permet aux utilisateurs de votre organisation de créer des réunions Microsoft Teams, puis de permettre aux utilisateurs de se connecter à ces réunions à l’aide d’un téléphone.
  
Un pont de conférence vous offre un ensemble de numéros de téléphone pour votre organisation. Tous ces ponts peuvent servir à participer à des réunions créées par un organisateur de réunion, mais vous pouvez sélectionner ceux qui doivent être inclus dans les invitations de réunion.
  
> [!NOTE]
> Il peut y avoir au maximum une ligne simple et une ligne de téléphone gratuite dont les numéros apparaissent sur l’invitation à la réunion pour un organisateur de réunion, mais il existe également un lien situé en bas de chaque invitation à une réunion qui ouvre la liste complète de tous les numéros de téléphone qui peuvent être utilisés pour participer à une réunion. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a>Attribution initiale des numéros de téléphone inclus dans les invitations aux réunions pour les nouveaux utilisateurs

Les numéros de téléphone inclus dans les invitations aux réunions des utilisateurs activés pour les conférences audio sont définis par le numéro de téléphone payant par défaut et les paramètres de l’utilisateur numéro de téléphone gratuit pour la Conférence par défaut. Chacun d’eux spécifie le numéro payant et le numéro gratuit inclus dans l’invitation à la réunion d’un utilisateur donné. Comme indiqué plus haut, chaque invitation à une réunion contient un numéro payant, un numéro gratuit facultatif et un lien permettant d’ouvrir la liste complète de tous les numéros de téléphone rendez-vous qui peuvent être utilisés pour participer à une réunion donnée.

S’il s’agit d’un nouvel utilisateur, les numéros payants de la Conférence par défaut sont attribués en fonction du pays défini dans le profil 365 Office de l’utilisateur lorsque l’utilisateur est activé pour le service d’audioconférence. S’il existe un numéro payant dans le pont de conférence qui correspond au pays de l’utilisateur, ce numéro sera automatiquement attribué en tant que numéro payant par défaut de l’utilisateur. Si ce n’est pas le cas, le numéro défini en tant que numéro payant par défaut du pont de conférence sera affecté en tant que numéro payant par défaut de l’utilisateur.  

Lorsque l’utilisateur est activé pour le service d’audioconférence, les numéros de téléphone gratuits et payants par défaut de l’utilisateur peuvent être modifiés à tout moment par l’administrateur client.

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>Définir ou changer le numéro de téléphone de l’audioconférence par défaut pour un utilisateur ou un organisateur de la réunion

![Icône illustrant le logo](media/teams-logo-30x30.png) de Microsoft teams à l' **aide du centre d’administration Microsoft teams**

1. Dans le volet de navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

    ![Sélection des utilisateurs dans le centre d’administration Microsoft teams](media/teams-set-phone-numbers-on-invites-image1.png)

2. En haut de la page, cliquez sur **Modifier**.

    ![Cliquez sur modifier dans le centre d’administration Microsoft teams](media/teams-set-phone-numbers-on-invites-image2.png)

3. A côté de **Conférence Audio**, cliquez sur **Modifier**. 
    
    ![Cliquez sur modifier en regard de audioconférence](media/teams-set-phone-numbers-on-invites-image3.png)

4. Utilisez les champs **numéro payant** ou **numéro gratuit** pour entrer les numéros de l’utilisateur.


> [!IMPORTANT]
> Lorsque vous modifiez les paramètres d’audioconférence d’un utilisateur, les réunions périodiques et périodiques de Microsoft teams doivent être mises à jour et envoyées aux participants. 

## <a name="want-to-use-windows-powershell"></a>Vous souhaitez utiliser Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleurs moyens de gérer Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps). 
  
    
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l’audioconférence dans Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[Modifier les numéros de téléphone de votre pont d’audioconférence](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
