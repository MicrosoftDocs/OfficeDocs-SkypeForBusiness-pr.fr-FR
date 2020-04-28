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
description: Apprenez à configurer une organisation Exchange hybride à utiliser avec Microsoft teams pour garantir la synchronisation des appartenances aux groupes.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ee558c8c8bfa6c5bd66e001d31ed76a8061df3f4
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43902959"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="17d3f-103">Configurer une organisation Exchange hybride à utiliser avec Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="17d3f-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="17d3f-p101">En règle générale, vous n’avez pas besoin de configurer une fonctionnalité Exchange Online à utiliser avec Microsoft Teams. Toutefois, pour les scénarios Exchange hybrides, il existe certaines étapes nécessaires pour garantir la synchronisation des appartenances aux groupes entre Exchange Server (local) et Exchange Online. Pour cela, vous devez activer la fonctionnalité d’écriture différée de groupe dans Azure AD Connect avec différents scripts d’initialisation : [configurer des groupes Microsoft 365 avec Exchange hybride local](https://go.microsoft.com/fwlink/?linkid=854389).</span><span class="sxs-lookup"><span data-stu-id="17d3f-p101">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams. However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online. This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Microsoft 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389).</span></span>
