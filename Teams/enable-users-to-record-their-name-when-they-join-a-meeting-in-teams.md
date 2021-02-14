---
title: Permettre aux utilisateurs d’enregistrer leur nom pour une réunion
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Découvrez comment autoriser les utilisateurs à enregistrer leur nom lorsqu'ils participent à une réunion dans Microsoft Teams.
ms.openlocfilehash: d7cab4fca4ad3e7732704da9837522d51314061d
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691580"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a><span data-ttu-id="a6bae-103">Autoriser les utilisateurs à enregistrer leur nom lorsqu'ils participent à une réunion dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a6bae-103">Enable users to record their name when they join a meeting in Microsoft Teams</span></span>

<span data-ttu-id="a6bae-104">Lors de la configuration de l’audioconférence dans Microsoft 365 ou Office 365, vous recevez des numéros de téléphone et un « pont de conférence » audio.</span><span class="sxs-lookup"><span data-stu-id="a6bae-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers and what is called an audio conferencing bridge.</span></span> <span data-ttu-id="a6bae-105">Un pont de conférence peut comporter un ou plusieurs numéros de téléphone qui peuvent être dédiés ou partagés.</span><span class="sxs-lookup"><span data-stu-id="a6bae-105">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="a6bae-106">Le pont de conférence répond à l’appel d’un utilisateur qui compose un numéro pour accéder à la réunion en utilisant un téléphone.</span><span class="sxs-lookup"><span data-stu-id="a6bae-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="a6bae-107">Il répond à l’appelant avec des invites vocales d’un standard automatique puis, en fonction des paramètres, il peut lire des notifications, demander aux appelants d’enregistrer leur nom et définir la sécurité avec un code confidentiel pour les organisateurs de la réunion.</span><span class="sxs-lookup"><span data-stu-id="a6bae-107">The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers.</span></span> <span data-ttu-id="a6bae-108">Les codes confidentiels sont donnés aux organisateurs de réunions pour leur permettre de démarrer une réunion.</span><span class="sxs-lookup"><span data-stu-id="a6bae-108">PINs are given to meeting organizers to allow them to start a meeting.</span></span> <span data-ttu-id="a6bae-109">Vous pouvez cependant définir les options de telle sorte qu'un code confidentiel ne soit pas nécessaire pour démarrer une réunion.</span><span class="sxs-lookup"><span data-stu-id="a6bae-109">However, you can set it up so a PIN isn't required to start a meeting.</span></span>

  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="a6bae-110">Définir si les appelants doivent enregistrer leur nom</span><span class="sxs-lookup"><span data-stu-id="a6bae-110">Set whether callers should record their name</span></span>

<span data-ttu-id="a6bae-111">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="a6bae-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="a6bae-112">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="a6bae-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="a6bae-113">En haut de la page Ponts **de** conférence, cliquez sur **Paramètres du pont.**</span><span class="sxs-lookup"><span data-stu-id="a6bae-113">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="a6bae-114">Activer ou désactiver les **notifications d’entrée et de sortie des réunions.**</span><span class="sxs-lookup"><span data-stu-id="a6bae-114">Enable or disable **Meeting entry and exit notifications**.</span></span>

4. <span data-ttu-id="a6bae-115">Si vous avez  activer les notifications, sélectionnez Noms ou numéros de téléphone sous Type d’annonce d’entrée/sortie, puis sélectionnez Demander aux appelants d’enregistrer leur nom avant de **rejoindre une réunion.** </span><span class="sxs-lookup"><span data-stu-id="a6bae-115">If enabling notifications, choose **Names or phone numbers** under **Entry/exit announcement type**, and then turn on **Ask callers to record their name before joining a meeting.**</span></span>

6. <span data-ttu-id="a6bae-116">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a6bae-116">Click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="a6bae-117">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="a6bae-117">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="a6bae-118">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="a6bae-118">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="a6bae-119">En Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 avec un seul point d’administration qui simplifiera votre travail si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="a6bae-119">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="a6bae-120">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="a6bae-120">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a6bae-121">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="a6bae-121">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="a6bae-122">Meilleurs moyens de gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6bae-122">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="a6bae-123">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="a6bae-123">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a6bae-124">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="a6bae-124">Related topics</span></span>

[<span data-ttu-id="a6bae-125">Essayer ou acheter l’audioconférence</span><span class="sxs-lookup"><span data-stu-id="a6bae-125">Try or purchase Audio Conferencing</span></span>](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
