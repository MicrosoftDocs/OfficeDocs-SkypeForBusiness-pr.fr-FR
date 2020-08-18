---
title: Messages électroniques envoyés aux utilisateurs lorsque leurs paramètres sont modifiés
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
description: 'Découvrez quelles informations sont envoyées automatiquement aux utilisateurs par e-mail lorsque leurs paramètres d’audioconférence sont modifiés dans Microsoft Teams. '
ms.openlocfilehash: 1cef5f0ea8865820f6f6f83e29fe5f66799b70ae
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788688"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a><span data-ttu-id="6a500-103">Courriers électroniques envoyés aux utilisateurs lorsque leurs paramètres sont modifiés dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6a500-103">Emails sent to users when their settings change in Microsoft Teams</span></span>

<span data-ttu-id="6a500-104">Des courriers électroniques seront envoyés automatiquement aux utilisateurs qui lesquels [l’audioconférence est activée](set-up-audio-conferencing-in-teams.md) et qui utilisent Microsoft comme fournisseur de service d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="6a500-104">Emails will be automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing-in-teams.md) using Microsoft as the audio conferencing provider.</span></span>

<span data-ttu-id="6a500-105">Par défaut, quatre types de courriers électroniques seront envoyés à vos utilisateurs pour lesquels la fonction d’audioconférence est activée.</span><span class="sxs-lookup"><span data-stu-id="6a500-105">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="6a500-106">Toutefois, si vous souhaitez imiter le nombre de messages électroniques envoyés aux utilisateurs, vous pouvez désactiver cette option.</span><span class="sxs-lookup"><span data-stu-id="6a500-106">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="6a500-107">L’audioconférence dans Microsoft 365 ou Office 365 envoie un message électronique aux messages électroniques de vos utilisateurs dans les cas suivants :</span><span class="sxs-lookup"><span data-stu-id="6a500-107">Audio Conferencing in Microsoft 365 or Office 365 will send email to your users' email when:</span></span>

- <span data-ttu-id="6a500-108">**Une licence pour l’audioconférence leur est attribuée ou le fournisseur de service d’audioconférence est remplacé par Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="6a500-108">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>

     <span data-ttu-id="6a500-109">Ce courrier électronique contient l'ID de conférence, le numéro de téléphone d'accès par défaut aux réunions, le code confidentiel d’audioconférence attribué à l'utilisateur, ainsi que les instructions et le lien de l'outil de mise à jour des réunions Skype Entreprise Online existantes de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6a500-109">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="6a500-110">Voir [affecter des licences de compléments Microsoft teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) ou [attribuez Microsoft en tant que fournisseur](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="6a500-110">See [Assign Microsoft Teams add-on licenses](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) or [Assign Microsoft as the audio conferencing provider](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

    > [!NOTE]
    > <span data-ttu-id="6a500-111">Si des ID de conférence dynamiques ont été activés pour votre organisation, toutes les réunions qu'un utilisateur planifie auront un ID de conférence unique.</span><span class="sxs-lookup"><span data-stu-id="6a500-111">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="6a500-112">Vous pouvez configurer des [ID dynamiques d’audioconférence dans votre organisation](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="6a500-112">You can set up [Audio Conferencing dynamic IDs in your organization](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span></span> 

    <span data-ttu-id="6a500-113">Voici un exemple de ce courrier électronique :</span><span class="sxs-lookup"><span data-stu-id="6a500-113">Here is an example of this email:</span></span>

     ![Vérifier la licence Skype Entreprise](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    <span data-ttu-id="6a500-115">Pour en savoir plus sur les licences, consultez [licences de complément Microsoft teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span><span class="sxs-lookup"><span data-stu-id="6a500-115">To find out more about licensing, see [Microsoft Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>

- <span data-ttu-id="6a500-116">**L'ID de conférence ou le numéro de téléphone de conférence par défaut d’un utilisateur est modifié.**</span><span class="sxs-lookup"><span data-stu-id="6a500-116">**The conference ID or default conference phone number of a user changes.**</span></span>

    <span data-ttu-id="6a500-117">Ce courrier électronique contient l'ID de conférence, le numéro d'accès à la conférence par défaut, ainsi que les instructions et le lien de l'outil de mise à jour de réunion de Skype Entreprise Online pour mettre à jour les réunions existantes de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6a500-117">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="6a500-118">Toutefois, il ne comporte pas le code confidentiel d’audioconférence de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6a500-118">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="6a500-119">Reportez-vous à la section [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="6a500-119">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>

    <span data-ttu-id="6a500-120">Voici un exemple de ce courrier électronique :</span><span class="sxs-lookup"><span data-stu-id="6a500-120">Here is an example of this email:</span></span>

     ![Les informations de conférence rendez-vous ont été modifiées.](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- <span data-ttu-id="6a500-122">**Le code confidentiel d’audioconférence d'un utilisateur est modifié.**</span><span class="sxs-lookup"><span data-stu-id="6a500-122">**The audio conferencing PIN of a user is reset.**</span></span>

    <span data-ttu-id="6a500-123">Ce courrier électronique contient le code confidentiel d’audioconférence de l'organisateur, l'ID de conférence existant et le numéro d'accès par défaut pour l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6a500-123">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="6a500-124">Reportez-vous à la section [Réinitialiser le code confidentiel d'audioconférence](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="6a500-124">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
     <span data-ttu-id="6a500-125">Voici un exemple de ce courrier électronique :</span><span class="sxs-lookup"><span data-stu-id="6a500-125">Here is an example of this email:</span></span>
    
     ![Le code confidentiel d’audioconférence a été modifiée.](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- <span data-ttu-id="6a500-127">**La licence d’un utilisateur est supprimée ou le fournisseur de service d’audioconférence Microsoft est remplacé par un autre fournisseur ou est défini sur Aucun.**</span><span class="sxs-lookup"><span data-stu-id="6a500-127">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>

    <span data-ttu-id="6a500-128">Cela se produit lorsque la licence d' **audioconférence** est supprimée d’un utilisateur ou lors de la définition du fournisseur de services d’audioconférence sur **aucun**.</span><span class="sxs-lookup"><span data-stu-id="6a500-128">This happens when the **Audio Conferencing** license is removed from a user or when setting the audio conferencing provider to **None**.</span></span>

    <span data-ttu-id="6a500-129">Voir [affecter ou supprimer des licences pour Microsoft 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="6a500-129">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

    <span data-ttu-id="6a500-130">Voici un exemple de ce courrier électronique :</span><span class="sxs-lookup"><span data-stu-id="6a500-130">Here is an example of this email:</span></span>

     ![La fonctionnalité Conférence rendez-vous est désactivée.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="6a500-132">Modifier les courriers électroniques qui leur sont envoyés</span><span class="sxs-lookup"><span data-stu-id="6a500-132">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="6a500-133">Vous pouvez modifier le message électronique qui est envoyé automatiquement aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6a500-133">You can make changes to the email that is automatically sent to users.</span></span> <span data-ttu-id="6a500-134">Par défaut, l’expéditeur des messages électroniques provient de Microsoft 365 ou d’Office 365, mais vous pouvez modifier le nom d’affichage à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a500-134">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the display name using Windows PowerShell.</span></span> <span data-ttu-id="6a500-135">Pour plus d’informations, consultez la [référence Microsoft teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) .</span><span class="sxs-lookup"><span data-stu-id="6a500-135">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="6a500-136">Comment procéder si vous ne souhaitez pas leur envoyer de courriers électroniques ?</span><span class="sxs-lookup"><span data-stu-id="6a500-136">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="6a500-137">Lorsque vous désactivez l'envoi de courriers électroniques, le courrier électronique ne sera pas envoyé même si l'utilisateur dispose d'une licence.</span><span class="sxs-lookup"><span data-stu-id="6a500-137">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="6a500-138">Dans le cas présent, l’ID de conférence, le numéro de téléphone de l’audioconférence par défaut et, plus important encore, le code confidentiel de l’audioconférence ne sera pas envoyé à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6a500-138">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="6a500-139">En pareil cas, vous devez en informer l'utilisateur en lui envoyant un courrier électronique distinct ou en l'appelant.</span><span class="sxs-lookup"><span data-stu-id="6a500-139">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>

<span data-ttu-id="6a500-140">Par défaut, les courriers électroniques seront envoyés à vos utilisateurs, mais si vous ne souhaitez pas qu’ils reçoivent du courrier électronique pour les conférences audio, vous pouvez utiliser Microsoft teams ou Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a500-140">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use Microsoft Teams or Windows PowerShell.</span></span> 

<span data-ttu-id="6a500-141">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="6a500-141">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="6a500-142">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="6a500-142">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="6a500-143">Dans la partie supérieure de la page de **conférences ponts** , cliquez sur **paramètres du pont**.</span><span class="sxs-lookup"><span data-stu-id="6a500-143">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="6a500-144">Dans le volet **paramètres du pont** , activez ou désactivez l' **envoi automatique de messages électroniques aux utilisateurs en cas de modification de leurs paramètres de connexion**.</span><span class="sxs-lookup"><span data-stu-id="6a500-144">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="6a500-145">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6a500-145">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="6a500-146">**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**</span><span class="sxs-lookup"><span data-stu-id="6a500-146">**Using Windows PowerShell**</span></span>

<span data-ttu-id="6a500-147">Pour plus d’informations, consultez la [référence Microsoft teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) .</span><span class="sxs-lookup"><span data-stu-id="6a500-147">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="6a500-148">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="6a500-148">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="6a500-149">Par défaut, l’expéditeur des messages électroniques provient de Microsoft 365 ou d’Office 365, mais vous pouvez modifier l’adresse de messagerie et le nom d’affichage à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a500-149">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> 

<span data-ttu-id="6a500-150">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="6a500-150">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="6a500-151">Windows PowerShell vous permet de gérer Microsoft 365 ou Office 365 à l’aide d’un point d’administration unique qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer.</span><span class="sxs-lookup"><span data-stu-id="6a500-151">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="6a500-152">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="6a500-152">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="6a500-153">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="6a500-153">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [<span data-ttu-id="6a500-154">Meilleurs moyens de gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a500-154">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

<span data-ttu-id="6a500-155">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="6a500-155">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="related-topics"></a><span data-ttu-id="6a500-156">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="6a500-156">Related topics</span></span>

[<span data-ttu-id="6a500-157">Activer ou désactiver l'envoi de messages électroniques lorsque modifient les paramètres de conférence Audio</span><span class="sxs-lookup"><span data-stu-id="6a500-157">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[<span data-ttu-id="6a500-158">Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio</span><span class="sxs-lookup"><span data-stu-id="6a500-158">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
