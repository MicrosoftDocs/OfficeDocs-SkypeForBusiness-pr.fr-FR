---
title: "Rechercher des événements Microsoft Teams dans le journal d'audit"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Découvrez comment récupérer des données Microsoft Teams à partir du journal d'audit."
ms.openlocfilehash: bea1a808fd92d3b43caf8ee61152a999ca3af8a3
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2017
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="177f4-103">Rechercher des événements Microsoft Teams dans le journal d'audit</span><span class="sxs-lookup"><span data-stu-id="177f4-103">Search the audit log for events in Microsoft Teams</span></span>
==================================================

<span data-ttu-id="177f4-p101">Le journal d'audit fournit des fonctionnalités de recherche ad hoc d'événements importants survenus dans les services Office 365. Dans le cas particulier Microsoft Teams, voici quelques exemples d'événements capturés :</span><span class="sxs-lookup"><span data-stu-id="177f4-p101">The Audit Log provides ad-hoc search capabilities into notable events across Office 365 services. For Microsoft Teams specifically, below are a few examples of events captured:</span></span>

-   <span data-ttu-id="177f4-106">Création d'une équipe</span><span class="sxs-lookup"><span data-stu-id="177f4-106">Team Creation</span></span>

-   <span data-ttu-id="177f4-107">Suppression d'une équipe</span><span class="sxs-lookup"><span data-stu-id="177f4-107">Team Deletion</span></span>

-   <span data-ttu-id="177f4-108">Ajout d'un canal</span><span class="sxs-lookup"><span data-stu-id="177f4-108">Added Channel</span></span>

-   <span data-ttu-id="177f4-109">Modification d'un paramètre</span><span class="sxs-lookup"><span data-stu-id="177f4-109">Changed Setting</span></span>

<span data-ttu-id="177f4-110">La liste complète des événements Office 365 est relativement étendue et disponible [ici](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US#ID0EABAAA=Audited_activities).</span><span class="sxs-lookup"><span data-stu-id="177f4-110">The complete event list across Office 365 is quite extensive and can be found [here](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US#ID0EABAAA=Audited_activities).</span></span>

<span data-ttu-id="177f4-p102">Avant de pouvoir examiner les activités d'audit, la fonctionnalité d'audit doit d'abord être activée. Pour activer la fonctionnalité d'audit, accédez au Centre d'administration *Sécurité et Conformité*. Sous *Rechercher une activité*, cliquez sur **Démarrer l'enregistrement**. Après 24 heures, les données d'audit seront disponibles via *Recherche du journal d'audit* située sous l'onglet *Recherche et examen*.</span><span class="sxs-lookup"><span data-stu-id="177f4-p102">Before you can dig into audit insights, auditing must first be enabled. To enable Auditing, navigate to the *Security & Compliance* Admin Center. Under *Search for activity*, click on **Start recording now**. After 24hrs, audit data will be available via *Audit Log Search* located under the *Search & Investigation* tab.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="177f4-115">Les données d'audit sont uniquement disponibles à partir du point d'activation de la fonctionnalité d'audit.</span><span class="sxs-lookup"><span data-stu-id="177f4-115">Audit data is only available from the point at which Auditing was enabled.</span></span>



![Capture d'écran de la page de recherche des journaux d'audit du Centre de sécurité et de conformité.](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image2.png)

<span data-ttu-id="177f4-117">À présent, passons à la récupération des données Microsoft Teams à partir du journal d'audit :</span><span class="sxs-lookup"><span data-stu-id="177f4-117">Now, let’s look at how to retrieve Microsoft Teams data from the Audit Log:</span></span>

1.  <span data-ttu-id="177f4-p103">Pour récupérer des informations du journal d'audit, accédez au Centre d'administration [Sécurité et Conformité](https://go.microsoft.com/fwlink/?linkid=855775). Sous *Recherche et examen*, sélectionnez **Recherche du journal d'audit.**</span><span class="sxs-lookup"><span data-stu-id="177f4-p103">To retrieve Audit Log information, navigate to the [Security & Compliance Admin Center](https://go.microsoft.com/fwlink/?linkid=855775). Under *Search & Investigation*, select **Audit log search.**</span></span>

    <span data-ttu-id="177f4-p104">a.  Microsoft Teams a défini des activités d'audit qui peuvent être sélectionnées comme indiqué ci-après.</span><span class="sxs-lookup"><span data-stu-id="177f4-p104">a.  Microsoft Teams has defined audit activities that can be selected as shown below.</span></span>

![Capture d'écran de la page de recherche des journaux d'audit du Centre de sécurité et de conformité.](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)

2.  <span data-ttu-id="177f4-p105">Une fois les activités qui vous intéressent sélectionnées, fournissez une plage de dates et des utilisateurs pour lesquels vous souhaitez récupérer les informations Microsoft Teams. Cliquez sur **Rechercher** pour récupérer les résultats.</span><span class="sxs-lookup"><span data-stu-id="177f4-p105">After selecting the activities of interest, supply a date range and users to retrieve Microsoft Teams information from. Click **Search** to retrieve the results.</span></span>

3.  <span data-ttu-id="177f4-125">Vous pouvez exporter ces informations au format Excel et les filtrer en fonction de vos besoins.</span><span class="sxs-lookup"><span data-stu-id="177f4-125">This information can be exported to Excel and filtered as needed.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="177f4-126">Si la fonction d'audit n'a pas été préalablement activée, vous devez l'activer pour obtenir des données dans le journal d'audit.</span><span class="sxs-lookup"><span data-stu-id="177f4-126">If auditing has not been enabled previously, that needs to be enabled before data will appear in the Audit Log.</span></span>


