---
title: Utiliser la traduction des messages incorporée dans Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser la traduction incorporée dans Microsoft Teams.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58e6fb04dd015e939125b75d604fe9692a32c0e2
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30459907"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="63dc3-103">Utiliser la traduction des messages incorporée dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="63dc3-103">Use inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="63dc3-104">La traduction des messages incorporée est une nouvelle fonctionnalité de Microsoft Teams, qui permet aux utilisateurs de traduire automatiquement les messages Teams dans la [langue](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) spécifiée par leurs paramètres de langue personnels pour Office 365.</span><span class="sxs-lookup"><span data-stu-id="63dc3-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="63dc3-105">La traduction des messages incorporée est déployée par défaut pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="63dc3-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="63dc3-106">Si vous souhaitez autoriser les utilisateurs à utiliser cette fonctionnalité dans le client d’équipes, vous devez activer ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="63dc3-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on.</span></span>

> [!NOTE]
><span data-ttu-id="63dc3-107">Ce déploiement est exclu des abonnements Office 365 dans les environnements de notre nuage de la Communauté Office 365 pour le gouvernement et Office 365 Allemagne.</span><span class="sxs-lookup"><span data-stu-id="63dc3-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="enable-by-using-powershell"></a><span data-ttu-id="63dc3-108">Activer à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="63dc3-108">Enable by using PowerShell</span></span>

<span data-ttu-id="63dc3-109">Vous pouvez activer la fonctionnalité de traduction de messages incorporés à l’aide de la stratégie de messagerie.</span><span class="sxs-lookup"><span data-stu-id="63dc3-109">You can turn on the inline message translation feature by using the Messaging Policy.</span></span>

1. <span data-ttu-id="63dc3-110">Activer la stratégie à l’aide de l’applet de commande [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="63dc3-110">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span>
2. <span data-ttu-id="63dc3-111">La stratégie prend quelques minutes à appliquer.</span><span class="sxs-lookup"><span data-stu-id="63dc3-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="63dc3-112">Vous devrez vous déconnecter et vous reconnecter aux équipes des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="63dc3-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="enable-by-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="63dc3-113">Activer à l’aide du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="63dc3-113">Enable by using the Microsoft Teams admin center</span></span>

<span data-ttu-id="63dc3-114">Dans le **Centre d’administration de Microsoft équipes**, sélectionnez **Stratégies de messagerie** dans la barre de gauche, soit créer une nouvelle stratégie ou modifier une stratégie existante, puis définissez l’option **Autoriser les utilisateurs à convertir des messages** **sur**.</span><span class="sxs-lookup"><span data-stu-id="63dc3-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left-hand bar, then either create a new policy or edit an existing policy, and set the **Allow users to translate messages** option to **On**.</span></span>

> [!NOTE]
><span data-ttu-id="63dc3-115">Traduction est effectuée par le service et remise au client avec aucun effet sur le contenu capturé dans les enregistrements de conformité.</span><span class="sxs-lookup"><span data-stu-id="63dc3-115">Translation is done by the service and delivered to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="63dc3-116">Pour plus d’informations sur la traduction, voir [What ' s Microsoft Translator ?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span><span class="sxs-lookup"><span data-stu-id="63dc3-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>