---
title: Teams pour les visites virtuelles
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Utiliser Microsoft Teams pour configurer votre système de visites virtuelles
ms.openlocfilehash: 6753afbabf6bbcb420f9ddf479249a968d33eb2c
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055691"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a><span data-ttu-id="decd1-103">Visites virtuelles avec Teams - Intégration à EHR</span><span class="sxs-lookup"><span data-stu-id="decd1-103">Virtual visits with Teams - Integration into EHR</span></span>

<span data-ttu-id="decd1-104">Microsoft Teams Electronic Health Record (EHR) Connector permet aux cartésiens de lancer facilement une visite de patient virtuel ou une consultation avec un autre fournisseur dans Teams directement à partir du système EHR.</span><span class="sxs-lookup"><span data-stu-id="decd1-104">Microsoft Teams Electronic Health Record (EHR) Connector makes it easy for clinicians to launch a virtual patient visit or consultation with another provider in Teams directly from the EHR system.</span></span> <span data-ttu-id="decd1-105">Conçu sur le cloud Microsoft 365, Microsoft Teams permet une collaboration et une communication simples et sécurisées grâce aux outils de conversation, vidéo, voix et soins de santé dans un hub unique qui prend en charge la conformité avec hipAA, la certification HITECH et bien plus encore.</span><span class="sxs-lookup"><span data-stu-id="decd1-105">Built on the Microsoft 365 cloud, Microsoft Teams enables simple, secure collaboration and communication with chat, video, voice, and healthcare tools in a single hub that supports compliance with HIPAA, HITECH certification, and more.</span></span>
<span data-ttu-id="decd1-106">La plateforme de communication et de collaboration de Teams permet aux responsables de réduire facilement l’encombrement des systèmes fragmentés et leur permet de consacrer du temps aux meilleurs soins possibles.</span><span class="sxs-lookup"><span data-stu-id="decd1-106">The communication and collaboration platform of Teams makes it easy for clinicians to cut through the clutter of fragmented systems so they can spend time providing the best possible care.</span></span> <span data-ttu-id="decd1-107">Microsoft Teams Electronic Health Record (EHR) Connector peut :</span><span class="sxs-lookup"><span data-stu-id="decd1-107">Microsoft Teams Electronic Health Record (EHR) Connector can:</span></span>
- <span data-ttu-id="decd1-108">Lancez les visites virtuelles Teams à partir des portails des fournisseurs et des patients.</span><span class="sxs-lookup"><span data-stu-id="decd1-108">Launch Teams virtual visits from both provider and patient portals.</span></span>
- <span data-ttu-id="decd1-109">Écrivez de nouveau dans les métadonnées EHR sur les événements de connexion et de déconnexion pour activer l’audit automatique et la conservation d’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="decd1-109">Write back into EHR metadata on connect and disconnect events to enable automatic auditing and record keeping.</span></span>
- <span data-ttu-id="decd1-110">Intégrez-vous aux flux de travail de patient et de patient existants tout en leur permettant d’utiliser Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="decd1-110">Integrate into existing clinician and patient workflows while allowing them to use Microsoft Teams.</span></span>

  <span data-ttu-id="decd1-111">Regardez la vidéo sur la gestion des visites virtuelles à partir du portail EHR.</span><span class="sxs-lookup"><span data-stu-id="decd1-111">Watch the video of How to manage virtual visits from the EHR portal.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a><span data-ttu-id="decd1-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="decd1-112">Before you begin</span></span>

<span data-ttu-id="decd1-113">Avant d’intégrer le connecteur EHR, vous devez vous assurer que vous avez les conditions préalables suivantes :</span><span class="sxs-lookup"><span data-stu-id="decd1-113">You’ll need to make sure you have the following prerequisites before you can integrate the EHR connector:</span></span>

- <span data-ttu-id="decd1-114">Accès à l’application Microsoft Teams dans [le marketplace App Marketplace de Android.](https://apporchard.epic.com/Gallery?id=6153)</span><span class="sxs-lookup"><span data-stu-id="decd1-114">Access to use to the Microsoft Teams app in [Epic’s App Orchard marketplace](https://apporchard.epic.com/Gallery?id=6153).</span></span>

- <span data-ttu-id="decd1-115">Abonnement actif à Microsoft Cloud pour les soins de santé ou abonnement à l’offre autonome Microsoft Teams EHR Connector.</span><span class="sxs-lookup"><span data-stu-id="decd1-115">Active subscription to Microsoft Cloud for Healthcare or subscription to Microsoft Teams EHR Connector standalone offer.</span></span>

- <span data-ttu-id="decd1-116">Les utilisateurs doivent avoir une licence Microsoft 365 ou Office 365 appropriée qui inclut les réunions Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="decd1-116">Users must have an appropriate Microsoft 365 or Office 365 license that includes Microsoft Teams meetings.</span></span>

- <span data-ttu-id="decd1-117">Microsoft Teams doit être adopté et utilisé au sein de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="decd1-117">Microsoft Teams should be adopted and used inside the organization.</span></span>

- <span data-ttu-id="decd1-118">Les organisations doivent avoir cette version en novembre 2018 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="decd1-118">Organizations must have with Epic version November 2018 or later.</span></span>

- <span data-ttu-id="decd1-119">Vos systèmes doivent satisfaire toutes les conditions requises pour les [logiciels et les navigateurs.](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)</span><span class="sxs-lookup"><span data-stu-id="decd1-119">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

<span data-ttu-id="decd1-120">Vous aurez également besoin des informations des personnes suivantes de votre organisation :</span><span class="sxs-lookup"><span data-stu-id="decd1-120">You’ll also need information from the following people in your organization:</span></span>

- <span data-ttu-id="decd1-121">Administrateur Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="decd1-121">Microsoft 365 administrator</span></span>

- <span data-ttu-id="decd1-122">Analyste client fidèle</span><span class="sxs-lookup"><span data-stu-id="decd1-122">Epic customer analyst</span></span>

> [!Note]
> <span data-ttu-id="decd1-123">Demandez à votre spécialiste technique de l’équipement de Epic-Microsoft le guide d’intégration de la téléhealthe de Teams disponible sur le marketplace Dessinsus.</span><span class="sxs-lookup"><span data-stu-id="decd1-123">Request your Epic technical specialist to provide the Epic-Microsoft Teams Telehealth Integration Guide available in the Epic marketplace.</span></span>

## <a name="connector-setup"></a><span data-ttu-id="decd1-124">Configuration des connecteurs</span><span class="sxs-lookup"><span data-stu-id="decd1-124">Connector setup</span></span>

<span data-ttu-id="decd1-125">La configuration du connecteur nécessite que vous :</span><span class="sxs-lookup"><span data-stu-id="decd1-125">The connector setup requires that you:</span></span>

- [<span data-ttu-id="decd1-126">Lancer le portail de configuration du connecteur EHR</span><span class="sxs-lookup"><span data-stu-id="decd1-126">Launch the EHR Connector configuration portal</span></span>](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [<span data-ttu-id="decd1-127">Informations de configuration</span><span class="sxs-lookup"><span data-stu-id="decd1-127">Configuration information</span></span>](ehr-admin.md#configuration-information)
- [<span data-ttu-id="decd1-128">Approuver ou afficher la configuration</span><span class="sxs-lookup"><span data-stu-id="decd1-128">Approve or view configuration</span></span>](ehr-admin.md#approve-or-view-configuration)
- [<span data-ttu-id="decd1-129">Passer en revue et terminer la configuration</span><span class="sxs-lookup"><span data-stu-id="decd1-129">Review and finish the configuration</span></span>](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[<span data-ttu-id="decd1-130">Lancer le portail de configuration du connecteur EHR</span><span class="sxs-lookup"><span data-stu-id="decd1-130">Launch the EHR Connector configuration portal</span></span>](#launch-the-ehr-connector-configuration-portal)

<span data-ttu-id="decd1-131">La configuration de votre organisation de santé pour lancer des visites virtuelles avec Microsoft Teams commence par le portail de configuration ehr Connector.</span><span class="sxs-lookup"><span data-stu-id="decd1-131">Configuring your healthcare organization to launch virtual visits with Microsoft Teams starts by launching the EHR Connector configuration portal.</span></span> <span data-ttu-id="decd1-132">Vous configurez une ou plusieurs organisations pour tester l’intégration.</span><span class="sxs-lookup"><span data-stu-id="decd1-132">You configure a single or multiple organizations to test the integration.</span></span> <span data-ttu-id="decd1-133">Configurez l’URL de test et de production dans le portail de configuration.</span><span class="sxs-lookup"><span data-stu-id="decd1-133">Configure the test and production URL in the configuration portal.</span></span> <span data-ttu-id="decd1-134">Testez l’intégration à partir de l’environnement de test DeNs avant de passer à la production.</span><span class="sxs-lookup"><span data-stu-id="decd1-134">Test the integration from Epic’s test environment before moving to production.</span></span>
  
- <span data-ttu-id="decd1-135">URL de configuration du connecteur EHR : [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="decd1-135">EHR connector configuration URL: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span></span>

<span data-ttu-id="decd1-136">L’administrateur Microsoft 365 et l’analyste client Yahoo ! de votre organisation doivent suivre les étapes d’intégration et d’information dans le portail de configuration.</span><span class="sxs-lookup"><span data-stu-id="decd1-136">The Microsoft 365 admin and Epic customer analyst from your organization must complete the information and integration steps in the configuration portal.</span></span> <span data-ttu-id="decd1-137">Pour plus d’informations sur la configuration du site, contactez la ressource du spécialiste technique Desas qui est affectée à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="decd1-137">For Epic configuration steps, contact the Epic technical specialist resource assigned to your organization.</span></span>

### <a name="configuration-information"></a>[<span data-ttu-id="decd1-138">Informations de configuration</span><span class="sxs-lookup"><span data-stu-id="decd1-138">Configuration information</span></span>](#configuration-information)

<span data-ttu-id="decd1-139">Cette étape doit être effectuée par **l’administrateur Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="decd1-139">This step is to be completed by the **Microsoft 365 administrator**.</span></span> <span data-ttu-id="decd1-140">L’administrateur Microsoft 365 doit lancer le portail de configuration des connecteurs et se connecter avec les informations d’identification Microsoft pour démarrer le processus de configuration.</span><span class="sxs-lookup"><span data-stu-id="decd1-140">The Microsoft 365 administrator must launch the connector configuration portal and sign in with Microsoft credentials to start the configuration process.</span></span>

<span data-ttu-id="decd1-141">Pour effectuer cette étape, l’administrateur Microsoft 365 doit recevoir une URL de base Fast Health Interoperability Resources (F URL) valide de votre spécialiste technique Ceci et le nom d’utilisateur de l’analyste client Terminée qui approuvera la configuration.</span><span class="sxs-lookup"><span data-stu-id="decd1-141">To complete this step, the Microsoft 365 administrator must receive a valid Fast Health Interoperability Resources (FHIR) base URL from your Epic technical specialist and the username of the Epic customer analyst who will be approving the configuration.</span></span> <span data-ttu-id="decd1-142">L’administrateur Microsoft 365 doit lancer la page de configuration du connecteur et se connecter avec les informations d’identification Microsoft pour démarrer le processus de configuration.</span><span class="sxs-lookup"><span data-stu-id="decd1-142">The Microsoft 365 administrator must launch the connector configuration page and sign in with Microsoft credentials to start the configuration process.</span></span>

- <span data-ttu-id="decd1-143">L’URL de base FEMBA est une adresse statique correspondant au point de terminaison de l’API FEMBA de votre serveur.</span><span class="sxs-lookup"><span data-stu-id="decd1-143">The FHIR base URL is a static address corresponding to your server FHIR API endpoint.</span></span> <span data-ttu-id="decd1-144">Par exemple, l’URL `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST` est .</span><span class="sxs-lookup"><span data-stu-id="decd1-144">An example URL is `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span></span>

- <span data-ttu-id="decd1-145">Le nom de l’approbateur de configuration est le nom de l’analyste clientRobien qui sera responsable de l’approbation de la configuration au cours de l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="decd1-145">Configuration approver name is the name of the Epic customer analyst who will be responsible for approving the configuration in the next step.</span></span> <span data-ttu-id="decd1-146">L’analyste client Densoine est une personne de votre organisation qui a accès à La france.</span><span class="sxs-lookup"><span data-stu-id="decd1-146">The Epic customer analyst is a person in your organization with signin access to Epic.</span></span>

  ![Le nom de l’approveur de configuration est sélectionné dans une liste du connecteur EHR.](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[<span data-ttu-id="decd1-148">Approuver ou afficher la configuration</span><span class="sxs-lookup"><span data-stu-id="decd1-148">Approve or view configuration</span></span>](#approve-or-view-configuration)

<span data-ttu-id="decd1-149">L’analyste client de votre organisation médicale qui a été ajoutée en tant qu’approbation doit maintenant utiliser la même URL de connecteur EHR que lors de l’étape précédente pour se connecter à l’aide de ses informations d’identification Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="decd1-149">The Epic customer analyst for your healthcare organization who was added as an approver must now use the same EHR Connector URL from the previous step to sign in using their Microsoft 365 credentials.</span></span> <span data-ttu-id="decd1-150">Une fois la validation validée, l’approuveur sera invité à se connecter à l’aide de ses informations d’identification Densique pour valider l’organisation.</span><span class="sxs-lookup"><span data-stu-id="decd1-150">After successful validation, the approver is going to be asked to sign in using their Epic credentials to validate the Epic organization.</span></span>

> [!Note]
> <span data-ttu-id="decd1-151">L’administrateur Microsoft 365 et l’analyste client Andyh de votre organisation peuvent être la même personne.</span><span class="sxs-lookup"><span data-stu-id="decd1-151">The Microsoft 365 admin and Epic customer analyst in your organization can be the same person.</span></span> <span data-ttu-id="decd1-152">Dans ce cas, ajoutez votre propre nom d’utilisateur en tant qu’approver.</span><span class="sxs-lookup"><span data-stu-id="decd1-152">In that case, add your own username as approver.</span></span> <span data-ttu-id="decd1-153">Vous devrez tout de même vous connectez à Ainsi, pour valider votre accès.</span><span class="sxs-lookup"><span data-stu-id="decd1-153">You'll still need to sign in to Epic to validate your access.</span></span> <span data-ttu-id="decd1-154">La validation de la validation de l’URL de base de votre FEMBA est uniquement utilisée.</span><span class="sxs-lookup"><span data-stu-id="decd1-154">The Epic sign in is only used to validate your FHIR base URL.</span></span> <span data-ttu-id="decd1-155">Microsoft ne stocke pas les informations d’identification ou n’accède pas aux données EHR avec cette connexion.</span><span class="sxs-lookup"><span data-stu-id="decd1-155">Microsoft won't store credentials or access EHR data with this sign in.</span></span>

  ![Vérifiez et approuvez la configuration des informations d’identification.](../../media/approve-view-configuration.png)

<span data-ttu-id="decd1-157">Après une bonne inscription au service, l’analyste du client Quiz doit **approuver** la configuration.</span><span class="sxs-lookup"><span data-stu-id="decd1-157">After a successful Epic sign in, the Epic customer analyst **must** approve the configuration.</span></span> <span data-ttu-id="decd1-158">Si la configuration n’est pas correcte, l’administrateur Microsoft 365 aura la possibilité de modifier les configurations d’origine en se connectant à nouveau au portail de connecteur Ehr Microsoft.</span><span class="sxs-lookup"><span data-stu-id="decd1-158">If the configuration isn't correct, the Microsoft 365 admin will have the ability to modify the original configurations by signing in to the Microsoft EHR connector portal again.</span></span> 

![Confirmez que le connecteur EHR est configuré et l’option de modification de la configuration.](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[<span data-ttu-id="decd1-160">Passer en revue et terminer la configuration</span><span class="sxs-lookup"><span data-stu-id="decd1-160">Review and finish the configuration</span></span>](#review-and-finish-the-configuration)

<span data-ttu-id="decd1-161">Lorsque les informations de configuration sont approuvées par l’administrateur d’Équipe, des enregistrements d’intégration pour le lancement par les patients et les fournisseurs s’offrent à vous.</span><span class="sxs-lookup"><span data-stu-id="decd1-161">When the configuration information is approved by the Epic administrator, you'll be presented with integration records for patient and provider launch.</span></span> <span data-ttu-id="decd1-162">Ces enregistrements sont nécessaires pour effectuer la configuration de la visite virtuelle dans Le Monde.</span><span class="sxs-lookup"><span data-stu-id="decd1-162">These records are necessary to complete the virtual visit configuration in Epic.</span></span> <span data-ttu-id="decd1-163">Pour plus d’informations, reportez-vous Epic-Microsoft guide d’intégration de la téléhealthe de Teams.</span><span class="sxs-lookup"><span data-stu-id="decd1-163">Refer to the Epic-Microsoft Teams Telehealth Integration guide for more details.</span></span>

> [!Note]  
> <span data-ttu-id="decd1-164">L’analyste client Microsoft 365 ou Yahoo! peut à tout moment se connecter au portail de configuration pour afficher les enregistrements d’intégration et modifier la configuration de l’organisation, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="decd1-164">At any time the Microsoft 365 or Epic customer analyst can sign in to the configuration portal to view integration records and modify organization configuration, if needed.</span></span>

![Les informations d’intégration s’affichent.](../../media/finish-configuration.png)

> [!Note]
> <span data-ttu-id="decd1-166">Avant cela, le processus d’approbation doit être effectué par l’analyste client Qun lui-même pour chaque URL F URL configurée par l’administrateur Microsoft.</span><span class="sxs-lookup"><span data-stu-id="decd1-166">The approval process must be completed by the Epic customer analyst for every FHIR URL configured by the Microsoft admin before.</span></span>

![Les informations de configuration sont approuvées.](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a><span data-ttu-id="decd1-168">Lancer des visites virtuelles Teams</span><span class="sxs-lookup"><span data-stu-id="decd1-168">Launch Teams virtual visits</span></span>

<span data-ttu-id="decd1-169">Une fois que vous avez terminé les étapes du connecteur EHR et la configuration d’Andy, votre organisation est prête à prendre en charge les visites vidéo avec Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="decd1-169">After completing the EHR Connector steps and Epic configuration, your organization is ready to support video visits with Microsoft Teams.</span></span>

### <a name="virtual-visit-prerequisites"></a><span data-ttu-id="decd1-170">Conditions préalables pour une visite virtuelle</span><span class="sxs-lookup"><span data-stu-id="decd1-170">Virtual visit prerequisites</span></span>

- <span data-ttu-id="decd1-171">Vos systèmes doivent satisfaire toutes les conditions requises pour les [logiciels et les navigateurs.](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)</span><span class="sxs-lookup"><span data-stu-id="decd1-171">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

- <span data-ttu-id="decd1-172">L’organisation de soins de santé doit avoir effectué la configuration entre l’organisation Ci-après et l’organisation Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="decd1-172">Healthcare organization must have completed the setup between the Epic organization and Microsoft 365 organization.</span></span>

### <a name="provider-experience"></a><span data-ttu-id="decd1-173">Expérience du fournisseur</span><span class="sxs-lookup"><span data-stu-id="decd1-173">Provider experience</span></span>

<span data-ttu-id="decd1-174">Les fournisseurs de soins de votre organisation peuvent également participer à des visites virtuelles avec Microsoft Teams à partir de leurs applications fournisseurs de service (Hyperspace,Pérku, Canto).</span><span class="sxs-lookup"><span data-stu-id="decd1-174">Healthcare providers from your organization can also join virtual visits with Microsoft Teams from their Epic provider applications (Hyperspace, Haiku, Canto).</span></span> <span data-ttu-id="decd1-175">Le **bouton Démarrer la visite** virtuelle est incorporé dans le flux du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="decd1-175">The **Begin virtual visit** button is embedded in the provider flow.</span></span>

<span data-ttu-id="decd1-176">Principales fonctionnalités de l’expérience du fournisseur :</span><span class="sxs-lookup"><span data-stu-id="decd1-176">Key features of the provider experience:</span></span>

- <span data-ttu-id="decd1-177">Les fournisseurs peuvent participer à des visites virtuelles à l’aide de navigateurs pris en charge ou de l’application Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="decd1-177">Providers can join virtual visits using supported browsers or the Microsoft Teams application.</span></span>

- <span data-ttu-id="decd1-178">Les fournisseurs doivent se connecter une seule fois avec leur compte Microsoft 365 lorsqu’ils participent à une visite virtuelle pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="decd1-178">Providers must do a one-time sign-in with their Microsoft 365 account when joining a virtual visit for the first time.</span></span>

- <span data-ttu-id="decd1-179">Après la première inscription, le fournisseur sera directement placé sur le rendez-vous virtuel dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="decd1-179">After the one-time sign-in, the provider will be taken straight to the virtual appointment in Microsoft Teams.</span></span> <span data-ttu-id="decd1-180">(Le fournisseur doit être inscrit à Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="decd1-180">(Provider must be signed-in to Microsoft Teams).</span></span>

- <span data-ttu-id="decd1-181">Le fournisseur peut voir les mises à jour en temps réel des participants se connecter et se déconnecter pour un rendez-vous donné.</span><span class="sxs-lookup"><span data-stu-id="decd1-181">Provider can see real-time updates of participants connect and disconnect for a given appointment.</span></span> <span data-ttu-id="decd1-182">Le fournisseur peut voir quand le patient est connecté à une visite virtuelle.</span><span class="sxs-lookup"><span data-stu-id="decd1-182">The provider can see when the patient is connected to a virtual visit.</span></span>

  ![Expérience du fournisseur d’une visite virtuelle avec un patient](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a><span data-ttu-id="decd1-184">Expérience des patients</span><span class="sxs-lookup"><span data-stu-id="decd1-184">Patient experience</span></span>

<span data-ttu-id="decd1-185">Le connecteur prend en charge les patients rejoignant des visites virtuelles via MyChart web et mobile.</span><span class="sxs-lookup"><span data-stu-id="decd1-185">The connector supports patients joining virtual visits through MyChart web and mobile.</span></span> <span data-ttu-id="decd1-186">Au moment du rendez-vous, les patients peuvent démarrer une visite virtuelle à partir de MyChart à l’aide du **bouton Commencer la visite** virtuelle.</span><span class="sxs-lookup"><span data-stu-id="decd1-186">At the time of the appointment, patients can start a virtual visit from MyChart using the **Begin virtual visit** button.</span></span>

<span data-ttu-id="decd1-187">Principales fonctionnalités de l’expérience du patient :</span><span class="sxs-lookup"><span data-stu-id="decd1-187">Key features of the patient experience:</span></span>

- <span data-ttu-id="decd1-188">Les patients peuvent rejoindre des visites virtuelles à partir de navigateurs web modernes sur un ordinateur de bureau ou un appareil mobile sans installation de l’application.</span><span class="sxs-lookup"><span data-stu-id="decd1-188">Patients can join virtual visits from modern web browsers on desktop and mobile without app installation.</span></span>

- <span data-ttu-id="decd1-189">Les patients peuvent participer à des visites virtuelles d’un simple clic et il n’est pas nécessaire d’utiliser un autre compte ou aucune autre inscription.</span><span class="sxs-lookup"><span data-stu-id="decd1-189">Patients can join virtual visits with a single click and there is no other account or sign-in required.</span></span>

- <span data-ttu-id="decd1-190">Les patients n’ont pas besoin de créer un compte Microsoft ou de se connecter pour lancer une visite virtuelle.</span><span class="sxs-lookup"><span data-stu-id="decd1-190">Patients aren't required to create a Microsoft account or sign in to launch a virtual visit.</span></span>

- <span data-ttu-id="decd1-191">Les patients sont placés dans une salle d’accueil jusqu’à ce que le fournisseur de soins rejoigne le rendez-vous et les admette à la visite virtuelle.</span><span class="sxs-lookup"><span data-stu-id="decd1-191">Patients will be placed in a lobby until the healthcare provider joins the appointment and admits them to the virtual visit.</span></span>

- <span data-ttu-id="decd1-192">Test de la vidéo et du microphone est disponible dans la salle d’accueil avant de rejoindre la visite virtuelle.</span><span class="sxs-lookup"><span data-stu-id="decd1-192">Testing of the video and microphone is available in the lobby before joining the virtual visit.</span></span>

  ![Expérience patient de la visite virtuelle](../../media/ehc-virtual-visit-5.png)

> [!Note]
> <span data-ttu-id="decd1-194">Les productions d’Omkt, de MyChart, de Référence et de Canto sont des marques commerciales de Système d’image.</span><span class="sxs-lookup"><span data-stu-id="decd1-194">Epic, MyChart, Haiku, and Canto are trademarks of Epic Systems Corporation.</span></span>

### <a name="privacy-and-location-of-data"></a><span data-ttu-id="decd1-195">Confidentialité et emplacement des données</span><span class="sxs-lookup"><span data-stu-id="decd1-195">Privacy and location of data</span></span>

<span data-ttu-id="decd1-196">L’intégration de Teams aux systèmes EHR optimise la quantité de données utilisées et stockées pendant l’intégration et les flux de visites virtuelles.</span><span class="sxs-lookup"><span data-stu-id="decd1-196">Teams integration into EHR systems optimizes the amount of data being used and stored during integration and virtual visit flows.</span></span> <span data-ttu-id="decd1-197">La solution est adaptée aux principes et directives généraux de confidentialité et de gestion des données de Teams décrits dans la protection des données.</span><span class="sxs-lookup"><span data-stu-id="decd1-197">The solution follows the overall Teams privacy and data management principles and guidelines outlined in Teams Privacy.</span></span>

<span data-ttu-id="decd1-198">Le connecteur EHR de Microsoft Teams ne stocke ni ne transfère aucune donnée personnelle identifiable ou les dossiers médicaux des patients ou fournisseurs de soins à partir du système EHR.</span><span class="sxs-lookup"><span data-stu-id="decd1-198">The Microsoft Teams EHR connector doesn't store nor transfer any identifiable personal data or any health records of patients or healthcare providers from the EHR system.</span></span> <span data-ttu-id="decd1-199">Les seules données stockées par le connecteur EHR sont l’ID unique de l’utilisateur EHR, qui est utilisé lors de l’installation de la réunion Teams.</span><span class="sxs-lookup"><span data-stu-id="decd1-199">The only data that is stored by the EHR connector is the EHR user’s unique ID, which is used during Teams meeting setup.</span></span> <span data-ttu-id="decd1-200">L’ID unique de l’utilisateur EHR est stocké dans l’une des trois régions géographiques décrites dans l’emplacement où sont stockées les données client de votre [client Microsoft 365.](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies)</span><span class="sxs-lookup"><span data-stu-id="decd1-200">The EHR user’s unique ID is stored in one of the three geographic regions described in [Where your Microsoft 365 customer data is stored](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies).</span></span> <span data-ttu-id="decd1-201">Toutes les discussions, enregistrements et autres données entrées dans Teams par les participants à la réunion sont stockés conformément aux stratégies de stockage existantes.</span><span class="sxs-lookup"><span data-stu-id="decd1-201">All chat, recordings, and other data entered into Teams by the meeting participants are stored according to existing storage policies.</span></span> <span data-ttu-id="decd1-202">Si vous voulez en savoir plus sur l’emplacement des données dans Microsoft Teams, consultez [Emplacement des données dans Teams.](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams)</span><span class="sxs-lookup"><span data-stu-id="decd1-202">If you want to learn more information on the location of data in Microsoft Teams, visit [Locations of data in Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span></span>
