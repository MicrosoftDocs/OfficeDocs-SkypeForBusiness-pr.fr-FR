---
title: Courriers électroniques envoyés aux utilisateurs lorsque leurs paramètres sont modifiés dans Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Découvrez quelles informations sont envoyées automatiquement aux utilisateurs par e-mail lorsque leurs paramètres d’audioconférence sont modifiés dans Microsoft Teams. '
ms.openlocfilehash: 1431cd4391219e052ec2ad3702a9e4c227912a06
ms.sourcegitcommit: d3c459dc1304db5f5ba78b5e093b5a4fd797c8ec
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2019
ms.locfileid: "30178692"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a><span data-ttu-id="b3f49-103">Courriers électroniques envoyés aux utilisateurs lorsque leurs paramètres sont modifiés dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b3f49-103">Emails sent to users when their settings change in Microsoft Teams</span></span>

<span data-ttu-id="b3f49-104">Des courriers électroniques seront envoyés automatiquement aux utilisateurs qui lesquels [l’audioconférence est activée](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) et qui utilisent Microsoft comme fournisseur de service d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="b3f49-104">Emails will be automatically sent to users who are [enabled for Audio Conferencing](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) using Microsoft as the audio conferencing provider.</span></span>

<span data-ttu-id="b3f49-105">Par défaut, quatre types de courriers électroniques seront envoyés à vos utilisateurs pour lesquels la fonction d’audioconférence est activée.</span><span class="sxs-lookup"><span data-stu-id="b3f49-105">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="b3f49-106">Toutefois, si vous souhaitez imiter le nombre de messages électroniques envoyés aux utilisateurs, vous pouvez désactiver cette option.</span><span class="sxs-lookup"><span data-stu-id="b3f49-106">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="b3f49-107">La fonction d’audioconférence dans Office 365 enverra un courrier électronique à vos utilisateurs dans les cas suivants :</span><span class="sxs-lookup"><span data-stu-id="b3f49-107">Audio Conferencing in Office 365 will send email to your users' email when:</span></span>

- <span data-ttu-id="b3f49-108">**Une licence pour l’audioconférence leur est attribuée ou le fournisseur de service d’audioconférence est remplacé par Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="b3f49-108">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>

     <span data-ttu-id="b3f49-109">Ce courrier électronique contient l'ID de conférence, le numéro de téléphone d'accès par défaut aux réunions, le code confidentiel d’audioconférence attribué à l'utilisateur, ainsi que les instructions et le lien de l'outil de mise à jour des réunions Skype Entreprise Online existantes de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b3f49-109">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="b3f49-110">Voir [licences attribuer les équipes Microsoft](assign-teams-licenses.md) ou [Affecter de Microsoft en tant que le fournisseur de services d’audioconférence](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span><span class="sxs-lookup"><span data-stu-id="b3f49-110">See [Assign Microsoft Teams licenses](assign-teams-licenses.md) or [Assign Microsoft as the audio conferencing provider](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

    > [!NOTE]
    > <span data-ttu-id="b3f49-111">Si des ID de conférence dynamiques ont été activés pour votre organisation, toutes les réunions qu'un utilisateur planifie auront un ID de conférence unique.</span><span class="sxs-lookup"><span data-stu-id="b3f49-111">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="b3f49-112">Vous pouvez configurer des [ID dynamiques d’audioconférence dans votre organisation](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="b3f49-112">You can set up [Audio Conferencing dynamic IDs in your organization](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span></span> 

    <span data-ttu-id="b3f49-113">Voici un exemple de ce courrier électronique :</span><span class="sxs-lookup"><span data-stu-id="b3f49-113">Here is an example of this email:</span></span>

     ![Vérifier la licence Skype Entreprise](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    <span data-ttu-id="b3f49-115">Pour en savoir plus sur les licences, voir [Gestion des licences de module complémentaire équipes Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="b3f49-115">To find out more about licensing, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

- <span data-ttu-id="b3f49-116">**L'ID de conférence ou le numéro de téléphone de conférence par défaut d’un utilisateur est modifié.**</span><span class="sxs-lookup"><span data-stu-id="b3f49-116">**The conference ID or default conference phone number of a user changes.**</span></span>

    <span data-ttu-id="b3f49-117">Ce courrier électronique contient l'ID de conférence, le numéro d'accès à la conférence par défaut, ainsi que les instructions et le lien de l'outil de mise à jour de réunion de Skype Entreprise Online pour mettre à jour les réunions existantes de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b3f49-117">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="b3f49-118">Toutefois, il ne comporte pas le code confidentiel d’audioconférence de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b3f49-118">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="b3f49-119">Reportez-vous à la section [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b3f49-119">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>

    <span data-ttu-id="b3f49-120">Voici un exemple de ce courrier électronique :</span><span class="sxs-lookup"><span data-stu-id="b3f49-120">Here is an example of this email:</span></span>

     ![Les informations de conférence rendez-vous ont été modifiées.](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- <span data-ttu-id="b3f49-122">**Le code confidentiel d’audioconférence d'un utilisateur est modifié.**</span><span class="sxs-lookup"><span data-stu-id="b3f49-122">**The audio conferencing PIN of a user is reset.**</span></span>

    <span data-ttu-id="b3f49-123">Ce courrier électronique contient le code confidentiel d’audioconférence de l'organisateur, l'ID de conférence existant et le numéro d'accès par défaut pour l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b3f49-123">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="b3f49-124">Reportez-vous à la section [Réinitialiser le code confidentiel d'audioconférence](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b3f49-124">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
     <span data-ttu-id="b3f49-125">Voici un exemple de ce courrier électronique :</span><span class="sxs-lookup"><span data-stu-id="b3f49-125">Here is an example of this email:</span></span>
    
     ![Le code confidentiel d’audioconférence a été modifiée.](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- <span data-ttu-id="b3f49-127">**La licence d’un utilisateur est supprimée ou le fournisseur de service d’audioconférence Microsoft est remplacé par un autre fournisseur ou est défini sur Aucun.**</span><span class="sxs-lookup"><span data-stu-id="b3f49-127">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>

    <span data-ttu-id="b3f49-128">Cela se produit lorsque la licence pour l’**audioconférence** d'un utilisateur est supprimée, lorsque vous remplacez le fournisseur de service d’audioconférence Microsoft d'un utilisateur par un fournisseur de service d'audioconférence tiers ou lorsque le fournisseur est défini sur **Aucun**.</span><span class="sxs-lookup"><span data-stu-id="b3f49-128">This happens when the **Audio Conferencing** license is removed from a user or when changing the audio conferencing provider of a user from Microsoft to a third-party audio conferencing provider or when setting the provider to **None**.</span></span> <span data-ttu-id="b3f49-129">Ce courrier électronique contient les instructions et les informations nécessaires à l'utilisateur pour utiliser l'outil de mise à jour de réunion de Skype Entreprise Online pour supprimer les informations spécifiques à l’audioconférence, comme le numéro de téléphone de conférence par défaut ou l'ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="b3f49-129">This email contains the instructions and information for the user to use the Skype for Business Online Meeting Update Tool to remove audio conferencing specific information, such as the default conference phone number or conference ID.</span></span>

    <span data-ttu-id="b3f49-130">Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="b3f49-130">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

    <span data-ttu-id="b3f49-131">Voici un exemple de ce courrier électronique :</span><span class="sxs-lookup"><span data-stu-id="b3f49-131">Here is an example of this email:</span></span>

     ![La fonctionnalité Conférence rendez-vous est désactivée.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="b3f49-133">Modifier les courriers électroniques qui leur sont envoyés</span><span class="sxs-lookup"><span data-stu-id="b3f49-133">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="b3f49-134">Vous pouvez apporter des modifications aux courriers électroniques envoyés automatiquement à vos utilisateurs, dont l'adresse électronique et le nom d'affichage figurant dans les informations de contact *De*.</span><span class="sxs-lookup"><span data-stu-id="b3f49-134">You can make changes to the email that is automatically sent to users including the email address and the display name that is included in the *From* contact information.</span></span> <span data-ttu-id="b3f49-135">Par défaut, l'envoi des courriers électroniques se fera à partir d'Office 365, mais vous pouvez modifier l'adresse électronique et le nom d'affichage à l'aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b3f49-135">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> <span data-ttu-id="b3f49-136">Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="b3f49-136">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="b3f49-137">Comment procéder si vous ne souhaitez pas leur envoyer de courriers électroniques ?</span><span class="sxs-lookup"><span data-stu-id="b3f49-137">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="b3f49-138">Lorsque vous désactivez l'envoi de courriers électroniques aux utilisateurs, le courrier électronique ne sera pas envoyé même si une licence est attribuée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b3f49-138">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="b3f49-139">Dans ce cas, l'ID de conférence, le numéro de téléphone d'accès par défaut à la conférence et, plus important, son code confidentiel d’audioconférence ne seront pas envoyés à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b3f49-139">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="b3f49-140">En pareil cas, vous devez en informer l'utilisateur en lui envoyant un courrier électronique distinct ou en l'appelant.</span><span class="sxs-lookup"><span data-stu-id="b3f49-140">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>

<span data-ttu-id="b3f49-141">Par défaut, des courriers électroniques seront envoyés à vos utilisateurs, mais si vous ne souhaitez pas qu'ils en reçoivent pour l’audioconférence, vous pouvez utiliser Microsoft Teams ou Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b3f49-141">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use Microsoft Teams or Windows PowerShell.</span></span> 

<span data-ttu-id="b3f49-142">![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft équipes**</span><span class="sxs-lookup"><span data-stu-id="b3f49-142">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="b3f49-143">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="b3f49-143">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="b3f49-144">En haut de la page **Conference Bridges** (Ponts de conférence), cliquez sur **Bridge Settings** (Paramètres du pont).</span><span class="sxs-lookup"><span data-stu-id="b3f49-144">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="b3f49-145">Dans le volet **Bridge settings** (Paramètres du pont), activez ou désactivez l’option **Envoyer automatiquement un courrier électronique aux utilisateurs en cas de modification de leurs paramètres de numérotation**.</span><span class="sxs-lookup"><span data-stu-id="b3f49-145">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="b3f49-146">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b3f49-146">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="b3f49-147">**Utiliser Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="b3f49-147">**Using Windows PowerShell**</span></span>

<span data-ttu-id="b3f49-148">Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="b3f49-148">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="b3f49-149">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="b3f49-149">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="b3f49-150">Par défaut, l'envoi des courriers électroniques se fera à partir d'Office 365, mais vous pouvez modifier l'adresse électronique et le nom d'affichage à l'aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b3f49-150">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> 

<span data-ttu-id="b3f49-p109">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="b3f49-p109">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="b3f49-154">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="b3f49-154">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [<span data-ttu-id="b3f49-155">Meilleurs moyens de gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3f49-155">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

<span data-ttu-id="b3f49-156">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="b3f49-156">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="related-topics"></a><span data-ttu-id="b3f49-157">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="b3f49-157">Related topics</span></span>

[<span data-ttu-id="b3f49-158">Activer ou désactiver l'envoi de courriers électroniques lorsque les paramètres d’audioconférence sont modifiés</span><span class="sxs-lookup"><span data-stu-id="b3f49-158">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[<span data-ttu-id="b3f49-159">Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio</span><span class="sxs-lookup"><span data-stu-id="b3f49-159">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
