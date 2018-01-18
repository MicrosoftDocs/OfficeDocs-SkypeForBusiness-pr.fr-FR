---
title: "Permettre aux utilisateurs d’enregistrer leur nom lorsqu’ils joignent une réunion"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Apprenez à activer ou à désactiver si les utilisateurs peuvent enregistrer leurs noms lorsqu’ils joignent une réunion "
ms.openlocfilehash: f07bb24530e7b59ab6f54dfe2cd4eadf91def20c
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting"></a><span data-ttu-id="82f1a-103">Permettre aux utilisateurs d’enregistrer leur nom lorsqu’ils joignent une réunion</span><span class="sxs-lookup"><span data-stu-id="82f1a-103">Enable users to record their name when they join a meeting</span></span>

<span data-ttu-id="82f1a-104">Lorsque vous configurez une conférence Audio dans Office 365, vous recevrez les numéros de téléphone et ce que l'on appelle un pont de téléconférence audio.</span><span class="sxs-lookup"><span data-stu-id="82f1a-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers and what is called an audio conferencing bridge.</span></span> <span data-ttu-id="82f1a-105">Un pont de conférence peut contenir un ou plusieurs numéros de téléphone qui peuvent être un numéro de téléphone dédiés ou partagés.</span><span class="sxs-lookup"><span data-stu-id="82f1a-105">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="82f1a-106">Le pont de conférence répond à un appel d’un utilisateur qui appelle à une réunion à l’aide d’un téléphone.</span><span class="sxs-lookup"><span data-stu-id="82f1a-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="82f1a-107">Le pont de conférence répond à l’appelant avec des invites vocales de surveillance automatique et ensuite, en fonction de leurs paramètres, peut lire les notifications, demandez aux appelants d’enregistrer leur nom et de la sécurité du code PIN pour les organisateurs de la réunion.</span><span class="sxs-lookup"><span data-stu-id="82f1a-107">The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers.</span></span> <span data-ttu-id="82f1a-108">Les broches sont donnés aux organisateurs des réunions pour pouvoir démarrer une réunion.</span><span class="sxs-lookup"><span data-stu-id="82f1a-108">PINs are given to meeting organizers to allow them to start a meeting.</span></span> <span data-ttu-id="82f1a-109">Toutefois, vous pouvez configurer un code confidentiel n’est pas requis pour démarrer une réunion.</span><span class="sxs-lookup"><span data-stu-id="82f1a-109">However, you can set it up so a PIN isn't required to start a meeting.</span></span>
  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="82f1a-110">Définir si les appelants doivent enregistrer leur nom</span><span class="sxs-lookup"><span data-stu-id="82f1a-110">Set whether callers should record their name</span></span>

1. <span data-ttu-id="82f1a-111">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="82f1a-111">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="82f1a-112">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="82f1a-112">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="82f1a-113">Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **paramètres de pont de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="82f1a-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="82f1a-114">Sous **l’expérience de jointure de la réunion**, consultez la case à cocher intitulée **Activer l’accès à la réunion et de quitter des notifications pour être activée**.</span><span class="sxs-lookup"><span data-stu-id="82f1a-114">Under **Meeting join experience**, see the check box labeled **Enable meeting entry and exit notifications to be turned on**.</span></span>
    
  - <span data-ttu-id="82f1a-115">**Sélectionné** Vous demandera d’appelants pour enregistrer leur nom avant leur entrée à la réunion.</span><span class="sxs-lookup"><span data-stu-id="82f1a-115">**Selected** Callers will be asked to record their name before they enter the meeting.</span></span> <span data-ttu-id="82f1a-116">Cette option est sélectionnée par défaut.</span><span class="sxs-lookup"><span data-stu-id="82f1a-116">This is selected by default.</span></span>
    
  - <span data-ttu-id="82f1a-117">**Désactivée** Les appelants ne seront pas invités à enregistrer leur nom avant leur entrée à la réunion.</span><span class="sxs-lookup"><span data-stu-id="82f1a-117">**Cleared** Callers won't be asked to record their name before they enter the meeting.</span></span>
    
5. <span data-ttu-id="82f1a-118">**Demander aux appelants d'enregistrer leur nom avant de participer à la réunion**: cette option est sélectionnée par défaut. Si vous la désélectionnez, les appelants ne seront pas invités à enregistrer leur nom avant de rejoindre à la réunion.</span><span class="sxs-lookup"><span data-stu-id="82f1a-118">After you make your changes, click **Save**.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="82f1a-119">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="82f1a-119">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="82f1a-120">Pour gagner du temps ou d’automatiser cette action, vous pouvez utiliser l’applet de commande [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) .</span><span class="sxs-lookup"><span data-stu-id="82f1a-120">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
-  <span data-ttu-id="82f1a-121">Windows PowerShell est la gestion des utilisateurs et les utilisateurs sont autorisés à faire.</span><span class="sxs-lookup"><span data-stu-id="82f1a-121">Windows PowerShell is all about managing users and what users are allowed to do.</span></span> <span data-ttu-id="82f1a-122">Avec Windows PowerShell, vous pouvez gérer Office 365 à l’aide d’un unique point d’administration qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer.</span><span class="sxs-lookup"><span data-stu-id="82f1a-122">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="82f1a-123">Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="82f1a-123">To get started with Windows PowerShell, see these topics:</span></span>
    
  - <span data-ttu-id="82f1a-124">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="82f1a-124">[Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)</span></span>
    
  - [<span data-ttu-id="82f1a-125">Six raisons d'utiliser Windows PowerShell pour gérer Office 365 </span><span class="sxs-lookup"><span data-stu-id="82f1a-125">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="82f1a-126">Windows PowerShell offre de nombreux avantages de vitesse, de simplicité et de productivité, plutôt seulement le centre d’administration d’Office 365, par exemple lorsque vous devez apporter des modifications de paramètre pour de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="82f1a-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="82f1a-127">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="82f1a-127">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="82f1a-128">Présentation de Windows PowerShell et de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="82f1a-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="82f1a-129">Utiliser Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="82f1a-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="82f1a-130">Utiliser Windows PowerShell pour les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="82f1a-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="82f1a-p106">Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="82f1a-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="82f1a-133">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="82f1a-133">Related topics</span></span>

[<span data-ttu-id="82f1a-134">Configurer l’audioconférence pour Skype Entreprise et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="82f1a-134">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)

