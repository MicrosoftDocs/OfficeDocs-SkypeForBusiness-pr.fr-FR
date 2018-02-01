---
title: "Rechercher des événements Microsoft Teams dans le journal d'audit"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 01/22/2018
ms.topic: article
ms.service: msteams
description: "Découvrez comment récupérer des données Microsoft Teams à partir du journal d'audit d’Office 365."
ms.openlocfilehash: 229ddc5fb1e8a775524564c27ffeecce96483fe1
ms.sourcegitcommit: 9f185be910855f6312344ea906e96e5e6449cf4c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2018
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="c8f33-103">Rechercher des événements Microsoft Teams dans le journal d'audit</span><span class="sxs-lookup"><span data-stu-id="c8f33-103">Search the audit log for events in Microsoft Teams</span></span>
==================================================

<span data-ttu-id="c8f33-104">Le journal d’audit peut vous aider à vérifier des activités spécifiques dans les services Office 365.</span><span class="sxs-lookup"><span data-stu-id="c8f33-104">The audit log can help you investigate specific activities across Office 365 services.</span></span> <span data-ttu-id="c8f33-105">Pour Teams, voici certaines des activités qui sont vérifiées :</span><span class="sxs-lookup"><span data-stu-id="c8f33-105">For Teams, here are some of the activities that are audited:</span></span>

-   <span data-ttu-id="c8f33-106">Création d'une équipe</span><span class="sxs-lookup"><span data-stu-id="c8f33-106">Team Creation</span></span>

-   <span data-ttu-id="c8f33-107">Suppression d'une équipe</span><span class="sxs-lookup"><span data-stu-id="c8f33-107">Team Deletion</span></span>

-   <span data-ttu-id="c8f33-108">Ajout d'un canal</span><span class="sxs-lookup"><span data-stu-id="c8f33-108">Added Channel</span></span>

-   <span data-ttu-id="c8f33-109">Modification d'un paramètre</span><span class="sxs-lookup"><span data-stu-id="c8f33-109">Changed Setting</span></span>

<span data-ttu-id="c8f33-110">Pour la liste complète des activités qui sont vérifiées dans Office 365, consultez la rubrique [Effectuer des recherches dans le journal d'audit dans le Centre de sécurité et de conformité d'Office 365](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c?=&PickTab=Activities&ad=US#PickTab=Activities).</span><span class="sxs-lookup"><span data-stu-id="c8f33-110">To see the complete list of activities that are audited in Office 365, read [Search the audit log in the Office 365 Security & Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c?=&PickTab=Activities&ad=US#PickTab=Activities).</span></span>

## <a name="turn-on-auditing-in-teams"></a><span data-ttu-id="c8f33-111">Activer l’audit dans Teams</span><span class="sxs-lookup"><span data-stu-id="c8f33-111">Turn on auditing in Teams</span></span>

<span data-ttu-id="c8f33-112">Pour consulter les données d’audit, vous devez au préalable activer la fonctionnalité d’audit dans le **Centre de sécurité et de conformité**(https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="c8f33-112">Before you can look at audit data, you have to first turn on auditing in the **Security & Compliance Center**(https://protection.office.com).</span></span> <span data-ttu-id="c8f33-113">Pour obtenir de l’aide sur la fonctionnalité d’audit, consultez la rubrique [Activer ou désactiver la recherche du journal d’audit d’Office 365](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span><span class="sxs-lookup"><span data-stu-id="c8f33-113">For help turning on auditing, read [Turn Office 365 audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="c8f33-114">Les données d'audit sont disponibles uniquement à partir du point d'activation de la fonctionnalité d'audit.</span><span class="sxs-lookup"><span data-stu-id="c8f33-114">Audit data is only available from the point at which Auditing was enabled.</span></span>



## <a name="retrieve-teams-data-from-the-audit-log"></a><span data-ttu-id="c8f33-115">Récupérer des données Teams à partir du journal d'audit</span><span class="sxs-lookup"><span data-stu-id="c8f33-115">Retrieve Teams data from the audit log</span></span>

1.  <span data-ttu-id="c8f33-116">Pour récupérer les journaux d’audit, accédez au [Centre de sécurité et de conformité](https://go.microsoft.com/fwlink/?linkid=855775).</span><span class="sxs-lookup"><span data-stu-id="c8f33-116">To retrieve audit logs, go to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="c8f33-117">Sous **Recherche et examen**, sélectionnez **Recherche du journal d’audit**.</span><span class="sxs-lookup"><span data-stu-id="c8f33-117">Under **Search & Investigation**, select **Audit log search**.</span></span>

![Capture d'écran de la page de recherche des journaux d'audit du Centre de sécurité et de conformité.](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)

2.  <span data-ttu-id="c8f33-119">Utilisez l’option **Rechercher** pour filtrer les données en fonction des activités, dates et utilisateurs que vous souhaitez vérifier.</span><span class="sxs-lookup"><span data-stu-id="c8f33-119">Use **Search** to filter by the activities, dates, and users you want to audit.</span></span>

3.  <span data-ttu-id="c8f33-120">Pour une analyse plus approfondie, exportez les résultats dans Excel.</span><span class="sxs-lookup"><span data-stu-id="c8f33-120">Export your results to Excel for further analysis.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="c8f33-121">Les données d’audit sont visibles dans le journal d’audit si la fonctionnalité d’audit est activée.</span><span class="sxs-lookup"><span data-stu-id="c8f33-121">Audit data is only visible in the Audit Log if auditing is turned on.</span></span>

## <a name="video-techtip-using-audit-log-search-in-teams"></a><span data-ttu-id="c8f33-122">Vidéo : Conseil technique : utilisation de la recherche du journal d’audit dans Teams</span><span class="sxs-lookup"><span data-stu-id="c8f33-122">Video: TechTip: Using Audit Log Search in Teams</span></span>

<span data-ttu-id="c8f33-123">Rejoignez Ansuman Acharya, gestionnaire de programmes pour Teams, qui explique comment effectuer une recherche du journal d’audit pour Teams dans la Centre de sécurité et de conformité d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="c8f33-123">Join Ansuman Acharya, a program manager for Teams, as he demonstrates conducting an Audit Log search for Teams in the Office 365 Security & Compliance Center.</span></span> 


> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]






