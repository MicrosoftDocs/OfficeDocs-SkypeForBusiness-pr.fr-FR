---
title: Problèmes connus pour les stratégies de rétention dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anach
description: Liste actuelle des problèmes connus pour les stratégies de rétention de Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: d070180505081971eca6c4075bd5bc4563bcd184
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41838204"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a><span data-ttu-id="04b56-103">Problèmes connus pour les stratégies de rétention dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="04b56-103">Known issues for retention policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="04b56-104">Nous ne prenons pas encore en charge la configuration de la conservation des messages de canal privé.</span><span class="sxs-lookup"><span data-stu-id="04b56-104">We don’t yet support configuration for retention of private channel messages.</span></span> <span data-ttu-id="04b56-105">La conservation des fichiers partagés dans des canaux privés est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="04b56-105">Retention of files shared in private channels is supported.</span></span>

<span data-ttu-id="04b56-106">Vous trouverez ci-après des problèmes connus liés aux stratégies de rétention dans les équipes qui sont suivies et examinées.</span><span class="sxs-lookup"><span data-stu-id="04b56-106">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="04b56-107">Sous choisir des équipes dans la ligne d’emplacement des messages de canal Teams, vous pouvez voir les groupes Office 365 qui ne sont pas également équipes.</span><span class="sxs-lookup"><span data-stu-id="04b56-107">Under Choose Teams in the Teams Channel messages location row, you may see Office 365 Groups that are not also Teams.</span></span> <span data-ttu-id="04b56-108">Ce problème sera résolu dans le futur.</span><span class="sxs-lookup"><span data-stu-id="04b56-108">This will be addressed in the future.</span></span>

- <span data-ttu-id="04b56-109">Sous choisir les utilisateurs dans la ligne d’emplacement de conversation de l’équipe, il est possible que les utilisateurs invités et non-boîte aux lettres apparaissent.</span><span class="sxs-lookup"><span data-stu-id="04b56-109">Under Choose Users in the Teams Chat location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="04b56-110">Les stratégies de rétention ne sont pas destinées à être définies pour les invités et nous travaillons à la suppression de celles-ci dans la liste.</span><span class="sxs-lookup"><span data-stu-id="04b56-110">Retention policies are not meant to be set for guests, and we are working to remove these from the list.</span></span>

- <span data-ttu-id="04b56-111">L’Assistant ELC (Exchange Life cycle Assistant) s’exécute quotidiennement, mais il dispose d’un SLA de 7 jours.</span><span class="sxs-lookup"><span data-stu-id="04b56-111">Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days.</span></span> <span data-ttu-id="04b56-112">Par conséquent, il est possible que, si vous disposez d’une stratégie de rétention teams pour supprimer des éléments de plus de 60 jours, ces éléments peuvent persister pendant 67 jours maximum.</span><span class="sxs-lookup"><span data-stu-id="04b56-112">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="04b56-113">Ce n’est pas une nouvelle situation : elle suit le modèle Exchange.</span><span class="sxs-lookup"><span data-stu-id="04b56-113">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="04b56-114">Dans la plupart des cas, il n’y a aucun retard.</span><span class="sxs-lookup"><span data-stu-id="04b56-114">Of course, in most cases, there is no delay.</span></span>


| | | |
|---------|---------|---------|
|![Icône représentant un point de décision](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |<span data-ttu-id="04b56-116">Point de décision</span><span class="sxs-lookup"><span data-stu-id="04b56-116">Decision point</span></span>         |<span data-ttu-id="04b56-p105">De quelles fonctionnalités de sécurité et de conformité votre organisation a-t-elle besoin ? Votre organisation dispose-t-elle des licences requises pour satisfaire les besoins en matière de sécurité et de conformité ?</span><span class="sxs-lookup"><span data-stu-id="04b56-p105">What security and compliance features does your organization require? Does your organization have the required licenses to meet Security and Compliance business requirements?</span></span>         |
|![Icône représentant les étapes suivantes](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |<span data-ttu-id="04b56-120">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="04b56-120">Next steps</span></span>         |<span data-ttu-id="04b56-121">Documentez les fonctionnalités de sécurité et de conformité requises.</span><span class="sxs-lookup"><span data-stu-id="04b56-121">Document your required security and compliance features.</span></span>         |
