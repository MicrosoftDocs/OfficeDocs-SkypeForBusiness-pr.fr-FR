---
title: Problèmes connus pour les stratégies de rétention dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: anach
description: Liste actuelle des problèmes connus pour les stratégies de rétention de Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 38fd76bff3309655cb7d2fa1f0acf18559f15220
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2019
ms.locfileid: "34433366"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a><span data-ttu-id="1ee54-103">Problèmes connus pour les stratégies de rétention dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1ee54-103">Known issues for retention policies in Microsoft Teams</span></span>

<span data-ttu-id="1ee54-104">Vous trouverez ci-après des problèmes connus liés aux stratégies de rétention dans les équipes qui sont suivies et examinées.</span><span class="sxs-lookup"><span data-stu-id="1ee54-104">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="1ee54-105">Sous choisir des équipes dans la ligne d’emplacement des messages de canal Teams, vous pouvez voir les groupes Office 365 qui ne sont pas également équipes.</span><span class="sxs-lookup"><span data-stu-id="1ee54-105">Under Choose Teams in the Teams Channel messages location row, you may see Office 365 Groups that are not also Teams.</span></span> <span data-ttu-id="1ee54-106">Ce problème sera résolu dans le futur.</span><span class="sxs-lookup"><span data-stu-id="1ee54-106">This will be addressed in the future.</span></span>

- <span data-ttu-id="1ee54-107">Sous choisir les utilisateurs dans la ligne d’emplacement de conversation de l’équipe, il est possible que les utilisateurs invités et non-boîte aux lettres apparaissent.</span><span class="sxs-lookup"><span data-stu-id="1ee54-107">Under Choose Users in the Teams Chat location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="1ee54-108">Les stratégies de rétention ne sont pas destinées à être définies pour les invités et nous travaillons à la suppression de celles-ci dans la liste.</span><span class="sxs-lookup"><span data-stu-id="1ee54-108">Retention policies are not meant to be set for guests, and we are working to remove these from the list.</span></span>

- <span data-ttu-id="1ee54-109">L’Assistant ELC (Exchange Life cycle Assistant) s’exécute quotidiennement, mais il dispose d’un SLA de 7 jours.</span><span class="sxs-lookup"><span data-stu-id="1ee54-109">Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days.</span></span> <span data-ttu-id="1ee54-110">Par conséquent, il est possible que, si vous disposez d’une stratégie de rétention teams pour supprimer des éléments de plus de 60 jours, ces éléments peuvent persister pendant 67 jours maximum.</span><span class="sxs-lookup"><span data-stu-id="1ee54-110">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="1ee54-111">Ce n’est pas une nouvelle situation: elle suit le modèle Exchange.</span><span class="sxs-lookup"><span data-stu-id="1ee54-111">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="1ee54-112">Dans la plupart des cas, il n’y a aucun retard.</span><span class="sxs-lookup"><span data-stu-id="1ee54-112">Of course, in most cases, there is no delay.</span></span>


| | | |
|---------|---------|---------|
|![Icône représentant un point de décision](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |<span data-ttu-id="1ee54-114">Point de décision</span><span class="sxs-lookup"><span data-stu-id="1ee54-114">Decision point</span></span>         |<span data-ttu-id="1ee54-p104">De quelles fonctionnalités de sécurité et de conformité votre organisation a-t-elle besoin ? Votre organisation dispose-t-elle des licences requises pour satisfaire les besoins en matière de sécurité et de conformité ?</span><span class="sxs-lookup"><span data-stu-id="1ee54-p104">What security and compliance features does your organization require? Does your organization have the required licenses to meet Security and Compliance business requirements?</span></span>         |
|![Icône représentant les étapes suivantes](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |<span data-ttu-id="1ee54-118">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="1ee54-118">Next steps</span></span>         |<span data-ttu-id="1ee54-119">Documentez les fonctionnalités de sécurité et de conformité requises.</span><span class="sxs-lookup"><span data-stu-id="1ee54-119">Document your required security and compliance features.</span></span>         |
