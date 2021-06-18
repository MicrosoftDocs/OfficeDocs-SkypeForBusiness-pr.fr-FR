---
title: Options de messagerie électronique en cas de modification des paramètres d’audioconférence
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
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
description: 'Découvrez comment activer ou désactiver Skype d’envoyer des courriers électroniques aux utilisateurs lorsque des paramètres tels que les modifications d’épingle ou le numéro de conférence par défaut changent dans Microsoft Teams. '
ms.openlocfilehash: 17c2864703eafa2c70709da0381f870abba58ad0
ms.sourcegitcommit: 8c2093f7a048a9a56b36e4a3b4c48ae1206c52f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/17/2021
ms.locfileid: "53004166"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="1ca1d-103">Activer ou désactiver l'envoi de courriers électroniques lorsque les paramètres d’audioconférence sont modifiés dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1ca1d-103">Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams</span></span>

<span data-ttu-id="1ca1d-104">Les utilisateurs sont automatiquement avertis par courrier électronique lorsqu’ils sont activés pour l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="1ca1d-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="1ca1d-105">Toutefois, il peut être possible que vous vouliez réduire le nombre de courriers électroniques envoyés à Microsoft Teams utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="1ca1d-105">There may be times, however, when you want to reduce the number of emails that are sent to Microsoft Teams users.</span></span> <span data-ttu-id="1ca1d-106">Dans ce cas, vous pouvez désactiver l’envoi de courriers électroniques.</span><span class="sxs-lookup"><span data-stu-id="1ca1d-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="1ca1d-107">Si vous désactivez l’envoi de courriers électroniques, les messages audioconférences ne seront pas envoyés à vos utilisateurs, y compris les courriers électroniques concernant les moments où les utilisateurs sont activés ou désactivés pour l’audioconférence, lorsque leur code confidentiel est réinitialisé, et lorsque l’ID de conférence et le numéro de téléphone de conférence par défaut changent.</span><span class="sxs-lookup"><span data-stu-id="1ca1d-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="1ca1d-108">Voici un exemple du courrier électronique envoyé aux utilisateurs lorsqu’ils sont activés pour l’audioconférence :</span><span class="sxs-lookup"><span data-stu-id="1ca1d-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Exemple de message électronique d’audioconférence](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="1ca1d-110">Quand les messages électroniques sont-ils envoyés à vos utilisateurs ?</span><span class="sxs-lookup"><span data-stu-id="1ca1d-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="1ca1d-111">Après avoir activé l’audioconférence, plusieurs messages électroniques sont envoyés aux utilisateurs de votre organisation :</span><span class="sxs-lookup"><span data-stu-id="1ca1d-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="1ca1d-112">**Lorsqu’une licence d’audioconférence** leur est affectée.</span><span class="sxs-lookup"><span data-stu-id="1ca1d-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="1ca1d-113">Lorsque vous réinitialisez manuellement le code confidentiel de l’utilisateur pour l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="1ca1d-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="1ca1d-114">Lorsque vous réinitialisez manuellement l'ID de conférence de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1ca1d-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="1ca1d-115">Lorsque la **licence d’audioconférence** leur est retirée.</span><span class="sxs-lookup"><span data-stu-id="1ca1d-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="1ca1d-116">Lorsque le fournisseur de services d’audioconférence d’un utilisateur passe de Microsoft à un autre fournisseur ou à **Aucun.**</span><span class="sxs-lookup"><span data-stu-id="1ca1d-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="1ca1d-117">Lorsque Microsoft est le fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="1ca1d-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="1ca1d-118">Activer ou désactiver l’envoi de courriers électroniques aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="1ca1d-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="1ca1d-119">Vous pouvez utiliser des Microsoft Teams ou Windows PowerShell pour activer ou désactiver le courrier électronique envoyé aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="1ca1d-119">You can use Microsoft Teams or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="1ca1d-120">![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="1ca1d-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="1ca1d-121">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="1ca1d-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="1ca1d-122">En haut de la page Ponts **de** conférence, cliquez sur **Paramètres du pont.**</span><span class="sxs-lookup"><span data-stu-id="1ca1d-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="1ca1d-123">Dans le **volet Paramètres du** pont, activez ou désactivez automatiquement l’envoi de courriers électroniques aux utilisateurs en cas de modification de **leurs paramètres de connexion.**</span><span class="sxs-lookup"><span data-stu-id="1ca1d-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="1ca1d-124">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1ca1d-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="1ca1d-125">**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**</span><span class="sxs-lookup"><span data-stu-id="1ca1d-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="1ca1d-126">Vous pouvez également utiliser le module Microsoft Teams PowerShell et exécuter :</span><span class="sxs-lookup"><span data-stu-id="1ca1d-126">You can also use the Microsoft Teams PowerShell module and run:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

<span data-ttu-id="1ca1d-127">Vous pouvez également utiliser Windows PowerShell et exécuter :[](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings)</span><span class="sxs-lookup"><span data-stu-id="1ca1d-127">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) to manage other settings for your organization, including email.</span></span>

<span data-ttu-id="1ca1d-128">Pour plus [d’informations, Microsoft Teams la référence PowerShell.](/powershell/module/teams/?view=teams-ps)</span><span class="sxs-lookup"><span data-stu-id="1ca1d-128">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="1ca1d-129">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="1ca1d-129">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="1ca1d-130">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="1ca1d-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="1ca1d-131">En Windows PowerShell, vous pouvez gérer vos tâches Microsoft 365 Office 365 d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="1ca1d-131">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="1ca1d-132">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="1ca1d-132">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="1ca1d-133">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="1ca1d-133">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="1ca1d-134">[Meilleurs moyens de gérer Office 365 avec Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="1ca1d-134">[Best ways to manage Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="1ca1d-135">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="1ca1d-135">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="1ca1d-136">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="1ca1d-136">Related topics</span></span>

[<span data-ttu-id="1ca1d-137">Messages électroniques envoyés aux utilisateurs en cas de modification de leurs paramètres d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="1ca1d-137">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="1ca1d-138">Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio</span><span class="sxs-lookup"><span data-stu-id="1ca1d-138">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
