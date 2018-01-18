---
title: "Modifier les paramètres d’un pont de conférence de données Audio"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
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
description: "Obtenir les étapes que vous devez modifier les paramètres d’un pont de conférences à distance de Microsoft qui permet aux appelants de demander et de recueillir des broches pour les organisateurs de la réunion et noms lorsqu’ils utilisent pas Skype pour les clients de l’entreprise. "
ms.openlocfilehash: 5da33e083999f00d217a86455f61fd58ca2d1713
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="1e90d-103">Modifier les paramètres d’un pont de conférence de données Audio</span><span class="sxs-lookup"><span data-stu-id="1e90d-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="1e90d-104">Lorsque vous configurez une conférence Audio dans Office 365, vous recevrez des numéros de téléphone pour vos utilisateurs à partir de ce que l'on appelle un pont de téléconférence audio.</span><span class="sxs-lookup"><span data-stu-id="1e90d-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="1e90d-105">Un pont de conférence peut contenir un ou plusieurs numéros de téléphone.</span><span class="sxs-lookup"><span data-stu-id="1e90d-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="1e90d-106">Ces numéros de téléphone sont utilisés lorsque les appelants de se connectent à une réunion.</span><span class="sxs-lookup"><span data-stu-id="1e90d-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="1e90d-107">Le numéro de téléphone est inclus au bas de la Skype pour l’invitation à une réunion commerciale ou Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1e90d-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="1e90d-108">Le pont de conférence répond à un appel et vous demande de l’appelant avec des invites vocales à l’aide d’un fichier auto réunion standard, puis, selon vos paramètres, peut lire les notifications, demandez les appelants pour enregistrer leur nom et contrôler les paramètres de code PIN.</span><span class="sxs-lookup"><span data-stu-id="1e90d-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="1e90d-109">Broches sont indiquées pour les organisateurs de la réunion pour pouvoir démarrer une réunion lorsqu’ils sont ne sont pas à l’aide un Skype pour application métier ou Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1e90d-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

    > [!IMPORTANT]
    > A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting. If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting. 
  
## <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="1e90d-110">Modifier les paramètres d’un pont de conférence audio</span><span class="sxs-lookup"><span data-stu-id="1e90d-110">Change the settings for an audio conferencing bridge</span></span>

 <span data-ttu-id="1e90d-111">**Configurer l’expérience de réunion lorsque les appelants de joindre une réunion**</span><span class="sxs-lookup"><span data-stu-id="1e90d-111">**Set up the meeting experience when callers join a meeting**</span></span>
  
1. <span data-ttu-id="1e90d-112">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="1e90d-112">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="1e90d-113">Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="1e90d-113">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="1e90d-114">Dans le **Skype pour le centre d’administration commerciale**, dans la navigation gauche atteindre **audioconférence** > **paramètres de pont de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="1e90d-114">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="1e90d-115">Dans la page **paramètres du pont Microsoft** , sous **rencontrer de jointure de la réunion**, sélectionnez :</span><span class="sxs-lookup"><span data-stu-id="1e90d-115">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
  - <span data-ttu-id="1e90d-116">**Activer l’accès à la réunion et de quitter des notifications pour être activé** Cette option est sélectionnée par défaut.</span><span class="sxs-lookup"><span data-stu-id="1e90d-116">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="1e90d-117">Si vous désactivez la case à cocher, les utilisateurs qui ont déjà joint la réunion ne serez pas avertis lorsque quelqu'un entre ou quitte la réunion.</span><span class="sxs-lookup"><span data-stu-id="1e90d-117">If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="1e90d-118">Lorsque vous sélectionnez **Activer l’accès à la réunion et de quitter des notifications pour être activé**, vous pouvez sélectionner ces options dans la liste **type d’annonce d’entrée et de sortie** :</span><span class="sxs-lookup"><span data-stu-id="1e90d-118">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
  - <span data-ttu-id="1e90d-119">**Les noms ou les numéros de téléphone** Lorsque les utilisateurs se connecter à une réunion, son numéro de téléphone sera lu lorsqu’ils joignent l’il.</span><span class="sxs-lookup"><span data-stu-id="1e90d-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
  - <span data-ttu-id="1e90d-120">**Tonalités** Lorsque les utilisateurs se connecter à une réunion, un signal audio est lu lorsqu’ils joignent l’il.</span><span class="sxs-lookup"><span data-stu-id="1e90d-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1e90d-121">À l’aide de la **tonalité** comme type d’annonce est actuellement disponible à tous les clients sous la forme d’une fonction d’aperçu.</span><span class="sxs-lookup"><span data-stu-id="1e90d-121">Using **Tone** as the announcement type is currently available to all customers as a preview feature.</span></span>
  
  - <span data-ttu-id="1e90d-122">**Appelants de demander d’enregistrer leur nom avant de rejoindre la réunion** Cette option est sélectionnée par défaut.</span><span class="sxs-lookup"><span data-stu-id="1e90d-122">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="1e90d-123">Si vous désactivez la case à cocher, les appelants ne vous demandera d’enregistrer leur nom avant de participer à une réunion.</span><span class="sxs-lookup"><span data-stu-id="1e90d-123">If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="1e90d-124">**Demander aux appelants d'enregistrer leur nom avant de participer à la réunion**: cette option est sélectionnée par défaut. Si vous la désélectionnez, les appelants ne seront pas invités à enregistrer leur nom avant de rejoindre à la réunion.</span><span class="sxs-lookup"><span data-stu-id="1e90d-124">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="1e90d-125">Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="1e90d-125">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="1e90d-126">Définition de la longueur du code confidentiel pour les réunions</span><span class="sxs-lookup"><span data-stu-id="1e90d-126">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="1e90d-127">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="1e90d-127">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="1e90d-128">Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **paramètres de pont de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="1e90d-128">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="1e90d-129">Dans la page **paramètres du pont Microsoft** , sous **sécurité**, entrez le nombre de chiffres que vous souhaitez pour le code confidentiel dans la liste **longueur du code confidentiel** , puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1e90d-129">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1e90d-130">Le code confidentiel doit comporter entre 4 et 12 chiffres.</span><span class="sxs-lookup"><span data-stu-id="1e90d-130">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="1e90d-131">**Indiquez si vous souhaitez envoyer un courrier électronique à vos utilisateurs**</span><span class="sxs-lookup"><span data-stu-id="1e90d-131">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="1e90d-132">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="1e90d-132">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="1e90d-133">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="1e90d-133">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="1e90d-134">Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **paramètres de pont de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="1e90d-134">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="1e90d-135">Dans la page **paramètres du pont Microsoft** , sélectionnez ou désactivez **Envoyer automatiquement des e-mails aux utilisateurs si leur configuration d’audioconférence change**, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1e90d-135">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their audio conferencing configuration changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="1e90d-136">Pour plus d’informations, reportez-vous à la section [E-mails envoyés automatiquement aux utilisateurs lors de la modifient de leurs paramètres d’audioconférence](emails-sent-to-users-when-their-settings-change.md) .</span><span class="sxs-lookup"><span data-stu-id="1e90d-136">See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="1e90d-137">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="1e90d-137">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="1e90d-138">Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l’applet de commande [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) .</span><span class="sxs-lookup"><span data-stu-id="1e90d-138">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet.</span></span>
    
- <span data-ttu-id="1e90d-139">Windows PowerShell est la gestion des utilisateurs et les utilisateurs qui sont autorisés ou non à faire.</span><span class="sxs-lookup"><span data-stu-id="1e90d-139">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="1e90d-140">Avec Windows PowerShell, vous pouvez gérer Office 365 à l’aide d’un unique point d’administration qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer.</span><span class="sxs-lookup"><span data-stu-id="1e90d-140">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="1e90d-141">Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="1e90d-141">To get started with Windows PowerShell, see these topics:</span></span>
    
  - <span data-ttu-id="1e90d-142">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="1e90d-142">[Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)</span></span>
    
  - [<span data-ttu-id="1e90d-143">Six raisons d'utiliser Windows PowerShell pour gérer Office 365 </span><span class="sxs-lookup"><span data-stu-id="1e90d-143">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="1e90d-144">Windows PowerShell offre de nombreux avantages de vitesse, de simplicité et de productivité, plutôt seulement le centre d’administration d’Office 365, par exemple lorsque vous devez apporter des modifications de paramètre pour de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="1e90d-144">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="1e90d-145">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="1e90d-145">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="1e90d-146">Présentation de Windows PowerShell et de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="1e90d-146">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="1e90d-147">Utiliser Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="1e90d-147">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="1e90d-148">Utiliser Windows PowerShell pour les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="1e90d-148">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="1e90d-p107">Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="1e90d-p107">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="1e90d-151">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="1e90d-151">Related topics</span></span>

[<span data-ttu-id="1e90d-152">Configurer l’audioconférence pour Skype Entreprise et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1e90d-152">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)

