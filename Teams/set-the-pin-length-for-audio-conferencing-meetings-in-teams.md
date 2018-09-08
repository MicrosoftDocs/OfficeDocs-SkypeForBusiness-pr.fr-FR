---
title: Définir la longueur du code confidentiel pour les réunions de conférence Audio dans Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Découvrez les paramètres de la longueur et la configuration requise d’un code confidentiel et comment définir la longueur de réunions dans Microsoft Teams.
ms.openlocfilehash: 0300bba9139bdf98315b8af4200dd729ff6e70a1
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882990"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a><span data-ttu-id="cba04-103">Définir la longueur du code confidentiel pour les réunions de conférence Audio dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cba04-103">Set the PIN length for Audio Conferencing meetings in Microsoft Teams</span></span>

<span data-ttu-id="cba04-104">Lorsque vous configurez des services d’audioconférence Teams Microsoft, vous obtiendrez un pont de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="cba04-104">When you are setting up audio conferencing for Microsoft Teams, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="cba04-105">Un pont de conférence peut comporter un ou plusieurs numéros de téléphone.</span><span class="sxs-lookup"><span data-stu-id="cba04-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="cba04-106">Le numéro de téléphone que vous avez figureront dans les invitations de réunion pour l’application Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cba04-106">The phone number you set will be included on the meeting invites for the Microsoft Teams app.</span></span>
  
<span data-ttu-id="cba04-107">Le pont de conférence audio répond à un appel pour les personnes qui sont connectent à une réunion à l’aide d’un téléphone.</span><span class="sxs-lookup"><span data-stu-id="cba04-107">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="cba04-108">Il répond à l’appelant à invites vocales à partir d’un standard automatique, puis, en fonction de vos paramètres, peut lire des notifications et poser aux appelants à enregistrer leur nom.</span><span class="sxs-lookup"><span data-stu-id="cba04-108">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="cba04-109">Les **Paramètres de pont de Microsoft** permettent de modifier les paramètres des notifications de réunion et l’expérience d’accès aux réunions, et de définir la longueur des codes confidentiels utilisés par les organisateurs de réunions.</span><span class="sxs-lookup"><span data-stu-id="cba04-109">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="cba04-110">Organisateurs de réunion permet de démarrer les réunions si elles ne peuvent pas participer à la réunion à l’aide de l’application Microsoft Teams codes confidentiels.</span><span class="sxs-lookup"><span data-stu-id="cba04-110">Meeting organizers use PINs to start meetings if they can't join the meeting using the Microsoft Teams app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="cba04-111">Définir la longueur du code confidentiel</span><span class="sxs-lookup"><span data-stu-id="cba04-111">Setting the PIN length</span></span>

1. <span data-ttu-id="cba04-112">Dans la navigation de gauche, accédez à des **réunions** > **Ponts de conférence**.</span><span class="sxs-lookup"><span data-stu-id="cba04-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="cba04-113">En haut de la page de **Ponts de conférence** , cliquez sur **Paramètres du pont**.</span><span class="sxs-lookup"><span data-stu-id="cba04-113">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="cba04-114">Dans le volet **paramètres du pont** , sous **longueur du code confidentiel**, sélectionnez le nombre de chiffres que vous voulez pour le code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="cba04-114">In the **Bridge settings** pane, under **PIN length**, select the number of digits you want for the PIN.</span></span>

4. <span data-ttu-id="cba04-115">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="cba04-115">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="cba04-p103">Un code confidentiel est différent d'un ID de conférence. Les ID de conférence sont utilisés par les appelants lorsqu'ils rejoignent la réunion. Ils permettent d'identifier la réunion. Le code confidentiel est utilisé pour authentifier un appelant en tant qu'organisateur de la réunion.</span><span class="sxs-lookup"><span data-stu-id="cba04-p103">A PIN is different from a conference ID. Conference IDs are used by callers when they join the meeting. They are used to identify the meeting. The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="cba04-120">Vous souhaitez en savoir plus sur les paramètres de code confidentiel ?</span><span class="sxs-lookup"><span data-stu-id="cba04-120">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="cba04-121">Codes confidentiels peuvent être de 4 à 12 chiffres ; la valeur par défaut est 5.</span><span class="sxs-lookup"><span data-stu-id="cba04-121">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="cba04-122">Seuls des chiffres doivent être utilisés lors de la création de codes confidentiels.</span><span class="sxs-lookup"><span data-stu-id="cba04-122">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="cba04-123">Les lettres et les caractères spéciaux ne sont pas autorisés.</span><span class="sxs-lookup"><span data-stu-id="cba04-123">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="cba04-124">Un code confidentiel est uniquement requis pour l’organisateur de la réunion lorsqu’un utilisateur Teams Microsoft n’a pas déjà démarré la réunion.</span><span class="sxs-lookup"><span data-stu-id="cba04-124">A PIN is only required for the meeting organizer when a Microsoft Teams user hasn't already started the meeting.</span></span> <span data-ttu-id="cba04-125">Si tout le monde compose un numéro pour accéder à la réunion, le code confidentiel est nécessaire pour que l'organisateur puisse commencer la réunion.</span><span class="sxs-lookup"><span data-stu-id="cba04-125">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="cba04-p106">Les paramètres de sécurité de code confidentiel sont appliqués à tous les numéros de téléphone associés à un pont Microsoft. Ils sont appliqués à toutes les réunions qui utilisent les numéros de téléphone associés à un pont spécifique.</span><span class="sxs-lookup"><span data-stu-id="cba04-p106">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge. They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="cba04-128">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="cba04-128">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="cba04-p107">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="cba04-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="cba04-132">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="cba04-132">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="cba04-133">Six raisons d'utiliser Windows PowerShell pour gérer Office 365 </span><span class="sxs-lookup"><span data-stu-id="cba04-133">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="cba04-134">Pour plus d’informations sur Windows PowerShell, voir la [référence PowerShell d’équipes Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="cba04-134">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="cba04-135">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="cba04-135">Related topics</span></span>

[<span data-ttu-id="cba04-136">Tester ou acheter l'audioconférence dans Office 365</span><span class="sxs-lookup"><span data-stu-id="cba04-136">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
