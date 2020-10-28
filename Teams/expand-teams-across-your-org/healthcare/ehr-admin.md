---
title: Équipes pour les visites virtuelles
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Utiliser Microsoft teams pour configurer votre système de visites virtuelles
ms.openlocfilehash: 3d5d68e7c4ba3cc203df33604a7210e67b402938
ms.sourcegitcommit: a1524afb546fde9844f53390fab85e7073da8cb2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48778887"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a><span data-ttu-id="f46ac-103">Visites virtuelles avec teams-Integration dans le DMI</span><span class="sxs-lookup"><span data-stu-id="f46ac-103">Virtual visits with Teams - Integration into EHR</span></span>

<span data-ttu-id="f46ac-104">Le connecteur de l’état de santé électronique de Microsoft Teams (DMI) permet aux médecins de lancer facilement une visite ou une consultation virtuelle du patient auprès d’un autre fournisseur en équipe directement à partir du système DMI.</span><span class="sxs-lookup"><span data-stu-id="f46ac-104">Microsoft Teams Electronic Health Record (EHR) Connector makes it easy for clinicians to launch a virtual patient visit or consultation with another provider in Teams directly from the EHR system.</span></span> <span data-ttu-id="f46ac-105">Bâti sur le Cloud Microsoft 365, Microsoft teams permet une collaboration simple et sécurisée et une communication avec les outils de chat, de vidéo, de voix et de santé sur un seul et même concentrateur prenant en charge la conformité à la certification HIPAA, Hi-Tech, etc.</span><span class="sxs-lookup"><span data-stu-id="f46ac-105">Built on the Microsoft 365 cloud, Microsoft Teams enables simple, secure collaboration and communication with chat, video, voice, and healthcare tools in a single hub that supports compliance with HIPAA, HITECH certification, and more.</span></span>

<span data-ttu-id="f46ac-106">La plateforme de communication et de collaboration d’équipes permet aux médecins de réduire le nombre de systèmes fragmentés de façon à ce qu’ils puissent consacrer du temps à la meilleure prise en charge possible.</span><span class="sxs-lookup"><span data-stu-id="f46ac-106">The communication and collaboration platform of Teams makes it easy for clinicians to cut through the clutter of fragmented systems so they can spend time providing the best possible care.</span></span> <span data-ttu-id="f46ac-107">Le connecteur de l’état de santé électronique de Microsoft Teams (DMI) peut :</span><span class="sxs-lookup"><span data-stu-id="f46ac-107">Microsoft Teams Electronic Health Record (EHR) Connector can:</span></span>

- <span data-ttu-id="f46ac-108">Lancer des visites virtuelles d’équipes à partir de portails du fournisseur et du patient.</span><span class="sxs-lookup"><span data-stu-id="f46ac-108">Launch Teams virtual visits from both provider and patient portals.</span></span>

- <span data-ttu-id="f46ac-109">Écrivez de nouveau dans les métadonnées du DMI sur les événements de connexion et de déconnexion pour activer l’audit automatique et la conservation des enregistrements.</span><span class="sxs-lookup"><span data-stu-id="f46ac-109">Write back into EHR metadata on connect and disconnect events to enable automatic auditing and record keeping.</span></span>

- <span data-ttu-id="f46ac-110">Intégration aux flux de travail de clinicien et de patient tout en leur permettant d’utiliser Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f46ac-110">Integrate into existing clinician and patient workflows while allowing them to use Microsoft Teams.</span></span>

  <span data-ttu-id="f46ac-111">Regardez la vidéo sur la façon de gérer les visites virtuelles à partir du portail DMI.</span><span class="sxs-lookup"><span data-stu-id="f46ac-111">Watch the video of How to manage virtual visits from the EHR portal.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a><span data-ttu-id="f46ac-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="f46ac-112">Before you begin</span></span>

<span data-ttu-id="f46ac-113">Pour pouvoir intégrer le connecteur DMI, vous devez vous assurer que vous disposez de la configuration requise suivante :</span><span class="sxs-lookup"><span data-stu-id="f46ac-113">You’ll need to make sure you have the following prerequisites before you can integrate the EHR connector:</span></span>

- <span data-ttu-id="f46ac-114">Abonnement actif à Microsoft Cloud pour la santé ou un abonnement à l’abonnement au connecteur DMI de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f46ac-114">Active subscription to Microsoft Cloud for Healthcare or subscription to Microsoft Teams EHR Connector standalone offer.</span></span>

- <span data-ttu-id="f46ac-115">Les utilisateurs doivent disposer d’une licence Microsoft 365 ou Office 365 appropriée incluant les réunions Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f46ac-115">Users must have an appropriate Microsoft 365 or Office 365 license that includes Microsoft Teams meetings.</span></span>

- <span data-ttu-id="f46ac-116">Microsoft teams doit être adopté et utilisé au sein de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="f46ac-116">Microsoft Teams should be adopted and used inside the organization.</span></span>

- <span data-ttu-id="f46ac-117">Les organisations doivent avoir la version Epic 2018 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="f46ac-117">Organizations must have with Epic version November 2018 or later.</span></span>

- <span data-ttu-id="f46ac-118">Vos systèmes doivent répondre à la [Configuration requise pour les logiciels et les navigateurs](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span><span class="sxs-lookup"><span data-stu-id="f46ac-118">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

<span data-ttu-id="f46ac-119">Vous aurez également besoin des informations des personnes suivantes de votre organisation :</span><span class="sxs-lookup"><span data-stu-id="f46ac-119">You’ll also need information from the following people in your organization:</span></span>

- <span data-ttu-id="f46ac-120">Administrateur Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f46ac-120">Microsoft 365 administrator</span></span>

- <span data-ttu-id="f46ac-121">Administrateur épique</span><span class="sxs-lookup"><span data-stu-id="f46ac-121">Epic administrator</span></span>

> [!Note]
> <span data-ttu-id="f46ac-122">Demandez à votre administrateur épique de fournir le Guide d’intégration de Epic-Microsoft teams Telehealth disponible sur le marché épique.</span><span class="sxs-lookup"><span data-stu-id="f46ac-122">Request your Epic admin to provide the Epic-Microsoft Teams Telehealth Integration Guide available in the Epic marketplace.</span></span>

## <a name="connector-setup"></a><span data-ttu-id="f46ac-123">Configuration de connecteur</span><span class="sxs-lookup"><span data-stu-id="f46ac-123">Connector setup</span></span>

<span data-ttu-id="f46ac-124">Pour configurer le connecteur, vous avez besoin des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="f46ac-124">The connector setup requires that you:</span></span>

- [<span data-ttu-id="f46ac-125">Lancer le portail de configuration de connecteur DMI</span><span class="sxs-lookup"><span data-stu-id="f46ac-125">Launch the EHR Connector configuration portal</span></span>](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [<span data-ttu-id="f46ac-126">Configurer les informations d’organisation du fournisseur</span><span class="sxs-lookup"><span data-stu-id="f46ac-126">Configure provider organization information</span></span>](ehr-admin.md#configure-provider-organization-information)
- [<span data-ttu-id="f46ac-127">Vérifier et approuver la configuration</span><span class="sxs-lookup"><span data-stu-id="f46ac-127">Verify and approve the configuration</span></span>](ehr-admin.md#verify-and-approve-the-configuration)
- [<span data-ttu-id="f46ac-128">Vérifier et terminer la configuration</span><span class="sxs-lookup"><span data-stu-id="f46ac-128">Review and finish the configuration</span></span>](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[<span data-ttu-id="f46ac-129">Lancer le portail de configuration de connecteur DMI</span><span class="sxs-lookup"><span data-stu-id="f46ac-129">Launch the EHR Connector configuration portal</span></span>](#launch-the-ehr-connector-configuration-portal)

<span data-ttu-id="f46ac-130">La configuration de votre organisation de santé pour lancer des visites virtuelles à l’aide de Microsoft teams démarre en lançant le portail de configuration de connecteur DMI.</span><span class="sxs-lookup"><span data-stu-id="f46ac-130">Configuring your healthcare organization to launch virtual visits with Microsoft Teams starts by launching the EHR Connector configuration portal.</span></span> <span data-ttu-id="f46ac-131">Utilisez l’URL de test pour configurer le connecteur pour votre environnement de test épique.</span><span class="sxs-lookup"><span data-stu-id="f46ac-131">Use the test URL to configure the connector for your Epic test environment.</span></span> <span data-ttu-id="f46ac-132">Utilisez l’URL de production lorsque vous êtes prêt à activer votre environnement de production épique.</span><span class="sxs-lookup"><span data-stu-id="f46ac-132">Use the production URL when you're ready to enable your Epic production environment.</span></span>
  
- <span data-ttu-id="f46ac-133">Environnement de test [https://ehrconnector-ppe.teams.microsoft.com](https://ehrconnector-ppe.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="f46ac-133">Test environment [https://ehrconnector-ppe.teams.microsoft.com](https://ehrconnector-ppe.teams.microsoft.com)</span></span>
- <span data-ttu-id="f46ac-134">Environnement de production [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="f46ac-134">Production environment [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span></span>

<span data-ttu-id="f46ac-135">L’administrateur 365 et l’administrateur Epic de votre organisation doivent suivre les informations et les étapes d’intégration du portail de configuration.</span><span class="sxs-lookup"><span data-stu-id="f46ac-135">The Microsoft 365 admin and Epic admin from your organization must complete the information and integration steps in the configuration portal.</span></span> <span data-ttu-id="f46ac-136">Pour les étapes de configuration épique, contactez la ressource Epic affectée à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f46ac-136">For Epic configuration steps, contact the Epic resource assigned to your organization.</span></span>

### <a name="configure-provider-organization-information"></a>[<span data-ttu-id="f46ac-137">Configurer les informations d’organisation du fournisseur</span><span class="sxs-lookup"><span data-stu-id="f46ac-137">Configure provider organization information</span></span>](#configure-provider-organization-information)

<span data-ttu-id="f46ac-138">Cette étape doit être effectuée par l’administrateur Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f46ac-138">This step is to be completed by the Microsoft 365 administrator.</span></span> <span data-ttu-id="f46ac-139">Pour démarrer le processus de configuration, l’administrateur 365 doit lancer le portail de configuration des connecteurs et se connecter à l’aide des informations d’identification Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f46ac-139">The Microsoft 365 administrator must launch the connector configuration portal and sign in with Microsoft credentials to start the configuration process.</span></span>

<span data-ttu-id="f46ac-140">Pour effectuer cette étape, l’administrateur 365 doit recevoir une URL de base de l’interopérabilité rapide valide de votre administrateur Microsoft 365 et le nom d’utilisateur de l’administrateur Epic qui approuvera la configuration.</span><span class="sxs-lookup"><span data-stu-id="f46ac-140">To complete this step, the Microsoft 365 administrator must receive a valid Fast Health Interoperability Resources (FHIR) base URL from your Microsoft 365 administrator and the username of the Epic administrator who will be approving the configuration.</span></span> <span data-ttu-id="f46ac-141">Pour démarrer le processus de configuration, l’administrateur 365 doit lancer la page Configuration du connecteur et se connecter à l’aide des informations d’identification Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f46ac-141">The Microsoft 365 administrator must launch the connector configuration page and sign in with Microsoft credentials to start the configuration process.</span></span>

- <span data-ttu-id="f46ac-142">L’URL de base FHIR est une adresse statique correspondant au point de terminaison de l’API FHIR Server.</span><span class="sxs-lookup"><span data-stu-id="f46ac-142">The FHIR base URL is a static address corresponding to your server FHIR API endpoint.</span></span> <span data-ttu-id="f46ac-143">Par exemple, URL [https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST](https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST) .</span><span class="sxs-lookup"><span data-stu-id="f46ac-143">An example URL is [https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST](https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST).</span></span>

- <span data-ttu-id="f46ac-144">Nom de l’approbateur de configuration indique le nom de l’administrateur de système Epic qui sera chargé d’approuver la configuration.</span><span class="sxs-lookup"><span data-stu-id="f46ac-144">Configuration approver name is the name of the Epic system administrator who will be responsible for approving the configuration.</span></span>

  ![Le nom de l’approbateur de configuration est sélectionné à partir d’une liste dans le connecteur DMI.](../../media/ehc-provider-1.png)

### <a name="verify-and-approve-the-configuration"></a>[<span data-ttu-id="f46ac-146">Vérifier et approuver la configuration</span><span class="sxs-lookup"><span data-stu-id="f46ac-146">Verify and approve the configuration</span></span>](#verify-and-approve-the-configuration)

<span data-ttu-id="f46ac-147">L’administrateur épique de votre organisation de soins de santé qui a été ajouté en tant qu’approbateur doit désormais utiliser la même URL de connecteur DMI que l’étape précédente pour se connecter à l’aide de ses informations d’identification Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f46ac-147">The Epic administrator for your healthcare organization who was added as an approver must now use the same EHR Connector URL from the previous step to sign in using their Microsoft 365 credentials.</span></span> <span data-ttu-id="f46ac-148">Après validation réussie, l’approbateur va être invité à se connecter à l’aide de ses informations d’identification Epic pour valider l’organisation Epic.</span><span class="sxs-lookup"><span data-stu-id="f46ac-148">After successful validation, the approver is going to be asked to sign in using their Epic credentials to validate the Epic organization.</span></span>

> [!Note]
> <span data-ttu-id="f46ac-149">L’administrateur 365 Microsoft et l’administrateur Epic de votre organisation peuvent être la même personne.</span><span class="sxs-lookup"><span data-stu-id="f46ac-149">The Microsoft 365 admin and Epic admin in your organizations can be the same person.</span></span> <span data-ttu-id="f46ac-150">Dans ce cas, ajoutez votre propre nom d’utilisateur en tant qu’approbateur à la première étape.</span><span class="sxs-lookup"><span data-stu-id="f46ac-150">In that case, add your own username as approver in the first step.</span></span> <span data-ttu-id="f46ac-151">Vous devrez toujours vous connecter à Epic pour valider votre accès.</span><span class="sxs-lookup"><span data-stu-id="f46ac-151">You'll still need to sign in to Epic to validate your access.</span></span> <span data-ttu-id="f46ac-152">La connexion épique est utilisée uniquement pour valider votre URL de base FHIR.</span><span class="sxs-lookup"><span data-stu-id="f46ac-152">The Epic sign in is only used to validate your FHIR base URL.</span></span> <span data-ttu-id="f46ac-153">Microsoft n’enregistre pas les informations d’identification ou accède aux données DMI avec cette connexion.</span><span class="sxs-lookup"><span data-stu-id="f46ac-153">Microsoft will not store credentials or access EHR data with this sign in.</span></span>

  ![Vérifiez et approuvez la configuration des informations d’identification.](../../media/ehc-provider-2.png)

<span data-ttu-id="f46ac-155">Dès qu’un utilisateur se connecte, l’administrateur épique **doit** approuver la configuration.</span><span class="sxs-lookup"><span data-stu-id="f46ac-155">After a successful Epic sign in, the Epic administrator **must** approve the configuration.</span></span> <span data-ttu-id="f46ac-156">Si la configuration n’est pas correcte, l’administrateur 365 de Microsoft pourra modifier les configurations d’origine en vous connectant au portail du connecteur Microsoft DMI.</span><span class="sxs-lookup"><span data-stu-id="f46ac-156">If the configuration isn't correct, the Microsoft 365 admin will have the ability to modify the original configurations by signing in to the Microsoft EHR Connector portal again.</span></span>

![Vérifiez que le connecteur DMI est configuré et qu’il est possible de modifier la configuration.](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[<span data-ttu-id="f46ac-158">Vérifier et terminer la configuration</span><span class="sxs-lookup"><span data-stu-id="f46ac-158">Review and finish the configuration</span></span>](#review-and-finish-the-configuration)

<span data-ttu-id="f46ac-159">Lorsque les informations de configuration sont approuvées par l’administrateur épique, vous êtes invité à fournir des enregistrements d’intégration pour le lancement du patient et du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="f46ac-159">When the configuration information is approved by the Epic administrator, you'll be presented with integration records for patient and provider launch.</span></span> <span data-ttu-id="f46ac-160">Ces enregistrements sont nécessaires pour terminer la configuration de la visite virtuelle dans EPIC.</span><span class="sxs-lookup"><span data-stu-id="f46ac-160">These records are necessary to complete the virtual visit configuration in Epic.</span></span> <span data-ttu-id="f46ac-161">Pour plus d’informations, reportez-vous au Guide d’intégration de Epic-Microsoft teams Telehealth.</span><span class="sxs-lookup"><span data-stu-id="f46ac-161">Refer to the Epic-Microsoft Teams Telehealth Integration guide for more details.</span></span>

> [!Note]  
> <span data-ttu-id="f46ac-162">À tout moment, l’administrateur Microsoft 365 ou Epic peut se connecter au portail de configuration pour afficher les enregistrements d’intégration et modifier la configuration de l’organisation, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="f46ac-162">At any time the Microsoft 365 or Epic administrator can sign in to the configuration portal to view integration records and modify organization configuration, if needed.</span></span>

![Les informations d’intégration sont affichées.](../../media/ehc-final-config-4.png)

## <a name="launch-teams-virtual-visits"></a><span data-ttu-id="f46ac-164">Lancer des visites virtuelles dans teams</span><span class="sxs-lookup"><span data-stu-id="f46ac-164">Launch Teams virtual visits</span></span>

<span data-ttu-id="f46ac-165">Après avoir effectué les étapes du connecteur DMI et la configuration épique, votre organisation est prête à prendre en charge les visites vidéo avec Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f46ac-165">After completing the EHR Connector steps and Epic configuration, your organization is ready to support video visits with Microsoft Teams.</span></span>

### <a name="virtual-visit-prerequisites"></a><span data-ttu-id="f46ac-166">Conditions préalables pour les visites virtuelles</span><span class="sxs-lookup"><span data-stu-id="f46ac-166">Virtual visit prerequisites</span></span>

- <span data-ttu-id="f46ac-167">Vos systèmes doivent répondre à la [Configuration requise pour les logiciels et les navigateurs](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span><span class="sxs-lookup"><span data-stu-id="f46ac-167">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

- <span data-ttu-id="f46ac-168">L’organisation du secteur de la santé doit avoir effectué le programme d’installation entre l’organisation Epic et Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f46ac-168">Healthcare organization must have completed the setup between the Epic organization and Microsoft 365 organization.</span></span>

### <a name="provider-experience"></a><span data-ttu-id="f46ac-169">Expertise du fournisseur</span><span class="sxs-lookup"><span data-stu-id="f46ac-169">Provider experience</span></span>

<span data-ttu-id="f46ac-170">Les prestataires de services de santé de votre organisation peuvent également rejoindre des visites virtuelles à l’aide de Microsoft teams à partir de leurs applications de fournisseurs de Epic (Hyper-Haiku, Canto).</span><span class="sxs-lookup"><span data-stu-id="f46ac-170">Healthcare providers from your organization can also join virtual visits with Microsoft Teams from their Epic provider applications (Hyperspace, Haiku, Canto).</span></span> <span data-ttu-id="f46ac-171">Le bouton **commencer la visite virtuelle** est incorporé dans le flux du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="f46ac-171">The **Begin virtual visit** button is embedded in the provider flow.</span></span>

<span data-ttu-id="f46ac-172">Principales fonctionnalités de l’interface du fournisseur :</span><span class="sxs-lookup"><span data-stu-id="f46ac-172">Key features of the provider experience:</span></span>

- <span data-ttu-id="f46ac-173">Les fournisseurs peuvent rejoindre des visites virtuelles à l’aide de navigateurs pris en charge ou de l’application Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f46ac-173">Providers can join virtual visits using supported browsers or the Microsoft Teams application.</span></span>

- <span data-ttu-id="f46ac-174">Les fournisseurs doivent se connecter une seule fois avec leur compte Microsoft 365 pour participer à une visite virtuelle pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="f46ac-174">Providers must do a one time sign in with their Microsoft 365 account when joining a virtual visit for the first time.</span></span>

- <span data-ttu-id="f46ac-175">Après la connexion unique, le fournisseur sera directement dirigé vers le rendez-vous virtuel dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f46ac-175">After the one time sign in, the provider will be taken straight to the virtual appointment in Microsoft Teams.</span></span> <span data-ttu-id="f46ac-176">(Le fournisseur doit être connecté à Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="f46ac-176">(Provider must be signed-in to Microsoft Teams).</span></span>

- <span data-ttu-id="f46ac-177">Le fournisseur peut voir les mises à jour en temps réel des participants se connectent et se déconnectent pour un rendez-vous donné.</span><span class="sxs-lookup"><span data-stu-id="f46ac-177">Provider can see real-time updates of participants connect and disconnect for a given appointment.</span></span> <span data-ttu-id="f46ac-178">Le fournisseur peut voir lorsque le patient est connecté à une visite virtuelle.</span><span class="sxs-lookup"><span data-stu-id="f46ac-178">The provider can see when the patient is connected to a virtual visit.</span></span>

  ![Expertise d’une visite virtuelle avec le patient](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a><span data-ttu-id="f46ac-180">Convivialité du patient</span><span class="sxs-lookup"><span data-stu-id="f46ac-180">Patient experience</span></span>

<span data-ttu-id="f46ac-181">Le connecteur prend en charge les patients qui rejoignent les visites virtuelles via le Web et le mobile de MyChart.</span><span class="sxs-lookup"><span data-stu-id="f46ac-181">The connector supports patients joining virtual visits through MyChart web and mobile.</span></span> <span data-ttu-id="f46ac-182">Lorsque le rendez-vous est utilisé, les patients peuvent démarrer une visite virtuelle depuis MyChart à l’aide du bouton **commencer la visite virtuelle** .</span><span class="sxs-lookup"><span data-stu-id="f46ac-182">At the time of the appointment, patients can start a virtual visit from MyChart using the **Begin virtual visit** button.</span></span>

<span data-ttu-id="f46ac-183">Principales fonctionnalités de l’interface du patient :</span><span class="sxs-lookup"><span data-stu-id="f46ac-183">Key features of the patient experience:</span></span>

- <span data-ttu-id="f46ac-184">Les patients peuvent rejoindre des visites virtuelles à partir d’un navigateur Web moderne sur un ordinateur de bureau et sur un appareil mobile sans installation d’applications.</span><span class="sxs-lookup"><span data-stu-id="f46ac-184">Patients can join virtual visits from modern web browsers on desktop and mobile without app installation.</span></span>

- <span data-ttu-id="f46ac-185">Les patients peuvent rejoindre des visites virtuelles d’un simple clic et il n’y a pas de compte supplémentaire ou de connexion obligatoire.</span><span class="sxs-lookup"><span data-stu-id="f46ac-185">Patients can join virtual visits with a single click and there is no additional account or sign in required.</span></span>

- <span data-ttu-id="f46ac-186">Il n’est pas nécessaire de créer un compte Microsoft ou de vous connecter pour lancer une visite virtuelle.</span><span class="sxs-lookup"><span data-stu-id="f46ac-186">Patients aren't required to create a Microsoft account or sign in to launch a virtual visit.</span></span>

- <span data-ttu-id="f46ac-187">Les patients seront placés dans la salle d’attente jusqu’à ce que le prestataire de services de santé rejoigne le rendez-vous et l’autorise à la visite virtuelle.</span><span class="sxs-lookup"><span data-stu-id="f46ac-187">Patients will be placed in a lobby until the healthcare provider joins the appointment and admits them to the virtual visit.</span></span>

- <span data-ttu-id="f46ac-188">Le test de la vidéo et du microphone est disponible dans la salle d’attente avant d’avoir rejoint la visite virtuelle.</span><span class="sxs-lookup"><span data-stu-id="f46ac-188">Testing of the video and microphone is available in the lobby before joining the virtual visit.</span></span>

  ![Convivialité du patient dans la visite virtuelle](../../media/ehc-virtual-visit-5.png)

> [!Note]
> <span data-ttu-id="f46ac-190">Epic, MyChart, Haiku et Canto sont des marques commerciales de Epic Systems Corporation.</span><span class="sxs-lookup"><span data-stu-id="f46ac-190">Epic, MyChart, Haiku, and Canto are trademarks of Epic Systems Corporation.</span></span>

### <a name="privacy-and-location-of-data"></a><span data-ttu-id="f46ac-191">Confidentialité et emplacement des données</span><span class="sxs-lookup"><span data-stu-id="f46ac-191">Privacy and location of data</span></span>

<span data-ttu-id="f46ac-192">L’intégration des équipes aux systèmes DMI optimise le volume de données utilisé et stocké lors de l’intégration et des flux de visites virtuelles.</span><span class="sxs-lookup"><span data-stu-id="f46ac-192">Teams integration into EHR systems optimizes the amount of data being used and stored during integration and virtual visit flows.</span></span> <span data-ttu-id="f46ac-193">La solution suit les principes et recommandations en matière de gestion de la confidentialité et de la gestion des données de teams dans la vie privée de teams.</span><span class="sxs-lookup"><span data-stu-id="f46ac-193">The solution follows the overall Teams privacy and data management principles and guidelines outlined in Teams Privacy.</span></span>

<span data-ttu-id="f46ac-194">Le connecteur DMI de Microsoft Teams ne stocke ni ne transmet de données personnelles identifiables ou des enregistrements médicaux de patients ou de prestataires de services de santé du système DMI.</span><span class="sxs-lookup"><span data-stu-id="f46ac-194">The Microsoft Teams EHR connector doesn't store nor transfer any identifiable personal data or any health records of patients or healthcare providers from the EHR system.</span></span> <span data-ttu-id="f46ac-195">Les seules données stockées par le connecteur DMI sont le numéro unique de l’utilisateur DMI, qui est utilisé lors de la configuration d’une réunion Teams.</span><span class="sxs-lookup"><span data-stu-id="f46ac-195">The only data that is stored by the EHR connector is the EHR user’s unique ID, which is used during Teams meeting setup.</span></span> <span data-ttu-id="f46ac-196">L’identificateur unique de l’utilisateur DMI est stocké dans l’une des trois régions géographiques décrites dans l’article [où sont stockées les données client Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies) .</span><span class="sxs-lookup"><span data-stu-id="f46ac-196">The EHR user’s unique ID is stored in one of the three geographic regions described in the [Where your Microsoft 365 customer data is stored](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies) article.</span></span> <span data-ttu-id="f46ac-197">Toutes les discussions, tous les enregistrements et autres données entrées dans teams par les participants à la réunion sont stockés conformément aux stratégies de stockage existantes.</span><span class="sxs-lookup"><span data-stu-id="f46ac-197">All chat, recordings, and other data entered into Teams by the meeting participants are stored according to existing storage policies.</span></span> <span data-ttu-id="f46ac-198">Pour en savoir plus sur l’emplacement des données dans Microsoft Teams, voir [emplacements des données dans teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span><span class="sxs-lookup"><span data-stu-id="f46ac-198">If you want to learn more information on the location of data in Microsoft Teams, visit [Locations of data in Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span></span>
