---
title: Autoriser les utilisateurs à enregistrer leur nom lorsqu'ils participent à une réunion dans Microsoft Teams
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Découvrez comment autoriser les utilisateurs à enregistrer leur nom lorsqu'ils participent à une réunion dans Microsoft Teams.
ms.openlocfilehash: c09cd9b5fd0a8934c61a37212de53d750f7deac7
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/08/2018
ms.locfileid: "23893001"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a><span data-ttu-id="e34a2-103">Autoriser les utilisateurs à enregistrer leur nom lorsqu'ils participent à une réunion dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e34a2-103">Enable users to record their name when they join a meeting</span></span>

<span data-ttu-id="e34a2-104">Lorsque vous configurez l’audioconférence dans Office 365, vous obtenez des numéros de téléphone et ce que l’on appelle un pont d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="e34a2-104">When you are setting up dial-in conferencing in Skype for Business Online, you will receive phone numbers and what is called a dial-in or audio conferencing bridge.</span></span> <span data-ttu-id="e34a2-105">Un pont de conférence peut comporter un ou plusieurs numéros de téléphone qui peuvent être dédiés ou partagés.</span><span class="sxs-lookup"><span data-stu-id="e34a2-105">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="e34a2-106">Le pont de conférence répond à l’appel d’un utilisateur qui compose un numéro pour accéder à la réunion en utilisant un téléphone.</span><span class="sxs-lookup"><span data-stu-id="e34a2-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="e34a2-107">Il répond à l’appelant avec des invites vocales d’un standard automatique puis, en fonction des paramètres, il peut lire des notifications, demander aux appelants d’enregistrer leur nom et définir la sécurité avec un code confidentiel pour les organisateurs de la réunion.</span><span class="sxs-lookup"><span data-stu-id="e34a2-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="e34a2-108">Les codes confidentiels sont donnés aux organisateurs de réunions pour leur permettre de démarrer une réunion.</span><span class="sxs-lookup"><span data-stu-id="e34a2-108">PINs are given to meeting organizers to allow them to start a meeting.</span></span> <span data-ttu-id="e34a2-109">Vous pouvez cependant définir les options de telle sorte qu'un code confidentiel ne soit pas nécessaire pour démarrer une réunion.</span><span class="sxs-lookup"><span data-stu-id="e34a2-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="e34a2-110">Définir si les appelants doivent enregistrer leur nom</span><span class="sxs-lookup"><span data-stu-id="e34a2-110">Set whether callers should record their name</span></span>

1. <span data-ttu-id="e34a2-111">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="e34a2-111">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="e34a2-112">En haut de la page **Conference Bridges** (Ponts de conférence), cliquez sur **Bridge Settings** (Paramètres du pont).</span><span class="sxs-lookup"><span data-stu-id="e34a2-112">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="e34a2-113">Activez ou désactivez l’option **Meeting entry and exit notifications** (Notifications d’entrée et de sortie de réunion).</span><span class="sxs-lookup"><span data-stu-id="e34a2-113">In the Bridge settings pane, enable or disable **Meeting entry and exit notifications**.</span></span>

4. <span data-ttu-id="e34a2-114">Si vous activez les notifications, sélectionnez **Names or phone numbers** (Noms ou numéros de téléphone) sous **Type d’annonces entrée-sortie**, et activez l’option **Ask callers to record their name before joining a meeting** (Demander aux appelants d'enregistrer leur nom avant de rejoindre la réunion).</span><span class="sxs-lookup"><span data-stu-id="e34a2-114">If enabling notifications, choose **Names or phone numbers** under **Entry/exit announcement type**, and then turn on **Ask callers to record their name before joining a meeting.**</span></span>

6. <span data-ttu-id="e34a2-115">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e34a2-115">Click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="e34a2-116">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="e34a2-116">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="e34a2-p103">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="e34a2-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e34a2-120">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="e34a2-120">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="e34a2-121">Meilleurs moyens de gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e34a2-121">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="e34a2-122">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="e34a2-122">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e34a2-123">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="e34a2-123">Related topics</span></span>

[<span data-ttu-id="e34a2-124">Tester ou acheter l'audioconférence dans Office 365</span><span class="sxs-lookup"><span data-stu-id="e34a2-124">Try or purchase Audio Conferencing in Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
