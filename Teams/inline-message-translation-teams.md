---
title: Utiliser la traduction des messages incorporée dans Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 10/30/2018
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
ms.openlocfilehash: 69c6e8046b185cc8dbc85ac0c99dc5b4cfa6fe2a
ms.sourcegitcommit: bb3f235265cddae9578ec1bf605c4edc7f14fb30
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2018
ms.locfileid: "25851567"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="990ea-103">Utiliser la traduction des messages incorporée dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="990ea-103">Use inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="990ea-104">La traduction des messages incorporée est une nouvelle fonctionnalité de Microsoft Teams, qui permet aux utilisateurs de traduire automatiquement les messages Teams dans la [langue](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) spécifiée par leurs paramètres de langue personnels pour Office 365.</span><span class="sxs-lookup"><span data-stu-id="990ea-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="990ea-105">La traduction des messages incorporée est déployée par défaut pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="990ea-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="990ea-106">Si vous souhaitez autoriser les utilisateurs à utiliser cette fonctionnalité dans le client Teams, vous devez activer ce paramètre à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="990ea-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on by using PowerShell.</span></span> <span data-ttu-id="990ea-107">Cette option n’est pas disponible actuellement dans le Centre d’administration de Microsoft Teams et Skype Entreprise, mais elle le sera prochainement.</span><span class="sxs-lookup"><span data-stu-id="990ea-107">Currently, this option is not available in the Microsoft Teams and Skype for Business Admin Center, but will be soon.</span></span>

> [!NOTE]
><span data-ttu-id="990ea-108">Ce déploiement est exclu des abonnements Office 365 dans notre cloud communautaire pour le service public Office 365 et dans les environnements Office 365 en Allemagne.</span><span class="sxs-lookup"><span data-stu-id="990ea-108">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span> 

## <a name="enable-by-using-powershell"></a><span data-ttu-id="990ea-109">Activer à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="990ea-109">Enable by using PowerShell</span></span>

<span data-ttu-id="990ea-110">Vous pouvez activer la fonctionnalité de traduction des messages incorporée en utilisant la stratégie de messagerie.</span><span class="sxs-lookup"><span data-stu-id="990ea-110">You can turn on the inline message translation feature by using the Messaging Policy.</span></span> 

1. <span data-ttu-id="990ea-111">Activez la stratégie à l’aide de l’applet de commande [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="990ea-111">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span>
2. <span data-ttu-id="990ea-112">L’application de la stratégie prend quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="990ea-112">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="990ea-113">Les utilisateurs devront peut-être se déconnecter et se reconnecter à Teams.</span><span class="sxs-lookup"><span data-stu-id="990ea-113">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="enable-by-using-the-microsoft-teams--skype-for-business-admin-center"></a><span data-ttu-id="990ea-114">Activer à l’aide du Microsoft Teams & Skype entreprise centre d’administration</span><span class="sxs-lookup"><span data-stu-id="990ea-114">Enable by using the Microsoft Teams & Skype for Business Admin Center</span></span>

<span data-ttu-id="990ea-115">L’option pour activer la fonctionnalité de traduction en ligne message avec le modèle Microsoft Teams & Skype entreprise centre d’administration seront prochainement disponibles.</span><span class="sxs-lookup"><span data-stu-id="990ea-115">The option to turn on the inline message translation feature using the Microsoft Teams & Skype for Business Admin Center is coming soon.</span></span>

> [!NOTE]
><span data-ttu-id="990ea-116">La traduction ne s’applique que du côté client et n’a aucune incidence sur le contenu capturé dans les enregistrements de conformité.</span><span class="sxs-lookup"><span data-stu-id="990ea-116">Translation is strictly client-side and has no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="990ea-117">Pour en savoir plus sur la traduction, reportez-vous à la section [Qu’est-ce que Microsoft Translator ?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span><span class="sxs-lookup"><span data-stu-id="990ea-117">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>