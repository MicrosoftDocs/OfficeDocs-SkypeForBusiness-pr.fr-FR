---
title: Activer ou désactiver l’envoi de messages électroniques lorsque les paramètres de conférence Audio changent dans Skype pour Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 4d52603fb0d2701cbebd58644cd002dbc94baf89
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490584"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a><span data-ttu-id="b2863-103">Activer ou désactiver l’envoi de messages électroniques lorsque les paramètres de conférence Audio changent dans Skype pour Business Online</span><span class="sxs-lookup"><span data-stu-id="b2863-103">Enable or disable sending emails when Audio Conferencing settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="b2863-104">Si vous souhaitez activer ou désactiver l’envoi d’e-mails dans Microsoft Teams, voir [Activer ou désactiver l’envoi de messages électroniques lorsque les paramètres de conférence Audio changent dans les équipes Microsoft](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span><span class="sxs-lookup"><span data-stu-id="b2863-104">If you want to enable or disable sending emails in Microsoft Teams, see [Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="b2863-105">Les utilisateurs sont avertis automatiquement par courrier électronique lorsqu’ils sont activés pour une audioconférence.</span><span class="sxs-lookup"><span data-stu-id="b2863-105">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="b2863-106">Il peut arriver, cependant, lorsque vous souhaitez réduire le nombre de messages électroniques qui sont envoyés à Skype pour les utilisateurs professionnels.</span><span class="sxs-lookup"><span data-stu-id="b2863-106">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business users.</span></span> <span data-ttu-id="b2863-107">Dans ce cas, vous pouvez désactiver l’envoi de courrier électronique.</span><span class="sxs-lookup"><span data-stu-id="b2863-107">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="b2863-108">Si vous désactivez envoi de courriers électroniques, messages électroniques de conférence Audio ne seront pas envoyées à vos utilisateurs, y compris pour les messages électroniques lorsque les utilisateurs sont activés ou désactivés pour l’audioconférence, leur code confidentiel est réinitialisé et modifications numéros de téléphone de l’ID de conférence et la conférence par défaut .</span><span class="sxs-lookup"><span data-stu-id="b2863-108">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="b2863-109">Voici un exemple du courrier électronique qui est envoyé aux utilisateurs lorsqu’ils sont activés pour une audioconférence :</span><span class="sxs-lookup"><span data-stu-id="b2863-109">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Conférence audio par courrier électronique](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="b2863-111">Quand les messages électroniques sont-ils envoyés à vos utilisateurs ?</span><span class="sxs-lookup"><span data-stu-id="b2863-111">When are emails being sent to your users?</span></span>

- <span data-ttu-id="b2863-112">Il existe plusieurs messages électroniques envoyés aux utilisateurs de votre organisation une fois qu’ils sont activés pour les conférences audio :</span><span class="sxs-lookup"><span data-stu-id="b2863-112">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="b2863-113">Lorsqu’une licence de **Conférence Audio** est attribuée.</span><span class="sxs-lookup"><span data-stu-id="b2863-113">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="b2863-114">Lorsque vous réinitialisez manuellement code confidentiel de conférence audio de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b2863-114">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="b2863-115">Lorsque vous réinitialisez manuellement l'ID de conférence de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b2863-115">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="b2863-116">Lorsque la licence de **Conférence Audio** est supprimée à partir de celles-ci.</span><span class="sxs-lookup"><span data-stu-id="b2863-116">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="b2863-117">Lorsque le fournisseur de services d’audioconférence d’un utilisateur est modifié à partir de Microsoft vers un autre fournisseur ou **Aucun**.</span><span class="sxs-lookup"><span data-stu-id="b2863-117">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="b2863-118">Lorsque le fournisseur de services d’audioconférence d’un utilisateur est remplacé par Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b2863-118">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="b2863-119">Activer ou désactiver la messagerie d’être envoyés aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="b2863-119">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="b2863-120">Activation ou désactivation de l'envoi de messages électroniques aux utilisateurs d'appels entrants</span><span class="sxs-lookup"><span data-stu-id="b2863-120">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>

 
<span data-ttu-id="b2863-121">![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="b2863-121">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="b2863-122">Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, cliquez sur **conférence Audio**.</span><span class="sxs-lookup"><span data-stu-id="b2863-122">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="b2863-123">Dans la page **paramètres du pont Microsoft** , activez ou désactivez l' **Envoyer automatiquement des messages électroniques aux utilisateurs si modifient leurs paramètres de conférence audio**.</span><span class="sxs-lookup"><span data-stu-id="b2863-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="b2863-124">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b2863-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="b2863-125">Vous pouvez également envoyer des e-mail à un utilisateur avec les paramètres de conférence audio en accédant à la **conférence Audio** > **les utilisateurs**, sélectionnez l’utilisateur, puis cliquez sur **Envoyer les informations de conférence par courrier électronique**.</span><span class="sxs-lookup"><span data-stu-id="b2863-125">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="b2863-126">Si vous le faites, un message électronique sera envoyé qui inclut uniquement les ID de conférence et numéro de téléphone de conférence, mais pas le code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="b2863-126">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="b2863-127">Pour plus d’informations, voir [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md) .</span><span class="sxs-lookup"><span data-stu-id="b2863-127">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="b2863-128">Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.</span><span class="sxs-lookup"><span data-stu-id="b2863-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="b2863-129">Exécutez la procédure suivante pour désactiver l’envoi de messages électroniques :</span><span class="sxs-lookup"><span data-stu-id="b2863-129">Run the following to disable sending emails:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="b2863-130">Pour une assistance avec cette cmdlet, voir [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="b2863-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="b2863-131">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="b2863-131">What else should you know?</span></span>

- <span data-ttu-id="b2863-132">Lorsque les messages électroniques automatiques sont désactivées, vous pouvez manuellement déclencher l’envoi d’un message électronique avec le numéro de téléphone et les ID de conférence à l’aide de la Skype pour le centre d’administration de Business.</span><span class="sxs-lookup"><span data-stu-id="b2863-132">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="b2863-133">Toutefois, si vous faites cela, le code confidentiel ne sera inclus.</span><span class="sxs-lookup"><span data-stu-id="b2863-133">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="b2863-134">Si vous souhaitez réinitialiser le code confidentiel de conférence audio et l’envoi d’e-mails est désactivé, vous devrez envoyer à l’utilisateur d’une autre manière.</span><span class="sxs-lookup"><span data-stu-id="b2863-134">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="b2863-135">L'envoi de courrier électronique à vos utilisateurs peut être désactivé à l'aide du Centre d'administration Skype Entreprise ou de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b2863-135">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="b2863-136">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="b2863-136">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="b2863-137">Vous pouvez utiliser ces applets de commande pour gagner du temps ou d’automatiser cette action.</span><span class="sxs-lookup"><span data-stu-id="b2863-137">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="b2863-138">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="b2863-138">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="b2863-139">Remove-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="b2863-139">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="b2863-140">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="b2863-140">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="b2863-141">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="b2863-141">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  <span data-ttu-id="b2863-p104">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="b2863-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - <span data-ttu-id="b2863-145">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="b2863-145">[Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)</span></span>
    
  - [<span data-ttu-id="b2863-146">Six raisons d'utiliser Windows PowerShell pour gérer Office 365 </span><span class="sxs-lookup"><span data-stu-id="b2863-146">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="b2863-147">Windows PowerShell présente de nombreux avantages dans vitesse, la simplicité et la productivité sur qu’à l’aide du centre d’administration Office 365, tels que lorsque vous devez apporter des modifications de paramètre pour de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="b2863-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="b2863-148">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="b2863-148">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="b2863-149">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="b2863-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="b2863-150">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="b2863-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="b2863-151">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="b2863-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="b2863-p106">Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="b2863-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b2863-154">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="b2863-154">Related topics</span></span>

[<span data-ttu-id="b2863-155">Messages électroniques envoyés aux utilisateurs lorsque modifient leurs paramètres de conférence Audio</span><span class="sxs-lookup"><span data-stu-id="b2863-155">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="b2863-156">Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio</span><span class="sxs-lookup"><span data-stu-id="b2863-156">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)


