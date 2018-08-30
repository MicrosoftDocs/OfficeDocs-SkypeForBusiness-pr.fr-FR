---
title: Modifier les numéros de téléphone de votre pont d’audioconférence
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
description: Modifier les numéros de téléphone de votre pont d’audioconférence Le pont d’audioconférence vous fournit des numéros de téléphone à composer à partir de différents endroits afin que les organisateurs et participants aux réunions puissent les utiliser pour rejoindre les réunions Skype Entreprise et Microsoft Teams à l’aide d’un téléphone.
ms.openlocfilehash: c567c1394c60b0be04cae90865cea14b856f1cd5
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23255710"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a><span data-ttu-id="1daf3-104">Modifier les numéros de téléphone de votre pont d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="1daf3-104">Change the phone numbers on your Audio Conferencing bridge</span></span>

<span data-ttu-id="1daf3-105">Lorsque vous achetez des licences **Audioconférence**, Microsoft héberge le *pont d’audioconférence*  pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1daf3-105">When you buy **Skype for Business PSTN Conferencing** licenses, Microsoft is hosting a *conferencing bridge*  for your organization.</span></span> <span data-ttu-id="1daf3-106">Le pont d’audioconférence vous fournit des numéros de téléphone à composer à partir de différents endroits afin que les organisateurs et participants aux réunions puissent les utiliser pour rejoindre les réunions Skype Entreprise et Microsoft Teams à l’aide d’un téléphone.</span><span class="sxs-lookup"><span data-stu-id="1daf3-106">The conferencing bridge gives out dial-in phone numbers from different locations so meeting organizers and participants can use them to join meetings using a phone.</span></span>

<span data-ttu-id="1daf3-107">Outre les numéros de téléphone déjà affectés à votre pont de conférence, vous pouvez [obtenir des numéros de service supplémentaires](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md) (numéros gratuits et payants utilisés pour les audioconférences) d’autres endroits, puis les affecter au pont de conférence afin d’étendre la couverture pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="1daf3-107">In addition to the phone numbers already assigned to your conferencing bridge, you can [Getting Skype for Business service phone numbers](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md) (toll and toll-free numbers used for dial-in conferencing) from other locations and then assign them to the conferencing bridge so you can expand the area/country/region coverage for your users.</span></span>

> [!NOTE]
> <span data-ttu-id="1daf3-108">Pour pouvoir affecter/annuler l’affectation d’un numéro de téléphone pour un pont de conférence, le numéro de téléphone doit être un numéro de « *service* ».</span><span class="sxs-lookup"><span data-stu-id="1daf3-108">To be able to assign/unassign a phone number for a conferencing bridge, the phone number must be a 'service' number.</span></span> <span data-ttu-id="1daf3-109">Vous pouvez voir le type de numéro en accédant à **Voix** > **Numéros de téléphone** et en consultant la colonne **Type de numéro**.</span><span class="sxs-lookup"><span data-stu-id="1daf3-109">You can see the type of number it is by using the **Voice** > **Phone numbers** tab and look under the **Number Type** column.</span></span> <span data-ttu-id="1daf3-110">Les crédits de communication Office 365 doivent être configurés en premier pour permettre aux utilisateurs de se connecter au pont via un numéro gratuit.</span><span class="sxs-lookup"><span data-stu-id="1daf3-110">Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll free number.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a><span data-ttu-id="1daf3-111">Procédure d’affectation d’un nouveau numéro de téléphone de service à votre pont de conférence</span><span class="sxs-lookup"><span data-stu-id="1daf3-111">Steps when you are assigning a new service phone number to your conference bridge</span></span>

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a><span data-ttu-id="1daf3-112">Étape 1 : Affectation d’un nouveau numéro de téléphone de service à votre pont d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="1daf3-112">Step 1 - Assign the new phone number to your conferencing bridge</span></span>

1. <span data-ttu-id="1daf3-113">Connectez-vous à Office 365 à l’aide de votre compte professionnel.</span><span class="sxs-lookup"><span data-stu-id="1daf3-113">Sign in to Office 365 with your work account.</span></span>

2. <span data-ttu-id="1daf3-114">Accédez au **Centre d’administration Office 365** > **Centres d’administration** > **Skype Entreprise** > **Voix** > **Numéros de téléphone**.</span><span class="sxs-lookup"><span data-stu-id="1daf3-114">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Voice** > **Phone numbers** and find the phone number.</span></span>

3. <span data-ttu-id="1daf3-115">Sélectionnez le numéro de téléphone dans la liste et cliquez sur **Affecter** dans le volet Action.</span><span class="sxs-lookup"><span data-stu-id="1daf3-115">Select the phone number from the list and in the Action pane, click **Assign**.</span></span>

4. <span data-ttu-id="1daf3-116">Sur la page **Affecter**, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1daf3-116">On the **Assign** page, click **Save**.</span></span>

    <span data-ttu-id="1daf3-117">Seul un numéro de service payant peut être défini comme numéro par défaut pour votre pont de conférence. **Vous ne pouvez pas définir un numéro de service gratuit comme numéro par défaut pour votre pont de conférence**.</span><span class="sxs-lookup"><span data-stu-id="1daf3-117">Only a service toll number can be set as the default number for your conferencing bridge, **service toll-free numbers can't be set as the default number of your conferencing bridge**.</span></span> <span data-ttu-id="1daf3-118">Si vous attribuez un numéro de service payant et que vous souhaitez le définir comme nouveau numéro par défaut de votre pont d’audioconférence, sélectionnez **Utiliser ce numéro par défaut**.</span><span class="sxs-lookup"><span data-stu-id="1daf3-118">If you are assigning a service toll number and you would like to set it as the new default number for your conferencing bridge, check **Use this number as the default**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1daf3-119">Après avoir affecté un nouveau numéro de téléphone, même si le numéro est devenu le nouveau numéro par défaut, le numéro par défaut pour les utilisateurs existants ne changera pas.</span><span class="sxs-lookup"><span data-stu-id="1daf3-119">After a new phone number has been assigned, even if the number became the new default number, the default number for existing users won't change.</span></span> <span data-ttu-id="1daf3-120">Pour définir le numéro gratuit ou payant par défaut qui est ajouté aux invitations aux réunions d’un organisateur, consultez la rubrique [Définir les numéros inclus dans les invitations](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="1daf3-120">To set the default toll or a toll-free number that is added to an organizer's meeting invites, see [Set the Audio Conferencing phone numbers for meeting organizers that are included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>



### <a name="step-2---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a><span data-ttu-id="1daf3-121">Étape 2 : Modification des numéros de téléphone par défaut inclus dans les invitations aux réunions des utilisateurs (facultatif)</span><span class="sxs-lookup"><span data-stu-id="1daf3-121">Step 2 - Change the default phone numbers that are included in the meeting invites of users (optional)</span></span>

<span data-ttu-id="1daf3-122">Les numéros de téléphone par défaut pour les utilisateurs sont inclus dans leurs invitations lorsqu'ils planifient une réunion.</span><span class="sxs-lookup"><span data-stu-id="1daf3-122">The default phone numbers for user are the ones that are included on their meeting invites when they schedule a meeting.</span></span> <span data-ttu-id="1daf3-123">Pour plus d’informations, voir [Définir les numéros de téléphone inclus dans les invitations](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="1daf3-123">For more information, see [Set the Audio Conferencing phone numbers for meeting organizers that are included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>

1. <span data-ttu-id="1daf3-124">Connectez-vous à Office 365 à l’aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="1daf3-124">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="1daf3-125">Accédez au **Centre d’administration Office 365** > **Centres d’administration** > **Skype Entreprise** > **Audioconférence** > **Utilisateurs** et sélectionnez les utilisateurs dans la liste.</span><span class="sxs-lookup"><span data-stu-id="1daf3-125">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Dial-in conferencing** > **Dial-in users** and find the users in the list.</span></span>

3. <span data-ttu-id="1daf3-126">Cliquez sur **Modifier** dans le volet Action.</span><span class="sxs-lookup"><span data-stu-id="1daf3-126">Click **Edit** in the action pane.</span></span>

4. <span data-ttu-id="1daf3-127">Sous **Numéro payant par défaut** ou **Numéro gratuit par défaut**, sélectionnez le numéro dans la liste et cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1daf3-127">Under ** Default toll number** or Default toll-free number, select the number in the list and click **Save**.</span></span>

<span data-ttu-id="1daf3-128">Une fois les modifications enregistrées, les nouveaux numéros de téléphone par défaut seront inclus dans les invitations des organisateurs lorsqu’ils planifieront leur prochaine réunion.</span><span class="sxs-lookup"><span data-stu-id="1daf3-128">Once the changes have been saved, the new default phone numbers will be included on the meeting invites of organizers the next time they schedule a new meeting.</span></span>

### <a name="step-3---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a><span data-ttu-id="1daf3-129">Étape 3 : Mise à jour des invitations aux réunions des utilisateurs à l’aide du service Meeting Migration Service (facultatif)</span><span class="sxs-lookup"><span data-stu-id="1daf3-129">Step 3 - Update existing meeting invites of users using the Meeting Migration Service (optional)</span></span>

<span data-ttu-id="1daf3-130">Pour les deux étapes suivantes, vous devrez démarrer Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1daf3-130">For the first three steps, you will need to start Windows PowerShell.</span></span>

<span data-ttu-id="1daf3-131">Grâce au service Meeting Migration Service (MMS), vous pouvez éventuellement mettre à jour les invitations aux réunions envoyées aux utilisateurs de votre organisation avant la modification de leur numéros de téléphone par défaut.</span><span class="sxs-lookup"><span data-stu-id="1daf3-131">Using the Meeting Migration Service, you can optionally update meeting invites that were already sent to users in your organization before their default phone numbers had been changed.</span></span> <span data-ttu-id="1daf3-132">Pour plus d'informations, reportez-vous à la rubrique [Configuration de Meeting Migration Service (MMS)](setting-up-the-meeting-migration-service-mms.md).</span><span class="sxs-lookup"><span data-stu-id="1daf3-132">For additional information, see [Setting up the Meeting Migration Service (MMS)](setting-up-the-meeting-migration-service-mms.md).</span></span>

- <span data-ttu-id="1daf3-133">Exécutez le service Meeting Migration Service (MMS) pour les utilisateurs dont le numéro de téléphone par défaut a été modifié à l'étape 2.</span><span class="sxs-lookup"><span data-stu-id="1daf3-133">Run the Meeting Migration Service for the users that had their default phone numbers changed in Step 2.</span></span> <span data-ttu-id="1daf3-134">Pour cela, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="1daf3-134">To do this, run the following command:</span></span>

```
    Start-CsExMeetingMigration user@contoso.com
```

- <span data-ttu-id="1daf3-p109">Vous pouvez également afficher le statut de migration des réunions. Toutes les réunions seront replanifiées lorsque plus aucune opération ne sera dans les états *En attente* ou *En cours*.</span><span class="sxs-lookup"><span data-stu-id="1daf3-p109">You can also view the meeting migration status. All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a><span data-ttu-id="1daf3-137">Procédure d’annulation d’affectation d’un numéro de téléphone de service d’un pont de conférence</span><span class="sxs-lookup"><span data-stu-id="1daf3-137">Steps when you are unassigning a service phone number for a conferencing bridge</span></span>


<span data-ttu-id="1daf3-138">Lorsque vous annulez l’affectation d’un numéro de téléphone d’un pont de conférence, les utilisateurs ne peuvent plus rejoindre aucune réunion à l’aide de ce numéro.</span><span class="sxs-lookup"><span data-stu-id="1daf3-138">When you unassign a phone number from a conferencing bridge, users won't be able to join any meetings using that phone number anymore.</span></span> <span data-ttu-id="1daf3-139">En raison de la modification du numéro de téléphone, il est important de mettre à jour tous les utilisateurs pouvant disposer d’un numéro de téléphone par défaut (le cas échéant), ainsi que leurs invitations aux réunions existantes avant d’annuler l’affectation du numéro du pont d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="1daf3-139">Because the phone number is changing, it's important to update all users that could have a phone number as their default number (if any) and to update their existing meeting invites before the phone number is unassigned from the bridge.</span></span>

<span data-ttu-id="1daf3-140">Si le numéro de téléphone est supprimé sans ces mises à jour, leurs invitations risquent de contenir un numéro qui ne leur permettra plus de rejoindre les réunions..</span><span class="sxs-lookup"><span data-stu-id="1daf3-140">If the phone number is removed without updating the users and their meetings, their existing meeting invites could contain a phone number that won't work for joining their meetings anymore.</span></span>

<span data-ttu-id="1daf3-141">Dans le cas de ces trois premières étapes, vous devrez démarrer Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1daf3-141">For the first three steps, you will need to start Windows PowerShell.</span></span> <span data-ttu-id="1daf3-142">Pour consulter l’aide à ce sujet, cliquez sur [Vous souhaitez savoir comment gérer avec Windows PowerShell ?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span><span class="sxs-lookup"><span data-stu-id="1daf3-142">To see how to do this, click [Want to know how to manage with Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span></span>

### <a name="step-1---update-users-that-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a><span data-ttu-id="1daf3-143">Étape 1 : Mise à jour des utilisateurs dont l’affectation du numéro de téléphone comme numéro par défaut doit être annulée</span><span class="sxs-lookup"><span data-stu-id="1daf3-143">Step 1 - Update users that have the phone number to be unassigned as one of their default numbers</span></span>

<span data-ttu-id="1daf3-p112">Remplacez le numéro payant ou gratuit par défaut de tous les utilisateurs dont l'affectation de numéro de téléphone comme numéro par défaut doit être annulée et lancez le processus de nouvelle planification de leurs réunions. Pour cela, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="1daf3-p112">Replace the default toll or toll-free number for all users that have the number to be unassigned as a default number and start the process of rescheduling their meetings. To do this, run the following command:</span></span>

```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT]
 ><span data-ttu-id="1daf3-146">Vous pouvez également modifier le numéro de téléphone payant ou gratuit par défaut des utilisateurs dans le Centre d’administration Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="1daf3-146">You can also change the default toll or toll-free number of users in the Skype for Business admin center, however, this won't automatically reschedule their meetings.</span></span> <span data-ttu-id="1daf3-147">Toutefois, cela ne replanifiera pas leurs réunions de manière automatique.</span><span class="sxs-lookup"><span data-stu-id="1daf3-147">However, this won't automatically reschedule their meetings.</span></span>

 <span data-ttu-id="1daf3-148">Pour plus d’informations, voir [Définir les numéros de téléphone inclus dans les invitations](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="1daf3-148">For more information, see [Set the Audio Conferencing phone numbers for meeting organizers that are included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="1daf3-149">En fonction de la taille de votre organisation, cette opération peut prendre un certain temps.</span><span class="sxs-lookup"><span data-stu-id="1daf3-149">Depending on the size of your organization, this could take some time to complete.</span></span>

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a><span data-ttu-id="1daf3-150">Étape 2 : Affichage du statut de migration des réunions à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1daf3-150">Step 2 - View meeting migration status using Windows PowerShell</span></span>

<span data-ttu-id="1daf3-151">Toutes les réunions seront replanifiées lorsque plus aucune opération ne sera dans les états *En attente* ou *En cours*.</span><span class="sxs-lookup"><span data-stu-id="1daf3-151">All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="1daf3-152">Pour plus d’informations sur le service Meeting Migration Service, reportez-vous à la rubrique [Configuration de Meeting Migration Service (MMS)](setting-up-the-meeting-migration-service-mms.md).</span><span class="sxs-lookup"><span data-stu-id="1daf3-152">For more information about the Meeting Migration Service, see [Setting up the Meeting Migration Service (MMS)](setting-up-the-meeting-migration-service-mms.md).</span></span>

### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a><span data-ttu-id="1daf3-153">Étape 3 : Annulation de l’affectation de l’ancien numéro de téléphone dans le pont d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="1daf3-153">Step 3 - Unassign the old phone number from the dial-in conferencing bridge</span></span>

1. <span data-ttu-id="1daf3-154">Connectez-vous à Office 365 à l’aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="1daf3-154">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="1daf3-155">Accédez au **Centre d’administration Office 365** > **Centres d’administration** > **Skype Entreprise** > **Voix** > **Numéros de téléphone**.</span><span class="sxs-lookup"><span data-stu-id="1daf3-155">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Voice** > **Phone numbers** and find the phone number.</span></span>

3. <span data-ttu-id="1daf3-156">Sélectionnez le numéro de téléphone dans la liste et cliquez sur **Annuler l’affectation** dans le volet Action.</span><span class="sxs-lookup"><span data-stu-id="1daf3-156">Select the phone number from the list and in the Action pane, click **Unassign**.</span></span>

4. <span data-ttu-id="1daf3-157">Dans la fenêtre de confirmation, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="1daf3-157">In the ** Reset conference ID?** window, click **Yes**.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="1daf3-158">Une fois l’affectation d’un numéro de téléphone annulée pour un pont d’audioconférence, le numéro de téléphone ne sera plus disponible et les utilisateurs ne pourront plus rejoindre les nouvelles réunions ou celles existantes.</span><span class="sxs-lookup"><span data-stu-id="1daf3-158">Once a phone number is unassigned from a conferencing bridge, the phone number will no longer be available for users to join new or existing meetings.</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="1daf3-159">Vous souhaitez savoir comment gérer avec Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="1daf3-159">Want to know how to manage with Windows PowerShell?</span></span>
<span data-ttu-id="1daf3-160"><a name="bkPowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="1daf3-160"></span></span>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a><span data-ttu-id="1daf3-161">Pour vérifier que Windows PowerShell est prêt à fonctionner</span><span class="sxs-lookup"><span data-stu-id="1daf3-161">To verify that Windows PowerShell is ready to go</span></span>

 <span data-ttu-id="1daf3-162">Ces étapes permettent de vérifier que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1daf3-162">Check that you are running Windows PowerShell version 3.0 or higher</span></span>

1. <span data-ttu-id="1daf3-163">Depuis le **Menu Démarrer** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="1daf3-163">Type **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="1daf3-164">Dans la fenêtre **Windows PowerShell** pour vérifier la version, tapez _Get-Host_.</span><span class="sxs-lookup"><span data-stu-id="1daf3-164">Type _Get-Host_ in the **Windows PowerShell** window to check the version.</span></span>

3. <span data-ttu-id="1daf3-p114">Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="1daf3-p114">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="1daf3-168">Vous devez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="1daf3-168">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="1daf3-169">Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="1daf3-169">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span>
<span data-ttu-id="1daf3-170">Redémarrez votre ordinateur si vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="1daf3-170">Restart your computer if you are prompted.</span></span>

<span data-ttu-id="1daf3-171">Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="1daf3-171">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>

### <a name="to-start-windows-powershell"></a><span data-ttu-id="1daf3-172">Lancer Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1daf3-172">To start Windows PowerShell</span></span>

 <span data-ttu-id="1daf3-173">**Démarrez une session Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="1daf3-173">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="1daf3-174">Depuis le **Menu Démarrer** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="1daf3-174">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="1daf3-175">Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :</span><span class="sxs-lookup"><span data-stu-id="1daf3-175">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>

    > [!NOTE]
    > <span data-ttu-id="1daf3-176">Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="1daf3-176">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

>
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

<span data-ttu-id="1daf3-177">Pour plus d’informations sur le démarrage de Windows PowerShell, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou[Connexion à Skype Entreprise Online à l'aide de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="1daf3-177">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or[Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>

### <a name="save-time-and-automate"></a><span data-ttu-id="1daf3-178">Gagner du temps et automatiser</span><span class="sxs-lookup"><span data-stu-id="1daf3-178">Save time or automate</span></span>

<span data-ttu-id="1daf3-179">Pour gagner du temps en automatisant ce processus, vous pouvez utiliser les applets de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) ou **Set-CsOnlineDialInConferencingUserDefaultNumber**.</span><span class="sxs-lookup"><span data-stu-id="1daf3-179">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) or the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlets.</span></span>

- <span data-ttu-id="1daf3-180">Utilisez l’applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) pour modifier le numéro payant ou gratuit par défaut pour des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="1daf3-180">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>

  - <span data-ttu-id="1daf3-181">Pour modifier le numéro gratuit par défaut pour un utilisateur, exécutez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="1daf3-181">To change the default toll-free number for a user, run:</span></span>

  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- <span data-ttu-id="1daf3-182">Utilisez l’applet de commande **Set-CsOnlineDialInConferencingUserDefaultNumber** pour modifier le numéro gratuit ou payant par défaut des utilisateurs en fonction de leur numéro par défaut d’origine ou de leur emplacement.</span><span class="sxs-lookup"><span data-stu-id="1daf3-182">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1daf3-183">Pour trouver le BridgeID, utilisez **Get-CsOnlineDialInConferencingBridge**.</span><span class="sxs-lookup"><span data-stu-id="1daf3-183">Note:To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>

  - <span data-ttu-id="1daf3-184">Pour définir le numéro gratuit par défaut pour tous les utilisateurs qui n’en ont pas sur 8005551234, exécutez la commande :</span><span class="sxs-lookup"><span data-stu-id="1daf3-184">To set the default toll-free number for all users without one to 8005551234, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="1daf3-185">Pour remplacer le numéro gratuit par défaut 8005551234 pour tous les utilisateurs qui l'utilisent par 8005551239 et replanifier leurs réunions de manière automatique, exécutez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="1daf3-185">To change the default toll-free number of all users that have 8005551234 as their default toll-free number to 8005551239 and automatically reschedule their meetings, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - <span data-ttu-id="1daf3-186">Pour définir le numéro gratuit par défaut de tous les utilisateurs situés aux États-Unis sur 8005551234 et replanifier leurs réunions de manière automatique, exécutez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="1daf3-186">To set the default toll-free number of all users located in the U.S. to 8005551234 and automatically reschedule their meetings, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > <span data-ttu-id="1daf3-187">L’emplacement utilisé ci-dessus doit correspondre aux coordonnées des utilisateurs qui sont définies dans le Centre d’administration Office 365.</span><span class="sxs-lookup"><span data-stu-id="1daf3-187">The location that is used above needs to match the contact information of user(s) that is set in the Office 365 admin center.</span></span>

## <a name="about-windows-powershell"></a><span data-ttu-id="1daf3-188">À propos de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1daf3-188">About Windows PowerShell</span></span>

<span data-ttu-id="1daf3-189">Avec Windows PowerShell, vous pouvez gérer les utilisateurs et leurs autorisations.</span><span class="sxs-lookup"><span data-stu-id="1daf3-189">With Windows PowerShell you can manage users and what they are or are not allowed to do.</span></span> <span data-ttu-id="1daf3-190">Windows PowerShell peut vous aider à gérer Office 365 et Skype Entreprise Online à l’aide d’un point d’administration unique qui peut simplifier votre travail au quotidien, lorsque vous devez effectuer plusieurs tâches.</span><span class="sxs-lookup"><span data-stu-id="1daf3-190">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="1daf3-191">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="1daf3-191">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="1daf3-192">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="1daf3-192">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="1daf3-193">Pourquoi utiliser Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="1daf3-193">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

<span data-ttu-id="1daf3-p117">Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="1daf3-p117">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="1daf3-196">Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1daf3-196">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="1daf3-197">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="1daf3-197">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="1daf3-198">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="1daf3-198">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="1daf3-199">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="1daf3-199">Related topics</span></span>
[<span data-ttu-id="1daf3-200">Modifier les paramètres pour un pont d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="1daf3-200">Change the settings for an Audio Conferencing bridge</span></span>](change-the-settings-for-an-audio-conferencing-bridge.md)
