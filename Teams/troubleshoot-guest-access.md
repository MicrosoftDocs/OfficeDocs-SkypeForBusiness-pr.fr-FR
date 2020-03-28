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
ms.openlocfilehash: 0c0f65f7026e6c083d9230551d689f0dd19d6b0d
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837634"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="4dea9-103">Résolution des problèmes liés à l’accès invité dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4dea9-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>
======================================================

> [!IMPORTANT]
> <span data-ttu-id="4dea9-104">Il est possible que les modifications ne prennent effet qu'après 24 heures.</span><span class="sxs-lookup"><span data-stu-id="4dea9-104">You may have to wait up to 24 hours for your changes to take effect.</span></span> 


- <span data-ttu-id="4dea9-105">Pour rechercher les problèmes de prise en charge actuels avec l’accès invité dans Teams, voir [Résolution des problèmes liés à Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span><span class="sxs-lookup"><span data-stu-id="4dea9-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="4dea9-106">Pour vérifier que votre problème est connu, consultez les [Problèmes connus pour Microsoft Teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4dea9-106">To see whether we know about your problem, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="4dea9-107">Les invités sont des utilisateurs extérieurs à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4dea9-107">Guests are users outside your organization.</span></span> <span data-ttu-id="4dea9-108">Si une personne se trouve à l'intérieur de votre organisation (y compris vos employés et les fournisseurs et agents sur site), elle ne peut pas être ajoutée en tant qu'invité.</span><span class="sxs-lookup"><span data-stu-id="4dea9-108">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="4dea9-109">La même chose s'applique pour les affiliés.</span><span class="sxs-lookup"><span data-stu-id="4dea9-109">The same applies to your affiliates.</span></span>
- <span data-ttu-id="4dea9-110">Vous trouverez des informations sur les fonctionnalités d'accès invité à venir, nouvelles ou mises à jour, dans la [Feuille de route de Teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="4dea9-110">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="4dea9-111">Indiquez-nous ce que vous souhaitez dans [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="4dea9-111">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="4dea9-112">Si vos invités remarquent des erreurs de licence</span><span class="sxs-lookup"><span data-stu-id="4dea9-112">If your guests are seeing license errors</span></span>

<span data-ttu-id="4dea9-113">L’accès invité dans Teams utilise Azure Active Directory (Azure AD) Business to Business (B2B) et son modèle de licence.</span><span class="sxs-lookup"><span data-stu-id="4dea9-113">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="4dea9-114">L'accès invité est fourni avec tous les abonnements Office 365 Business Premium, Office 365 Entreprise et Office 365 Education.</span><span class="sxs-lookup"><span data-stu-id="4dea9-114">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="4dea9-115">Aucune licence Office 365 supplémentaire n'est requise.</span><span class="sxs-lookup"><span data-stu-id="4dea9-115">No additional Office 365 license is necessary.</span></span>

<span data-ttu-id="4dea9-116">Si vous voyez des erreurs liées aux licences, assurez-vous de lire le [Guide d'attribution de licences pour Azure Active Directory B2B Collaboration](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) pour déterminer si les critères de licences répondent à vos besoins pour l’accès invité au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4dea9-116">If you’re seeing licensing errors, make sure to read the [Azure Active Directory B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>


- <span data-ttu-id="4dea9-117">Les licences invité sont décomptées du nombre existant au sein de l’organisation qui invite.</span><span class="sxs-lookup"><span data-stu-id="4dea9-117">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="4dea9-118">Tenez-en compte au moment de calculer le nombre de licences dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="4dea9-118">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="4dea9-119">Les licences sont décomptées du nombre existant au sein de votre organisation si les invités proviennent d’un autre client Office 365 ou utilisent leur adresse de courrier personnelle.</span><span class="sxs-lookup"><span data-stu-id="4dea9-119">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="4dea9-120">Prise en charge des types d’utilisateur B2B</span><span class="sxs-lookup"><span data-stu-id="4dea9-120">Support for B2B User types</span></span>
<span data-ttu-id="4dea9-121">Actuellement, Teams prend uniquement en charge les types d’États 1 et 2 des utilisateurs invités [définis par Azure B2B.](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)</span><span class="sxs-lookup"><span data-stu-id="4dea9-121">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4dea9-122">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="4dea9-122">Related topics</span></span>

[<span data-ttu-id="4dea9-123">Accès invité dans Teams</span><span class="sxs-lookup"><span data-stu-id="4dea9-123">Guest access in Teams</span></span>](guest-access.md)


