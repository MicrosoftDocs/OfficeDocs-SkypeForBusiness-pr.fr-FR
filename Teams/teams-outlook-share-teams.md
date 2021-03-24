---
title: Partager avec Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: Découvrez la fonctionnalité Partager avec Teams, qui permet aux utilisateurs de partager des e-mails et des pièces jointes à partir d’Outlook dans n’importe quelle conversation ou canal dans Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: af5c2f6029b0c5314c507de7734abf8c479af709
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098220"
---
# <a name="share-to-teams-from-outlook"></a><span data-ttu-id="c8b10-103">Partager dans Teams à partir d’Outlook</span><span class="sxs-lookup"><span data-stu-id="c8b10-103">Share to Teams from Outlook</span></span>

<span data-ttu-id="c8b10-104">Partager avec Teams à partir d’Outlook (Partager avec Teams) permet aux utilisateurs de partager des e-mails, y compris des pièces jointes, à partir d’Outlook vers n’importe quelle conversation ou canal dans Teams.</span><span class="sxs-lookup"><span data-stu-id="c8b10-104">Share to Teams from Outlook (Share to Teams) enables users to share emails, including attachments, from Outlook to any chat or channel in Teams.</span></span>

## <a name="outlook-add-in-for-share-to-teams"></a><span data-ttu-id="c8b10-105">Outlook add-in for Share to Teams</span><span class="sxs-lookup"><span data-stu-id="c8b10-105">Outlook add-in for Share to Teams</span></span> 

<span data-ttu-id="c8b10-106">La fonctionnalité Partager avec Teams nécessite un module pour Outlook.</span><span class="sxs-lookup"><span data-stu-id="c8b10-106">The Share to Teams feature requires an add-in for Outlook.</span></span> <span data-ttu-id="c8b10-107">Ce module est installé automatiquement chaque fois qu’un utilisateur se connecte à l’application Web Teams ou au client de bureau Teams.</span><span class="sxs-lookup"><span data-stu-id="c8b10-107">This add-in is installed automatically whenever a user logs on to either the Teams Web app or the Teams desktop client.</span></span>

> [!NOTE]
> <span data-ttu-id="c8b10-108">N’oubliez pas de passer en revue les [modules add-ins](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) pour Outlook dans Exchange Online et les règles d’accès client [dans Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) pour vous assurer que vos modules pour Outlook fonctionnent correctement.</span><span class="sxs-lookup"><span data-stu-id="c8b10-108">Be sure to review [Add-ins for Outlook in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) and [Client Access Rules in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) to make sure your add-ins for Outlook function correctly.</span></span> <span data-ttu-id="c8b10-109">Par ailleurs, la désactivation des expériences connectées peut empêcher le fonctionnement correct des modules pour Outlook.</span><span class="sxs-lookup"><span data-stu-id="c8b10-109">Also, disabling connected experiences can prevent add-ins for Outlook from working properly.</span></span> <span data-ttu-id="c8b10-110">Pour plus [d’informations, voir](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) Expériences connectées dans Office.</span><span class="sxs-lookup"><span data-stu-id="c8b10-110">See [Connected experiences in Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) for more information.</span></span>  

<span data-ttu-id="c8b10-111">Le partage avec Teams utilise le même mécanisme de transport que lorsqu’un utilisateur envoie un e-mail à un canal.</span><span class="sxs-lookup"><span data-stu-id="c8b10-111">Share to Teams uses the same transport mechanism as when a user emails a channel.</span></span> <span data-ttu-id="c8b10-112">Pour le partage de conversations, les messages électroniques (y compris les pièces jointes) sont copiés dans l’onedrive de l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="c8b10-112">For sharing to chats, emails (including email attachments) are copied to the sender’s OneDrive.</span></span> <span data-ttu-id="c8b10-113">Pour le partage dans les canaux, les messages électroniques et les pièces jointes sont copiés dans le dossier **Messages** électroniques dans SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c8b10-113">For sharing to channels, emails and attachments are copied to the **Email messages** folder in SharePoint.</span></span>

<span data-ttu-id="c8b10-114">Le add-in Outlook pour Partager avec Teams utilise la condition requise définie 1.7, comme détaillé dans la documentation des [add-ins Outlook,](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)qui comprend des détails sur les modules outlook, les conditions requises pour les environnements pour les add-ins Outlook et les clients Outlook spécifiques pris en charge avec l’exigence définie 1.7.</span><span class="sxs-lookup"><span data-stu-id="c8b10-114">The Outlook add-in for Share to Teams uses requirement set 1.7, as detailed in [Outlook add-ins documentation](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook), which includes details on Outlook add-ins, environment requirements for Outlook add-ins, and the specific Outlook clients that are supported with requirement set 1.7.</span></span>

## <a name="enabling-or-disabling-share-to-teams"></a><span data-ttu-id="c8b10-115">Activation ou désactivation du partage dans Teams</span><span class="sxs-lookup"><span data-stu-id="c8b10-115">Enabling or disabling Share to Teams</span></span>

<span data-ttu-id="c8b10-116">Le ajouter Outlook pour partager avec Teams peut être désactivé ou activé de manière sélective pour chaque utilisateur à l’aide des cmdlets PowerShell suivantes.</span><span class="sxs-lookup"><span data-stu-id="c8b10-116">The Outlook add-in for Share to Teams can be selectively disabled or enabled on a per-user basis using the following PowerShell cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="c8b10-117">La désactivation du add-in n’est possible qu’une fois qu’il a été installé.</span><span class="sxs-lookup"><span data-stu-id="c8b10-117">Disabling the add-in is only possible after the add-in has been installed.</span></span> <span data-ttu-id="c8b10-118">Si vous voulez appliquer la désactivation pour tous les utilisateurs de votre client, exécutez un script régulièrement.</span><span class="sxs-lookup"><span data-stu-id="c8b10-118">If you would like to enforce disabling for all users in your tenant, run a script periodically.</span></span>

<span data-ttu-id="c8b10-119">Pour désactiver le add-in pour Outlook utilisé par Partager avec Teams, exécutez [l’cmdlet trouvée ici.](/powershell/module/exchange/disable-app?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="c8b10-119">To disable the add-in for Outlook used by Share to Teams, run the [cmdlet found here](/powershell/module/exchange/disable-app?view=exchange-ps).</span></span> 

<span data-ttu-id="c8b10-120">Pour activer le add-in pour Outlook utilisé par Partager avec Teams, exécutez [l’cmdlet trouvée ici.](/powershell/module/exchange/enable-app?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="c8b10-120">To enable the add-in for Outlook used by Share to Teams, run the [cmdlet found here](/powershell/module/exchange/enable-app?view=exchange-ps).</span></span>

## <a name="browsers-and-single-sign-on"></a><span data-ttu-id="c8b10-121">Navigateurs et sign-on unique</span><span class="sxs-lookup"><span data-stu-id="c8b10-121">Browsers and Single Sign-on</span></span>

<span data-ttu-id="c8b10-122">La fonction Partager avec Teams, dans les clients de bureau Outlook sur le web et Outlook, s’appuie sur un navigateur WebView.</span><span class="sxs-lookup"><span data-stu-id="c8b10-122">Share to Teams, in both Outlook on the web and Outlook desktop clients, relies on a browser WebView.</span></span> <span data-ttu-id="c8b10-123">Pour plus d’informations sur les clients qui utilisent des [navigateurs spécifiques,](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) consultez les navigateurs utilisés par les modules détaillés.</span><span class="sxs-lookup"><span data-stu-id="c8b10-123">See [Browsers used by Office Add-ins](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) for details on which clients use which specific browsers.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="c8b10-124">Le partage avec Teams nécessite que les cookies tiers et l’accès au stockage local soient activés pour les navigateurs des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c8b10-124">Share to Teams requires both third-party cookies and local storage access to be enabled for users' browsers.</span></span>

<span data-ttu-id="c8b10-125">La fonction Partager avec Teams utilise l' single sign-on (SSO), ce qui signifie que les utilisateurs n’ont pas besoin de fournir leurs informations d’identification lorsqu’ils utilisent le add-in via Share to Teams.</span><span class="sxs-lookup"><span data-stu-id="c8b10-125">Share to Teams uses Single Sign-on (SSO), which means users don’t need to provide their credentials when using the add-in via Share to Teams.</span></span> <span data-ttu-id="c8b10-126">L’os SSO pour Outlook sur le web prend en charge les URL de réponse et les prend https://outlook.office365.com/owa/extSSO.aspx https://outlook.office.com/owa/extSSO.aspx en charge par défaut.</span><span class="sxs-lookup"><span data-stu-id="c8b10-126">SSO for Outlook on the web supports https://outlook.office365.com/owa/extSSO.aspx and https://outlook.office.com/owa/extSSO.aspx reply URLs by default.</span></span> <span data-ttu-id="c8b10-127">Pour les domaines personnel, les administrateurs doivent ajouter l’URL de réponse Azure Active Directory appropriée.</span><span class="sxs-lookup"><span data-stu-id="c8b10-127">For vanity domains, administrators need to add the appropriate Azure Active Directory reply URL.</span></span>