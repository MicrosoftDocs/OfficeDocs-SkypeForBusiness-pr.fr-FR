---
title: Courriers électroniques envoyés aux utilisateurs en cas de modification de leurs paramètres dans Skype entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'En savoir plus sur les informations envoyées automatiquement aux utilisateurs par courrier électronique en cas de modification de leurs paramètres de conférence rendez-vous dans Skype entreprise online. '
ms.openlocfilehash: acdc16a1af2666dcb84599fae31a910be83ac08f
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494285"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a><span data-ttu-id="62ba7-103">Courriers électroniques envoyés aux utilisateurs en cas de modification de leurs paramètres dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="62ba7-103">Emails sent to users when their settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="62ba7-104">Si vous recherchez des informations de messagerie automatique dans Microsoft Teams, voir [messages électroniques envoyés aux utilisateurs lorsque leurs paramètres changent dans Microsoft teams](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams).</span><span class="sxs-lookup"><span data-stu-id="62ba7-104">If you're looking for automatic email information in Microsoft Teams, see [Emails sent to users when their settings change in Microsoft Teams](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="62ba7-105">Des courriers électroniques seront automatiquement envoyés aux utilisateurs qui sont [activés pour les conférences audio](set-up-audio-conferencing.md) en utilisant Microsoft comme fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="62ba7-105">Emails will be automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing.md) using Microsoft as the audio conferencing provider.</span></span>
  
<span data-ttu-id="62ba7-106">Par défaut, il existe quatre types de messages électroniques qui seront envoyés aux utilisateurs qui sont activés pour les conférences audio.</span><span class="sxs-lookup"><span data-stu-id="62ba7-106">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="62ba7-107">Toutefois, si vous voulez limiter le nombre de messages électroniques envoyés aux utilisateurs, vous pouvez désactiver cette option.</span><span class="sxs-lookup"><span data-stu-id="62ba7-107">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="62ba7-108">L’audioconférence dans Office 365 envoie un message électronique aux messages électroniques de vos utilisateurs dans les cas suivants:</span><span class="sxs-lookup"><span data-stu-id="62ba7-108">Audio Conferencing in Office 365 will send email to your users' email when:</span></span>
  
- <span data-ttu-id="62ba7-109">**Une licence d’audioconférence lui est affectée ou lorsque vous modifiez le fournisseur de services d’audioconférence pour Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="62ba7-109">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>
    
     <span data-ttu-id="62ba7-110">Cet e-mail contient l’ID de conférence, le numéro de téléphone de la Conférence par défaut pour les réunions, le code confidentiel d’audioconférence pour l’utilisateur, ainsi que les instructions et le lien pour utiliser l’outil de mise à jour des réunions de Skype entreprise Online qui est utilisé pour mettre à jour les réunions existantes pour le Il.</span><span class="sxs-lookup"><span data-stu-id="62ba7-110">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="62ba7-111">Consultez la rubrique [affectation de licences Skype entreprise](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) ou [affectation de Microsoft en tant que fournisseur](assign-microsoft-as-the-audio-conferencing-provider.md)de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="62ba7-111">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="62ba7-112">Si votre organisation a été activée pour les ID de conférence dynamiques, toutes les réunions d'un utilisateur planifiées auront un ID de conférence unique.</span><span class="sxs-lookup"><span data-stu-id="62ba7-112">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="62ba7-113">Vous pouvez configurer les [ID dynamiques de l’audioconférence dans votre organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="62ba7-113">You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
    <span data-ttu-id="62ba7-114">Voici un exemple de ce courrier électronique :</span><span class="sxs-lookup"><span data-stu-id="62ba7-114">Here is an example of this email:</span></span>
    
     ![Skype for Business Verify License](../images/audio-conferencing-user-enabled.png)
  
    <span data-ttu-id="62ba7-116">Pour plus d'informations sur l'affectation de licences Skype Entreprise, reportez-vous à la rubrique [Licences de module complémentaire Skype Entreprise](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="62ba7-116">You can find out more about Skype for Business licensing by seeing [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
- <span data-ttu-id="62ba7-117">**L'ID de conférence ou le numéro de téléphone par défaut d'une conférence pour un utilisateur change.**</span><span class="sxs-lookup"><span data-stu-id="62ba7-117">**The conference ID or default conference phone number of a user changes.**</span></span>
    
    <span data-ttu-id="62ba7-118">Ce courrier électronique contient l'ID de conférence, le numéro d'accès à la conférence par défaut, ainsi que les instructions et le lien de l'outil de mise à jour de réunion de Skype Entreprise Online pour mettre à jour les réunions existantes de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="62ba7-118">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="62ba7-119">Mais ce message ne comprend pas le code confidentiel de l’audioconférence de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="62ba7-119">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="62ba7-120">Reportez-vous à la rubrique [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="62ba7-120">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="62ba7-121">Si votre organisation a été activée pour les ID de conférence dynamiques, toutes les réunions d'un utilisateur planifiées auront un ID de conférence unique.</span><span class="sxs-lookup"><span data-stu-id="62ba7-121">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="62ba7-122">Vous pouvez configurer les [ID dynamiques de l’audioconférence dans votre organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="62ba7-122">You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
    <span data-ttu-id="62ba7-123">Voici un exemple de ce courrier électronique :</span><span class="sxs-lookup"><span data-stu-id="62ba7-123">Here is an example of this email:</span></span>
    
     ![Les informations de la conférence rendez-vous ont été modifiées.](../images/audio-conferencing-info-change.png)
  
- <span data-ttu-id="62ba7-125">**Le code confidentiel de conférence audio d’un utilisateur est réinitialisé.**</span><span class="sxs-lookup"><span data-stu-id="62ba7-125">**The audio conferencing PIN of a user is reset.**</span></span>
    
    <span data-ttu-id="62ba7-126">Ce courrier électronique contient le code confidentiel d’audioconférence de l’organisateur, l’ID de conférence actuel et le numéro de téléphone de la Conférence par défaut de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="62ba7-126">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="62ba7-127">Voir [Réinitialiser le code confidentiel de l’audioconférence](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="62ba7-127">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="62ba7-128">Si votre organisation a été activée pour les ID de conférence dynamiques, toutes les réunions d'un utilisateur planifiées auront un ID de conférence unique.</span><span class="sxs-lookup"><span data-stu-id="62ba7-128">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="62ba7-129">Vous pouvez configurer les [ID dynamiques de l’audioconférence dans votre organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="62ba7-129">You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
    <span data-ttu-id="62ba7-130">Voici un exemple de ce courrier électronique :</span><span class="sxs-lookup"><span data-stu-id="62ba7-130">Here is an example of this email:</span></span>
    
     ![Le code confidentiel de la conférence rendez-vous a été modifié.](../images/audio-conferencing-pin-has-changed.png)
  
- <span data-ttu-id="62ba7-132">**La licence d’un utilisateur est supprimée ou le fournisseur de services d’audioconférence passe de Microsoft à un autre fournisseur ou à aucun.**</span><span class="sxs-lookup"><span data-stu-id="62ba7-132">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>
    
    <span data-ttu-id="62ba7-133">Cette situation se produit lorsque la licence de **conférence audio** est supprimée d’un utilisateur ou lorsque vous définissez un fournisseur de services d’audioconférence tiers pour un utilisateur ou un fournisseur de services d’audioconférence tiers ou lorsque vous définissez le fournisseur sur **aucun**.</span><span class="sxs-lookup"><span data-stu-id="62ba7-133">This happens when the **Audio Conferencing** license is removed from a user or when changing the audio conferencing provider of a user from Microsoft to a third-party audio conferencing provider or when setting the provider to **None**.</span></span> <span data-ttu-id="62ba7-134">Ce courrier électronique contient les instructions et les informations nécessaires à l’utilisateur pour utiliser l’outil de mise à jour des réunions de Skype entreprise Online afin de supprimer les informations spécifiques aux services d’audioconférence, comme le numéro de téléphone de la Conférence par défaut ou l’ID de conférence.</span><span class="sxs-lookup"><span data-stu-id="62ba7-134">This email contains the instructions and information for the user to use the Skype for Business Online Meeting Update Tool to remove audio conferencing specific information, such as the default conference phone number or conference ID.</span></span>
    
    <span data-ttu-id="62ba7-135">Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="62ba7-135">See [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
    
    <span data-ttu-id="62ba7-136">Voici un exemple de ce courrier électronique :</span><span class="sxs-lookup"><span data-stu-id="62ba7-136">Here is an example of this email:</span></span>
    
     ![La fonctionnalité Conférence rendez-vous est désactivée.](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="62ba7-138">Modifier les courriers électroniques qui leur sont envoyés</span><span class="sxs-lookup"><span data-stu-id="62ba7-138">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="62ba7-139">Vous pouvez modifier le message électronique qui est envoyé automatiquement aux utilisateurs, notamment l’adresse de courrier et le nom d’affichage qui est inclus dans les informations *de contact de* .</span><span class="sxs-lookup"><span data-stu-id="62ba7-139">You can make changes to the email that is automatically sent to users including the email address and the display name that is included in the *From* contact information.</span></span> <span data-ttu-id="62ba7-140">Par défaut, l’expéditeur des messages électroniques provient d’Office 365, mais vous pouvez modifier l’adresse de messagerie et le nom d’affichage à l’aide de Windows PowerShell et de l’applet [de passe Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) .</span><span class="sxs-lookup"><span data-stu-id="62ba7-140">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span> <span data-ttu-id="62ba7-141">Pour modifier l’adresse de messagerie qui envoie le message électronique aux utilisateurs, vous devez:</span><span class="sxs-lookup"><span data-stu-id="62ba7-141">To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="62ba7-142">entrer l'adresse électronique dans le paramètre À _SendEmailFromAddress_;</span><span class="sxs-lookup"><span data-stu-id="62ba7-142">Enter the email address in the  _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="62ba7-143">entrer le nom d'affichage associé à l'adresse électronique dans le paramètre  _SendEmailFromDisplayName_.</span><span class="sxs-lookup"><span data-stu-id="62ba7-143">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="62ba7-144">Définissez le paramètre _SendEmailOverride_ sur _true_.</span><span class="sxs-lookup"><span data-stu-id="62ba7-144">Set the  _SendEmailOverride_ parameter to  _True_.</span></span>
    
<span data-ttu-id="62ba7-145">Vous pouvez apporter des modifications aux courriers électroniques envoyés aux utilisateurs, comme l’adresse électronique d’envoi du courrier électronique et le nom d’affichage pour le message électronique, en exécutant:</span><span class="sxs-lookup"><span data-stu-id="62ba7-145">You can make changes to the email sent to users, such as the email address that the email is sent from and the display name for the email, by running:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  <span data-ttu-id="62ba7-146">Si vous souhaitez modifier les informations de l’adresse électronique, vous devez vous assurer que les stratégies de courrier électronique entrant de votre environnement autorisent les messages électroniques provenant de l’adresse personnalisée de l’expéditeur spécifiée.</span><span class="sxs-lookup"><span data-stu-id="62ba7-146">If you want to change the email address information, you need to make sure that the inbound email policies of your environment allow emails that come from the custom specified from address.</span></span> <span data-ttu-id="62ba7-147">Si vous décidez de remplacer les informations *de* contact, vous devez vérifier que les courriers électroniques sont correctement envoyés aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="62ba7-147">If you decide to override the *From* contact information, you should verify that the emails are correctly sent to users.</span></span> <span data-ttu-id="62ba7-148">Pour cela, vous pouvez le faire en test avec un seul utilisateur au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="62ba7-148">You can do this by testing this with one user in your organization.</span></span>
  
<span data-ttu-id="62ba7-149">Vous pouvez utiliser l’applet de cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) pour gérer d’autres paramètres de votre organisation, notamment la messagerie électronique.</span><span class="sxs-lookup"><span data-stu-id="62ba7-149">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="62ba7-150">Comment procéder si vous ne souhaitez pas leur envoyer de courriers électroniques ?</span><span class="sxs-lookup"><span data-stu-id="62ba7-150">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="62ba7-151">Lorsque vous désactivez l'envoi de courriers électroniques, le courrier électronique ne sera pas envoyé même si l'utilisateur dispose d'une licence.</span><span class="sxs-lookup"><span data-stu-id="62ba7-151">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="62ba7-152">Dans le cas présent, l’ID de conférence, le numéro de téléphone de l’audioconférence par défaut et, plus important encore, le code confidentiel de l’audioconférence ne sera pas envoyé à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="62ba7-152">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="62ba7-153">En pareil cas, vous devez en informer l'utilisateur en lui envoyant un courrier électronique distinct ou en l'appelant.</span><span class="sxs-lookup"><span data-stu-id="62ba7-153">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>
  
<span data-ttu-id="62ba7-154">Par défaut, les courriers électroniques seront envoyés à vos utilisateurs, mais si vous ne souhaitez pas qu’ils en reçoivent pour les conférences audio, vous pouvez utiliser le centre d’administration Skype entreprise ou Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="62ba7-154">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use the Skype for Business admin center or Windows PowerShell.</span></span> 
 
<span data-ttu-id="62ba7-155">![Icône illustrant le logo](../images/sfb-logo-30x30.png)Skype entreprise**dans le centre d’administration Skype entreprise**  </span><span class="sxs-lookup"><span data-stu-id="62ba7-155">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png)  **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="62ba7-156">Dans le **Centre d’administration de Skype entreprise**, dans le volet de navigation gauche, accédez à**paramètres du pont Microsoft** **Conferencing** > .</span><span class="sxs-lookup"><span data-stu-id="62ba7-156">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="62ba7-157">Dans la page **paramètres du pont Microsoft** , activez ou désactivez **Envoyer automatiquement les messages électroniques aux utilisateurs en cas de modification de leurs paramètres de conférence audio**.</span><span class="sxs-lookup"><span data-stu-id="62ba7-157">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their audio conferencing settings change**.</span></span> 
    
3. <span data-ttu-id="62ba7-158">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="62ba7-158">Click **Save**.</span></span> 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
<span data-ttu-id="62ba7-159">**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**</span><span class="sxs-lookup"><span data-stu-id="62ba7-159">**Using Windows PowerShell**</span></span>
  
1. <span data-ttu-id="62ba7-160">Pour désactiver l'envoi de courrier électronique à tous vos utilisateurs, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="62ba7-160">Run the following to disable sending all of your users email:</span></span>
    
   ```
   Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $false
   ```

<span data-ttu-id="62ba7-161">Vous pouvez utiliser l’applet de cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) pour gérer d’autres paramètres de votre organisation, notamment la messagerie électronique.</span><span class="sxs-lookup"><span data-stu-id="62ba7-161">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="62ba7-162">Que devez-vous savoir d'autre sur les courriers électroniques ?</span><span class="sxs-lookup"><span data-stu-id="62ba7-162">What else should you know about this email?</span></span>

- <span data-ttu-id="62ba7-163">Pour plus d'informations sur l'activation et la désactivation automatiques de l'envoi de courriers électroniques à vos utilisateurs, reportez-vous à la rubrique [Activer ou désactiver l'envoi de messages électroniques lorsque modifient les paramètres de conférence Audio](enable-or-disable-sending-emails-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="62ba7-163">For more on enabling and disabling automatically sending email to your users, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
    
- <span data-ttu-id="62ba7-164">Parfois, les utilisateurs perdent leurs informations audio et vous devez être en mesure de leur envoyer des informations audio.</span><span class="sxs-lookup"><span data-stu-id="62ba7-164">Sometimes users lose their audio information and you need to be able to send them all of their audio information to them.</span></span> <span data-ttu-id="62ba7-165">Pour cela, vous pouvez utiliser le centre d’administration Skype entreprise et cliquer sur **Envoyer les informations sur la Conférence par courrier électronique** sous les propriétés de l’audioconférence pour un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="62ba7-165">You can do this by using the Skype for Business admin center and clicking **Send conference info via email** under the audio conferencing properties for a user.</span></span> <span data-ttu-id="62ba7-166">Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="62ba7-166">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span> <span data-ttu-id="62ba7-167">Toutefois, ces informations n’incluent pas le code confidentiel de l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="62ba7-167">However, this information doesn't include the audio conferencing PIN.</span></span>
    
    <span data-ttu-id="62ba7-168">Voici un exemple du courrier électronique qui sera envoyé aux utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="62ba7-168">Here is an example of this email that will be sent to them:</span></span>
    
     ![Courrier électronique de conférence rendez-vous](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="62ba7-170">Comment utiliser Windows PowerShell pour gérer cette fonction ?</span><span class="sxs-lookup"><span data-stu-id="62ba7-170">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="62ba7-171">Par défaut, l’expéditeur des messages électroniques provient d’Office 365, mais vous pouvez modifier l’adresse de messagerie et le nom d’affichage à l’aide de Windows PowerShell et de l’applet [de passe Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) .</span><span class="sxs-lookup"><span data-stu-id="62ba7-171">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span>
    
- <span data-ttu-id="62ba7-p113">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="62ba7-p113">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="62ba7-175">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="62ba7-175">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="62ba7-176">Meilleurs moyens de gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="62ba7-176">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="62ba7-177">Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Office 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="62ba7-177">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="62ba7-178">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="62ba7-178">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="62ba7-179">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="62ba7-179">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="62ba7-180">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="62ba7-180">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="62ba7-181">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="62ba7-181">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="62ba7-p115">Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="62ba7-p115">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="62ba7-184">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="62ba7-184">Related topics</span></span>

[<span data-ttu-id="62ba7-185">Activer ou désactiver l'envoi de messages électroniques lorsque modifient les paramètres de conférence Audio</span><span class="sxs-lookup"><span data-stu-id="62ba7-185">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[<span data-ttu-id="62ba7-186">Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio</span><span class="sxs-lookup"><span data-stu-id="62ba7-186">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)
