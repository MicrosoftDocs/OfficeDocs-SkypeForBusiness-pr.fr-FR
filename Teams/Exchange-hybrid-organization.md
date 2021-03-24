---
title: Configurer une organisation Exchange hybride
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Découvrez comment configurer une organisation Exchange hybride pour l’utiliser avec Microsoft Teams pour vous assurer que les appartenances aux groupes sont synchronisées.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 90250b3d3f3593990d356843bebea324060d6f8b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094606"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="8a93c-103">Configurer une organisation Exchange hybride à utiliser avec Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8a93c-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="8a93c-104">En règle générale, vous ne devez configurer aucune fonctionnalité Exchange Online pour une utilisation avec Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8a93c-104">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams.</span></span> <span data-ttu-id="8a93c-105">Toutefois, pour les scénarios Exchange hybrides, il existe des étapes nécessaires pour s’assurer que les appartenances aux groupes sont synchronisées entre Exchange Server (local) et Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8a93c-105">However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online.</span></span> <span data-ttu-id="8a93c-106">Cela implique l’enablement de la fonctionnalité de écriture de groupe dans Azure AD Connect, ainsi que divers scripts d’initialisation : Configurer des groupes [Microsoft 365](/exchange/hybrid-deployment/set-up-microsoft-365-groups)avec un environnement Exchange hybride local.</span><span class="sxs-lookup"><span data-stu-id="8a93c-106">This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Microsoft 365 Groups with on-premises Exchange hybrid](/exchange/hybrid-deployment/set-up-microsoft-365-groups).</span></span>