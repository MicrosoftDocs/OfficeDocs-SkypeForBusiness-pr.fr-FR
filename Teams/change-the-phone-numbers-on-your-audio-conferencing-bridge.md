---
title: Modification des numéros de téléphone dans le pont d’audioconférence
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Découvrez les étapes requises pour affecter un nouveau numéro de téléphone de service à votre pont de conférence afin de développer la couverture pour vos utilisateurs.
ms.openlocfilehash: e2e1aa3d5626f6592f22e0850a8c7419d7549b38
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569186"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a><span data-ttu-id="c7d2a-103">Modifier les numéros de téléphone de votre pont d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="c7d2a-103">Change the phone numbers on your Audio Conferencing bridge</span></span>

<span data-ttu-id="c7d2a-104">Lorsque vous achetez **des licences d’audioconférence,** Microsoft héberge votre pont de conférence audio pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-104">When you buy **Audio Conferencing** licenses, Microsoft is hosting your audio conferencing bridge for your organization.</span></span> <span data-ttu-id="c7d2a-105">Le pont de conférence audio fournit des numéros de téléphone à composer à partir de différents emplacements de sorte que les organisateurs et participants à la réunion peuvent les utiliser pour participer aux réunions Skype Entreprise ou Microsoft Teams à l’aide d’un téléphone.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-105">The audio conferencing bridge gives out dial-in phone numbers from different locations so that meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.</span></span>
  
<span data-ttu-id="c7d2a-106">Outre les numéros de téléphone déjà affectés à votre pont de conférence, vous pouvez obtenir des numéros de [service](/microsoftteams/getting-service-phone-numbers) supplémentaires (numéros gratuits et gratuits utilisés pour l’audioconférence) à partir d’autres emplacements, puis les affecter au pont de conférence afin d’étendre la couverture pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-106">In addition to the phone numbers already assigned to your conferencing bridge, you can [get additional service numbers](/microsoftteams/getting-service-phone-numbers) (toll and toll-free numbers used for audio conferencing) from other locations, and then assign them to the conferencing bridge so you can expand coverage for your users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c7d2a-107">Pour pouvoir affecter/désaffecter un numéro de téléphone pour un pont de conférence, le numéro de téléphone doit être un numéro *de « service*».</span><span class="sxs-lookup"><span data-stu-id="c7d2a-107">To be able to assign/unassign a phone number for a conferencing bridge, the phone number must be a '*service*' number.</span></span> <span data-ttu-id="c7d2a-108">Vous pouvez voir le type de numéro en naviguant vers les numéros de téléphone vocal dans le Centre d’administration Microsoft Teams et en regardant dans la  >   colonne **Type de** numéro.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-108">You can see the type of number it is by navigating to **Voice** > **Phone numbers** in the Microsoft Teams admin center and looking in the **Number Type** column.</span></span> <span data-ttu-id="c7d2a-109">Les crédits de communication Microsoft 365 ou Office 365 doivent d’abord être réglés pour que les utilisateurs peuvent se rendre sur le pont à l’aide d’un numéro gratuit.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-109">Microsoft 365 or Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll-free number.</span></span>

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a><span data-ttu-id="c7d2a-110">Procédure d'affectation d'un nouveau numéro de téléphone de service à votre pont de conférence</span><span class="sxs-lookup"><span data-stu-id="c7d2a-110">Steps when you are assigning a new service phone number to your conference bridge</span></span>

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a><span data-ttu-id="c7d2a-111">Étape 1 : affecter le nouveau numéro de téléphone à votre pont de conférence audio</span><span class="sxs-lookup"><span data-stu-id="c7d2a-111">Step 1 - Assign the new phone number to your audio conferencing bridge</span></span>

<span data-ttu-id="c7d2a-112">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="c7d2a-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="c7d2a-113">Dans le volet de navigation gauche, allez sur **Numéros de**  >  **téléphone vocal.**</span><span class="sxs-lookup"><span data-stu-id="c7d2a-113">On the left navigation pane, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="c7d2a-114">Sélectionnez le numéro de téléphone dans la liste, puis cliquez sur **Modifier.**</span><span class="sxs-lookup"><span data-stu-id="c7d2a-114">Select the phone number from the list, and click **Edit**.</span></span>

3. <span data-ttu-id="c7d2a-115">Dans la page **Modifier,** sous **Affecté à,** développez la page de texte, puis sélectionnez **Appliquer le pont de**  >  **conférence.**</span><span class="sxs-lookup"><span data-stu-id="c7d2a-115">On the **Edit** page, under **Assigned to**, expand the dropdown and then select **Conference bridge** > **Apply**.</span></span>

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a><span data-ttu-id="c7d2a-116">Étape 2 : modifier le numéro de téléphone par défaut de votre pont de conférence (facultatif)</span><span class="sxs-lookup"><span data-stu-id="c7d2a-116">Step 2 - Change the default phone number of your conference bridge (optional)</span></span>

<span data-ttu-id="c7d2a-117">Le numéro de téléphone par défaut de votre pont de conférence définit l’ID d’appelant qui sera utilisé lorsqu’un participant ou l’organisateur d’un appel sortant sera passé à partir d’une réunion.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-117">The default phone number of your conference bridge defines the caller ID that will be used when an outbound call is placed by a participant or the organizer from within a meeting.</span></span>

<span data-ttu-id="c7d2a-118">Seul un numéro de service gratuit peut être réglé comme numéro par défaut pour votre pont de conférence. **des numéros gratuits de service ne peuvent** pas être définir comme numéro par défaut de votre pont de conférence.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-118">Only a service toll number can be set as the default number for your conferencing bridge; **service toll-free numbers can't be set as the default number of your conferencing bridge**.</span></span> <span data-ttu-id="c7d2a-119">Si vous attribuez un numéro de service gratuit et que vous souhaitez le définir comme nouveau numéro par défaut de votre pont de conférence audio, effectuez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="c7d2a-119">If you are assigning a service toll number and you would like to set it as the new default number for your audio conferencing bridge, perform these steps:</span></span>

<span data-ttu-id="c7d2a-120">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="c7d2a-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="c7d2a-121">Dans le volet de navigation gauche, allez sur **ponts de** conférence  >  **Réunions.**</span><span class="sxs-lookup"><span data-stu-id="c7d2a-121">On the left navigation pane, go to **Meetings** > **Conference bridges**.</span></span>

2. <span data-ttu-id="c7d2a-122">Mettez en évidence le numéro de service gratuit que vous souhaitez configurer par défaut.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-122">Highlight the service toll number that you want to configure as the default.</span></span>

3. <span data-ttu-id="c7d2a-123">Sélectionnez **Définir par défaut**.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-123">Select **Set as default**.</span></span>
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a><span data-ttu-id="c7d2a-124">Étape 3 : modifier les numéros de téléphone par défaut inclus dans les invitations aux réunions des utilisateurs (facultatif)</span><span class="sxs-lookup"><span data-stu-id="c7d2a-124">Step 3 - Change the default phone numbers that are included in the meeting invites of users (optional)</span></span>

<span data-ttu-id="c7d2a-125">Les numéros de téléphone par défaut d’un utilisateur sont inclus dans son invitation lorsqu’il planifiera une réunion.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-125">The default phone numbers of a user are the ones that are included on their meeting invites when they schedule a meeting.</span></span> <span data-ttu-id="c7d2a-126">Pour plus d’informations, notamment sur la manière dont les numéros de téléphone par défaut sont attribués aux nouveaux [utilisateurs,](set-the-phone-numbers-included-on-invites-in-teams.md) consultez Définir les numéros de téléphone inclus dans les invitations dans Microsoft Teams ou définir les numéros de téléphone inclus dans les [invitations dans Skype Entreprise Online.](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)</span><span class="sxs-lookup"><span data-stu-id="c7d2a-126">For more information, including how the default phone numbers are assigned for new users, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

<span data-ttu-id="c7d2a-127">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="c7d2a-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="c7d2a-128">Dans le volet de navigation  gauche, cliquez sur Le nom d’affichage de l’utilisateur souhaité dans la liste.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-128">On the left navigation pane, go to **Users** and click the Display name of the desired user on the list.</span></span>

2. <span data-ttu-id="c7d2a-129">En plus de **l’audioconférence,** cliquez sur **Modifier.**</span><span class="sxs-lookup"><span data-stu-id="c7d2a-129">Next to **Audio conferencing**, click on **Edit**.</span></span>

3. <span data-ttu-id="c7d2a-130">Sous **Numéro gratuit** ou Numéro **gratuit,** sélectionnez le numéro dans la dropdown et cliquez sur **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="c7d2a-130">Under **Toll number** or **Toll-free number**, select the number from the dropdown and click **Apply**.</span></span>

<span data-ttu-id="c7d2a-131">Une fois les modifications appliquées, les nouveaux numéros de téléphone par défaut seront inclus dans les invitations aux réunions des organisateurs lors de leur prochaine planification.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-131">After the changes have been applied, the new default phone numbers will be included on the meeting invites of organizers the next time they schedule a new meeting.</span></span>

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a><span data-ttu-id="c7d2a-132">Étape 4 : mettre à jour les invitations aux réunions existantes des utilisateurs à l’aide du service Meeting Migration Service (facultatif)</span><span class="sxs-lookup"><span data-stu-id="c7d2a-132">Step 4 - Update existing meeting invites of users using the Meeting Migration Service (optional)</span></span>

<span data-ttu-id="c7d2a-133">Pour les deux étapes suivantes, vous devrez commencer à Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-133">For the next two steps, you will need to start Windows PowerShell.</span></span>
  
<span data-ttu-id="c7d2a-134">Si vous avez mis à jour les numéros de téléphone par défaut inclus dans les invitations à des réunions pour certains ou l’ensemble de vos utilisateurs, vous pouvez éventuellement mettre à jour les invitations aux réunions envoyées aux utilisateurs de votre organisation avant la modification de leurs numéros de téléphone par défaut à l’aide du service Meeting Migration Service .)</span><span class="sxs-lookup"><span data-stu-id="c7d2a-134">If you updated the default phone numbers that are included in the meeting invites for some or all of your users, you can optionally update meeting invites that were already sent to users in your organization before their default phone numbers were changed using the Meeting Migration Service.</span></span> <span data-ttu-id="c7d2a-135">Pour plus d'informations, reportez-vous à la rubrique [Configuration de Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="c7d2a-135">For additional information, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
- <span data-ttu-id="c7d2a-136">Exécutez meeting Migration Service (MMS) pour les utilisateurs dont le numéro de téléphone par défaut a été modifié à l’étape 2.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-136">Run the Meeting Migration Service (MMS) for the users who had their default phone numbers changed in Step 2.</span></span> <span data-ttu-id="c7d2a-137">Pour cela, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c7d2a-137">To do this, run the following command:</span></span>

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- <span data-ttu-id="c7d2a-138">Vous pouvez également afficher le statut de migration des réunions.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-138">You can also view the meeting migration status.</span></span> <span data-ttu-id="c7d2a-139">Toutes les réunions seront replanifiées lorsque plus aucune opération ne sera définie sur  *En attente*  ou *En cours*  .</span><span class="sxs-lookup"><span data-stu-id="c7d2a-139">All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a><span data-ttu-id="c7d2a-140">Procédure d'annulation d'affectation d'un numéro de téléphone de service dans votre pont de conférence</span><span class="sxs-lookup"><span data-stu-id="c7d2a-140">Steps when you are unassigning a service phone number for a conferencing bridge</span></span>


<span data-ttu-id="c7d2a-141">Lorsque vous annulez l'affectation d'un numéro de téléphone dans votre pont de conférence, les utilisateurs ne peuvent plus rejoindre aucune réunion à l'aide de ce numéro.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-141">When you unassign a phone number from a conferencing bridge, users won't be able to join any meetings using that phone number anymore.</span></span> <span data-ttu-id="c7d2a-142">Dans la mesure où le numéro de téléphone change, il est important de mettre à jour tous les utilisateurs qui pourraient avoir un numéro de téléphone comme numéro par défaut (le cas où ils en ont un) et de mettre à jour leurs invitations aux réunions existantes avant que le numéro ne soit non suspendu dans le pont de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-142">Because the phone number is changing, it's important to update all users who could have a phone number as their default number (if any) and to update their existing meeting invites before the phone number is unassigned from the audio conferencing bridge.</span></span>

<span data-ttu-id="c7d2a-143">Si le numéro de téléphone est supprimé sans mettre à jour les utilisateurs et leurs réunions, leurs invitations aux réunions existantes peuvent contenir un numéro de téléphone qui ne leur permet pas de rejoindre les réunions.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-143">If the phone number is removed without updating the users and their meetings, their existing meeting invites could contain a phone number that won't work for joining their meetings.</span></span>

<span data-ttu-id="c7d2a-144">Dans le cas de ces trois premières étapes, vous devrez démarrer Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-144">For the first three steps, you will need to start Windows PowerShell.</span></span> <span data-ttu-id="c7d2a-145">Pour consulter l’aide à ce sujet, cliquez sur [Vous souhaitez savoir comment gérer avec Windows PowerShell ?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="c7d2a-145">To see how to do this, click [Want to know how to manage with Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)</span></span>

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a><span data-ttu-id="c7d2a-146">Étape 1 : mettre à jour les utilisateurs dont l’utilisation du numéro de téléphone comme numéro par défaut doit être non celle des numéros par défaut</span><span class="sxs-lookup"><span data-stu-id="c7d2a-146">Step 1 - Update users who have the phone number to be unassigned as one of their default numbers</span></span>

<span data-ttu-id="c7d2a-147">Remplacez le numéro gratuit ou gratuit par défaut pour tous les utilisateurs dont l’utilisation du numéro de téléphone comme numéro par défaut doit être non prévue et lancez le processus de nouvelle planification de leurs réunions.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-147">Replace the default toll or toll-free number for all users who have the number to be unassigned as a default number and start the process of rescheduling their meetings.</span></span> <span data-ttu-id="c7d2a-148">Pour cela, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c7d2a-148">To do this, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 ><span data-ttu-id="c7d2a-149">Vous pouvez également modifier le nombre d’utilisateurs par défaut (gratuit ou gratuit) dans le Centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-149">You can also change the default toll or toll-free number of users in the Microsoft Teams admin center.</span></span> <span data-ttu-id="c7d2a-150">Toutefois, cela ne replanifiera pas leurs réunions de manière automatique.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-150">However, this won't automatically reschedule their meetings.</span></span> 
 
 <span data-ttu-id="c7d2a-151">Pour plus d’informations, consultez Définir les numéros de téléphone inclus dans les [invitations dans Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) ou définir les numéros de téléphone inclus dans les [invitations dans Skype Entreprise Online.](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)</span><span class="sxs-lookup"><span data-stu-id="c7d2a-151">For additional information, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

  > [!NOTE]
  > <span data-ttu-id="c7d2a-152">En fonction de la taille de votre organisation, cette opération peut prendre un certain temps.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-152">Depending on the size of your organization, this could take some time to complete.</span></span>

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a><span data-ttu-id="c7d2a-153">Étape 2 : Affichage du statut de migration des réunions à l'aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c7d2a-153">Step 2 - View meeting migration status using Windows PowerShell</span></span>

<span data-ttu-id="c7d2a-154">Toutes les réunions seront reprogrammées dès qu’aucune opération n’est en attente ou en cours *d’état.* </span><span class="sxs-lookup"><span data-stu-id="c7d2a-154">All meetings will be rescheduled once there are no operations in *Pending* or *In-Progress* state.</span></span>

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="c7d2a-155">Pour plus d'informations sur le service Meeting Migration Service (MMS), reportez-vous à la rubrique [Configuration de Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="c7d2a-155">For more information about the Meeting Migration Service, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a><span data-ttu-id="c7d2a-156">Étape 3 : désaffecter l’ancien numéro de téléphone du pont de conférence audio</span><span class="sxs-lookup"><span data-stu-id="c7d2a-156">Step 3 - Unassign the old phone number from the audio conferencing bridge</span></span>

<span data-ttu-id="c7d2a-157">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="c7d2a-157">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="c7d2a-158">Dans le groupe de navigation de gauche, allez **sur Numéros** de  >  **téléphone vocal.**</span><span class="sxs-lookup"><span data-stu-id="c7d2a-158">In the left navigation, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="c7d2a-159">Si le numéro de téléphone est un numéro gratuit, sélectionnez-le dans la liste, puis cliquez sur **Publication.**</span><span class="sxs-lookup"><span data-stu-id="c7d2a-159">If the phone number is a toll-free number, select the phone number from the list, and click **Release**.</span></span> <span data-ttu-id="c7d2a-160">Si le numéro de téléphone est un numéro gratuit, contactez le [support Technique Microsoft](https://go.microsoft.com/fwlink/?linkid=2091806) pour que l’on ne l’utilise pas.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-160">If the phone number is a toll number, please contact [Microsoft support](https://go.microsoft.com/fwlink/?linkid=2091806) to have the phone number unassigned.</span></span>

3. <span data-ttu-id="c7d2a-161">Si le numéro de téléphone est un numéro gratuit, cliquez sur **Oui** dans la fenêtre de confirmation.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-161">If the phone number is a toll-free number, click **Yes** in the confirmation window.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="c7d2a-162">Une fois le numéro de téléphone non signé dans un pont de conférence audio, il ne sera plus disponible pour les utilisateurs qui participent à des réunions nouvelles ou existantes.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-162">After a phone number is unassigned from an audio conferencing bridge, the phone number will no longer be available for users to join new or existing meetings.</span></span>

### <a name="save-time-and-automate"></a><span data-ttu-id="c7d2a-163">Gagner du temps et automatiser</span><span class="sxs-lookup"><span data-stu-id="c7d2a-163">Save time and automate</span></span>

<span data-ttu-id="c7d2a-164">Pour gagner du temps en automatisant ce processus, vous pouvez utiliser les [cmdlets Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) ou **Set-CsOnlineDialInConferencingUserDefaultNumber.**</span><span class="sxs-lookup"><span data-stu-id="c7d2a-164">To save time by automating this process, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) or the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlets.</span></span>

- <span data-ttu-id="c7d2a-165">Utilisez l'applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) pour modifier le numéro payant ou gratuit par défaut pour des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-165">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>

  - <span data-ttu-id="c7d2a-166">Pour modifier le numéro gratuit par défaut pour un utilisateur, exécutez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="c7d2a-166">To change the default toll-free number for a user, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- <span data-ttu-id="c7d2a-167">Utilisez l'applet de commande **Set-CsOnlineDialInConferencingUserDefaultNumber** pour modifier le numéro gratuit ou payant par défaut des utilisateurs en fonction de leur numéro par défaut d'origine ou de leur emplacement.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-167">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c7d2a-168">Pour trouver le BridgeID, utilisez **Get-CsOnlineDialInConferencingBridge.**</span><span class="sxs-lookup"><span data-stu-id="c7d2a-168">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>

  - <span data-ttu-id="c7d2a-169">Pour définir le numéro gratuit par défaut pour tous les utilisateurs qui n'en ont pas sur 8005551234, exécutez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="c7d2a-169">To set the default toll-free number for all users without one to 8005551234, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="c7d2a-170">Pour remplacer le numéro gratuit par défaut 8005551234 pour tous les utilisateurs qui l'utilisent par 8005551239 et replanifier leurs réunions de manière automatique, exécutez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="c7d2a-170">To change the default toll-free number of all users that have 8005551234 as their default toll-free number to 8005551239 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - <span data-ttu-id="c7d2a-171">Pour définir le numéro gratuit par défaut de tous les utilisateurs situés aux États-Unis sur 8005551234 et replanifier leurs réunions de manière automatique, exécutez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="c7d2a-171">To set the default toll-free number of all users located in the U.S. to 8005551234 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > <span data-ttu-id="c7d2a-172">L’emplacement utilisé ci-dessus doit correspondre aux informations de contact du ou des utilisateurs définies dans le Centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-172">The location that is used above needs to match the contact information of user(s) that is set in the Microsoft 365 admin center.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="c7d2a-173">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="c7d2a-173">Troubleshooting</span></span>

<span data-ttu-id="c7d2a-174">**Le bouton d’affectation n’est pas disponible**</span><span class="sxs-lookup"><span data-stu-id="c7d2a-174">**Unassign button isn't available**</span></span>

<span data-ttu-id="c7d2a-175">Vous souhaitez désaffecter un numéro mais le bouton n’est pas disponible. Si vous pointez dessus, vous êtes redirigé pour contacter le support technique avec le message suivant : « Les numéros par défaut ou partagés ne peuvent pas être désaffectés du _pont. Pour désaffecter des numéros de téléphone toll dédiés, contactez le support technique._«</span><span class="sxs-lookup"><span data-stu-id="c7d2a-175">You want to Unassign a number but the button isn't available, and if while hovering over it, you are redirected to contact Support with the following message _"Default or shared numbers can´t be unassigned from the bridge. To unassign dedicated toll numbers, please contact support._".</span></span>

<span data-ttu-id="c7d2a-176">Pour obtenir des informations supplémentaires sur le ou les ponts, exécutez la powershell suivante :</span><span class="sxs-lookup"><span data-stu-id="c7d2a-176">To obtain more information about the bridge(s), run the following Powershell :</span></span>
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

<span data-ttu-id="c7d2a-177">Le résultat, à côté d’autres informations telles que Identity, Name et Region, doit également contenir DefaultServiceNumber.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-177">The result, aside other information like Identity, Name and Region, should also contain the DefaultServiceNumber.</span></span>

<span data-ttu-id="c7d2a-178">**Exemple**, pour désaffecter, DefaultServiceNumber « 8005551234 »</span><span class="sxs-lookup"><span data-stu-id="c7d2a-178">**Example**, to unassign, the DefaultServiceNumber "8005551234"</span></span>
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a><span data-ttu-id="c7d2a-179">À propos de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c7d2a-179">About Windows PowerShell</span></span>

<span data-ttu-id="c7d2a-180">Avec Windows PowerShell, vous pouvez gérer les utilisateurs et leurs autorisations.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-180">With Windows PowerShell you can manage users and what they are or are not allowed to do.</span></span> <span data-ttu-id="c7d2a-181">Windows PowerShell peut vous aider à gérer Microsoft 365 ou Office 365 et Skype Entreprise Online à l’aide d’un seul point d’administration qui peut simplifier votre travail quotidien, en particulier si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-181">Windows PowerShell  can help you manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, especially when you've got multiple tasks to do.</span></span> <span data-ttu-id="c7d2a-182">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="c7d2a-182">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="c7d2a-183">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="c7d2a-183">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="c7d2a-184">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="c7d2a-184">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

<span data-ttu-id="c7d2a-185">Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d’utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-185">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="c7d2a-186">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="c7d2a-186">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="c7d2a-187">Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c7d2a-187">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="c7d2a-188">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="c7d2a-188">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="c7d2a-189">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="c7d2a-189">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="c7d2a-190">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c7d2a-190">Related topics</span></span>
[<span data-ttu-id="c7d2a-191">Modifier les paramètres d’un pont d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="c7d2a-191">Change the settings for an Audio Conferencing bridge</span></span>](change-the-settings-for-an-audio-conferencing-bridge.md)
