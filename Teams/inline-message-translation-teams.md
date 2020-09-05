---
title: Activer la traduction de messages en ligne
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
description: Découvrez comment activer la traduction intraligne dans Microsoft teams à l’aide du centre d’administration Microsoft teams ou de PowerShell.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 012f2431ec7fb249a2f2e3b963c41166c4649a5c
ms.sourcegitcommit: 2e6b0930645cd97dbd597e9346a6fe1788c6facf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/04/2020
ms.locfileid: "47395383"
---
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="18a74-103">Désactiver la traduction de messages en ligne dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="18a74-103">Turn off inline message translation in Microsoft Teams</span></span>
=================================================

<span data-ttu-id="18a74-104">La traduction de messages en ligne est une fonctionnalité Microsoft teams qui permet aux utilisateurs de traduire des messages de teams dans la [langue](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) spécifiée par leurs paramètres de langue personnels.</span><span class="sxs-lookup"><span data-stu-id="18a74-104">Inline message translation is a Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings.</span></span>

<span data-ttu-id="18a74-105">La traduction de messages incluse est déployée par défaut pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="18a74-105">Inline message translation is rolled out by default for your organization.</span></span> <span data-ttu-id="18a74-106">Vous n’avez pas besoin d’apporter des modifications si vous voulez autoriser les utilisateurs à utiliser cette fonctionnalité dans le client Teams.</span><span class="sxs-lookup"><span data-stu-id="18a74-106">You don't need to make changes if you want to allow users to use this feature within the Teams client.</span></span>

> [!NOTE]
><span data-ttu-id="18a74-107">Ce déploiement est exclu des abonnements Office 365 dans le Cloud Office 365 Government Community et les environnements Office 365 Germany.</span><span class="sxs-lookup"><span data-stu-id="18a74-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-off-inline-message-translation"></a><span data-ttu-id="18a74-108">Utiliser PowerShell pour désactiver la traduction de messages en ligne</span><span class="sxs-lookup"><span data-stu-id="18a74-108">Use PowerShell to turn off inline message translation</span></span>

<span data-ttu-id="18a74-109">Vous pouvez utiliser la stratégie de messagerie pour désactiver la traduction de messages insérés.</span><span class="sxs-lookup"><span data-stu-id="18a74-109">You can use the messaging policy to turn off the inline message translation.</span></span>

<span data-ttu-id="18a74-110">Désactivez la stratégie à l’aide de l’applet de connexion [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="18a74-110">Turn off the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="18a74-111">L’application de la stratégie prend quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="18a74-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="18a74-112">Vous devrez peut-être vous déconnecter et vous reconnecter à Teams.</span><span class="sxs-lookup"><span data-stu-id="18a74-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a><span data-ttu-id="18a74-113">Utiliser le centre d’administration de Microsoft teams pour désactiver la traduction de messages en ligne</span><span class="sxs-lookup"><span data-stu-id="18a74-113">Use the Microsoft Teams admin center to turn off inline message translation</span></span>

<span data-ttu-id="18a74-114">Dans le **Centre d’administration de Microsoft teams**, sélectionnez **stratégies de messagerie** dans le volet de navigation de gauche, puis créez une nouvelle stratégie ou modifiez une stratégie existante et définissez l’option **traduire les messages** sur **Désactiver**.</span><span class="sxs-lookup"><span data-stu-id="18a74-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Translate messages** option to **Off**.</span></span>

> [!NOTE]
> <span data-ttu-id="18a74-115">Le service effectue la traduction et le remet au client, sans effet sur le contenu capturé dans les enregistrements de conformité.</span><span class="sxs-lookup"><span data-stu-id="18a74-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="18a74-116">Pour en savoir plus sur la traduction, voir [qu’est-ce que Microsoft Translator ?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)</span><span class="sxs-lookup"><span data-stu-id="18a74-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)</span></span>
