---
title: Vérifier la préparation de votre environnement pour Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 5/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dansteve
description: Découvrez quelles données que vous devez rechercher lors de la vérification de la préparation de votre environnement pour Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 057493f42a4bbfa012fb57c2394c372dfc25c9fc
ms.sourcegitcommit: a3181bc3707b09c1e3f87c343b38259fdc6dabd2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/14/2018
ms.locfileid: "27264827"
---
<a name="check-your-environments-readiness-for-microsoft-teams"></a><span data-ttu-id="806a7-103">Vérifier la préparation de votre environnement pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="806a7-103">Check your environment’s readiness for Microsoft Teams</span></span>
===========================================

<span data-ttu-id="806a7-104">La transition vers le cloud varie pour chaque organisation et l'état actuel peut affecter le fonctionnement de Teams.</span><span class="sxs-lookup"><span data-stu-id="806a7-104">The transition to the cloud will vary by each organization, and current state may have an impact on how Teams will function.</span></span>

<span data-ttu-id="806a7-105">Les établissements d’enseignement sont vivement recommandés de [déployer la synchronisation des données de l’école](https://docs.microsoft.com/schooldatasync/) avant de déployer Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="806a7-105">Educational institutions are strongly encouraged to [deploy School Data Sync](https://docs.microsoft.com/schooldatasync/) before deploying Microsoft Teams.</span></span> <span data-ttu-id="806a7-106">Synchronisation des données de l’école utilise les données de liste de votre école SIS pour créer automatiquement les classes et les groupes pour Teams Microsoft et d’autres applications.</span><span class="sxs-lookup"><span data-stu-id="806a7-106">School Data Sync uses your school’s SIS roster data to automatically create classes and groups for Microsoft Teams and other applications.</span></span>

<span data-ttu-id="806a7-107">Pour obtenir la meilleure expérience sur les équipes, votre organisation doit avoir déployé Exchange Online et SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="806a7-107">To get the best experience on Teams, your organization must have deployed Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="806a7-108">Vous devez également vous assurer que votre environnement est prêt pour les équipes.</span><span class="sxs-lookup"><span data-stu-id="806a7-108">You must also ensure that your current environment is ready for Teams.</span></span>  <span data-ttu-id="806a7-109">Reportez-vous à ces liens pour une assistance :</span><span class="sxs-lookup"><span data-stu-id="806a7-109">Refer to these links for help:</span></span>

-   <span data-ttu-id="806a7-110">Si votre organisation n'a déployé aucune charge de travail Office 365, reportez-vous à l'article [Prise en main d'Office 365 pour les entreprises.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)</span><span class="sxs-lookup"><span data-stu-id="806a7-110">If your organization has not deployed any Office 365 workloads, see [Getting Started with Office 365 for business.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)</span></span>

-   <span data-ttu-id="806a7-111">Si votre organisation n'a pas ajouté ni configuré un domaine vérifié pour Office 365, reportez-vous à l'article [Vérifier votre domaine Office 365](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span><span class="sxs-lookup"><span data-stu-id="806a7-111">If your organization has not added or configured a verified domain for Office 365, see [Verify your Office 365 domain](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

-   <span data-ttu-id="806a7-112">Si votre organisation n'a pas synchronisé les identités dans Azure Active Directory, reportez-vous à la page [Identity models and authentication in Microsoft Teams](identify-models-authentication.md) (Modèles d'identité et authentification dans Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="806a7-112">If your organization has not synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

-   <span data-ttu-id="806a7-113">Si votre organisation ne dispose pas d'Exchange Online, reportez-vous à la page [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md) (Interaction entre Exchange et Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="806a7-113">If your organization does not have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

-   <span data-ttu-id="806a7-114">Si votre organisation ne dispose pas de SharePoint Online, reportez-vous à la page [Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams](SharePoint-OneDrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="806a7-114">If your organization does not have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="806a7-115">Si votre organisation est un établissement scolaire et que vous utilisez un étudiant informations système (SIS), [déployer la synchronisation des données de l’école](https://docs.microsoft.com/schooldatasync/) avant de déployer Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="806a7-115">If your organization is an educational institution and you use a Student Information System (SIS), [deploy School Data Sync](https://docs.microsoft.com/schooldatasync/) before deploying Microsoft Teams.</span></span>

- <span data-ttu-id="806a7-116">Si votre organisation a un Skype local existant pour le déploiement de serveur d’entreprise (ou Lync Server), vous devez configurer Azure AD se connecter pour synchroniser votre annuaire local avec Office 365.</span><span class="sxs-lookup"><span data-stu-id="806a7-116">If your organization has an existing on-premises Skype for Business Server (or Lync Server) deployment, you must configure Azure AD Connect to synchronize your on-premises directory with Office 365.</span></span>  <span data-ttu-id="806a7-117">Pour plus d’informations, voir [configurer les Azure AD Connect pour les équipes et Skype pour les entreprises](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/configure-azure-ad-connect).</span><span class="sxs-lookup"><span data-stu-id="806a7-117">For more information, see [Configure Azure AD Connect for Teams and Skype for Business](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/configure-azure-ad-connect).</span></span>