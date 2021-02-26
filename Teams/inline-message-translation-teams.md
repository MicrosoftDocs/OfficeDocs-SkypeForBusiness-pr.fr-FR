---
title: Activer la traduction incorporée des messages
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
description: Découvrez comment activer la traduction incorporée dans Microsoft Teams à l’aide du Centre d’administration Microsoft Teams ou de PowerShell.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 012f2431ec7fb249a2f2e3b963c41166c4649a5c
ms.sourcegitcommit: 2e6b0930645cd97dbd597e9346a6fe1788c6facf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/04/2020
ms.locfileid: "47395383"
---
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="d99a8-103">Désactiver la traduction incorporée des messages dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d99a8-103">Turn off inline message translation in Microsoft Teams</span></span>
=================================================

<span data-ttu-id="d99a8-104">La traduction incorporée des messages est une fonctionnalité de Microsoft Teams qui permet aux utilisateurs de traduire les messages des équipes dans la [langue](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) spécifiée par leurs paramètres linguistiques personnels.</span><span class="sxs-lookup"><span data-stu-id="d99a8-104">Inline message translation is a Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings.</span></span>

<span data-ttu-id="d99a8-105">La traduction incorporée des messages est déployée par défaut pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d99a8-105">Inline message translation is rolled out by default for your organization.</span></span> <span data-ttu-id="d99a8-106">Vous n’avez pas besoin d’apporter de modifications si vous souhaitez autoriser les utilisateurs à utiliser cette fonctionnalité dans le client Teams.</span><span class="sxs-lookup"><span data-stu-id="d99a8-106">You don't need to make changes if you want to allow users to use this feature within the Teams client.</span></span>

> [!NOTE]
><span data-ttu-id="d99a8-107">Ce déploiement ne fait pas partie des abonnements Office 365 dans nos environnements Office 365 GCC et Office 365 Germany.</span><span class="sxs-lookup"><span data-stu-id="d99a8-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-off-inline-message-translation"></a><span data-ttu-id="d99a8-108">Utiliser PowerShell pour désactiver la traduction incorporée des messages</span><span class="sxs-lookup"><span data-stu-id="d99a8-108">Use PowerShell to turn off inline message translation</span></span>

<span data-ttu-id="d99a8-109">Vous pouvez utiliser la stratégie de messagerie pour désactiver la traduction incorporée des messages.</span><span class="sxs-lookup"><span data-stu-id="d99a8-109">You can use the messaging policy to turn off the inline message translation.</span></span>

<span data-ttu-id="d99a8-110">Désactiver la stratégie à l’aide de la cmdlet [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d99a8-110">Turn off the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="d99a8-111">L’application de cette stratégie prend quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="d99a8-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="d99a8-112">Les utilisateurs devront peut-être se déconnecter, puis se reconnecter à Teams.</span><span class="sxs-lookup"><span data-stu-id="d99a8-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a><span data-ttu-id="d99a8-113">Utiliser le Centre d'administration Microsoft Teams pour désactiver la traduction incorporée des messages dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d99a8-113">Use the Microsoft Teams admin center to turn off inline message translation</span></span>

<span data-ttu-id="d99a8-114">Dans le **Centre d’administration Microsoft Teams**, sélectionnez **Stratégies de messagerie** dans le menu de navigation gauche, créez une stratégie ou modifiez une stratégie existante, puis définissez l’option **Traduire les messages** sur **Off**.</span><span class="sxs-lookup"><span data-stu-id="d99a8-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Translate messages** option to **Off**.</span></span>

> [!NOTE]
> <span data-ttu-id="d99a8-115">Le service effectue, puis livre la traduction au client sans effet sur le contenu capturé dans les enregistrements de conformité.</span><span class="sxs-lookup"><span data-stu-id="d99a8-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="d99a8-116">Si vous souhaitez en savoir plus sur la traduction, veuillez consulter la rubrique [Qu’est-ce que Microsoft Translator ?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)</span><span class="sxs-lookup"><span data-stu-id="d99a8-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)</span></span>
