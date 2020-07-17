---
title: Étude de cas de voix contoso teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Étude de cas de voix dans teams pour les entreprises à plusieurs nationaux
appliesto:
- Microsoft Teams
ms.openlocfilehash: f58f3518202fd836ff962374e8f3b3a00ab71817
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786038"
---
# <a name="contoso-case-study-audio-conferencing"></a><span data-ttu-id="a4240-103">Étude de cas contoso : audioconférence</span><span class="sxs-lookup"><span data-stu-id="a4240-103">Contoso case study: Audio Conferencing</span></span>

<span data-ttu-id="a4240-104">Pour mieux comprendre les fonctionnalités de l’audioconférence &mdash; , son coût, sa disponibilité et son mode de fonctionnement, &mdash; Contoso a examiné [l’audioconférence dans Office 365](deploy-audio-conferencing-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="a4240-104">To gain an understanding of audio conferencing&mdash;what it is, what it costs, availability, and how it works&mdash;Contoso reviewed [Audio Conferencing in Office 365](deploy-audio-conferencing-teams-landing-page.md).</span></span> 

## <a name="overview"></a><span data-ttu-id="a4240-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="a4240-105">Overview</span></span> 

<span data-ttu-id="a4240-106">Pour les services d’audioconférence, Contoso utilise des numéros de téléphone bien connus au sein de l’organisation ainsi que dans l’extérieur.</span><span class="sxs-lookup"><span data-stu-id="a4240-106">For audio conferencing, Contoso used phone numbers that are well known within the organization as well as externally.</span></span> <span data-ttu-id="a4240-107">Étant donné que contoso souhaite conserver ces numéros dans la mesure du possible, il a examiné les informations relatives à l’attribution de numéros de téléphone dédiés et partagés au pont de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="a4240-107">Because Contoso wanted to maintain these numbers where possible, they reviewed the information on assigning dedicated and shared phone numbers to the audio conferencing bridge.</span></span> 

<span data-ttu-id="a4240-108">D’après les recherches, Contoso a pris les décisions suivantes :</span><span class="sxs-lookup"><span data-stu-id="a4240-108">Based on their research, Contoso made the following decisions:</span></span> 

- <span data-ttu-id="a4240-109">Seul un segment du remplissage qui héberge régulièrement les appels de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="a4240-109">Only a segment of the population that regularly host audio conferencing calls would receive Audio Conferencing licenses.</span></span> 

- <span data-ttu-id="a4240-110">Contoso utilisera des numéros de téléphone dédiés et transférera leurs numéros existants pour une utilisation avec la fonction de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="a4240-110">Contoso would use dedicated phone numbers and port their existing numbers for use with Audio Conferencing.</span></span>   

<span data-ttu-id="a4240-111">Les utilisateurs de contoso utilisant Skype entreprise et la boîte aux lettres de tous les utilisateurs se trouvant en ligne, de nombreux utilisateurs ont planifié une réunion existante.</span><span class="sxs-lookup"><span data-stu-id="a4240-111">Because Contoso users were using Skype for Business and all users' mailboxes reside online, many users have existing meetings scheduled.</span></span> <span data-ttu-id="a4240-112">Contoso a lu [grâce au service de migration de réunion (MMS)](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) pour savoir que les réunions existantes sont mises à jour automatiquement pour Contoso lorsqu’elles transforment l’utilisateur final en mode TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="a4240-112">Contoso read [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) to learn that existing meetings are updated automatically for Contoso when they change the end user to TeamsOnly mode.</span></span>  


## <a name="configuration"></a><span data-ttu-id="a4240-113">Configuration</span><span class="sxs-lookup"><span data-stu-id="a4240-113">Configuration</span></span>

<span data-ttu-id="a4240-114">Les numéros de téléphone associés aux conférences audio sont désignés sous le nom de numéros de service au sein du système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="a4240-114">Phone numbers that are associated with audio conferencing are referred to as service numbers within Phone System.</span></span> 

- <span data-ttu-id="a4240-115">Pour les lieux utilisant des forfaits d’appel, pour porter leurs numéros de téléphone existants de leur opérateur téléphonique vers Office 365, Contoso a suivi les étapes décrites dans la rubrique [obtenir des numéros de téléphone de service](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="a4240-115">For locations using Calling Plans, to port their existing phone numbers from their phone carrier to Office 365, Contoso followed the steps in [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

- <span data-ttu-id="a4240-116">Pour affecter la licence d’audioconférence à l’utilisateur final au programme pilote technique, l’administrateur Contoso a suivi les étapes décrites dans [gérer les paramètres de l’audioconférence pour votre organisation](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="a4240-116">To assign the Audio Conferencing license to the end user in the technical pilot, the Contoso administrator followed the steps in [Manage the Audio Conferencing settings for your organization](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).</span></span> 

- <span data-ttu-id="a4240-117">Pour le pilote et la migration de l’entreprise, Contoso a utilisé une licence basée sur le groupe en suivant les étapes décrites dans [attribuer des licences aux utilisateurs par l’appartenance aux groupes dans Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="a4240-117">For the business pilot and migration, Contoso used group-based licensing by following the steps in [Assign licenses to users by group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

 

 