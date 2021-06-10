---
title: Expérience de mise à jour des applications dans Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment mettre à jour les applications dans Microsoft Teams.
ms.openlocfilehash: b39b831b644b19038b8f4574acf3e5bc5c50d73c
ms.sourcegitcommit: 40f76bc6b5e304faea8516a78f8576ba1cdb7f7c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52337824"
---
# <a name="update-apps-in-microsoft-teams"></a><span data-ttu-id="0102d-103">Mettre à jour des applications dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0102d-103">Update apps in Microsoft Teams</span></span>

<span data-ttu-id="0102d-104">Dans la plupart des cas, une fois que les développeurs d’applications publient une mise à jour d’application, la nouvelle version s’affiche automatiquement pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0102d-104">In most cases, after app developers publish an app update, the new version automatically appears for users.</span></span> <span data-ttu-id="0102d-105">Toutefois, certaines mises à jour du manifeste <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams</a> nécessitent l’acceptation des utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="0102d-105">However, there are some updates to the <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="0102d-106">Un robot a été ajouté ou supprimé</span><span class="sxs-lookup"><span data-stu-id="0102d-106">A bot was added or removed</span></span>
* <span data-ttu-id="0102d-107">La propriété « botId » d’un robot existant a été modifiée</span><span class="sxs-lookup"><span data-stu-id="0102d-107">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="0102d-108">La propriété « isNotificationOnly » d’un robot existant a été modifiée</span><span class="sxs-lookup"><span data-stu-id="0102d-108">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="0102d-109">La propriété « SupportsFiles » du bot a été modifiée</span><span class="sxs-lookup"><span data-stu-id="0102d-109">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="0102d-110">Une extension de messagerie a été ajoutée ou supprimée</span><span class="sxs-lookup"><span data-stu-id="0102d-110">A messaging extension was added or removed</span></span>
* <span data-ttu-id="0102d-111">Un nouveau connecteur a été ajouté</span><span class="sxs-lookup"><span data-stu-id="0102d-111">A new connector was added</span></span>
* <span data-ttu-id="0102d-112">Un nouvel onglet statique a été ajouté</span><span class="sxs-lookup"><span data-stu-id="0102d-112">A new static tab was added</span></span>
* <span data-ttu-id="0102d-113">Un nouvel onglet configurable a été ajouté</span><span class="sxs-lookup"><span data-stu-id="0102d-113">A new configurable tab was added</span></span>
* <span data-ttu-id="0102d-114">Propriétés dans « webApplicationInfo » modifiées</span><span class="sxs-lookup"><span data-stu-id="0102d-114">Properties inside "webApplicationInfo" changed</span></span>

![nouvelle version disponible](media/manage-your-custom-apps-update1.png)

![option de mise à niveau pour une application](media/manage-your-custom-apps-update2.png)

> [!NOTE] 
> <span data-ttu-id="0102d-117">Le processus de mise à jour s’applique à toutes les mises à jour d’application pour les applications Microsoft, les applications personnalisées et les applications tierces.</span><span class="sxs-lookup"><span data-stu-id="0102d-117">The update process applies to all app updates for Microsoft apps, custom apps, and third-party apps.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="0102d-118">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="0102d-118">Related topics</span></span>

[<span data-ttu-id="0102d-119">Gérer les applications</span><span class="sxs-lookup"><span data-stu-id="0102d-119">Manage apps</span></span>](manage-apps.md)