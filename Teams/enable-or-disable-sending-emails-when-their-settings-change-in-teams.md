---
title: Activer ou désactiver l'envoi de courriers électroniques lorsque les paramètres d’audioconférence sont modifiés dans Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Cette section explique comment activer ou désactiver dans Skype l’option d’envoi de courriers électroniques lorsque des paramètres tels que le code confidentiel ou le numéro de conférence par défaut sont modifiés. '
ms.openlocfilehash: a59553f26ee39e042fa28d9e58e7f5ae2aae21be
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23892501"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="12235-103">Activer ou désactiver l'envoi de courriers électroniques lorsque les paramètres d’audioconférence sont modifiés dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="12235-103">Enable or disable sending emails when Audio Conferencing settings change</span></span>

<span data-ttu-id="12235-104">Lorsque l’audioconférence est activée pour eux, les utilisateurs sont avertis automatiquement par e-mail.</span><span class="sxs-lookup"><span data-stu-id="12235-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="12235-105">Il peut arriver que vous souhaitiez réduire le nombre de courriers électroniques envoyés aux utilisateurs de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="12235-105">There may be times though when you want to reduce the number of emails that are sent to users, and in that case you can disable this.</span></span> <span data-ttu-id="12235-106">Dans ce cas, vous pouvez désactiver l’envoi de courriers électroniques.</span><span class="sxs-lookup"><span data-stu-id="12235-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="12235-107">Si vous désactivez l'envoi de courriers électroniques, aucun message d’audioconférence n'est envoyé à vos utilisateurs, dont les messages relatifs à l'activation et la désactivation des utilisateurs pour l’audioconférence, la réinitialisation de leur code confidentiel ou la modification de l'ID de conférence ou du numéro de téléphone de conférence par défaut.</span><span class="sxs-lookup"><span data-stu-id="12235-107">If you disable sending emails, all dial-in conferencing emails won't be sent to your users including emails for when users are enabled or disabled for dial-in conferencing, when their PIN is reset, when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="12235-108">Voici un exemple de courrier électronique envoyé aux utilisateurs activés pour l’audioconférence :</span><span class="sxs-lookup"><span data-stu-id="12235-108">Here is an example of the email that is sent to users that are enabled for dial-in conferencing:</span></span>
  
![Courrier électronique d’audioconférence](media/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="12235-110">Quand des messages électroniques sont-ils envoyés à vos utilisateurs ?</span><span class="sxs-lookup"><span data-stu-id="12235-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="12235-111">Plusieurs courriers électroniques sont envoyés aux utilisateurs lorsqu'ils sont activés pour l’audioconférence :</span><span class="sxs-lookup"><span data-stu-id="12235-111">There are several emails that are sent to users in your organization after they are enabled for dial-in conferencing:</span></span>
    
  - <span data-ttu-id="12235-112">Lorsqu'une licence pour l’**Audioconférence** leur est attribuée.</span><span class="sxs-lookup"><span data-stu-id="12235-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="12235-113">Lorsque vous réinitialisez manuellement le code confidentiel d’audioconférence de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="12235-113">When you manually reset the user's dial-in conferencing PIN.</span></span>
    
  - <span data-ttu-id="12235-114">Lorsque vous réinitialisez manuellement l’ID de conférence de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="12235-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="12235-115">Lorsque la licence pour l’**Audioconférence** leur est retirée.</span><span class="sxs-lookup"><span data-stu-id="12235-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="12235-116">Lorsque le fournisseur d’audioconférence d’un utilisateur passe de Microsoft à un autre fournisseur ou à **Aucun** fournisseur.</span><span class="sxs-lookup"><span data-stu-id="12235-116">When the dial-in conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="12235-117">Lorsque le fournisseur d’audioconférence d’un utilisateur est remplacé par Microsoft.</span><span class="sxs-lookup"><span data-stu-id="12235-117">When the dial-in conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="12235-118">Activer ou désactiver l’envoi de courriers électroniques aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="12235-118">Enable or disable email from being sent to audio users</span></span>

<span data-ttu-id="12235-119">Pour activer ou désactiver l’envoi de courriers électroniques aux utilisateurs, vous pouvez utiliser Microsoft Teams ou Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12235-119">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="12235-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Utiliser le Centre d’Administration de Microsoft Teams et de Skype Entreprise :**</span><span class="sxs-lookup"><span data-stu-id="12235-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>
1. <span data-ttu-id="12235-121">Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).</span><span class="sxs-lookup"><span data-stu-id="12235-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="12235-122">En haut de la page **Conference Bridges** (Ponts de conférence), cliquez sur **Bridge Settings** (Paramètres du pont).</span><span class="sxs-lookup"><span data-stu-id="12235-122">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="12235-123">Dans le volet **Bridge settings** (Paramètres du pont), activez ou désactivez l’option **Envoyer automatiquement un courrier électronique aux utilisateurs en cas de modification de leurs paramètres de numérotation**.</span><span class="sxs-lookup"><span data-stu-id="12235-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="12235-124">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="12235-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="12235-125">**Utiliser Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="12235-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="12235-126">Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="12235-126">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="12235-127">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="12235-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="12235-p102">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="12235-p102">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="12235-131">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="12235-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="12235-132">Meilleurs moyens de gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="12235-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="12235-133">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="12235-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="12235-134">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="12235-134">Related topics</span></span>

[<span data-ttu-id="12235-135">Courriers électroniques envoyés aux utilisateurs lorsque leurs paramètres d’audioconférence sont modifiés</span><span class="sxs-lookup"><span data-stu-id="12235-135">Emails sent to users when their settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="12235-136">Envoyer à un utilisateur un courrier électronique qui contient ses informations d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="12235-136">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


