---
title: "Configurer une organisation Exchange hybride à utiliser avec Microsoft Teams | Support Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Découvrez comment configurer une organisation Exchange hybride à utiliser avec Microsoft Teams."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 9a046dd3eb2c36e84da913c2aad8b5606f019b04
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2017
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="a111c-103">Configurer une organisation Exchange hybride à utiliser avec Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a111c-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="a111c-p101">En général, il n'est pas nécessaire de configurer des fonctionnalités Exchange Online à utiliser avec Microsoft Teams. Toutefois, dans un scénarion Exchange hybride, des étapes sont requises pour assurer la synchronisation des appartenances de groupe entre Exchange Server (sur site) et Exchange Online. Cela implique l'activation de la fonctionnalité Écriture différée de groupe dans Azure AD Connect avec divers scripts d'initialisation : [Configurer des groupes Office 365 avec Exchange hybride sur site](https://go.microsoft.com/fwlink/?linkid=854389)</span><span class="sxs-lookup"><span data-stu-id="a111c-p101">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams. However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online. This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389)</span></span>
