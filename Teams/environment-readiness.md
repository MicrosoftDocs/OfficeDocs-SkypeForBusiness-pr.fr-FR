---
title: Vérifier la préparation de votre environnement pour Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 5/11/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dansteve
description: Découvrez quelles données que vous devez rechercher lors de la vérification de la préparation de votre environnement pour Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7988d286c7f75f880572f42793568eb083929e8e
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37567451"
---
<a name="check-your-environments-readiness-for-microsoft-teams"></a><span data-ttu-id="b23ae-103">Vérifier la préparation de votre environnement pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b23ae-103">Check your environment’s readiness for Microsoft Teams</span></span>
===========================================

<span data-ttu-id="b23ae-104">La transition vers le cloud varie pour chaque organisation et l'état actuel peut affecter le fonctionnement de Teams.</span><span class="sxs-lookup"><span data-stu-id="b23ae-104">The transition to the cloud will vary by each organization, and current state may have an impact on how Teams will function.</span></span>

<span data-ttu-id="b23ae-105">Les établissements d’enseignement sont fortement encouragés à [déployer School Data Sync](https://docs.microsoft.com/schooldatasync/) avant le déploiement de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b23ae-105">Educational institutions are strongly encouraged to [deploy School Data Sync](https://docs.microsoft.com/schooldatasync/) before deploying Microsoft Teams.</span></span> <span data-ttu-id="b23ae-106">School Data Sync utilise les données de la liste du SIS de votre établissement scolaire pour créer automatiquement des classes et des groupes pour Microsoft teams et d’autres applications.</span><span class="sxs-lookup"><span data-stu-id="b23ae-106">School Data Sync uses your school’s SIS roster data to automatically create classes and groups for Microsoft Teams and other applications.</span></span>

<span data-ttu-id="b23ae-107">Pour tirer le meilleur parti de teams, votre organisation doit avoir déployé Exchange Online et SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b23ae-107">To get the best experience on Teams, your organization must have deployed Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="b23ae-108">Vous devez également vous assurer que votre environnement actuel est prêt pour Teams.</span><span class="sxs-lookup"><span data-stu-id="b23ae-108">You must also ensure that your current environment is ready for Teams.</span></span>  <span data-ttu-id="b23ae-109">Pour obtenir de l’aide, consultez les liens suivants :</span><span class="sxs-lookup"><span data-stu-id="b23ae-109">Refer to these links for help:</span></span>

-   <span data-ttu-id="b23ae-110">Si votre organisation n'a déployé aucune charge de travail Office 365, reportez-vous à l'article [Prise en main d'Office 365 pour les entreprises.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)</span><span class="sxs-lookup"><span data-stu-id="b23ae-110">If your organization has not deployed any Office 365 workloads, see [Getting Started with Office 365 for business.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)</span></span>

-   <span data-ttu-id="b23ae-111">Si votre organisation n'a pas ajouté ni configuré un domaine vérifié pour Office 365, reportez-vous à l'article [Vérifier votre domaine Office 365](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span><span class="sxs-lookup"><span data-stu-id="b23ae-111">If your organization has not added or configured a verified domain for Office 365, see [Verify your Office 365 domain](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

-   <span data-ttu-id="b23ae-112">Si votre organisation n'a pas synchronisé les identités dans Azure Active Directory, reportez-vous à la page [Identity models and authentication in Microsoft Teams](identify-models-authentication.md) (Modèles d'identité et authentification dans Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="b23ae-112">If your organization has not synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

-   <span data-ttu-id="b23ae-113">Si votre organisation ne dispose pas d'Exchange Online, reportez-vous à la page [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md) (Interaction entre Exchange et Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="b23ae-113">If your organization does not have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

-   <span data-ttu-id="b23ae-114">Si votre organisation ne dispose pas de SharePoint Online, reportez-vous à la page [Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams](SharePoint-OneDrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="b23ae-114">If your organization does not have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="b23ae-115">Si votre organisation est une institution éducative et que vous utilisez un système d’information sur les étudiants, vous devez [déployer School Data Sync](https://docs.microsoft.com/schooldatasync/) avant de déployer Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b23ae-115">If your organization is an educational institution and you use a Student Information System (SIS), [deploy School Data Sync](https://docs.microsoft.com/schooldatasync/) before deploying Microsoft Teams.</span></span>

- <span data-ttu-id="b23ae-116">Si votre organisation dispose d’un déploiement Skype entreprise Server (ou Lync Server) local existant, vous devez configurer Azure AD Connect pour synchroniser votre annuaire local avec Office 365.</span><span class="sxs-lookup"><span data-stu-id="b23ae-116">If your organization has an existing on-premises Skype for Business Server (or Lync Server) deployment, you must configure Azure AD Connect to synchronize your on-premises directory with Office 365.</span></span>  <span data-ttu-id="b23ae-117">Pour plus d’informations, reportez-vous à la rubrique [configuration d’Azure ad Connect pour les équipes et Skype entreprise](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/configure-azure-ad-connect).</span><span class="sxs-lookup"><span data-stu-id="b23ae-117">For more information, see [Configure Azure AD Connect for Teams and Skype for Business](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/configure-azure-ad-connect).</span></span>