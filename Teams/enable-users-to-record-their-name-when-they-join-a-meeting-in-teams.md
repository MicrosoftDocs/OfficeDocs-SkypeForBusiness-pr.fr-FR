---
title: Permettre aux utilisateurs d’enregistrer leur nom lorsqu’ils rejoignent une réunion dans Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: Découvrez comment activer ou désactiver si vos utilisateurs peuvent enregistrer leurs noms lorsqu’ils rejoignent une réunion dans Microsoft Teams.
ms.openlocfilehash: 55aa14f53e71bb13c7219e3730cf91388b566047
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850792"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a><span data-ttu-id="528bd-103">Permettre aux utilisateurs d’enregistrer leur nom lorsqu’ils rejoignent une réunion dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="528bd-103">Enable users to record their name when they join a meeting in Microsoft Teams</span></span>

<span data-ttu-id="528bd-104">Lorsque vous configurez les services d’audioconférence dans Office 365, vous recevrez des numéros de téléphone et ce que l'on appelle un pont de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="528bd-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers and what is called an audio conferencing bridge.</span></span> <span data-ttu-id="528bd-105">Un pont de conférence peut comporter un ou plusieurs numéros de téléphone qui peuvent être dédiés ou partagés.</span><span class="sxs-lookup"><span data-stu-id="528bd-105">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="528bd-106">Le pont de conférence répond à l'appel d’un utilisateur se connectant à une réunion à l’aide de son téléphone.</span><span class="sxs-lookup"><span data-stu-id="528bd-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="528bd-107">Le pont de conférence répond à l’appelant à invites vocales à partir d’un standard automatique et, en fonction de leurs paramètres, peut diffuser les notifications, poser aux appelants à enregistrer leur nom et configurer la sécurité du code confidentiel pour les organisateurs de réunions.</span><span class="sxs-lookup"><span data-stu-id="528bd-107">The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers.</span></span> <span data-ttu-id="528bd-108">Codes confidentiels accordées aux organisateurs de réunions pour pouvoir démarrer une réunion.</span><span class="sxs-lookup"><span data-stu-id="528bd-108">PINs are given to meeting organizers to allow them to start a meeting.</span></span> <span data-ttu-id="528bd-109">Toutefois, vous pouvez configurer il afin d’un code confidentiel n’est pas nécessaire pour démarrer une réunion.</span><span class="sxs-lookup"><span data-stu-id="528bd-109">However, you can set it up so a PIN isn't required to start a meeting.</span></span>

  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="528bd-110">Définir si les appelants doivent enregistrer leur nom</span><span class="sxs-lookup"><span data-stu-id="528bd-110">Set whether callers should record their name</span></span>

1. <span data-ttu-id="528bd-111">Dans la navigation de gauche, accédez à des **réunions** > **Ponts de conférence**.</span><span class="sxs-lookup"><span data-stu-id="528bd-111">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="528bd-112">En haut de la page de **Ponts de conférence** , cliquez sur **paramètres du pont**.</span><span class="sxs-lookup"><span data-stu-id="528bd-112">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="528bd-113">Activer ou désactiver une **entrée de réunion et quitter des notifications**.</span><span class="sxs-lookup"><span data-stu-id="528bd-113">Enable or disable **Meeting entry and exit notifications**.</span></span>

4. <span data-ttu-id="528bd-114">Si vous activez les notifications, choisissez des **noms ou des numéros de téléphone** sous **type d’entrée/sortie annonce**et allumez **poser aux appelants à enregistrer leur nom avant de participer à une réunion.**</span><span class="sxs-lookup"><span data-stu-id="528bd-114">If enabling notifications, choose **Names or phone numbers** under **Entry/exit announcement type**, and then turn on **Ask callers to record their name before joining a meeting.**</span></span>

6. <span data-ttu-id="528bd-115">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="528bd-115">Click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="528bd-116">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="528bd-116">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="528bd-p103">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="528bd-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="528bd-120">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="528bd-120">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="528bd-121">Six raisons d'utiliser Windows PowerShell pour gérer Office 365 </span><span class="sxs-lookup"><span data-stu-id="528bd-121">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="528bd-122">Pour plus d’informations sur Windows PowerShell, voir la [référence PowerShell d’équipes Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="528bd-122">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="528bd-123">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="528bd-123">Related topics</span></span>

[<span data-ttu-id="528bd-124">Tester ou acheter l'audioconférence dans Office 365</span><span class="sxs-lookup"><span data-stu-id="528bd-124">Try or purchase Audio Conferencing in Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
