---
title: Teams cas Contoso voix
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
description: Teams cas de voix pour une entreprise multinationale
appliesto:
- Microsoft Teams
ms.openlocfilehash: 085c9994bc2522d1ab56abc1670113e22d35f642
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121302"
---
# <a name="contoso-case-study-audio-conferencing"></a><span data-ttu-id="bc9a2-103">Étude de cas Contoso : Audioconférence</span><span class="sxs-lookup"><span data-stu-id="bc9a2-103">Contoso case study: Audio Conferencing</span></span>

<span data-ttu-id="bc9a2-104">Pour comprendre ce qu’est l’audioconférence, ses coûts, sa disponibilité et son fonctionnement, l’audioconférence examinée par &mdash; &mdash; Contoso [dans Office 365.](deploy-audio-conferencing-teams-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="bc9a2-104">To gain an understanding of audio conferencing&mdash;what it is, what it costs, availability, and how it works&mdash;Contoso reviewed [Audio Conferencing in Office 365](deploy-audio-conferencing-teams-landing-page.md).</span></span> 

## <a name="overview"></a><span data-ttu-id="bc9a2-105">Présentation</span><span class="sxs-lookup"><span data-stu-id="bc9a2-105">Overview</span></span> 

<span data-ttu-id="bc9a2-106">Pour l’audioconférence, Contoso utilisait des numéros de téléphone bien connus au sein de l’organisation ainsi qu’à l’extérieur.</span><span class="sxs-lookup"><span data-stu-id="bc9a2-106">For audio conferencing, Contoso used phone numbers that are well known within the organization as well as externally.</span></span> <span data-ttu-id="bc9a2-107">Comme Contoso souhaitait conserver ces numéros autant que possible, il a examiné les informations sur l’affectation de numéros de téléphone dédiés et partagés au pont de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="bc9a2-107">Because Contoso wanted to maintain these numbers where possible, they reviewed the information on assigning dedicated and shared phone numbers to the audio conferencing bridge.</span></span> 

<span data-ttu-id="bc9a2-108">D’après leurs recherches, Contoso a pris les décisions suivantes :</span><span class="sxs-lookup"><span data-stu-id="bc9a2-108">Based on their research, Contoso made the following decisions:</span></span> 

- <span data-ttu-id="bc9a2-109">Seul un segment de la population qui héberge régulièrement des appels d’audioconférence reçoit des licences d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="bc9a2-109">Only a segment of the population that regularly host audio conferencing calls would receive Audio Conferencing licenses.</span></span> 

- <span data-ttu-id="bc9a2-110">Contoso utiliserait des numéros de téléphone dédiés et portait ses numéros existants pour une utilisation avec l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="bc9a2-110">Contoso would use dedicated phone numbers and port their existing numbers for use with Audio Conferencing.</span></span>   

<span data-ttu-id="bc9a2-111">Étant donné que les utilisateurs de Contoso Skype Entreprise et que les boîtes aux lettres de tous les utilisateurs sont en ligne, de nombreux utilisateurs ont déjà prévu des réunions.</span><span class="sxs-lookup"><span data-stu-id="bc9a2-111">Because Contoso users were using Skype for Business and all users' mailboxes reside online, many users have existing meetings scheduled.</span></span> <span data-ttu-id="bc9a2-112">Contoso lit Utiliser le [service Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json) pour découvrir que les réunions existantes sont mises à jour automatiquement pour Contoso lorsqu’elles changent l’utilisateur final en mode TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="bc9a2-112">Contoso read [Using the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json) to learn that existing meetings are updated automatically for Contoso when they change the end user to TeamsOnly mode.</span></span>  


## <a name="configuration"></a><span data-ttu-id="bc9a2-113">Configuration</span><span class="sxs-lookup"><span data-stu-id="bc9a2-113">Configuration</span></span>

<span data-ttu-id="bc9a2-114">Téléphone les numéros associés à l’audioconférence sont appelés des numéros de service dans Système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="bc9a2-114">Phone numbers that are associated with audio conferencing are referred to as service numbers within Phone System.</span></span> 

- <span data-ttu-id="bc9a2-115">Pour les lieux qui utilisent des forfaits d’appels, pour le portage de leurs numéros de téléphone existants de leur opérateur vers Office 365, Contoso a suivi les étapes de obtention de numéros [de téléphone de service.](getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="bc9a2-115">For locations using Calling Plans, to port their existing phone numbers from their phone carrier to Office 365, Contoso followed the steps in [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

- <span data-ttu-id="bc9a2-116">Pour affecter la licence d’audioconférence à l’utilisateur final dans le cadre du pilote technique, l’administrateur Contoso a suivi les étapes de gestion des paramètres d’audioconférence pour [votre organisation.](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="bc9a2-116">To assign the Audio Conferencing license to the end user in the technical pilot, the Contoso administrator followed the steps in [Manage the Audio Conferencing settings for your organization](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).</span></span> 

- <span data-ttu-id="bc9a2-117">Pour le pilote et la migration d’entreprise, Contoso a utilisé la gestion des licences basée sur les groupes en suivant les étapes de la procédure Attribuer des licences aux utilisateurs en fonction de l’appartenance aux groupes [dans Azure Active Directory.](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="bc9a2-117">For the business pilot and migration, Contoso used group-based licensing by following the steps in [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

 

