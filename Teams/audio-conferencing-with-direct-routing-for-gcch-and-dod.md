---
title: Audioconférence avec routage direct pour GCCH et DoD
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Découvrez comment utiliser les fonctionnalités d’audioconférence avec le routage direct dans les environnements GCCH et DoD.
ms.openlocfilehash: 54458087b508c607b797cf7e7e877a8a793d8ed8
ms.sourcegitcommit: 6cbdcb8606044ad7ab49a4e3c828c2dc3d50fcc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/09/2019
ms.locfileid: "36272239"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="b8f93-103">Audioconférence avec routage direct et DoD</span><span class="sxs-lookup"><span data-stu-id="b8f93-103">Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="b8f93-104">Les conférences audio avec le routage direct de GCC High et DoD permettent aux participants de participer à des réunions d’équipes au sein de votre organisation de la société ou de la DoD, à l’aide d’un appareil téléphonique.</span><span class="sxs-lookup"><span data-stu-id="b8f93-104">Audio Conferencing with Direct Routing for GCC High and DoD enables participants to join Teams meetings in your GCC High or DoD organization by using a phone device.</span></span> <span data-ttu-id="b8f93-105">Les participants à la réunion peuvent préférer utiliser un appareil téléphonique pour participer à des réunions d’équipes dans des scénarios tels que la connectivité Internet est limitée ou lorsque les utilisateurs sont en déplacement et ne peuvent pas accéder à Teams.</span><span class="sxs-lookup"><span data-stu-id="b8f93-105">Meeting participants might prefer to use a phone device to join Teams meetings in scenarios such as when internet connectivity is limited or when users are on the road and don’t have access to Teams.</span></span> <span data-ttu-id="b8f93-106">Les participants peuvent rejoindre une réunion en composant un numéro de téléphone à composer pour votre organisation ou en faisant appel à la réunion par téléphone.</span><span class="sxs-lookup"><span data-stu-id="b8f93-106">Participants can choose to join meetings by either dialing in to a dial-in phone number for your organization or by having the meeting dial out to their phone device.</span></span>

<span data-ttu-id="b8f93-107">Dans le cadre de l’audioconférence avec le routage direct de GCC High et DoD, votre organisation utilise ses propres numéros en tant que numéros de téléphone rendez-vous et tous les appels sortants vers les appareils mobiles sont routés via le routage direct.</span><span class="sxs-lookup"><span data-stu-id="b8f93-107">With Audio Conferencing with Direct Routing for GCC High and DoD, your organization uses its own numbers as dial-in phone numbers and all meeting dial-outs to phone devices are routed via Direct Routing.</span></span> <span data-ttu-id="b8f93-108">Pour activer le service, les organisations doivent configurer le routage direct et configurer des numéros de téléphone qui peuvent être utilisés en tant que numéros de téléphone à composer.</span><span class="sxs-lookup"><span data-stu-id="b8f93-108">To enable the service, organizations need to set up Direct Routing and configure phone numbers that can be used as dial-in phone numbers.</span></span> <span data-ttu-id="b8f93-109">La configuration requise pour l’utilisation du routage direct est différente de celle proposée par le service de conférence rendez-vous par Microsoft, qui n’est pas un service de conférence téléphonique.</span><span class="sxs-lookup"><span data-stu-id="b8f93-109">The requirement to use Direct Routing is different from the Audio Conferencing service that's offered to non-GCC High and non-DoD organizations where the dial-in phone numbers are provided by Microsoft.</span></span>

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="b8f93-110">Déploiement de l’audioconférence avec le routage direct pour les services d’audioconférence et de DoD</span><span class="sxs-lookup"><span data-stu-id="b8f93-110">Deploy Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a><span data-ttu-id="b8f93-111">Étape 1: obtenir des services d’audioconférence avec le routage direct pour les licences GCC High ou DoD</span><span class="sxs-lookup"><span data-stu-id="b8f93-111">Step 1: Get Audio Conferencing with Direct Routing for GCC High or DoD licenses</span></span> 

<span data-ttu-id="b8f93-112">Pour utiliser l’audioconférence dans GCC High ou DoD, votre organisation et les utilisateurs de votre organisation doivent disposer d’une conférence audio avec une licence de routage directe attribuée.</span><span class="sxs-lookup"><span data-stu-id="b8f93-112">To use Audio Conferencing in GCC High or DoD, your organization and the users in your organization need to have an Audio Conferencing with Direct Routing license assigned.</span></span> <span data-ttu-id="b8f93-113">Vous trouverez ci-dessous les licences dont vous avez besoin pour activer l’audioconférence avec le routage direct pour la fonction DoD High ou DoD.</span><span class="sxs-lookup"><span data-stu-id="b8f93-113">Here are the licenses you need to enable Audio Conferencing with Direct Routing for GCC High or DoD.</span></span>

- <span data-ttu-id="b8f93-114">GCC High: une audioconférence pour les conférences audio: une licence pour les clients de votre organisation et de l’audioconférence: des licences plus élevées pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="b8f93-114">GCC High: An Audio Conferencing - GCC High Tenant license for your organization and Audio Conferencing - GCC High licenses for your users.</span></span>

- <span data-ttu-id="b8f93-115">DoD: licence de client de services d’audioconférence pour les licences de votre organisation et audioconférence-DoD pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="b8f93-115">DoD: An Audio Conferencing - DoD Tenant license for your organization and Audio Conferencing - DoD licenses for your users.</span></span>

<span data-ttu-id="b8f93-116">Une licence client et au moins une licence utilisateur sont requises pour activer le service.</span><span class="sxs-lookup"><span data-stu-id="b8f93-116">A tenant license and at least one user license are required to enable the service.</span></span> <span data-ttu-id="b8f93-117">Vous ne pouvez pas activer le service avec uniquement la licence client ou uniquement pour les licences utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b8f93-117">You can't enable the service with only the tenant license or with only user licenses.</span></span> <span data-ttu-id="b8f93-118">Pour obtenir des licences de service pour votre client et les utilisateurs de votre organisation, contactez l’équipe de votre compte.</span><span class="sxs-lookup"><span data-stu-id="b8f93-118">To get service licenses for your tenant and the users in your organization, contact your account team.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8f93-119">Les utilisateurs ne peuvent pas être activés pour les conférences audio avec le routage direct tant que les numéros de téléphone de connexion n’ont pas été configurés.</span><span class="sxs-lookup"><span data-stu-id="b8f93-119">Users can’t be enabled for Audio Conferencing with Direct Routing until dial-in phone numbers are set up.</span></span> <span data-ttu-id="b8f93-120">Nous vous conseillons de ne pas affecter les conférences audio avec le routage direct pour les licences pour les utilisateurs de la fonction DoD (High ou DoD) aux utilisateurs tant que vous n’avez pas configuré les numéros de téléphone à composer comme décrit dans cet article.</span><span class="sxs-lookup"><span data-stu-id="b8f93-120">We recommend that you not assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to users until you set up dial-in phone numbers as outlined in this article.</span></span>

### <a name="step-2-set-up-direct-routing"></a><span data-ttu-id="b8f93-121">Étape 2: configurer le routage direct</span><span class="sxs-lookup"><span data-stu-id="b8f93-121">Step 2: Set up Direct Routing</span></span>

<span data-ttu-id="b8f93-122">Pour configurer le routage direct, voir les articles suivants:</span><span class="sxs-lookup"><span data-stu-id="b8f93-122">To set up Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="b8f93-123">Planifier le routage direct</span><span class="sxs-lookup"><span data-stu-id="b8f93-123">Plan Direct Routing</span></span>](direct-routing-plan.md)

- [<span data-ttu-id="b8f93-124">Configurer le routage direct</span><span class="sxs-lookup"><span data-stu-id="b8f93-124">Configure Direct Routing</span></span>](direct-routing-configure.md)

> [!NOTE]
> <span data-ttu-id="b8f93-125">Lorsque vous configurez le routage direct, n’oubliez pas d’utiliser les noms de domaine complets et les ports de FQDN</span><span class="sxs-lookup"><span data-stu-id="b8f93-125">When you set up Direct Routing, remember to use the GCC High or DoD-specific FQDNs and ports that are described in these two articles.</span></span>

### <a name="step-3-set-up-dial-in-phone-numbers"></a><span data-ttu-id="b8f93-126">Étape 3: configurer les numéros de téléphone à composer</span><span class="sxs-lookup"><span data-stu-id="b8f93-126">Step 3: Set up dial-in phone numbers</span></span>

<span data-ttu-id="b8f93-127">Les numéros de téléphone à composer sont les numéros de téléphone associés à votre pont de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="b8f93-127">Dial-in phone numbers are the phone numbers that are associated to your Audio Conferencing bridge.</span></span> <span data-ttu-id="b8f93-128">Ces numéros permettent aux participants de participer à des réunions planifiées par des utilisateurs au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b8f93-128">These numbers are used by participants to join meetings scheduled by users in your organization.</span></span> <span data-ttu-id="b8f93-129">Ces numéros sont également inclus dans les invitations aux réunions des utilisateurs qui planifient des réunions au sein de votre organisation et sur la page «Rechercher un numéro local».</span><span class="sxs-lookup"><span data-stu-id="b8f93-129">These numbers are also included in the meeting invites of the users who schedule meetings in your organization and on the “Find a local number” page.</span></span>

#### <a name="define-service-phone-numbers-in-your-tenant"></a><span data-ttu-id="b8f93-130">Définir des numéros de téléphone de service dans votre client</span><span class="sxs-lookup"><span data-stu-id="b8f93-130">Define service phone numbers in your tenant</span></span>

<span data-ttu-id="b8f93-131">Vous pouvez utiliser l’applet de demande PowerShell New-csHybridTelephoneNumber pour définir des numéros de téléphone de service dans votre client, qui peuvent être utilisés pour acheminer les appels vers le service de visioconférence via le routage direct.</span><span class="sxs-lookup"><span data-stu-id="b8f93-131">You can use the New-csHybridTelephoneNumber PowerShell cmdlet to define service phone numbers in your tenant that can be used to route calls to the Audio Conferencing service via Direct Routing.</span></span> 

  ```
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

<span data-ttu-id="b8f93-132">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b8f93-132">For example:</span></span>
  ```
  New-csHybridTelephoneNumber -TelephoneNumber “+14250000000”
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="b8f93-133">Affecter les numéros de téléphone de service au pont de conférence audio de votre organisation</span><span class="sxs-lookup"><span data-stu-id="b8f93-133">Assign the service phone numbers to the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="b8f93-134">Vous pouvez affecter des numéros de service à votre pont de conférence audio de votre organisation à l’aide de l’applet de méthode PowerShell Register-Csonlinedialinconferencingservicenumberhttp.</span><span class="sxs-lookup"><span data-stu-id="b8f93-134">You can assign service phone numbers to the Audio Conferencing bridge of your organization by using the Register-csOnlineDialInConferencingServiceNumber PowerShell cmdlet.</span></span>

  ```
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

<span data-ttu-id="b8f93-135">Vous pouvez voir l’ID de votre pont de conférence audio à l’aide de Get-CsOnlineDialInConferencingBridge.</span><span class="sxs-lookup"><span data-stu-id="b8f93-135">You can see the ID of your Audio Conferencing Bridge using Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="b8f93-136">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b8f93-136">For example:</span></span>

  ```
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```

### <a name="step-4-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a><span data-ttu-id="b8f93-137">Étape 4: attribuer des conférences audio avec le routage direct pour les licences GCC High ou DoD à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="b8f93-137">Step 4: Assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your users</span></span>

<span data-ttu-id="b8f93-138">Pour attribuer des conférences audio avec le routage direct pour les licences GCC High ou DoD aux utilisateurs, voir [attribuer des licences aux utilisateurs dans Office 365 pour les entreprises](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="b8f93-138">To assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your user, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span></span>

### <a name="step-5-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a><span data-ttu-id="b8f93-139">Étape 5: (facultatif) afficher une liste des numéros de conférence audio dans teams</span><span class="sxs-lookup"><span data-stu-id="b8f93-139">Step 5: (Optional) See a list of Audio Conferencing numbers in Teams</span></span>

<span data-ttu-id="b8f93-140">Pour afficher la liste des numéros de conférence audio de votre organisation, consultez la [liste des numéros de conférence audio dans Microsoft teams](see-a-list-of-audio-conferencing-numbers-in-teams.md) .</span><span class="sxs-lookup"><span data-stu-id="b8f93-140">To see the list of Audio Conferencing numbers of your organization, go to [See a list of Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span></span>

### <a name="step-6-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a><span data-ttu-id="b8f93-141">Étape 6: (facultatif) définir les langues du standard automatique pour les numéros d’accès pour les conférences audio de votre organisation</span><span class="sxs-lookup"><span data-stu-id="b8f93-141">Step 6: (Optional) Set auto attendant languages for the Audio Conferencing dial-in numbers of you organization</span></span>

<span data-ttu-id="b8f93-142">Pour modifier la langue des numéros d’accès pour les conférences audio de votre organisation, voir [définir les langues du standard automatique pour les conférences audio dans Microsoft teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="b8f93-142">To change the languages of the Audio Conferencing dial-in numbers of your organization, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)</span></span>

### <a name="step-7-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="b8f93-143">Étape 7: (facultatif) modifier les paramètres du pont de conférence audio de votre organisation</span><span class="sxs-lookup"><span data-stu-id="b8f93-143">Step 7: (Optional) Change the settings of the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="b8f93-144">Pour modifier les paramètres du pont de conférence audio de votre organisation, voir [modifier les paramètres d’un pont de conférence audio](change-the-settings-for-an-audio-conferencing-bridge.md) .</span><span class="sxs-lookup"><span data-stu-id="b8f93-144">To change the settings of the Audio Conferencing bridge of your organization, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md)</span></span>

### <a name="step-8-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a><span data-ttu-id="b8f93-145">Étape 8: (facultatif) définir les numéros de téléphone inclus dans les invitations aux réunions des utilisateurs de votre organisation</span><span class="sxs-lookup"><span data-stu-id="b8f93-145">Step 8: (Optional) Set the phone numbers included in the meeting invites of the users in your organization</span></span>

<span data-ttu-id="b8f93-146">Pour modifier l’ensemble des numéros de téléphone inclus dans les invitations aux réunions des utilisateurs de votre organisation, voir [définir les numéros de téléphone inclus dans les invitations dans Microsoft teams](set-the-phone-numbers-included-on-invites-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="b8f93-146">To change the set of phone numbers that are included in the meeting invites of the users is your organization, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md)</span></span>

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="b8f93-147">Les fonctionnalités d’audioconférence ne sont pas prises en charge dans les conférences audio avec le routage direct de GCC High et DoD</span><span class="sxs-lookup"><span data-stu-id="b8f93-147">Audio Conferencing capabilities not supported in Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="b8f93-148">Voici les fonctionnalités de l’audioconférence qui ne sont pas prises en charge dans les conférences audio avec le routage direct pour les services de préversion de GCC et de DoD:</span><span class="sxs-lookup"><span data-stu-id="b8f93-148">The following are Audio Conferencing capabilities that are not supported in Audio Conferencing with Direct Routing for GCC High and DoD:</span></span>

- <span data-ttu-id="b8f93-149">Notifications d’entrée et de sortie utilisant l’enregistrement de nom.</span><span class="sxs-lookup"><span data-stu-id="b8f93-149">Entry and exit notifications using name recording.</span></span> <span data-ttu-id="b8f93-150">Pour les conférences audio avec le routage direct, les notifications d’entrée et de sortie sont lues dans la réunion en tant que tonalités.</span><span class="sxs-lookup"><span data-stu-id="b8f93-150">For Audio Conferencing with Direct Routing, entry and exit notifications are played in the meeting as tones.</span></span>

- <span data-ttu-id="b8f93-151">Stratégies de restriction des appels sortants pour les conférences audio.</span><span class="sxs-lookup"><span data-stu-id="b8f93-151">Outbound calling restriction policies for Audio Conferencing.</span></span> <span data-ttu-id="b8f93-152">Les contrôles de niveau utilisateur permettant de limiter les appels sortants ne sont pas applicables aux appels sortants de réunion routés via le routage direct.</span><span class="sxs-lookup"><span data-stu-id="b8f93-152">User-level controls to restrict outbound calls aren’t applicable to meeting dial-out calls routed via Direct Routing.</span></span>

- <span data-ttu-id="b8f93-153">Désactivez l’utilisation des numéros sans frais pour l’organisateur de la réunion.</span><span class="sxs-lookup"><span data-stu-id="b8f93-153">Disable the usage of toll-free numbers for the meetings specific organizer.</span></span> <span data-ttu-id="b8f93-154">Les contrôles de niveau utilisateur permettant de limiter l’utilisation des numéros gratuits pour participer aux réunions de votre organisation ne sont pas applicables aux appels routés via le routage direct.</span><span class="sxs-lookup"><span data-stu-id="b8f93-154">User-level controls to restrict the usage of toll-free numbers to join the meetings of your organization aren’t applicable to calls routed via Direct Routing.</span></span>

- <span data-ttu-id="b8f93-155">Envoyer des notifications par courrier électronique aux utilisateurs en cas de modification de leurs paramètres.</span><span class="sxs-lookup"><span data-stu-id="b8f93-155">Sending notification emails to users when their settings change.</span></span> <span data-ttu-id="b8f93-156">Les messages électroniques de notification de l’audioconférence ne sont pas pris en charge pour les conférences audio avec le routage direct pour les services de messagerie générale de GCC.</span><span class="sxs-lookup"><span data-stu-id="b8f93-156">Audio Conferencing notification emails aren’t supported for Audio Conferencing with Direct Routing for GCC High and DoD.</span></span>
