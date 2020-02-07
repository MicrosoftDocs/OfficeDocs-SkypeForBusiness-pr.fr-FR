---
title: Activer la traduction de messages en ligne dans Microsoft teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser la traduction incorporée dans Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1926f574977f65181f12ddbb9f0239ad1547d1e5
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836634"
---
<a name="turn-on-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="520e0-103">Activer la traduction de messages en ligne dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="520e0-103">Turn on inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="520e0-104">La traduction de messages incorporés est une nouvelle fonctionnalité de Microsoft Teams, qui permet aux utilisateurs de traduire des messages de teams dans la [langue](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) spécifiée par leurs paramètres de langue personnels pour Office 365.</span><span class="sxs-lookup"><span data-stu-id="520e0-104">Inline message translation is a new Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="520e0-105">La traduction des messages incorporée est déployée par défaut pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="520e0-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="520e0-106">Si vous voulez autoriser les utilisateurs à utiliser cette fonctionnalité dans le client Teams, vous devez activer ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="520e0-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on.</span></span>

> [!NOTE]
><span data-ttu-id="520e0-107">Ce déploiement est exclu des abonnements Office 365 dans le Cloud Office 365 Government Community et les environnements Office 365 Germany.</span><span class="sxs-lookup"><span data-stu-id="520e0-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-on-inline-message-translation"></a><span data-ttu-id="520e0-108">Utiliser PowerShell pour activer la traduction de messages en ligne</span><span class="sxs-lookup"><span data-stu-id="520e0-108">Use PowerShell to turn on inline message translation</span></span>

<span data-ttu-id="520e0-109">Vous pouvez utiliser la stratégie de messagerie pour activer la traduction des messages insérés.</span><span class="sxs-lookup"><span data-stu-id="520e0-109">You can use the messaging policy to turn on the inline message translation.</span></span>

<span data-ttu-id="520e0-110">Activez la stratégie à l’aide de l’applet de cmdlet [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="520e0-110">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="520e0-111">L’application de la stratégie prend quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="520e0-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="520e0-112">Vous devrez peut-être vous déconnecter et vous reconnecter à Teams.</span><span class="sxs-lookup"><span data-stu-id="520e0-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-on-inline-message-translation"></a><span data-ttu-id="520e0-113">Utiliser le centre d’administration de Microsoft teams pour activer la traduction de messages en ligne</span><span class="sxs-lookup"><span data-stu-id="520e0-113">Use the Microsoft Teams admin center to turn on inline message translation</span></span>

<span data-ttu-id="520e0-114">Dans le **Centre d’administration de Microsoft teams**, sélectionnez **stratégies de messagerie** dans le volet de navigation de gauche, puis créez une nouvelle stratégie ou modifiez une stratégie existante et définissez l’option **autoriser les utilisateurs à traduire les messages** sur **activé**.</span><span class="sxs-lookup"><span data-stu-id="520e0-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Allow users to translate messages** option to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="520e0-115">Le service effectue la traduction et le remet au client, sans effet sur le contenu capturé dans les enregistrements de conformité.</span><span class="sxs-lookup"><span data-stu-id="520e0-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="520e0-116">Pour en savoir plus sur la traduction, voir [qu’est-ce que Microsoft Translator ?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span><span class="sxs-lookup"><span data-stu-id="520e0-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>