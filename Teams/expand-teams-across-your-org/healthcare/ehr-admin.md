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
- m365solution-healthcare
- m365solution-scenario
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Utiliser Microsoft Teams pour configurer votre système de visites virtuelles
ms.openlocfilehash: 6daa61ea44db02d48873a6fc494974c99573d0e8
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875174"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a><span data-ttu-id="a5d87-103">Visites virtuelles avec Teams – Intégration dans le dossier médical informatisé (DMI)</span><span class="sxs-lookup"><span data-stu-id="a5d87-103">Virtual visits with Teams - Integration into EHR</span></span>

<span data-ttu-id="a5d87-104">Le connecteur de dossier médical informatisé (DMI) de Microsoft Teams permet aux cliniciens de lancer facilement une visite virtuelle d'un patient ou de consulter un autre fournisseur dans Teams, directement à partir du système DMI.</span><span class="sxs-lookup"><span data-stu-id="a5d87-104">Microsoft Teams Electronic Health Record (EHR) Connector makes it easy for clinicians to launch a virtual patient visit or consultation with another provider in Teams directly from the EHR system.</span></span> <span data-ttu-id="a5d87-105">Conçus sur le cloud Microsoft 365, Microsoft Teams permet une collaboration et une communication simples et sécurisées grâce à des outils de conversation, vidéo, vocal et de santé au même endroit qui prend en charge la conformité avec les lois HIPAA, la certification HITECH, etc.</span><span class="sxs-lookup"><span data-stu-id="a5d87-105">Built on the Microsoft 365 cloud, Microsoft Teams enables simple, secure collaboration and communication with chat, video, voice, and healthcare tools in a single hub that supports compliance with HIPAA, HITECH certification, and more.</span></span>
<span data-ttu-id="a5d87-106">La plateforme de communication et de collaboration de Teams permet aux membres de l’équipe de réduire l’encombrement des systèmes fragmentés, de sorte qu’ils peuvent consacrer du temps à fournir les meilleurs soins possibles.</span><span class="sxs-lookup"><span data-stu-id="a5d87-106">The communication and collaboration platform of Teams makes it easy for clinicians to cut through the clutter of fragmented systems so they can spend time providing the best possible care.</span></span> <span data-ttu-id="a5d87-107">Le connecteur de dossier médical informatisé (DMI) Microsoft Teams peut :</span><span class="sxs-lookup"><span data-stu-id="a5d87-107">Microsoft Teams Electronic Health Record (EHR) Connector can:</span></span>

- <span data-ttu-id="a5d87-108">Lancer les visites virtuelles Teams à partir des portails des fournisseurs et des patients.</span><span class="sxs-lookup"><span data-stu-id="a5d87-108">Launch Teams virtual visits from both provider and patient portals.</span></span>
- <span data-ttu-id="a5d87-109">Réinscrire dans le DMI des métadonnées sur les événements de connexion et de déconnexion pour permettre un audit automatique et la conservation des enregistrements.</span><span class="sxs-lookup"><span data-stu-id="a5d87-109">Write back into EHR metadata on connect and disconnect events to enable automatic auditing and record keeping.</span></span>
- <span data-ttu-id="a5d87-110">S'intégrer aux flux de travail existants des cliniciens et des patients tout en leur permettant d'utiliser Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a5d87-110">Integrate into existing clinician and patient workflows while allowing them to use Microsoft Teams.</span></span>

  <span data-ttu-id="a5d87-111">Regarder la vidéo sur la gestion des visites virtuelles à partir du portail DMI.</span><span class="sxs-lookup"><span data-stu-id="a5d87-111">Watch the video of How to manage virtual visits from the EHR portal.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a><span data-ttu-id="a5d87-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="a5d87-112">Before you begin</span></span>

<span data-ttu-id="a5d87-113">Avant d’intégrer le connecteur DMI, vous devez vous assurer que vous disposez des conditions préalables suivantes :</span><span class="sxs-lookup"><span data-stu-id="a5d87-113">You’ll need to make sure you have the following prerequisites before you can integrate the EHR connector:</span></span>

- <span data-ttu-id="a5d87-114">Accès à l’utilisation de l’application Microsoft Teams dans [Marketplace de l’application Orchard Epic](https://apporchard.epic.com/Gallery?id=6153).</span><span class="sxs-lookup"><span data-stu-id="a5d87-114">Access to use to the Microsoft Teams app in [Epic’s App Orchard marketplace](https://apporchard.epic.com/Gallery?id=6153).</span></span>

- <span data-ttu-id="a5d87-115">Abonnement actif à Microsoft Cloud pour les soins de santé ou abonnement à l’offre autonome connecteur DMI Microsoft Teams (appliquée uniquement lors des tests en production).</span><span class="sxs-lookup"><span data-stu-id="a5d87-115">Active subscription to Microsoft Cloud for Healthcare or subscription to Microsoft Teams EHR Connector standalone offer (only enforced during production testing).</span></span>

- <span data-ttu-id="a5d87-116">Les utilisateurs doivent avoir une licence Microsoft 365 ou Office 365 appropriée qui inclut les réunions Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a5d87-116">Users must have an appropriate Microsoft 365 or Office 365 license that includes Microsoft Teams meetings.</span></span>

- <span data-ttu-id="a5d87-117">Microsoft Teams doit être adopté et utilisé au sein de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="a5d87-117">Microsoft Teams should be adopted and used inside the organization.</span></span>

- <span data-ttu-id="a5d87-118">Les organisations doivent avoir la version Epic de Novembre 2018 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="a5d87-118">Organizations must have with Epic version November 2018 or later.</span></span>

- <span data-ttu-id="a5d87-119">Vos systèmes doivent respecter toutes les [conditions préalables navigateur et logiciels](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span><span class="sxs-lookup"><span data-stu-id="a5d87-119">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

<span data-ttu-id="a5d87-120">Vous aurez également besoin des informations des membres suivants de votre organisation :</span><span class="sxs-lookup"><span data-stu-id="a5d87-120">You’ll also need information from the following people in your organization:</span></span>

- <span data-ttu-id="a5d87-121">Administrateur Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a5d87-121">Microsoft 365 administrator</span></span>

- <span data-ttu-id="a5d87-122">Analyse des clients</span><span class="sxs-lookup"><span data-stu-id="a5d87-122">Epic customer analyst</span></span>

> [!Note]
> <span data-ttu-id="a5d87-123">Examinez [le guide d’intégration de la téléhealthe de Microsoft Teams-Telehealth](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357) à l’aide de votre spécialiste technique Sous-site.</span><span class="sxs-lookup"><span data-stu-id="a5d87-123">Review the [Epic-Microsoft Teams Telehealth Integration Guide](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357) with your Epic technical specialist.</span></span> <span data-ttu-id="a5d87-124">Assurez-vous que toutes les conditions préalables sont terminées.</span><span class="sxs-lookup"><span data-stu-id="a5d87-124">Make sure that all pre-requisites are completed.</span></span> 

## <a name="connector-setup"></a><span data-ttu-id="a5d87-125">Configuration des connecteurs</span><span class="sxs-lookup"><span data-stu-id="a5d87-125">Connector setup</span></span>

<span data-ttu-id="a5d87-126">La configuration du connecteur nécessite que vous :</span><span class="sxs-lookup"><span data-stu-id="a5d87-126">The connector setup requires that you:</span></span>

- [<span data-ttu-id="a5d87-127">Lancer le portail de configuration de connecteur DMI</span><span class="sxs-lookup"><span data-stu-id="a5d87-127">Launch the EHR Connector configuration portal</span></span>](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [<span data-ttu-id="a5d87-128">Configuration information</span><span class="sxs-lookup"><span data-stu-id="a5d87-128">Configuration information</span></span>](ehr-admin.md#configuration-information)
- [<span data-ttu-id="a5d87-129">Approuver ou afficher la configuration</span><span class="sxs-lookup"><span data-stu-id="a5d87-129">Approve or view configuration</span></span>](ehr-admin.md#approve-or-view-configuration)
- [<span data-ttu-id="a5d87-130">Passer en revue et terminer la configuration</span><span class="sxs-lookup"><span data-stu-id="a5d87-130">Review and finish the configuration</span></span>](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[<span data-ttu-id="a5d87-131">Lancer le portail de configuration de connecteur DMI</span><span class="sxs-lookup"><span data-stu-id="a5d87-131">Launch the EHR Connector configuration portal</span></span>](#launch-the-ehr-connector-configuration-portal)

<span data-ttu-id="a5d87-132">La configuration de votre organisation de soins de santé pour lancer des visites virtuelles avec Microsoft Teams commence par le lancement du portail de configuration du connecteur DMI.</span><span class="sxs-lookup"><span data-stu-id="a5d87-132">Configuring your healthcare organization to launch virtual visits with Microsoft Teams starts by launching the EHR Connector configuration portal.</span></span> <span data-ttu-id="a5d87-133">Vous configurez une ou plusieurs organisations pour tester l’intégration.</span><span class="sxs-lookup"><span data-stu-id="a5d87-133">You configure a single or multiple organizations to test the integration.</span></span> <span data-ttu-id="a5d87-134">Configurez l’URL de test et de production dans le portail de configuration.</span><span class="sxs-lookup"><span data-stu-id="a5d87-134">Configure the test and production URL in the configuration portal.</span></span> <span data-ttu-id="a5d87-135">Testez l'intégration à partir de l'environnement de test d'Epic avant de passer en production.</span><span class="sxs-lookup"><span data-stu-id="a5d87-135">Test the integration from Epic’s test environment before moving to production.</span></span>
  
- <span data-ttu-id="a5d87-136">URL de configuration du connecteur DMI : [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="a5d87-136">EHR connector configuration URL: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span></span>

<span data-ttu-id="a5d87-137">L'administrateur Microsoft 365 et l'analyste client Epic de votre organisation doivent effectuer les étapes d'information et d'intégration dans le portail de configuration.</span><span class="sxs-lookup"><span data-stu-id="a5d87-137">The Microsoft 365 admin and Epic customer analyst from your organization must complete the information and integration steps in the configuration portal.</span></span> <span data-ttu-id="a5d87-138">Pour les étapes de configuration d'Epic, contactez la ressource spécialiste technique Epic affectée à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a5d87-138">For Epic configuration steps, contact the Epic technical specialist resource assigned to your organization.</span></span>

### <a name="configuration-information"></a>[<span data-ttu-id="a5d87-139">Configuration information</span><span class="sxs-lookup"><span data-stu-id="a5d87-139">Configuration information</span></span>](#configuration-information)

<span data-ttu-id="a5d87-140">Cette étape doit être effectuée par l’**administrateur Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="a5d87-140">This step is to be completed by the **Microsoft 365 administrator**.</span></span> <span data-ttu-id="a5d87-141">L’administrateur Microsoft 365 doit lancer le portail de configuration des connecteurs et se connecter avec des informations d’identification Microsoft pour démarrer le processus de configuration.</span><span class="sxs-lookup"><span data-stu-id="a5d87-141">The Microsoft 365 administrator must launch the connector configuration portal and sign in with Microsoft credentials to start the configuration process.</span></span>

<span data-ttu-id="a5d87-142">Pour effectuer cette étape, l'administrateur Microsoft 365 doit recevoir une URL de base Fast Health Interoperability Resources (FHIR) valide de la part de votre spécialiste technique Epic et le nom d'utilisateur de l'analyste client Epic qui approuvera la configuration.</span><span class="sxs-lookup"><span data-stu-id="a5d87-142">To complete this step, the Microsoft 365 administrator must receive a valid Fast Health Interoperability Resources (FHIR) base URL from your Epic technical specialist and the username of the Epic customer analyst who will be approving the configuration.</span></span> <span data-ttu-id="a5d87-143">L’administrateur Microsoft 365 doit lancer la page de configuration des connecteurs et se connecter avec des informations d’identification Microsoft pour démarrer le processus de configuration.</span><span class="sxs-lookup"><span data-stu-id="a5d87-143">The Microsoft 365 administrator must launch the connector configuration page and sign in with Microsoft credentials to start the configuration process.</span></span>

- <span data-ttu-id="a5d87-144">L'URL de base FHIR est une adresse statique correspondant au point de terminaison de l'API FHIR de votre serveur.</span><span class="sxs-lookup"><span data-stu-id="a5d87-144">The FHIR base URL is a static address corresponding to your server FHIR API endpoint.</span></span> <span data-ttu-id="a5d87-145">Exemple d’URL est `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span><span class="sxs-lookup"><span data-stu-id="a5d87-145">An example URL is `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span></span>

- <span data-ttu-id="a5d87-146">Le nom de l'approbateur de la configuration est le nom de l'analyste client Epic qui sera chargé d'approuver la configuration à l'étape suivante.</span><span class="sxs-lookup"><span data-stu-id="a5d87-146">Configuration approver name is the name of the Epic customer analyst who will be responsible for approving the configuration in the next step.</span></span> <span data-ttu-id="a5d87-147">L'analyste client d'Epic est une personne de votre organisation ayant un accès à Epic.</span><span class="sxs-lookup"><span data-stu-id="a5d87-147">The Epic customer analyst is a person in your organization with sign-in access to Epic.</span></span>

  ![Le nom de l'approbateur de la configuration est sélectionné dans une liste dans le connecteur DMI.](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[<span data-ttu-id="a5d87-149">Approuver ou afficher la configuration</span><span class="sxs-lookup"><span data-stu-id="a5d87-149">Approve or view configuration</span></span>](#approve-or-view-configuration)

<span data-ttu-id="a5d87-150">L'analyste client Epic de votre établissement de santé qui a été ajouté en tant qu'approbateur doit maintenant utiliser la même URL du connecteur DMI que celle de l'étape précédente pour se connecter à l'aide de ses informations d'identification Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a5d87-150">The Epic customer analyst for your healthcare organization who was added as an approver must now use the same EHR Connector URL from the previous step to sign in using their Microsoft 365 credentials.</span></span> <span data-ttu-id="a5d87-151">Après une validation réussie, l'approbateur sera invité à se connecter à l'aide de ses informations d'identification Epic pour valider l'organisation Epic.</span><span class="sxs-lookup"><span data-stu-id="a5d87-151">After successful validation, the approver is going to be asked to sign in using their Epic credentials to validate the Epic organization.</span></span>

> [!Note]
> <span data-ttu-id="a5d87-152">L'administrateur Microsoft 365 et l'analyste client Epic de votre organisation peuvent être la même personne.</span><span class="sxs-lookup"><span data-stu-id="a5d87-152">The Microsoft 365 admin and Epic customer analyst in your organization can be the same person.</span></span> <span data-ttu-id="a5d87-153">Dans ce cas, ajoutez votre propre nom d'utilisateur en tant qu’approbateur.</span><span class="sxs-lookup"><span data-stu-id="a5d87-153">In that case, add your own username as approver.</span></span> <span data-ttu-id="a5d87-154">Vous devrez toujours vous connecter à Epic pour valider votre accès.</span><span class="sxs-lookup"><span data-stu-id="a5d87-154">You'll still need to sign in to Epic to validate your access.</span></span> <span data-ttu-id="a5d87-155">La connexion Epic est uniquement utilisée pour valider votre URL de base FHIR.</span><span class="sxs-lookup"><span data-stu-id="a5d87-155">The Epic sign in is only used to validate your FHIR base URL.</span></span> <span data-ttu-id="a5d87-156">Microsoft ne stocke pas les informations d’identification et n’accède pas aux données DMI avec cette connexion.</span><span class="sxs-lookup"><span data-stu-id="a5d87-156">Microsoft won't store credentials or access EHR data with this sign in.</span></span>

  ![Vérifiez et approuvez la configuration des informations d’identification.](../../media/approve-view-configuration.png)

<span data-ttu-id="a5d87-158">Une fois la connexion Epic réussie, l'analyste client Epic **doit** approuver la configuration.</span><span class="sxs-lookup"><span data-stu-id="a5d87-158">After a successful Epic sign in, the Epic customer analyst **must** approve the configuration.</span></span> <span data-ttu-id="a5d87-159">Si la configuration n'est pas correcte, l'administrateur Microsoft 365 peut modifier les configurations d'origine en se connectant à nouveau au portail du connecteur Microsoft DMI.</span><span class="sxs-lookup"><span data-stu-id="a5d87-159">If the configuration isn't correct, the Microsoft 365 admin will have the ability to modify the original configurations by signing in to the Microsoft EHR connector portal again.</span></span> 

![Confirmez que le connecteur DMI est configuré et l’option de modification de la configuration.](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[<span data-ttu-id="a5d87-161">Passer en revue et terminer la configuration</span><span class="sxs-lookup"><span data-stu-id="a5d87-161">Review and finish the configuration</span></span>](#review-and-finish-the-configuration)

<span data-ttu-id="a5d87-162">Lorsque les informations de configuration sont approuvées par l'administrateur Epic, les enregistrements d'intégration pour le lancement du patient et du fournisseur vous sont présentés.</span><span class="sxs-lookup"><span data-stu-id="a5d87-162">When the configuration information is approved by the Epic administrator, you'll be presented with integration records for patient and provider launch.</span></span> <span data-ttu-id="a5d87-163">Ces enregistrements sont nécessaires pour terminer la configuration de la visite virtuelle dans Epic.</span><span class="sxs-lookup"><span data-stu-id="a5d87-163">These records are necessary to complete the virtual visit configuration in Epic.</span></span> <span data-ttu-id="a5d87-164">Pour plus d’informations, reportez-vous au guide sur l’intégration de la téléconsultation à Epic-Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a5d87-164">Refer to the Epic-Microsoft Teams Telehealth Integration guide for more details.</span></span>

> [!Note]  
> <span data-ttu-id="a5d87-165">À tout moment, l'analyste client Microsoft 365 ou Epic peut se connecter au portail de configuration pour consulter les enregistrements d'intégration et modifier la configuration de l'organisation, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="a5d87-165">At any time the Microsoft 365 or Epic customer analyst can sign in to the configuration portal to view integration records and modify organization configuration, if needed.</span></span>

![Les informations d’intégration sont affichées.](../../media/finish-configuration.png)

> [!Note]
> <span data-ttu-id="a5d87-167">Le processus d’approbation doit être effectué par l’analyste client Epic pour chaque URL FHIR configurée par l’administrateur Microsoft auparavant.</span><span class="sxs-lookup"><span data-stu-id="a5d87-167">The approval process must be completed by the Epic customer analyst for every FHIR URL configured by the Microsoft admin before.</span></span>

![Les informations de configuration sont approuvées.](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a><span data-ttu-id="a5d87-169">Lancer les visites virtuelles Teams</span><span class="sxs-lookup"><span data-stu-id="a5d87-169">Launch Teams virtual visits</span></span>

<span data-ttu-id="a5d87-170">Une fois que vous avez suivi les étapes du connecteur DMI et vous avez effectué la configuration Epic, votre organisation est prête à prendre en charge les visites vidéo dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a5d87-170">After completing the EHR Connector steps and Epic configuration, your organization is ready to support video visits with Microsoft Teams.</span></span>

### <a name="virtual-visit-prerequisites"></a><span data-ttu-id="a5d87-171">Conditions préalables pour la visite virtuelle</span><span class="sxs-lookup"><span data-stu-id="a5d87-171">Virtual visit prerequisites</span></span>

- <span data-ttu-id="a5d87-172">Vos systèmes doivent respecter toutes les [conditions préalables navigateur et logiciels](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span><span class="sxs-lookup"><span data-stu-id="a5d87-172">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

- <span data-ttu-id="a5d87-173">L'organisme de santé doit avoir terminé la configuration entre l'organisme Epic et l'organisme Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a5d87-173">Healthcare organization must have completed the setup between the Epic organization and Microsoft 365 organization.</span></span>

### <a name="provider-experience"></a><span data-ttu-id="a5d87-174">Expérience fournisseur</span><span class="sxs-lookup"><span data-stu-id="a5d87-174">Provider experience</span></span>

<span data-ttu-id="a5d87-175">Les fournisseurs de soins de santé de votre organisation peuvent également participer à des visites virtuelles avec Microsoft Teams à partir de leurs applications Epic pour fournisseurs (Hyperspace, Haiku, Canto).</span><span class="sxs-lookup"><span data-stu-id="a5d87-175">Healthcare providers from your organization can also join virtual visits with Microsoft Teams from their Epic provider applications (Hyperspace, Haiku, Canto).</span></span> <span data-ttu-id="a5d87-176">Le bouton **Commencer la visite virtuelle** est incorporé dans le flux du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="a5d87-176">The **Begin virtual visit** button is embedded in the provider flow.</span></span>

<span data-ttu-id="a5d87-177">Principales fonctionnalités de l’expérience fournisseur :</span><span class="sxs-lookup"><span data-stu-id="a5d87-177">Key features of the provider experience:</span></span>

- <span data-ttu-id="a5d87-178">Les fournisseurs peuvent rejoindre les visites virtuelles à l’aide de navigateurs pris en charge ou l’application Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a5d87-178">Providers can join virtual visits using supported browsers or the Microsoft Teams application.</span></span>

- <span data-ttu-id="a5d87-179">Les fournisseurs doivent se connectent une fois avec leur compte Microsoft 365 lorsqu’ils rejoignent une visite virtuelle pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="a5d87-179">Providers must do a one-time sign-in with their Microsoft 365 account when joining a virtual visit for the first time.</span></span>

- <span data-ttu-id="a5d87-180">Après la connexion unique, le fournisseur sera directement dirigé vers le rendez-vous virtuel dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a5d87-180">After the one-time sign-in, the provider will be taken straight to the virtual appointment in Microsoft Teams.</span></span> <span data-ttu-id="a5d87-181">(Le fournisseur doit être connecté à Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="a5d87-181">(Provider must be signed-in to Microsoft Teams).</span></span>

- <span data-ttu-id="a5d87-182">Le fournisseur peut consulter en temps réel les mises à jour des connexions et déconnexions des participants pour un rendez-vous donné.</span><span class="sxs-lookup"><span data-stu-id="a5d87-182">Provider can see real-time updates of participants connect and disconnect for a given appointment.</span></span> <span data-ttu-id="a5d87-183">Le fournisseur peut voir quand le patient est connecté à une visite virtuelle.</span><span class="sxs-lookup"><span data-stu-id="a5d87-183">The provider can see when the patient is connected to a virtual visit.</span></span>

  ![Expérience fournisseur d’une visite virtuelle avec le patient](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a><span data-ttu-id="a5d87-185">Expérience patient</span><span class="sxs-lookup"><span data-stu-id="a5d87-185">Patient experience</span></span>

<span data-ttu-id="a5d87-186">Le connecteur prend en charge les patients qui rejoignent des visites virtuelles via les applications web et mobiles MyChart.</span><span class="sxs-lookup"><span data-stu-id="a5d87-186">The connector supports patients joining virtual visits through MyChart web and mobile.</span></span> <span data-ttu-id="a5d87-187">Au moment du rendez-vous, les patients peuvent démarrer une visite virtuelle à partir de MyChart à l’aide du bouton **Commencer la visite virtuelle**.</span><span class="sxs-lookup"><span data-stu-id="a5d87-187">At the time of the appointment, patients can start a virtual visit from MyChart using the **Begin virtual visit** button.</span></span>

<span data-ttu-id="a5d87-188">Principales fonctionnalités de l’expérience du patient :</span><span class="sxs-lookup"><span data-stu-id="a5d87-188">Key features of the patient experience:</span></span>

- <span data-ttu-id="a5d87-189">Les patients peuvent rejoindre les visites virtuelles à partir de navigateurs web modernes sur ordinateurs de bureau et mobiles sans installation de l’application.</span><span class="sxs-lookup"><span data-stu-id="a5d87-189">Patients can join virtual visits from modern web browsers on desktop and mobile without app installation.</span></span>

- <span data-ttu-id="a5d87-190">Les patients peuvent rejoindre les visites virtuelles d'un simple clic et aucun autre compte ou connexion n'est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="a5d87-190">Patients can join virtual visits with a single click and there is no other account or sign-in required.</span></span>

- <span data-ttu-id="a5d87-191">Les patients n'ont pas besoin de créer un compte Microsoft ou de se connecter pour lancer une visite virtuelle.</span><span class="sxs-lookup"><span data-stu-id="a5d87-191">Patients aren't required to create a Microsoft account or sign in to launch a virtual visit.</span></span>

- <span data-ttu-id="a5d87-192">Les patients sont placés dans une salle d’accueil jusqu’à ce que le fournisseur de soins de santé rejoigne le rendez-vous et les admette dans la visite virtuelle.</span><span class="sxs-lookup"><span data-stu-id="a5d87-192">Patients will be placed in a lobby until the healthcare provider joins the appointment and admits them to the virtual visit.</span></span>

- <span data-ttu-id="a5d87-193">Un test de la vidéo et du microphone est disponible dans la salle d'accueil avant de rejoindre la visite virtuelle.</span><span class="sxs-lookup"><span data-stu-id="a5d87-193">Testing of the video and microphone is available in the lobby before joining the virtual visit.</span></span>

  ![Expérience patient de la visite virtuelle](../../media/ehc-virtual-visit-5.png)

> [!Note]
> <span data-ttu-id="a5d87-195">Epic, MyChart, Haiku et Canto sont des marques déposées d'Epic Systems Corporation.</span><span class="sxs-lookup"><span data-stu-id="a5d87-195">Epic, MyChart, Haiku, and Canto are trademarks of Epic Systems Corporation.</span></span>

### <a name="privacy-and-location-of-data"></a><span data-ttu-id="a5d87-196">Confidentialité et emplacement des données</span><span class="sxs-lookup"><span data-stu-id="a5d87-196">Privacy and location of data</span></span>

<span data-ttu-id="a5d87-197">L'intégration Teams dans les systèmes de DMI optimise la quantité de données utilisées et stockées pendant l'intégration et les flux de visites virtuelles.</span><span class="sxs-lookup"><span data-stu-id="a5d87-197">Teams integration into EHR systems optimizes the amount of data being used and stored during integration and virtual visit flows.</span></span> <span data-ttu-id="a5d87-198">La solution respecte les principes et les directives générales de Teams en matière de confidentialité et de gestion des données, décrits dans Confidentialité Teams.</span><span class="sxs-lookup"><span data-stu-id="a5d87-198">The solution follows the overall Teams privacy and data management principles and guidelines outlined in Teams Privacy.</span></span>

<span data-ttu-id="a5d87-199">Le connecteur DMI de Microsoft Teams ne stocke ni ne transfère les données personnelles identifiables ou les dossiers médicaux des patients ou fournisseurs de santé à partir du système de gestion des dossiers médicaux.</span><span class="sxs-lookup"><span data-stu-id="a5d87-199">The Microsoft Teams EHR connector doesn't store nor transfer any identifiable personal data or any health records of patients or healthcare providers from the EHR system.</span></span> <span data-ttu-id="a5d87-200">Les seules données stockées par le connecteur DMI sont l’ID unique de l’utilisateur DMI (utilisé lors de l’installation d’une réunion Teams).</span><span class="sxs-lookup"><span data-stu-id="a5d87-200">The only data that is stored by the EHR connector is the EHR user’s unique ID, which is used during Teams meeting setup.</span></span> <span data-ttu-id="a5d87-201">L’ID unique de l’utilisateur DMI est stocké dans l’une des trois zones géographiques décrites dans [Emplacement de stockage des données client Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies).</span><span class="sxs-lookup"><span data-stu-id="a5d87-201">The EHR user’s unique ID is stored in one of the three geographic regions described in [Where your Microsoft 365 customer data is stored](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies).</span></span> <span data-ttu-id="a5d87-202">Toutes les discussions, enregistrements et autres données entrés dans Teams par les participants à la réunion sont stockés conformément aux stratégies de stockage existantes.</span><span class="sxs-lookup"><span data-stu-id="a5d87-202">All chat, recordings, and other data entered into Teams by the meeting participants are stored according to existing storage policies.</span></span> <span data-ttu-id="a5d87-203">Pour plus d’informations sur l’emplacement des données dans Microsoft Teams, consultez [Emplacements des données dans Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span><span class="sxs-lookup"><span data-stu-id="a5d87-203">If you want to learn more information on the location of data in Microsoft Teams, visit [Locations of data in Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span></span>
