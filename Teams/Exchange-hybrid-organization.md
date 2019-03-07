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
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e52c757b3e2456561d664b07667a5f08fd1c1617
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30458931"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="eb1fc-103">Configurer une organisation Exchange hybride à utiliser avec Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="eb1fc-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="eb1fc-p101">En général, il n'est pas nécessaire de configurer des fonctionnalités Exchange Online à utiliser avec Microsoft Teams. Toutefois, dans un scénarion Exchange hybride, des étapes sont requises pour assurer la synchronisation des appartenances de groupe entre Exchange Server (sur site) et Exchange Online. Cela implique l'activation de la fonctionnalité Écriture différée de groupe dans Azure AD Connect avec divers scripts d'initialisation : [Configurer des groupes Office 365 avec Exchange hybride sur site](https://go.microsoft.com/fwlink/?linkid=854389)</span><span class="sxs-lookup"><span data-stu-id="eb1fc-p101">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams. However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online. This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389)</span></span>
