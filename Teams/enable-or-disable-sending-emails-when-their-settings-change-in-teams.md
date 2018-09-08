---
title: Activer ou désactiver l’envoi de messages électroniques lorsque les paramètres de conférence Audio changent dans Microsoft Teams
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
description: 'Découvrez comment activer ou désactiver Skype d’envoyer des messages électroniques aux utilisateurs lorsque les paramètres tels que du code confidentiel change ou les modifications de numéro de conférence par défaut dans Microsoft Teams. '
ms.openlocfilehash: a59553f26ee39e042fa28d9e58e7f5ae2aae21be
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23892501"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="2c49a-103">Activer ou désactiver l’envoi de messages électroniques lorsque les paramètres de conférence Audio changent dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2c49a-103">Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams</span></span>

<span data-ttu-id="2c49a-104">Les utilisateurs sont avertis automatiquement par courrier électronique lorsqu’ils sont activés pour une audioconférence.</span><span class="sxs-lookup"><span data-stu-id="2c49a-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="2c49a-105">Il peut arriver, cependant, lorsque vous souhaitez réduire le nombre de messages électroniques qui sont envoyés aux utilisateurs Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2c49a-105">There may be times, however, when you want to reduce the number of emails that are sent to Microsoft Teams users.</span></span> <span data-ttu-id="2c49a-106">Dans ce cas, vous pouvez désactiver l’envoi de courrier électronique.</span><span class="sxs-lookup"><span data-stu-id="2c49a-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="2c49a-107">Si vous désactivez envoi de courriers électroniques, messages électroniques de conférence Audio ne seront pas envoyées à vos utilisateurs, y compris pour les messages électroniques lorsque les utilisateurs sont activés ou désactivés pour l’audioconférence, leur code confidentiel est réinitialisé et modifications numéros de téléphone de l’ID de conférence et la conférence par défaut .</span><span class="sxs-lookup"><span data-stu-id="2c49a-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="2c49a-108">Voici un exemple du courrier électronique qui est envoyé aux utilisateurs lorsqu’ils sont activés pour une audioconférence :</span><span class="sxs-lookup"><span data-stu-id="2c49a-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Conférence audio par courrier électronique](media/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="2c49a-110">Quand les messages électroniques sont-ils envoyés à vos utilisateurs ?</span><span class="sxs-lookup"><span data-stu-id="2c49a-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="2c49a-111">Il existe plusieurs messages électroniques envoyés aux utilisateurs de votre organisation une fois qu’ils sont activés pour les conférences audio :</span><span class="sxs-lookup"><span data-stu-id="2c49a-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="2c49a-112">Lorsqu’une licence de **Conférence Audio** est attribuée.</span><span class="sxs-lookup"><span data-stu-id="2c49a-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="2c49a-113">Lorsque vous réinitialisez manuellement code confidentiel de conférence audio de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2c49a-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="2c49a-114">Lorsque vous réinitialisez manuellement l'ID de conférence de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2c49a-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="2c49a-115">Lorsque la licence de **Conférence Audio** est supprimée à partir de celles-ci.</span><span class="sxs-lookup"><span data-stu-id="2c49a-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="2c49a-116">Lorsque le fournisseur de services d’audioconférence d’un utilisateur est modifié à partir de Microsoft vers un autre fournisseur ou **Aucun**.</span><span class="sxs-lookup"><span data-stu-id="2c49a-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="2c49a-117">Lorsque le fournisseur de services d’audioconférence d’un utilisateur est remplacé par Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2c49a-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="2c49a-118">Activer ou désactiver la messagerie d’être envoyés aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="2c49a-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="2c49a-119">Vous pouvez utiliser Microsoft Teams ou Windows PowerShell pour activer ou désactiver le courrier envoyé aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="2c49a-119">You can use Microsoft Teams or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="2c49a-120">![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="2c49a-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>
1. <span data-ttu-id="2c49a-121">Dans la navigation de gauche, accédez à des **réunions** > **Ponts de conférence**.</span><span class="sxs-lookup"><span data-stu-id="2c49a-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="2c49a-122">En haut de la page de **Ponts de conférence** , cliquez sur **paramètres du pont**.</span><span class="sxs-lookup"><span data-stu-id="2c49a-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="2c49a-123">Dans le volet **paramètres du pont** , activez ou désactivez **Envoyer automatiquement des messages électroniques aux utilisateurs si leurs paramètres de connexion à modifient**.</span><span class="sxs-lookup"><span data-stu-id="2c49a-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="2c49a-124">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="2c49a-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="2c49a-125">**Utilisation de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="2c49a-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="2c49a-126">Voir la [référence PowerShell d’équipes Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="2c49a-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="2c49a-127">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="2c49a-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="2c49a-p102">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="2c49a-p102">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="2c49a-131">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="2c49a-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="2c49a-132">Six raisons d'utiliser Windows PowerShell pour gérer Office 365 </span><span class="sxs-lookup"><span data-stu-id="2c49a-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="2c49a-133">Pour plus d’informations sur Windows PowerShell, voir la [référence PowerShell d’équipes Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="2c49a-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="2c49a-134">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="2c49a-134">Related topics</span></span>

[<span data-ttu-id="2c49a-135">Messages électroniques envoyés aux utilisateurs lorsque modifient leurs paramètres de conférence Audio</span><span class="sxs-lookup"><span data-stu-id="2c49a-135">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="2c49a-136">Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio</span><span class="sxs-lookup"><span data-stu-id="2c49a-136">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


