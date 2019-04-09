---
title: Problèmes connus pour les stratégies de rétention dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: anach
description: Liste actuelle des problèmes connus pour les stratégies de rétention Teams Microsoft.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dca7decd2c3c051c0d56a14e2a2d1485b777f92e
ms.sourcegitcommit: 58fec9aebd80029e1f1e71376efe222f9abf707e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "31517062"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a><span data-ttu-id="de016-103">Problèmes connus pour les stratégies de rétention dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="de016-103">Known issues for retention policies in Microsoft Teams</span></span>

<span data-ttu-id="de016-104">Les éléments suivants sont des problèmes pour les stratégies de rétention dans les équipes qui sont en cours suivis et analysés.</span><span class="sxs-lookup"><span data-stu-id="de016-104">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="de016-105">Sous Choisissez les équipes dans la ligne d’emplacement de messages canal équipes, vous pouvez voir les équipes pas également Office 365 les groupes.</span><span class="sxs-lookup"><span data-stu-id="de016-105">Under Choose Teams in the Teams Channel messages location row, you may see Office 365 Groups that are not also Teams.</span></span> <span data-ttu-id="de016-106">Cela sera traité ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="de016-106">This will be addressed in the future.</span></span>

- <span data-ttu-id="de016-107">Sous Choisir les utilisateurs dans la ligne emplacement équipes conversation, vous pouvez voir les invités et les utilisateurs non-mailbox.</span><span class="sxs-lookup"><span data-stu-id="de016-107">Under Choose Users in the Teams Chat location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="de016-108">Stratégies de rétention ne sont pas destinés à définir pour les visiteurs et nous effectuons fonctionne pour les supprimer de la liste.</span><span class="sxs-lookup"><span data-stu-id="de016-108">Retention policies are not meant to be set for guests, and we are working to remove these from the list.</span></span>

- <span data-ttu-id="de016-109">Assistant de Cycle de vie Exchange (ELC) s’exécute tous les jours, mais il a un SLA de 7 jours.</span><span class="sxs-lookup"><span data-stu-id="de016-109">Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days.</span></span> <span data-ttu-id="de016-110">Par conséquent, il est possible que, si vous disposez d’une stratégie de rétention les équipes à supprimer les éléments antérieurs à 60 jours, ces éléments peuvent conserver 67 jours.</span><span class="sxs-lookup"><span data-stu-id="de016-110">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="de016-111">Ce n’est pas une situation nouvelle : elle suit le modèle Exchange.</span><span class="sxs-lookup"><span data-stu-id="de016-111">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="de016-112">Bien sûr, dans la plupart des cas, il n’existe aucun délai.</span><span class="sxs-lookup"><span data-stu-id="de016-112">Of course, in most cases, there is no delay.</span></span>


| | | |
|---------|---------|---------|
|![Icône Point de décision.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |<span data-ttu-id="de016-114">Point de décision</span><span class="sxs-lookup"><span data-stu-id="de016-114">Decision point</span></span>         |<span data-ttu-id="de016-p104">De quelles fonctionnalités de sécurité et de conformité votre organisation a-t-elle besoin ? Votre organisation dispose-t-elle des licences requises pour satisfaire les besoins en matière de sécurité et de conformité ?</span><span class="sxs-lookup"><span data-stu-id="de016-p104">What security and compliance features does your organization require? Does your organization have the required licenses to meet Security and Compliance business requirements?</span></span>         |
|![Icône Étapes suivantes.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |<span data-ttu-id="de016-118">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="de016-118">Next steps</span></span>         |<span data-ttu-id="de016-119">Documenter vos fonctionnalités de sécurité et de conformité requises.</span><span class="sxs-lookup"><span data-stu-id="de016-119">Document your required security and compliance features.</span></span>         |
