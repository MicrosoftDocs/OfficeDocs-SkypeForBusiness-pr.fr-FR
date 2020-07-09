---
title: Résolution des problèmes liés à l’accès invité dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: corbinm
search.appverid: MET150
description: Obtenir de l'aide pour résoudre et corriger les problèmes liés à l’accès invité dans Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 7e4db423d262f939362400cdec489ca065b5d5c1
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086201"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="e6b4b-103">Résolution des problèmes liés à l’accès invité dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e6b4b-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>
======================================================

- <span data-ttu-id="e6b4b-104">Pour savoir si le problème persiste, consultez l' [équipe de support au sein de votre organisation](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e6b4b-104">To see whether we know about your problem, check out [Support Teams in your organization](Known-issues.md).</span></span>
- <span data-ttu-id="e6b4b-105">Pour rechercher les problèmes de prise en charge actuels avec l’accès invité dans Teams, voir [Résolution des problèmes liés à Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span><span class="sxs-lookup"><span data-stu-id="e6b4b-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="e6b4b-106">Les invités sont des utilisateurs extérieurs à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-106">Guests are users outside your organization.</span></span> <span data-ttu-id="e6b4b-107">Si une personne se trouve à l'intérieur de votre organisation (y compris vos employés et les fournisseurs et agents sur site), elle ne peut pas être ajoutée en tant qu'invité.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-107">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="e6b4b-108">La même chose s'applique pour les affiliés.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-108">The same applies to your affiliates.</span></span>
- <span data-ttu-id="e6b4b-109">Vous trouverez des informations sur les fonctionnalités d'accès invité à venir, nouvelles ou mises à jour, dans la [Feuille de route de Teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="e6b4b-109">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="e6b4b-110">Indiquez-nous ce que vous souhaitez dans [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="e6b4b-110">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="e6b4b-111">Si vos invités remarquent des erreurs de licence</span><span class="sxs-lookup"><span data-stu-id="e6b4b-111">If your guests are seeing license errors</span></span>

<span data-ttu-id="e6b4b-112">L’accès invité dans Teams utilise Azure Active Directory (Azure AD) Business to Business (B2B) et son modèle de licence.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-112">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="e6b4b-113">L’accès invité est inclus dans tous les abonnements Microsoft 365 Business Standard, Office 365 Enterprise et Office 365 Éducation.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-113">Guest access is included with all Microsoft 365 Business Standard, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="e6b4b-114">Aucune licence Microsoft 365 ou Office 365 supplémentaire n'est requise.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-114">No additional Microsoft 365 or Office 365 license is necessary.</span></span>

> [!NOTE]
> <span data-ttu-id="e6b4b-115">Pour pouvoir se connecter et utiliser les équipes en tant qu’invités sur un autre client (ressource), les équipes doivent être activées sur le client d’origine d’un invité.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-115">Teams must be enabled on a guest's home tenant for guests to be able to sign in and use Teams as a guest on another (resource) tenant.</span></span>

<span data-ttu-id="e6b4b-116">Si vous rencontrez des erreurs de gestion des licences, veillez à lire les [recommandations d’Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) pour la gestion des licences en fonction de vos besoins en matière d’accès invité au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-116">If you're seeing licensing errors, make sure to read the [Azure Active Directory B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>


- <span data-ttu-id="e6b4b-117">Les licences invité sont décomptées du nombre existant au sein de l’organisation qui invite.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-117">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="e6b4b-118">Tenez-en compte au moment de calculer le nombre de licences dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-118">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="e6b4b-119">Les licences sont comptabilisées au niveau de votre organisation, que les invités invités proviennent d’une autre organisation 365 ou d’une organisation Office 365 ou utilisent leurs adresses de messagerie personnelles.</span><span class="sxs-lookup"><span data-stu-id="e6b4b-119">Licenses are counted against your organization whether the invited guests come from another Microsoft 365 or Office 365 organization or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="e6b4b-120">Prise en charge des types d’utilisateur B2B</span><span class="sxs-lookup"><span data-stu-id="e6b4b-120">Support for B2B User types</span></span>
<span data-ttu-id="e6b4b-121">Actuellement, Teams prend uniquement en charge les types d’États 1 et 2 des utilisateurs invités [définis par Azure B2B.](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)</span><span class="sxs-lookup"><span data-stu-id="e6b4b-121">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e6b4b-122">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="e6b4b-122">Related topics</span></span>

[<span data-ttu-id="e6b4b-123">Accès invité dans Teams</span><span class="sxs-lookup"><span data-stu-id="e6b4b-123">Guest access in Teams</span></span>](guest-access.md)


[<span data-ttu-id="e6b4b-124">Résolution des problèmes de Teams</span><span class="sxs-lookup"><span data-stu-id="e6b4b-124">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)