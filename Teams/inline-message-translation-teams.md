---
title: Utiliser la traduction des messages incorporée dans Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/16/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser la traduction incorporée dans Microsoft Teams.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9097e7421bb65b1a9ce0900df097080a6cfc2023
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016836"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="98457-103">Utiliser la traduction des messages incorporée dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="98457-103">Use inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="98457-104">La traduction des messages incorporée est une nouvelle fonctionnalité de Microsoft Teams, qui permet aux utilisateurs de traduire automatiquement les messages Teams dans la [langue](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) spécifiée par leurs paramètres de langue personnels pour Office 365.</span><span class="sxs-lookup"><span data-stu-id="98457-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="98457-105">Traduction des messages incorporés est déployée par défaut pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="98457-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="98457-106">Si vous souhaitez autoriser les utilisateurs à utiliser cette fonctionnalité dans le client d’équipes, vous devez activer ce paramètre à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="98457-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on by using PowerShell.</span></span> <span data-ttu-id="98457-107">Actuellement, cette option n’est pas disponible dans le Microsoft Teams et Skype entreprise centre d’administration, mais sera bientôt.</span><span class="sxs-lookup"><span data-stu-id="98457-107">Currently, this option is not available in the Microsoft Teams and Skype for Business Admin Center, but will be soon.</span></span>

> [!NOTE]
><span data-ttu-id="98457-108">Ce déploiement est exclu des abonnements Office 365 dans notre cloud communautaire pour le service public Office 365 et dans les environnements Office 365 en Allemagne.</span><span class="sxs-lookup"><span data-stu-id="98457-108">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span> 

## <a name="enable-by-using-powershell"></a><span data-ttu-id="98457-109">Activer à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="98457-109">Enable by using PowerShell</span></span>

<span data-ttu-id="98457-110">Vous pouvez activer la fonctionnalité de traduction des messages incorporée en utilisant la stratégie de messagerie.</span><span class="sxs-lookup"><span data-stu-id="98457-110">You can turn on the inline message translation feature by using the Messaging Policy.</span></span> 

1. <span data-ttu-id="98457-111">Activez la stratégie à l’aide de l’applet de commande [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="98457-111">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span>
2. <span data-ttu-id="98457-112">La stratégie prend quelques minutes à appliquer.</span><span class="sxs-lookup"><span data-stu-id="98457-112">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="98457-113">Vous devrez vous déconnecter et vous reconnecter aux équipes des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="98457-113">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="enable-by-using-the-teams-admin-center"></a><span data-ttu-id="98457-114">Activer en utilisant le Centre d’administration de Teams</span><span class="sxs-lookup"><span data-stu-id="98457-114">Enable by using the Teams Admin Center</span></span>

<span data-ttu-id="98457-115">L’option permettant d’activer la fonctionnalité de traduction des messages iincorporée à l’aide du Centre d’administration de Teams sera disponible prochainement.</span><span class="sxs-lookup"><span data-stu-id="98457-115">The option to turn on the inline message translation feature by using the Teams Admin Center is coming soon.</span></span>

> [!NOTE]
><span data-ttu-id="98457-116">Traduction est strictement côté client et n’a aucun effet sur le contenu capturé dans les enregistrements de conformité.</span><span class="sxs-lookup"><span data-stu-id="98457-116">Translation is strictly client-side and has no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="98457-117">Pour plus d’informations sur la traduction, voir [What ' s Microsoft Translator ?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span><span class="sxs-lookup"><span data-stu-id="98457-117">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>