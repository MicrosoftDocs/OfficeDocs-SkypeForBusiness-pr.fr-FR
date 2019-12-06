---
title: Résoudre les problèmes liés à l’accès invité dans Microsoft teams
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
description: Obtenez de l’aide pour résoudre les problèmes liés à l’accès invité dans Microsoft Teams.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: e0a3530b7a1f9029d9f671d0a02ef58cbb7907bf
ms.sourcegitcommit: 96d98e145ff300833d827a7d43b4e4b0331b7538
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871730"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="3159f-103">Résoudre les problèmes liés à l’accès invité dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="3159f-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>
======================================================

> [!IMPORTANT]
> <span data-ttu-id="3159f-104">Il est possible que vous deviez attendre 24 heures pour que vos modifications soient prises en compte.</span><span class="sxs-lookup"><span data-stu-id="3159f-104">You may have to wait up to 24 hours for your changes to take effect.</span></span> 


- <span data-ttu-id="3159f-105">Pour vérifier les problèmes de prise en charge de l’accès invité dans Microsoft Teams, voir [résolution des](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)problèmes liés aux équipes.</span><span class="sxs-lookup"><span data-stu-id="3159f-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="3159f-106">Pour savoir si le problème persiste, consultez les [problèmes connus de Microsoft teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3159f-106">To see whether we know about your problem, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="3159f-107">Les invités sont des utilisateurs extérieurs à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3159f-107">Guests are users outside your organization.</span></span> <span data-ttu-id="3159f-108">Si une personne se trouve au sein de votre organisation (y compris vos employés, prestataires de contenus sur site ou agents sur site), elle ne peut pas être ajoutée en tant qu’invités.</span><span class="sxs-lookup"><span data-stu-id="3159f-108">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="3159f-109">Il en va de même pour vos affiliés.</span><span class="sxs-lookup"><span data-stu-id="3159f-109">The same applies to your affiliates.</span></span>
- <span data-ttu-id="3159f-110">Apprenez-en davantage sur les nouvelles fonctionnalités de l’accès invité nouveau ou mis à jour dans la [feuilles de route de teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="3159f-110">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="3159f-111">Dites-nous ce que vous voulez dans [teams UserVoice](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="3159f-111">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="3159f-112">Si vos invités voient des erreurs de licence</span><span class="sxs-lookup"><span data-stu-id="3159f-112">If your guests are seeing license errors</span></span>

<span data-ttu-id="3159f-113">L’accès invité dans teams utilise Azure Active Directory (Azure AD) Business to Business (B2B) et son modèle de licence.</span><span class="sxs-lookup"><span data-stu-id="3159f-113">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="3159f-114">L'accès invité est fourni avec tous les abonnements Office 365 Business Premium, Office 365 Entreprise et Office 365 Education.</span><span class="sxs-lookup"><span data-stu-id="3159f-114">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="3159f-115">Aucune licence Office 365 supplémentaire n'est requise.</span><span class="sxs-lookup"><span data-stu-id="3159f-115">No additional Office 365 license is necessary.</span></span>

<span data-ttu-id="3159f-116">Si vous rencontrez des erreurs de gestion des licences, veillez à lire les [recommandations d’Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) pour la gestion des licences en fonction de vos besoins en matière d’accès invité au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3159f-116">If you’re seeing licensing errors, make sure to read the [Azure Active Directory B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>


- <span data-ttu-id="3159f-117">Les licences invité sont comptabilisées au niveau de l’organisation d’invitation.</span><span class="sxs-lookup"><span data-stu-id="3159f-117">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="3159f-118">Tenez compte de ce qui suit lorsque vous calculez le nombre de licences dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="3159f-118">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="3159f-119">Les licences sont comptabilisées au niveau de votre organisation, que les invités invités proviennent d’un autre client Office 365 ou utilisent leurs adresses de messagerie personnelles.</span><span class="sxs-lookup"><span data-stu-id="3159f-119">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="3159f-120">Prise en charge des types d’utilisateurs B2B</span><span class="sxs-lookup"><span data-stu-id="3159f-120">Support for B2B User types</span></span>
<span data-ttu-id="3159f-121">Actuellement Teams ne prend en charge que les types d’utilisateurs invités de l’État 1 et de l’état 2 [, tels qu’ils sont définis par Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span><span class="sxs-lookup"><span data-stu-id="3159f-121">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3159f-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3159f-122">Related topics</span></span>

[<span data-ttu-id="3159f-123">Accès invité dans Teams</span><span class="sxs-lookup"><span data-stu-id="3159f-123">Guest access in Teams</span></span>](guest-access.md)


