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
ms.openlocfilehash: b8ef4fb03de0172403556334e43359402ccce113
ms.sourcegitcommit: 25e70de7c943e22fe6ac6e8d6b4353ca68f81f83
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2020
ms.locfileid: "43157737"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="dad4e-103">Résolution des problèmes liés à l’accès invité dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dad4e-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>
======================================================

> [!IMPORTANT]
> <span data-ttu-id="dad4e-104">Il est possible que les modifications ne prennent effet qu'après 24 heures.</span><span class="sxs-lookup"><span data-stu-id="dad4e-104">You may have to wait up to 24 hours for your changes to take effect.</span></span> 


- <span data-ttu-id="dad4e-105">Pour rechercher les problèmes de prise en charge actuels avec l’accès invité dans Teams, voir [Résolution des problèmes liés à Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span><span class="sxs-lookup"><span data-stu-id="dad4e-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="dad4e-106">Pour vérifier que votre problème est connu, consultez les [Problèmes connus pour Microsoft Teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="dad4e-106">To see whether we know about your problem, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="dad4e-107">Les invités sont des utilisateurs extérieurs à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="dad4e-107">Guests are users outside your organization.</span></span> <span data-ttu-id="dad4e-108">Si une personne se trouve à l'intérieur de votre organisation (y compris vos employés et les fournisseurs et agents sur site), elle ne peut pas être ajoutée en tant qu'invité.</span><span class="sxs-lookup"><span data-stu-id="dad4e-108">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="dad4e-109">La même chose s'applique pour les affiliés.</span><span class="sxs-lookup"><span data-stu-id="dad4e-109">The same applies to your affiliates.</span></span>
- <span data-ttu-id="dad4e-110">Vous trouverez des informations sur les fonctionnalités d'accès invité à venir, nouvelles ou mises à jour, dans la [Feuille de route de Teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="dad4e-110">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="dad4e-111">Indiquez-nous ce que vous souhaitez dans [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="dad4e-111">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="dad4e-112">Si vos invités remarquent des erreurs de licence</span><span class="sxs-lookup"><span data-stu-id="dad4e-112">If your guests are seeing license errors</span></span>

<span data-ttu-id="dad4e-113">L’accès invité dans Teams utilise Azure Active Directory (Azure AD) Business to Business (B2B) et son modèle de licence.</span><span class="sxs-lookup"><span data-stu-id="dad4e-113">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="dad4e-114">L'accès invité est fourni avec tous les abonnements Office 365 Business Premium, Office 365 Entreprise et Office 365 Education.</span><span class="sxs-lookup"><span data-stu-id="dad4e-114">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="dad4e-115">Aucune licence Office 365 supplémentaire n'est requise.</span><span class="sxs-lookup"><span data-stu-id="dad4e-115">No additional Office 365 license is necessary.</span></span>

> [!NOTE]
> <span data-ttu-id="dad4e-116">Pour pouvoir se connecter et utiliser les équipes en tant qu’invités sur un autre client (ressource), les équipes doivent être activées sur le client d’origine d’un invité.</span><span class="sxs-lookup"><span data-stu-id="dad4e-116">Teams must be enabled on a guest's home tenant for guests to be able to sign in and use Teams as a guest on another (resource) tenant.</span></span>

<span data-ttu-id="dad4e-117">Si vous rencontrez des erreurs de gestion des licences, veillez à lire les [recommandations d’Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) pour la gestion des licences en fonction de vos besoins en matière d’accès invité au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="dad4e-117">If you're seeing licensing errors, make sure to read the [Azure Active Directory B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>


- <span data-ttu-id="dad4e-118">Les licences invité sont décomptées du nombre existant au sein de l’organisation qui invite.</span><span class="sxs-lookup"><span data-stu-id="dad4e-118">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="dad4e-119">Tenez-en compte au moment de calculer le nombre de licences dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="dad4e-119">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="dad4e-120">Les licences sont décomptées du nombre existant au sein de votre organisation si les invités proviennent d’un autre client Office 365 ou utilisent leur adresse de courrier personnelle.</span><span class="sxs-lookup"><span data-stu-id="dad4e-120">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="dad4e-121">Prise en charge des types d’utilisateur B2B</span><span class="sxs-lookup"><span data-stu-id="dad4e-121">Support for B2B User types</span></span>
<span data-ttu-id="dad4e-122">Actuellement, Teams prend uniquement en charge les types d’États 1 et 2 des utilisateurs invités [définis par Azure B2B.](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)</span><span class="sxs-lookup"><span data-stu-id="dad4e-122">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="dad4e-123">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="dad4e-123">Related topics</span></span>

[<span data-ttu-id="dad4e-124">Accès invité dans Teams</span><span class="sxs-lookup"><span data-stu-id="dad4e-124">Guest access in Teams</span></span>](guest-access.md)


