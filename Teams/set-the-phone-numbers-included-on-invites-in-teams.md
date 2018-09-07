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
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="7fd8e-103">Définir le téléphone numéros inclus sur invite dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7fd8e-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="7fd8e-104">Services d’audioconférence dans Office 365 permet aux utilisateurs de votre organisation de créer des réunions Microsoft Teams, puis autoriser les utilisateurs à se connecter à ces réunions à l’aide d’un téléphone.</span><span class="sxs-lookup"><span data-stu-id="7fd8e-104">Audio Conferencing in Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="7fd8e-105">Dans Office 365, vous avez la possibilité d’utiliser un pont de conférence audio Microsoft ou un pont de conférence audio tiers qui est hébergé par un fournisseur de services d’audioconférence approuvé (ACP).</span><span class="sxs-lookup"><span data-stu-id="7fd8e-105">In Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
<span data-ttu-id="7fd8e-106">Un pont de conférence vous offre un ensemble de numéros de téléphone pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="7fd8e-106">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="7fd8e-107">Tous les peuvent servir à participer à des réunions créé un organisateur de réunion, mais vous pouvez sélectionner ceux qui doivent être incluses dans les invitations de réunion.</span><span class="sxs-lookup"><span data-stu-id="7fd8e-107">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7fd8e-108">Il peut y avoir un maximum d’un numéro et un numéro de téléphone gratuit sur l’invitation à la réunion pour un organisateur de réunion, mais il existe également un lien situé en bas de chaque invitation à la réunion qui ouvre la liste complète de tous les numéros de téléphone qui peut être utilisé pour participer à une réunion.</span><span class="sxs-lookup"><span data-stu-id="7fd8e-108">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="7fd8e-109">Définir ou modifier le numéro de téléphone de conférence audio par défaut pour un utilisateur ou un organisateur de la réunion</span><span class="sxs-lookup"><span data-stu-id="7fd8e-109">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

1. <span data-ttu-id="7fd8e-110">Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="7fd8e-110">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

    ![Indique de sélectionner des utilisateurs dans le Microsoft Teams et Skype entreprise centre d’administration](media/teamsselectusers.png)

2. <span data-ttu-id="7fd8e-112">En haut de la page, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="7fd8e-112">At the top of the page, click **Edit**.</span></span>

    ![Cliquez sur Modifier dans les équipes Microsoft Skype entreprise centre d’administration](media/teamsedituser.png)

3. <span data-ttu-id="7fd8e-114">En regard de **Conférence Audio**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="7fd8e-114">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![Cliquez sur Modifier en regard de conférence Audio](media/teamseditaudioconf.png)

4. <span data-ttu-id="7fd8e-116">Utilisez les champs de **numéro de téléphone payant** ou **numéro d’appel gratuit** pour entrer les numéros pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7fd8e-116">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="7fd8e-117">Lorsque vous modifiez les paramètres de conférence audio d’un utilisateur, périodiques et futures réunions Teams Microsoft doivent être mis à jour et envoyées aux participants.</span><span class="sxs-lookup"><span data-stu-id="7fd8e-117">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span> 

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="7fd8e-118">Vous souhaitez utiliser Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="7fd8e-118">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="7fd8e-p103">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="7fd8e-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7fd8e-122">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="7fd8e-122">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="7fd8e-123">Six raisons d'utiliser Windows PowerShell pour gérer Office 365 </span><span class="sxs-lookup"><span data-stu-id="7fd8e-123">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="7fd8e-124">Pour plus d’informations sur Windows PowerShell, voir la [référence PowerShell d’équipes Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="7fd8e-124">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span> 
  
    
## <a name="related-topics"></a><span data-ttu-id="7fd8e-125">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="7fd8e-125">Related topics</span></span>

[<span data-ttu-id="7fd8e-126">Tester ou acheter l'audioconférence dans Office 365</span><span class="sxs-lookup"><span data-stu-id="7fd8e-126">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
