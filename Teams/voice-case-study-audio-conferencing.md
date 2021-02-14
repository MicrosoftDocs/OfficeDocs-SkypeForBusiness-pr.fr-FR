---
title: Étude de cas Teams voix Contoso
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
description: Étude de cas Voix Teams pour une entreprise multinationale
appliesto:
- Microsoft Teams
ms.openlocfilehash: f58f3518202fd836ff962374e8f3b3a00ab71817
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786038"
---
# <a name="contoso-case-study-audio-conferencing"></a><span data-ttu-id="d9b7d-103">Étude de cas Contoso : Audioconférence</span><span class="sxs-lookup"><span data-stu-id="d9b7d-103">Contoso case study: Audio Conferencing</span></span>

<span data-ttu-id="d9b7d-104">Pour comprendre ce qu’est l’audioconférence, ses coûts, sa disponibilité et son fonctionnement, l’audioconférence examinée par &mdash; &mdash; Contoso dans Office [365.](deploy-audio-conferencing-teams-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="d9b7d-104">To gain an understanding of audio conferencing&mdash;what it is, what it costs, availability, and how it works&mdash;Contoso reviewed [Audio Conferencing in Office 365](deploy-audio-conferencing-teams-landing-page.md).</span></span> 

## <a name="overview"></a><span data-ttu-id="d9b7d-105">Présentation</span><span class="sxs-lookup"><span data-stu-id="d9b7d-105">Overview</span></span> 

<span data-ttu-id="d9b7d-106">Pour l’audioconférence, Contoso utilisait des numéros de téléphone bien connus au sein de l’organisation ainsi qu’à l’extérieur.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-106">For audio conferencing, Contoso used phone numbers that are well known within the organization as well as externally.</span></span> <span data-ttu-id="d9b7d-107">Comme Contoso souhaitait conserver ces numéros autant que possible, il a examiné les informations sur l’affectation de numéros de téléphone dédiés et partagés au pont de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-107">Because Contoso wanted to maintain these numbers where possible, they reviewed the information on assigning dedicated and shared phone numbers to the audio conferencing bridge.</span></span> 

<span data-ttu-id="d9b7d-108">D’après leurs recherches, Contoso a pris les décisions suivantes :</span><span class="sxs-lookup"><span data-stu-id="d9b7d-108">Based on their research, Contoso made the following decisions:</span></span> 

- <span data-ttu-id="d9b7d-109">Seul un segment de la population qui héberge régulièrement des appels d’audioconférence reçoit des licences d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-109">Only a segment of the population that regularly host audio conferencing calls would receive Audio Conferencing licenses.</span></span> 

- <span data-ttu-id="d9b7d-110">Contoso utiliserait des numéros de téléphone dédiés et portait ses numéros existants pour une utilisation avec l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-110">Contoso would use dedicated phone numbers and port their existing numbers for use with Audio Conferencing.</span></span>   

<span data-ttu-id="d9b7d-111">Étant donné que les utilisateurs contoso utilisaient Skype Entreprise et que les boîtes aux lettres de tous les utilisateurs résident en ligne, de nombreux utilisateurs ont déjà une réunion prévue.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-111">Because Contoso users were using Skype for Business and all users' mailboxes reside online, many users have existing meetings scheduled.</span></span> <span data-ttu-id="d9b7d-112">Contoso lit Utiliser le [service Meeting Migration Service (MMS)](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) pour découvrir que les réunions existantes sont mises à jour automatiquement pour Contoso lorsqu’elles changent l’utilisateur final en mode TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-112">Contoso read [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) to learn that existing meetings are updated automatically for Contoso when they change the end user to TeamsOnly mode.</span></span>  


## <a name="configuration"></a><span data-ttu-id="d9b7d-113">Configuration</span><span class="sxs-lookup"><span data-stu-id="d9b7d-113">Configuration</span></span>

<span data-ttu-id="d9b7d-114">Les numéros de téléphone associés à l’audioconférence sont appelés numéros de service dans le système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="d9b7d-114">Phone numbers that are associated with audio conferencing are referred to as service numbers within Phone System.</span></span> 

- <span data-ttu-id="d9b7d-115">Pour les lieux utilisant des forfaits d’appels, pour le portage de leurs numéros de téléphone existants de leur opérateur vers Office 365, Contoso a suivi les étapes de obtention de numéros [de téléphone de service.](getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="d9b7d-115">For locations using Calling Plans, to port their existing phone numbers from their phone carrier to Office 365, Contoso followed the steps in [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

- <span data-ttu-id="d9b7d-116">Pour affecter la licence d’audioconférence à l’utilisateur final dans le cadre du pilote technique, l’administrateur Contoso a suivi les étapes de gestion des paramètres d’audioconférence pour [votre organisation.](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="d9b7d-116">To assign the Audio Conferencing license to the end user in the technical pilot, the Contoso administrator followed the steps in [Manage the Audio Conferencing settings for your organization](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).</span></span> 

- <span data-ttu-id="d9b7d-117">Pour le pilote et la migration d’entreprise, Contoso a utilisé la gestion des licences basée sur les groupes en suivant les étapes de la procédure Attribuer des licences à des utilisateurs en fonction de l’appartenance aux groupes [dans Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="d9b7d-117">For the business pilot and migration, Contoso used group-based licensing by following the steps in [Assign licenses to users by group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

 

 