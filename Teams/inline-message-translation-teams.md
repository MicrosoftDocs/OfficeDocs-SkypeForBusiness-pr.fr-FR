---
title: Utiliser la traduction en ligne d’un message dans Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/16/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: salilda
localization_priority: Priority
search.appverid: MET150
description: Découvrez comment utiliser Microsoft Teams traduction en ligne.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb7876d015fb736785fdaab99b1ed71b8e05b9dc
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23855820"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="8a2dc-103">Utiliser la traduction en ligne d’un message dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8a2dc-103">Use inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="8a2dc-104">Traduction en ligne d’un message est une nouvelle fonctionnalité Teams Microsoft qui permet aux utilisateurs de traduire automatiquement des messages d’équipes dans la [langue](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) spécifiée par leurs paramètres personnels de langue pour Office 365.</span><span class="sxs-lookup"><span data-stu-id="8a2dc-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="8a2dc-105">Traduction des messages incorporés est déployée par défaut pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8a2dc-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="8a2dc-106">Si vous souhaitez autoriser les utilisateurs à utiliser cette fonctionnalité dans le client d’équipes, vous devez activer ce paramètre à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a2dc-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on by using PowerShell.</span></span> <span data-ttu-id="8a2dc-107">Actuellement, cette option n’est pas disponible dans le Microsoft Teams et Skype entreprise centre d’administration, mais sera bientôt.</span><span class="sxs-lookup"><span data-stu-id="8a2dc-107">Currently, this option is not available in the Microsoft Teams and Skype for Business Admin Center, but will be soon.</span></span>

> [!NOTE]
><span data-ttu-id="8a2dc-108">Ce déploiement est exclu des abonnements Office 365 dans les environnements de notre nuage de la Communauté Office 365 pour le gouvernement et Office 365 Allemagne.</span><span class="sxs-lookup"><span data-stu-id="8a2dc-108">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span> 

## <a name="enable-by-using-powershell"></a><span data-ttu-id="8a2dc-109">Activer à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a2dc-109">Enable by using PowerShell</span></span>

<span data-ttu-id="8a2dc-110">Vous pouvez activer la fonctionnalité de traduction de messages incorporés à l’aide de la stratégie de messagerie.</span><span class="sxs-lookup"><span data-stu-id="8a2dc-110">You can turn on the inline message translation feature by using the Messaging Policy.</span></span> 

1. <span data-ttu-id="8a2dc-111">Activer la stratégie à l’aide de l’applet de commande [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="8a2dc-111">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span>
2. <span data-ttu-id="8a2dc-112">La stratégie prend quelques minutes à appliquer.</span><span class="sxs-lookup"><span data-stu-id="8a2dc-112">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="8a2dc-113">Vous devrez vous déconnecter et vous reconnecter aux équipes des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8a2dc-113">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="enable-by-using-the-teams-admin-center"></a><span data-ttu-id="8a2dc-114">Activer à l’aide du centre d’administration équipes</span><span class="sxs-lookup"><span data-stu-id="8a2dc-114">Enable by using the Teams Admin Center</span></span>

<span data-ttu-id="8a2dc-115">L’option pour activer la fonctionnalité de traduction de messages incorporés à l’aide du centre d’administration équipes seront prochainement disponibles.</span><span class="sxs-lookup"><span data-stu-id="8a2dc-115">The option to turn on the inline message translation feature by using the Teams Admin Center is coming soon.</span></span>

> [!NOTE]
><span data-ttu-id="8a2dc-116">Traduction est strictement côté client et n’a aucun effet sur le contenu capturé dans les enregistrements de conformité.</span><span class="sxs-lookup"><span data-stu-id="8a2dc-116">Translation is strictly client-side and has no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="8a2dc-117">Pour plus d’informations sur la traduction, voir [What ' s Microsoft Translator ?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span><span class="sxs-lookup"><span data-stu-id="8a2dc-117">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>