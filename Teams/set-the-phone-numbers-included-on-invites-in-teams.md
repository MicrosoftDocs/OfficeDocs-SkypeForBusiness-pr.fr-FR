---
title: Définir le téléphone numéros inclus sur invite dans Microsoft Teams
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
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtenir les étapes pour créer un numéro de téléphone par défaut pour les appelants à participer à une réunion Microsoft Teams. '
ms.openlocfilehash: 859bf6f4a99f95c67123385c99061b1546eaa60c
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296270"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="cff56-103">Définir les numéros de téléphone inclus dans les invitations dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cff56-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="cff56-104">La fonction d’audioconférence dans Office 365 permet aux utilisateurs dans votre organisation de créer des réunions Microsoft Teams, puis de composer un numéro pour accéder à ces réunions en utilisant un téléphone.</span><span class="sxs-lookup"><span data-stu-id="cff56-104">Audio Conferencing in Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="cff56-105">Dans Office 365, vous pouvez utiliser un pont d’audioconférence Microsoft ou un pont d'audioconférence tiers hébergé par un fournisseur de services d'audioconférence agréé.</span><span class="sxs-lookup"><span data-stu-id="cff56-105">In Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
<span data-ttu-id="cff56-106">Un pont de conférence vous fournit un ensemble de numéros de téléphone pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="cff56-106">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="cff56-107">Tous ces ponts peuvent servir à participer à des réunions créées par un organisateur de réunion, mais vous pouvez sélectionner ceux qui doivent être inclus dans les invitations de réunion.</span><span class="sxs-lookup"><span data-stu-id="cff56-107">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cff56-108">Il peut y avoir au maximum une ligne simple et une ligne de téléphone gratuite dont les numéros apparaissent sur l’invitation à la réunion pour un organisateur de réunion, mais il existe également un lien situé en bas de chaque invitation à une réunion qui ouvre la liste complète de tous les numéros de téléphone qui peuvent être utilisés pour participer à une réunion.</span><span class="sxs-lookup"><span data-stu-id="cff56-108">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="cff56-109">Définir ou modifier le numéro de téléphone d’audioconférence par défaut d’un organisateur ou utilisateur</span><span class="sxs-lookup"><span data-stu-id="cff56-109">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

![les équipes-logo-30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="cff56-111">À l’aide de Skype les équipes Microsoft Business centre d’administration</span><span class="sxs-lookup"><span data-stu-id="cff56-111">Using the Microsoft Teams and Skype for Business Admin Center</span></span>

1. <span data-ttu-id="cff56-112">Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="cff56-112">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

    ![Indique de sélectionner des utilisateurs dans le Microsoft Teams et Skype entreprise centre d’administration](media/teamsselectusers.png)

2. <span data-ttu-id="cff56-114">En haut de la page, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="cff56-114">At the top of the page, click **Edit**.</span></span>

    ![Cliquez sur Modifier dans les équipes Microsoft Skype entreprise centre d’administration](media/teamsedituser.png)

3. <span data-ttu-id="cff56-116">A côté de **Conférence Audio**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="cff56-116">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![Cliquez sur Modifier en regard de conférence Audio](media/teamseditaudioconf.png)

4. <span data-ttu-id="cff56-118">Utilisez les champs de **numéro de téléphone payant** ou **numéro d’appel gratuit** pour entrer les numéros pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cff56-118">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="cff56-119">Lorsque vous modifiez les paramètres de conférence audio d’un utilisateur, périodiques et futures réunions Teams Microsoft doivent être mis à jour et envoyées aux participants.</span><span class="sxs-lookup"><span data-stu-id="cff56-119">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span> 

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="cff56-120">Vous souhaitez utiliser Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="cff56-120">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="cff56-p103">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="cff56-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="cff56-124">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="cff56-124">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="cff56-125">Meilleurs moyens de gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cff56-125">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="cff56-126">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="cff56-126">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span> 
  
    
## <a name="related-topics"></a><span data-ttu-id="cff56-127">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="cff56-127">Related topics</span></span>

[<span data-ttu-id="cff56-128">Tester ou acheter l'audioconférence dans Office 365</span><span class="sxs-lookup"><span data-stu-id="cff56-128">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
