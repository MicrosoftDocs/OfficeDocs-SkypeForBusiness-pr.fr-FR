---
title: Envoyer à un utilisateur un courrier électronique qui contient ses informations d’audioconférence dans Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords: None
ms.custom:
- Audio Conferencing
description: Envoyez à vos utilisateurs un courrier électronique qui contient leurs informations d’audioconférence dans Microsoft Teams.
ms.openlocfilehash: 85e219481884bb08a2574809b6170c232abccf83
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892091"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a><span data-ttu-id="5344c-103">Envoyer à un utilisateur un courrier électronique qui contient ses informations d’audioconférence dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5344c-103">Send an email to a user with their Audio Conferencing information</span></span>

<span data-ttu-id="5344c-104">Parfois, les utilisateurs de Microsoft Teams peuvent avoir besoin que vous leur envoyiez leurs informations d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="5344c-104">Sometimes users may need you to send them their dial-in conferencing information.</span></span> <span data-ttu-id="5344c-105">Vous pouvez le faire en cliquant sur **Envoyer les informations de la conférence dans un courrier électronique** sous les propriétés d'un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5344c-105">You can do this by using the Skype for Business admin center and clicking **Send conference info via email** under the dial-in properties for a user.</span></span> <span data-ttu-id="5344c-106">Le courrier électronique que vous envoyez contiendra toutes les informations d’audioconférence, dont :</span><span class="sxs-lookup"><span data-stu-id="5344c-106">When you send this email, it will contain all of the dial-in information including:</span></span>
  
- <span data-ttu-id="5344c-107">Le numéro de téléphone de conférence ou le numéro de téléphone à composer pour l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5344c-107">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="5344c-108">L’ID de conférence de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5344c-108">The user's conference ID.</span></span>
    
   
<span data-ttu-id="5344c-109">Voici un exemple de courrier électronique envoyé :</span><span class="sxs-lookup"><span data-stu-id="5344c-109">Here is an example of the email that is sent to users that are enabled for dial-in conferencing:</span></span>
  
![Courrier électronique de conférence rendez-vous](media/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="5344c-111">Envoyer à un utilisateur un courrier électronique qui contient les informations d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="5344c-111">Send an email with audio conferencing information to a user</span></span>

1. <span data-ttu-id="5344c-112">Dans le volet de navigation de gauche, cliquez sur **Utilisateurs** et sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="5344c-112">In the **Skype for Business admin center**, in the left navigation go to Dial-in conferencingDial-in users, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="5344c-113">En haut de la page, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="5344c-113">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="5344c-114">Sous **Audioconférence**, cliquez sur **Envoyer les informations de la conférence dans un courrier électronique**.</span><span class="sxs-lookup"><span data-stu-id="5344c-114">Under **Audio Conferencing**, click **Send conference info in email**.</span></span>


## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="5344c-115">Informations supplémentaires sur ce courrier électronique</span><span class="sxs-lookup"><span data-stu-id="5344c-115">What else should you know about this email?</span></span>

- <span data-ttu-id="5344c-116">Plusieurs courriers électroniques sont envoyés aux utilisateurs lorsqu'ils sont activés pour l’audioconférence :</span><span class="sxs-lookup"><span data-stu-id="5344c-116">There are several emails that are sent to users in your organization after they are enabled for dial-in conferencing:</span></span>
    
  - <span data-ttu-id="5344c-117">Lorsqu'une licence pour l’**Audioconférence** leur est attribuée.</span><span class="sxs-lookup"><span data-stu-id="5344c-117">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="5344c-118">Lorsque vous réinitialisez manuellement le code confidentiel d’audioconférence de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5344c-118">When you manually reset the user's dial-in conferencing PIN.</span></span>
    
  - <span data-ttu-id="5344c-119">Lorsque vous réinitialisez manuellement l’ID de conférence de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5344c-119">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="5344c-120">Lorsqu'une licence pour l’**Audioconférence** leur est retirée.</span><span class="sxs-lookup"><span data-stu-id="5344c-120">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="5344c-121">Lorsque le fournisseur d’audioconférence passe de Microsoft à un autre fournisseur ou à **Aucun** fournisseur.</span><span class="sxs-lookup"><span data-stu-id="5344c-121">When the dial-in conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="5344c-122">Lorsque le fournisseur d’audioconférence d’un utilisateur est remplacé par Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5344c-122">When the dial-in conferencing provider for a user is changed to Microsoft.</span></span>
    
- <span data-ttu-id="5344c-123">Par défaut, l'envoi des courriers électroniques se fera à partir d'Office 365, mais vous pouvez modifier l'adresse électronique et le nom d'affichage à l'aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5344c-123">By default, the sender of the emails will be from Office 365 but you can change the email address and display name using Windows PowerShell and theSet-CsOnlineDialInConferencingTenantSettings cmdlet.</span></span> <span data-ttu-id="5344c-124">Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="5344c-124">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="5344c-125">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="5344c-125">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="5344c-p103">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="5344c-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5344c-129">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="5344c-129">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="5344c-130">Meilleurs moyens de gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5344c-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="5344c-131">Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="5344c-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="5344c-132">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="5344c-132">Related topics</span></span>

[<span data-ttu-id="5344c-133">Tester ou acheter l'audioconférence dans Office 365</span><span class="sxs-lookup"><span data-stu-id="5344c-133">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
