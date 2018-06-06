---
title: Modifier les numéros de téléphone sur le pont de conférence Audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Lorsque vous achetez des licences de services d’audioconférence, Microsoft héberge votre pont de conférence audio pour votre organisation. Le pont de conférence audio donne les numéros de téléphone à partir de différents emplacements si bien que les organisateurs de réunion et les participants peuvent les utiliser pour joindre Skype pour les réunions Microsoft Teams ou de l’entreprise à l’aide d’un téléphone.
ms.openlocfilehash: 0eceff97470bf6c0df6b0818734955ebf71d0f76
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568362"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a><span data-ttu-id="00a8a-104">Modifier les numéros de téléphone sur le pont de conférence Audio</span><span class="sxs-lookup"><span data-stu-id="00a8a-104">Change the phone numbers on your Audio Conferencing bridge</span></span>

<span data-ttu-id="00a8a-105">Lorsque vous achetez des licences de **Services d’audioconférence** , Microsoft héberge votre *pont de conférence audio* pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="00a8a-105">When you buy **Audio Conferencing** licenses, Microsoft is hosting your *audio conferencing bridge*  for your organization.</span></span> <span data-ttu-id="00a8a-106">Le pont de conférence audio donne les numéros de téléphone à partir de différents emplacements si bien que les organisateurs de réunion et les participants peuvent les utiliser pour joindre Skype pour les réunions Microsoft Teams ou de l’entreprise à l’aide d’un téléphone.</span><span class="sxs-lookup"><span data-stu-id="00a8a-106">The audio conferencing bridge gives out dial-in phone numbers from different locations so meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.</span></span>
  
<span data-ttu-id="00a8a-107">Outre les numéros de téléphone déjà affectés à votre pont de conférence, vous pouvez [obtenir les numéros de service supplémentaires](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md) (payants et gratuits utilisés pour la conférence audio) issus d’autres emplacements et le puis attribuer à la conférence un pont afin de pouvoir Développez la couverture pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="00a8a-107">In addition to the phone numbers already assigned to your conferencing bridge, you can [get additional service numbers](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md) (toll and toll-free numbers used for audio conferencing) from other locations and then assign them to the conferencing bridge so you can expand coverage for your users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="00a8a-108">Pour pouvoir affecter/annuler l’affectation d’un numéro de téléphone pour un pont de conférence, le numéro de téléphone doit être un nombre de «*service*».</span><span class="sxs-lookup"><span data-stu-id="00a8a-108">To be able to assign/unassign a phone number for a conferencing bridge, the phone number must be a '*service*' number.</span></span> <span data-ttu-id="00a8a-109">Vous pouvez voir le type de numéro en accédant à **voix** > de**numéros de téléphone** et de recherche dans la colonne **Type de numéro** .</span><span class="sxs-lookup"><span data-stu-id="00a8a-109">You can see the type of number it is by navigating to **Voice** > **Phone numbers** and looking in the **Number Type** column.</span></span> <span data-ttu-id="00a8a-110">Office 365 Communications crédits doit être définies en premier pour que les utilisateurs composer le numéro gratuit bridge.</span><span class="sxs-lookup"><span data-stu-id="00a8a-110">Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll free number.</span></span> 
  
## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a><span data-ttu-id="00a8a-111">Procédure d'affectation d'un nouveau numéro de téléphone de service à votre pont de conférence</span><span class="sxs-lookup"><span data-stu-id="00a8a-111">Steps when you are assigning a new service phone number to your conference bridge</span></span>

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a><span data-ttu-id="00a8a-112">Étape 1 : attribuer le numéro de téléphone à votre pont de conférence audio</span><span class="sxs-lookup"><span data-stu-id="00a8a-112">Step 1 - Assign the new phone number to your audio conferencing bridge</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

1. <span data-ttu-id="00a8a-113">Connectez-vous à Office 365 à l'aide de votre compte professionnel.</span><span class="sxs-lookup"><span data-stu-id="00a8a-113">Sign in to Office 365 with your work account.</span></span>
    
2. <span data-ttu-id="00a8a-114">Accéder au **Centre d’administration Office 365** > **Admin centres** > **Skype pour les entreprises** > **vocale** > **numéros de téléphone**.</span><span class="sxs-lookup"><span data-stu-id="00a8a-114">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Voice** > **Phone numbers**.</span></span>
    
3. <span data-ttu-id="00a8a-115">Sélectionnez le numéro de téléphone dans la liste, puis dans le volet Actions, cliquez sur **affecter**.</span><span class="sxs-lookup"><span data-stu-id="00a8a-115">Select the phone number from the list, and in the Action pane, click **Assign**.</span></span>
    
4. <span data-ttu-id="00a8a-116">Sur la page **Affecter**, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="00a8a-116">On the **Assign** page, click **Save**.</span></span>
    
    <span data-ttu-id="00a8a-117">Uniquement un numéro de service peut être défini en tant que le numéro par défaut pour votre pont de conférence ; **numéros gratuits service ne peut pas être définis en tant que le numéro par défaut de votre pont de conférence**.</span><span class="sxs-lookup"><span data-stu-id="00a8a-117">Only a service toll number can be set as the default number for your conferencing bridge; **service toll-free numbers can't be set as the default number of your conferencing bridge**.</span></span> <span data-ttu-id="00a8a-118">Si vous affectez un numéro de service et que vous souhaitez définir en tant que le nouveau numéro par défaut pour votre pont de conférence audio, sélectionnez **utiliser ce numéro par défaut**.</span><span class="sxs-lookup"><span data-stu-id="00a8a-118">If you are assigning a service toll number and you would like to set it as the new default number for your audio conferencing bridge, select **Use this number as the default**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="00a8a-119">Après avoir affecté un nouveau numéro de téléphone, même si le numéro est devenu le nouveau numéro par défaut, le numéro par défaut pour les utilisateurs existants ne changera pas.</span><span class="sxs-lookup"><span data-stu-id="00a8a-119">After a new phone number has been assigned, even if the number became the new default number, the default number for existing users won't change.</span></span> <span data-ttu-id="00a8a-120">Pour définir le numéro par défaut ou un numéro gratuit qui est ajouté à l’invite de réunion un organisateur, voir [l’invite inclus sur les numéros de téléphone](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="00a8a-120">To set the default toll or a toll-free number that is added to an organizer's meeting invites, see [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span> 
  


### <a name="step-2---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a><span data-ttu-id="00a8a-121">Étape 2 : Modification des numéros de téléphone par défaut inclus dans les invitations aux réunions (facultatif)</span><span class="sxs-lookup"><span data-stu-id="00a8a-121">Step 2 - Change the default phone numbers that are included in the meeting invites of users (optional)</span></span>

<span data-ttu-id="00a8a-122">Les numéros de téléphone par défaut pour les utilisateurs sont inclus dans leur invitation lorsqu'ils planifient une réunion.</span><span class="sxs-lookup"><span data-stu-id="00a8a-122">The default phone numbers for user are the ones that are included on their meeting invites when they schedule a meeting.</span></span> <span data-ttu-id="00a8a-123">Pour plus d’informations, voir [l’invite inclus sur les numéros de téléphone](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="00a8a-123">For more information, see [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
1. <span data-ttu-id="00a8a-124">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="00a8a-124">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="00a8a-125">Accéder au **Centre d’administration Office 365** > **Admin centres** > **Skype pour les entreprises** > **audioconférence** > **utilisateurs** et sélectionnez les utilisateurs dans la liste.</span><span class="sxs-lookup"><span data-stu-id="00a8a-125">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Audio conferencing** > **Users** and select the users in the list.</span></span>
    
3. <span data-ttu-id="00a8a-126">Cliquez sur **Modifier** dans le volet Action.</span><span class="sxs-lookup"><span data-stu-id="00a8a-126">Click **Edit** in the action pane.</span></span>
    
4. <span data-ttu-id="00a8a-127">Sous **numéro de téléphone payant par défaut** ou **par défaut numéro gratuit**, sélectionnez le numéro dans la liste, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="00a8a-127">Under **Default toll number** or **Default toll-free number**, select the number in the list and click **Save**.</span></span>
    
<span data-ttu-id="00a8a-128">Une fois que les modifications ont été enregistrées, l’autre numéro de téléphone par défaut numéros doivent être incluses dans la réunion invite des organisateurs la prochaine fois qu’il planifie une nouvelle réunion.</span><span class="sxs-lookup"><span data-stu-id="00a8a-128">After the changes have been saved, the new default phone numbers will be included on the meeting invites of organizers the next time they schedule a new meeting.</span></span>
  
### <a name="step-3---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a><span data-ttu-id="00a8a-129">Étape 3 : Mise à jour des invitations aux réunions des utilisateurs à l'aide du service Meeting Migration Service (MMS) (facultatif)</span><span class="sxs-lookup"><span data-stu-id="00a8a-129">Step 3 - Update existing meeting invites of users using the Meeting Migration Service (optional)</span></span>

<span data-ttu-id="00a8a-130">Pour les deux étapes suivantes, vous devrez démarrer de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="00a8a-130">For the next two steps, you will need to start Windows PowerShell.</span></span>
  
<span data-ttu-id="00a8a-131">À l’aide du Service de Migration de réunion, vous pouvez éventuellement mettre à jour des invitations de réunion qui ont déjà été envoyées aux utilisateurs de votre organisation avant que leurs numéros de téléphone par défaut ont été modifiées.</span><span class="sxs-lookup"><span data-stu-id="00a8a-131">Using the Meeting Migration Service, you can optionally update meeting invites that were already sent to users in your organization before their default phone numbers were changed.</span></span> <span data-ttu-id="00a8a-132">Pour plus d'informations, reportez-vous à la rubrique [Configuration de Meeting Migration Service (MMS)](setting-up-the-meeting-migration-service-mms.md).</span><span class="sxs-lookup"><span data-stu-id="00a8a-132">For additional information, see [Setting up the Meeting Migration Service (MMS)](setting-up-the-meeting-migration-service-mms.md).</span></span>
  
- <span data-ttu-id="00a8a-133">Exécutez le Service de Migration de réunion (MMS) pour les utilisateurs qui avaient leurs numéros de téléphone par défaut modifié à l’étape 2.</span><span class="sxs-lookup"><span data-stu-id="00a8a-133">Run the Meeting Migration Service (MMS) for the users who had their default phone numbers changed in Step 2.</span></span> <span data-ttu-id="00a8a-134">Pour cela, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="00a8a-134">To do this, run the following command:</span></span>
    
```
    Start-CsExMeetingMigration user@contoso.com
```

- <span data-ttu-id="00a8a-p109">Vous pouvez également afficher le statut de migration des réunions. Toutes les réunions seront replanifiées lorsque plus aucune opération ne sera définie sur  *En attente*  ou *En cours*  .</span><span class="sxs-lookup"><span data-stu-id="00a8a-p109">You can also view the meeting migration status. All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>
    
```
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a><span data-ttu-id="00a8a-137">Procédure d'annulation d'affectation d'un numéro de téléphone de service dans votre pont de conférence</span><span class="sxs-lookup"><span data-stu-id="00a8a-137">Steps when you are unassigning a service phone number for a conferencing bridge</span></span>


<span data-ttu-id="00a8a-138">Lorsque vous annulez l'affectation d'un numéro de téléphone dans votre pont de conférence, les utilisateurs ne peuvent plus rejoindre aucune réunion à l'aide de ce numéro.</span><span class="sxs-lookup"><span data-stu-id="00a8a-138">When you unassign a phone number from a conferencing bridge, users won't be able to join any meetings using that phone number anymore.</span></span> <span data-ttu-id="00a8a-139">Étant donné que le numéro de téléphone est modifié, il est important pour mettre à jour tous les utilisateurs qui peuvent avoir un numéro de téléphone comme leur numéro par défaut (le cas échéant) et mettre à jour les invitations aux réunions avant le numéro de téléphone non attribué dans le pont de conférence audio existant.</span><span class="sxs-lookup"><span data-stu-id="00a8a-139">Because the phone number is changing, it's important to update all users that could have a phone number as their default number (if any) and to update their existing meeting invites before the phone number is unassigned from the audio conferencing bridge.</span></span> 
  
<span data-ttu-id="00a8a-140">Si le numéro de téléphone est supprimé sans ces mises à jour, leurs invitations risquent de contenir un numéro qui ne leur permettra plus de rejoindre les réunions..</span><span class="sxs-lookup"><span data-stu-id="00a8a-140">If the phone number is removed without updating the users and their meetings, their existing meeting invites could contain a phone number that won't work for joining their meetings anymore.</span></span>
  
<span data-ttu-id="00a8a-141">Dans le cas de ces trois premières étapes, vous devrez démarrer Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="00a8a-141">For the first three steps, you will need to start Windows PowerShell.</span></span> <span data-ttu-id="00a8a-142">Pour voir comment faire pour ce faire, cliquez sur [pour en savoir comment gérer avec Windows PowerShell ?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span><span class="sxs-lookup"><span data-stu-id="00a8a-142">To see how to do this, click [Want to know how to manage with Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span></span>
  
### <a name="step-1---update-users-that-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a><span data-ttu-id="00a8a-143">Étape 1 : Mise à jour des utilisateurs dont l'affectation de numéro de téléphone comme numéro par défaut doit être annulée</span><span class="sxs-lookup"><span data-stu-id="00a8a-143">Step 1 - Update users that have the phone number to be unassigned as one of their default numbers</span></span>

<span data-ttu-id="00a8a-p112">Remplacez le numéro payant ou gratuit par défaut de tous les utilisateurs dont l'affectation de numéro de téléphone comme numéro par défaut doit être annulée et lancez le processus de nouvelle planification de leurs réunions. Pour cela, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="00a8a-p112">Replace the default toll or toll-free number for all users that have the number to be unassigned as a default number and start the process of rescheduling their meetings. To do this, run the following command:</span></span>
  
```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 ><span data-ttu-id="00a8a-146">Vous pouvez également modifier le numéro payant par défaut ou le numéro gratuit d’utilisateurs dans le Skype entreprise centre d’administration.</span><span class="sxs-lookup"><span data-stu-id="00a8a-146">You can also change the default toll or toll-free number of users in the Skype for Business admin center.</span></span> <span data-ttu-id="00a8a-147">Toutefois, cela ne replanifie automatiquement leurs réunions.</span><span class="sxs-lookup"><span data-stu-id="00a8a-147">However, this won't automatically reschedule their meetings.</span></span> 
 
 <span data-ttu-id="00a8a-148">Pour plus d’informations, voir [l’invite inclus sur les numéros de téléphone](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="00a8a-148">For additional information, see [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="00a8a-149">En fonction de la taille de votre organisation, cette opération peut prendre un certain temps.</span><span class="sxs-lookup"><span data-stu-id="00a8a-149">Depending on the size of your organization, this could take some time to complete.</span></span> 
  
### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a><span data-ttu-id="00a8a-150">Étape 2 : Affichage du statut de migration des réunions à l'aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="00a8a-150">Step 2 - View meeting migration status using Windows PowerShell</span></span>

<span data-ttu-id="00a8a-151">Toutes les réunions seront replanifiées alors qu’aucune opération à l’état *en attente* ou *En cours* .</span><span class="sxs-lookup"><span data-stu-id="00a8a-151">All meetings will be rescheduled once there are no operations in *Pending* or *In-Progress* state.</span></span>
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="00a8a-152">Pour plus d'informations sur le service Meeting Migration Service (MMS), reportez-vous à la rubrique [Configuration de Meeting Migration Service (MMS)](setting-up-the-meeting-migration-service-mms.md).</span><span class="sxs-lookup"><span data-stu-id="00a8a-152">For more information about the Meeting Migration Service, see [Setting up the Meeting Migration Service (MMS)](setting-up-the-meeting-migration-service-mms.md).</span></span>
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a><span data-ttu-id="00a8a-153">Étape 3 : annuler l’affectation de l’ancien numéro de téléphone à partir du pont d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="00a8a-153">Step 3 - Unassign the old phone number from the audio conferencing bridge</span></span>

1. <span data-ttu-id="00a8a-154">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="00a8a-154">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="00a8a-155">Accéder au **Centre d’administration Office 365** > **Admin centres** > **Skype pour les entreprises** > **vocale** > **numéros de téléphone**.</span><span class="sxs-lookup"><span data-stu-id="00a8a-155">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Voice** > **Phone numbers**.</span></span>
    
3. <span data-ttu-id="00a8a-156">Sélectionnez le numéro de téléphone dans la liste, puis dans le volet Actions, cliquez sur **Supprimer l’attribution**.</span><span class="sxs-lookup"><span data-stu-id="00a8a-156">Select the phone number from the list, and in the Action pane, click **Unassign**.</span></span>
    
4. <span data-ttu-id="00a8a-157">Dans la fenêtre de confirmation, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="00a8a-157">In the confirmation window, click **Yes**.</span></span>
    
  > [!IMPORTANT]
  > <span data-ttu-id="00a8a-158">Une fois un numéro de téléphone non attribué à partir d’un pont de conférence audio, le numéro de téléphone ne sera plus disponible pour les utilisateurs à participer à des réunions de nouveau ou existantes.</span><span class="sxs-lookup"><span data-stu-id="00a8a-158">After a phone number is unassigned from an audio conferencing bridge, the phone number will no longer be available for users to join new or existing meetings.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="00a8a-159">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="00a8a-159">Want to know how to manage with Windows PowerShell?</span></span>
<span data-ttu-id="00a8a-160"><a name="bkPowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="00a8a-160"></span></span>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a><span data-ttu-id="00a8a-161">Vérifier que Windows PowerShell est prêt</span><span class="sxs-lookup"><span data-stu-id="00a8a-161">To verify that Windows PowerShell is ready to go</span></span>

 <span data-ttu-id="00a8a-162">Ces étapes Vérifiez que vous exécutez Windows PowerShell version 3.0 ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="00a8a-162">These steps check that you are running Windows PowerShell version 3.0 or higher.</span></span>
  
1. <span data-ttu-id="00a8a-163">Tapez le **Menu Démarrer** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="00a8a-163">Type **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="00a8a-164">Dans la fenêtre **Windows PowerShell** pour vérifier la version, tapez _Get-Host_ .</span><span class="sxs-lookup"><span data-stu-id="00a8a-164">Type _Get-Host_ in the **Windows PowerShell** window to check the version.</span></span>
    
3. <span data-ttu-id="00a8a-p114">Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="00a8a-p114">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="00a8a-168">Vous devez également installer le module Windows PowerShell pour Skype pour Business en ligne qui vous permet de créer une session Windows PowerShell à distance qui se connecte à Skype pour Business Online.</span><span class="sxs-lookup"><span data-stu-id="00a8a-168">You also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="00a8a-169">Ce module est pris en charge uniquement sur les ordinateurs 64 bits et peut être téléchargé depuis le Center Download Microsoft sur [Le Module Windows PowerShell pour Skype pour Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="00a8a-169">This module is supported only on 64-bit computers and can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="00a8a-170">Redémarrez votre ordinateur si vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="00a8a-170">Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="00a8a-171">Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="00a8a-171">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
### <a name="to-start-windows-powershell"></a><span data-ttu-id="00a8a-172">Lancer Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="00a8a-172">To start Windows PowerShell</span></span>

 <span data-ttu-id="00a8a-173">**Démarrez une session Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="00a8a-173">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="00a8a-174">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="00a8a-174">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="00a8a-175">Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :</span><span class="sxs-lookup"><span data-stu-id="00a8a-175">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="00a8a-176">Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="00a8a-176">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
> 
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

<span data-ttu-id="00a8a-177">Si vous souhaitez plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [Connecting to Skype pour Business Online à l’aide de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="00a8a-177">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
### <a name="save-time-and-automate"></a><span data-ttu-id="00a8a-178">Gagner du temps et automatiser</span><span class="sxs-lookup"><span data-stu-id="00a8a-178">Save time and automate</span></span>

<span data-ttu-id="00a8a-179">Pour gagner du temps en l’automatisation de ce processus, vous pouvez utiliser la [Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688) ou les applets de commande **Set-CsOnlineDialInConferencingUserDefaultNumber** .</span><span class="sxs-lookup"><span data-stu-id="00a8a-179">To save time by automating this process, you can use the [Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688) or the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlets.</span></span>
  
- <span data-ttu-id="00a8a-180">Utilisez l'applet de commande [Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688) pour modifier le numéro payant ou gratuit par défaut pour des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="00a8a-180">Use the [Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>
    
  - <span data-ttu-id="00a8a-181">Pour modifier le numéro gratuit par défaut pour un utilisateur, exécutez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="00a8a-181">To change the default toll-free number for a user, run:</span></span>
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- <span data-ttu-id="00a8a-182">Utilisez l'applet de commande **Set-CsOnlineDialInConferencingUserDefaultNumber** pour modifier le numéro gratuit ou payant par défaut des utilisateurs en fonction de leur numéro par défaut d'origine ou de leur emplacement.</span><span class="sxs-lookup"><span data-stu-id="00a8a-182">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="00a8a-183">Pour rechercher la BridgeID, utilisez la **Get-CsOnlineDialInConferencingBridge**.</span><span class="sxs-lookup"><span data-stu-id="00a8a-183">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>
  
  - <span data-ttu-id="00a8a-184">Pour définir le numéro gratuit par défaut pour tous les utilisateurs qui n'en ont pas sur 8005551234, exécutez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="00a8a-184">To set the default toll-free number for all users without one to 8005551234, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - <span data-ttu-id="00a8a-185">Pour remplacer le numéro gratuit par défaut 8005551234 pour tous les utilisateurs qui l'utilisent par 8005551239 et replanifier leurs réunions de manière automatique, exécutez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="00a8a-185">To change the default toll-free number of all users that have 8005551234 as their default toll-free number to 8005551239 and automatically reschedule their meetings, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - <span data-ttu-id="00a8a-186">Pour définir le numéro gratuit par défaut de tous les utilisateurs situés aux États-Unis sur 8005551234 et replanifier leurs réunions de manière automatique, exécutez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="00a8a-186">To set the default toll-free number of all users located in the U.S. to 8005551234 and automatically reschedule their meetings, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > <span data-ttu-id="00a8a-187">L'emplacement utilisé ci-dessus doit correspondre aux coordonnées des utilisateurs qui sont définies dans le Centre d'administration Office 365.</span><span class="sxs-lookup"><span data-stu-id="00a8a-187">The location that is used above needs to match the contact information of user(s) that is set in the Office 365 admin center.</span></span> 
  
## <a name="about-windows-powershell"></a><span data-ttu-id="00a8a-188">À propos de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="00a8a-188">About Windows PowerShell</span></span>

<span data-ttu-id="00a8a-189">Avec Windows PowerShell, vous pouvez gérer les utilisateurs et ils sont ou ne sont pas autorisés à faire.</span><span class="sxs-lookup"><span data-stu-id="00a8a-189">With Windows PowerShell you can manage users and what they are or are not allowed to do.</span></span> <span data-ttu-id="00a8a-190">Windows PowerShell peut vous aider à gérer Office 365 et Skype pour Business Online à l’aide d’un point unique d’administration qui peut simplifier votre travail quotidien, en particulier lorsque vous avez plusieurs tâches.</span><span class="sxs-lookup"><span data-stu-id="00a8a-190">Windows PowerShell  can help you manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, especially when you've got multiple tasks to do.</span></span> <span data-ttu-id="00a8a-191">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="00a8a-191">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="00a8a-192">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="00a8a-192">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - <span data-ttu-id="00a8a-193">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="00a8a-193">[Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)</span></span>
    
<span data-ttu-id="00a8a-p117">Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="00a8a-p117">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="00a8a-196">Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="00a8a-196">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="00a8a-197">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="00a8a-197">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="00a8a-198">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="00a8a-198">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="00a8a-199">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="00a8a-199">Related topics</span></span>
[<span data-ttu-id="00a8a-200">Modifier les paramètres pour un pont d'audioconférence</span><span class="sxs-lookup"><span data-stu-id="00a8a-200">Change the settings for an Audio Conferencing bridge</span></span>](change-the-settings-for-an-audio-conferencing-bridge.md)
