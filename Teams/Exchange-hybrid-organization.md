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
description: Découvrez comment configurer une organisation Exchange hybride à utiliser avec Microsoft Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f1a59c01fa112294d771dc6f8d08f32a3c7a4f19
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136514"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="cf7cf-103">Configurer une organisation Exchange hybride à utiliser avec Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cf7cf-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="cf7cf-p101">En règle générale, vous n’avez pas besoin de configurer une fonctionnalité Exchange Online à utiliser avec Microsoft Teams. Toutefois, pour les scénarios Exchange hybrides, il existe certaines étapes nécessaires pour garantir la synchronisation des appartenances aux groupes entre Exchange Server (local) et Exchange Online. Pour cela, il est nécessaire d’activer la fonctionnalité d’écriture différée de groupe dans Azure AD Connect avec différents scripts d’initialisation : [configurer les groupes Office 365 avec Exchange hybride local](https://go.microsoft.com/fwlink/?linkid=854389).</span><span class="sxs-lookup"><span data-stu-id="cf7cf-p101">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams. However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online. This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389).</span></span>
