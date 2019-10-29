---
title: 'Application patients pour les administrateurs teams '
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto: Microsoft Teams
ms.reviewer: anach
description: Application patients pour les administrateurs teams
ms.openlocfilehash: 1ed3efc1aa5a6d3eb4554fca6ee3bd7cfe57f4c0
ms.sourcegitcommit: 25b6bf2c3050390cd668d2495ffcf31c44d0ff62
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2019
ms.locfileid: "37749556"
---
# <a name="patients-app-overview"></a><span data-ttu-id="6f74d-103">Vue d’ensemble de l’application patients</span><span class="sxs-lookup"><span data-stu-id="6f74d-103">Patients app overview</span></span>

<span data-ttu-id="6f74d-104">L’application patients est une application Microsoft teams Store disponible pour tous les utilisateurs d’Teams.</span><span class="sxs-lookup"><span data-stu-id="6f74d-104">The Patients application is a Microsoft Teams store app available to all Teams users.</span></span> <span data-ttu-id="6f74d-105">L’application permet aux équipes de soins du patient constituée de personnes cliniques (par exemple, infirmières, médecins, travailleurs sociaux) d’organiser et de réviser des listes de patients dans le cas de scénarios allant de segments et de réunions d’équipes interdisciplinaires à la surveillance générale du patient.</span><span class="sxs-lookup"><span data-stu-id="6f74d-105">The app enables patient care teams consisting of clinical workers (e.g. Nurses, physicians, social workers) can curate and review lists of patients for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span>   

<span data-ttu-id="6f74d-106">L’application possède deux modes :</span><span class="sxs-lookup"><span data-stu-id="6f74d-106">The app has two modes:</span></span> 

- <span data-ttu-id="6f74d-107">Le mode connecté EMR qui se connecte à EMRs via FHIR.</span><span class="sxs-lookup"><span data-stu-id="6f74d-107">The EMR Connected mode that connects to EMRs through FHIR.</span></span> <span data-ttu-id="6f74d-108">L’application en mode connecté EMR reste en version privée prédéfinie, et les utilisateurs intéressés ou les administrateurs peuvent demander l’accès à l’application en déplaçant le message électronique de Microsoft sur teamsforhealthcare@service.microsoft.com contenant des informations sur leur client Office 365.</span><span class="sxs-lookup"><span data-stu-id="6f74d-108">The EMR Connected mode app stays in private preview and interested customers or admins may request access to the app by dropping Microsoft an email at teamsforhealthcare@service.microsoft.com with information about their Office 365 tenant.</span></span> 
- <span data-ttu-id="6f74d-109">Le mode manuel qui permet aux équipes de soins d’ajouter/de mettre en place des informations relatives aux patients manuellement.</span><span class="sxs-lookup"><span data-stu-id="6f74d-109">The manual mode that enables care teams to manually add/bring in patient information.</span></span> <span data-ttu-id="6f74d-110">L’application est disponible dans le magasin d’applications teams pour permettre aux utilisateurs finaux de télécharger par défaut une version d’évaluation publique.</span><span class="sxs-lookup"><span data-stu-id="6f74d-110">The application is available in the Teams app store for end users to download by default and is in public preview.</span></span> <span data-ttu-id="6f74d-111">L’application peut être limitée à certaines sections d’utilisateurs à l’aide [de stratégies de configuration d’applications dans Microsoft teams](../../teams-app-setup-policies.md)</span><span class="sxs-lookup"><span data-stu-id="6f74d-111">The app can be restricted to certain sections of users using [app setup policies in Microsoft Teams](../../teams-app-setup-policies.md)</span></span>



## <a name="usage-example"></a><span data-ttu-id="6f74d-112">Exemple d’utilisation</span><span class="sxs-lookup"><span data-stu-id="6f74d-112">Usage example</span></span>

<span data-ttu-id="6f74d-113">Au cours d’un arrondi dans le cadre d’une période de travail dans les soins médicaux, les médecins regroupent dans la station albattable des nouvelles mises à jour de l’évolution des patients.</span><span class="sxs-lookup"><span data-stu-id="6f74d-113">During rounding sessions on every shift in medical wards, clinicians gather at the nursing station to discuss the latest updates on the progress with patients in the ward.</span></span>  <span data-ttu-id="6f74d-114">Ils ont mis en surbrillance les métriques critiques principales (qui ne sont pas nécessairement médicales ou dont la mention est explicite sur les dossiers médicaux des patients) et permettent de s’assurer que le patient se trouve sur le chemin coulissant approprié pour se décharger en fonction du diagnostic.</span><span class="sxs-lookup"><span data-stu-id="6f74d-114">They highlight the key critical metrics (not necessarily medical or that its explicit on the patients’ medical records) and ensure the patient is on the right glide path to discharge based on their diagnosis.</span></span> <span data-ttu-id="6f74d-115">Pour arrondir ce qui est le cas, les soins d’une équipe fixent l’application du patient au sein d’une équipe où tous les médecins sont ajoutés et ajoutent des patients à une liste de patients.</span><span class="sxs-lookup"><span data-stu-id="6f74d-115">In order to round around these patients, the charge nurse sets up the patient app in a team where all the clinicians are added and adds patients to a patient list.</span></span> <span data-ttu-id="6f74d-116">Pendant les arrondis, les infirmières et le Givers d’autres soins pour le patient accèdent à l’application Microsoft teams et au patients sur leurs appareils mobiles et mettent à jour les informations pertinentes du patient sur son appareil, puis tout autre membre de l’équipe de soins peut voir ces mises à jour et notes et Restez synchronisé. Deux fois par jour, au début et à la fin d’une équipe, il a également des réunions d’équipe displicinary pour passer à la liste des patients et utiliser l’application patients pour vous mettre en ligne et partager les informations relatives à chaque patient à l’aide de l’application patients sur un grand écran d’affichage.</span><span class="sxs-lookup"><span data-stu-id="6f74d-116">During the rounds, the nurses and the other care givers for the patient access Microsoft Teams and the Patients app on their mobile devices and update relevant patient information on their device and then everyone else in the care team can see those updates and notes and stay in sync. Twice a day, at the start and end of a shift, they also have multi-displicinary team meetings to go over the patient list and use the Patients App to ground themselves and share information about each patient using the Patients app on a large display screen.</span></span> <span data-ttu-id="6f74d-117">Dans la plupart des cas, certains cliniciens pourront également se connecter à distance à ces équipes et continuer à participer à la discussion.</span><span class="sxs-lookup"><span data-stu-id="6f74d-117">Often times, certain clinicians may also dial in to these Teams meetings remotely and still be part of the discussion.</span></span> 

## <a name="configure-patients-app"></a><span data-ttu-id="6f74d-118">Configurer l’application patients</span><span class="sxs-lookup"><span data-stu-id="6f74d-118">Configure Patients app</span></span>

<span data-ttu-id="6f74d-119">Pour plus d’informations sur la façon de préparer votre environnement pour l’utilisation de l’application patients en mode EMR, voir intégration des enregistrements de la [santé électronique dans Microsoft teams](patients-app.md).</span><span class="sxs-lookup"><span data-stu-id="6f74d-119">For information on how to prepare your environment to use the EMR mode Patients app, see [Integrating Electronic Healthcare Records into Microsoft Teams](patients-app.md).</span></span> <span data-ttu-id="6f74d-120">Vous devrez également consulter la rubrique [gérer les stratégies de configuration des applications dans Microsoft teams](../../teams-app-setup-policies.md) pour activer l’application patients pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6f74d-120">You will also need to see [Manage app setup policies in Microsoft Teams](../../teams-app-setup-policies.md) to enable Patients app for your organization.</span></span>

<!-- For information on how your end users can access and install the Patients App to a team that they own or manage, you will need to see [End user documentation for the Patients App]() -->

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="related-topics"></a><span data-ttu-id="6f74d-121">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="6f74d-121">Related topics</span></span>

[<span data-ttu-id="6f74d-122">Intégration des dossiers médicaux électroniques dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6f74d-122">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
