---
title: Configurer une organisation Exchange hybride à utiliser avec Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: crowe
description: Découvrez comment configurer une organisation Exchange hybride à utiliser avec Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 046b7ab0381391b16a306d36322086882c03f18a
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23849818"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="3ad89-103">Configurer une organisation Exchange hybride à utiliser avec Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3ad89-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="3ad89-p101">En général, il n'est pas nécessaire de configurer des fonctionnalités Exchange Online à utiliser avec Microsoft Teams. Toutefois, dans un scénarion Exchange hybride, des étapes sont requises pour assurer la synchronisation des appartenances de groupe entre Exchange Server (sur site) et Exchange Online. Cela implique l'activation de la fonctionnalité Écriture différée de groupe dans Azure AD Connect avec divers scripts d'initialisation : [Configurer des groupes Office 365 avec Exchange hybride sur site](https://go.microsoft.com/fwlink/?linkid=854389)</span><span class="sxs-lookup"><span data-stu-id="3ad89-p101">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams. However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online. This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389)</span></span>
