---
title: Affectations pour Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.assignments.overview
- ms.teamsadmincenter.assignments.tooltip.emaildigest
- ms.teamsadmincenter.assignments.tooltip.makecode
- ms.teamsadmincenter.assignments.tooltip.turnitin
description: Apprenez à gérer les devoirs dans le centre d’administration Microsoft teams dans teams éducation.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3a0bf0dd0141679dc89ed1d5ecc0cfc542854c8
ms.sourcegitcommit: 3eb5820b279fc904f34ac4259deeb419e02d832a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561050"
---
# <a name="assignments-in-teams-for-education"></a><span data-ttu-id="fac69-103">Devoirs dans Teams pour l’éducation</span><span class="sxs-lookup"><span data-stu-id="fac69-103">Assignments in Teams for Education</span></span>

<span data-ttu-id="fac69-104">Les affectations sont des tâches ou des unités de travail attribuées à un étudiant ou à un membre d’équipe dans une classe dans le cadre de leur étude.</span><span class="sxs-lookup"><span data-stu-id="fac69-104">Assignments are tasks or units of work assigned to a student or team member in a class as part of their study.</span></span> <span data-ttu-id="fac69-105">Vous pouvez créer des devoirs au sein de votre classe Teams.</span><span class="sxs-lookup"><span data-stu-id="fac69-105">You can create assignments within your Teams class.</span></span>

<span data-ttu-id="fac69-106">[En savoir plus sur les devoirs](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).</span><span class="sxs-lookup"><span data-stu-id="fac69-106">[Learn more about Assignments](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).</span></span>

> [!Note]
> <span data-ttu-id="fac69-107">Pour plus d’informations sur les affectations d’équipe sur différentes plateformes, voir [fonctionnalités d’équipes par plate-forme](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span><span class="sxs-lookup"><span data-stu-id="fac69-107">For details about Teams assignments on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="assignments-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="fac69-108">Devoirs dans le centre d’administration Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="fac69-108">Assignments in the Microsoft Teams admin center</span></span>

<span data-ttu-id="fac69-109">Les paramètres d’administration du centre d’administration Microsoft teams vous permettent d’activer ou de désactiver les fonctionnalités suivantes pour être disponibles pour les étudiants et enseignants au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fac69-109">With the admin settings in Microsoft Teams admin center, you can turn the following features on or off to be available for students and teachers within your organization.</span></span> <span data-ttu-id="fac69-110">Vous trouverez ci-dessous des paramètres relatifs aux devoirs :</span><span class="sxs-lookup"><span data-stu-id="fac69-110">The following are settings related to Assignments:</span></span>

<span data-ttu-id="fac69-111"><a name="#bkemaildigest"> </a></span><span class="sxs-lookup"><span data-stu-id="fac69-111"><a name="#bkemaildigest"> </a></span></span>
### <a name="weekly-guardian-email-digest"></a><span data-ttu-id="fac69-112">Résumé du message électronique du tuteur de chaque semaine</span><span class="sxs-lookup"><span data-stu-id="fac69-112">Weekly guardian email digest</span></span>

<span data-ttu-id="fac69-113">Les courriers électroniques contiennent des informations sur les affectations de la semaine précédente et de la semaine à venir, et seront envoyées pendant le week-end.</span><span class="sxs-lookup"><span data-stu-id="fac69-113">The emails will contain information about assignments from the previous week and for the upcoming week, and will be sent over the weekend.</span></span> <span data-ttu-id="fac69-114">Vous trouverez des informations sur le contenu du courrier électronique ici.</span><span class="sxs-lookup"><span data-stu-id="fac69-114">Information about the email content can be found here.</span></span> <span data-ttu-id="fac69-115">Les messages électroniques doivent être configurés et mis à jour par les administrateurs via [School Data Sync](https://docs.microsoft.com/schooldatasync/).</span><span class="sxs-lookup"><span data-stu-id="fac69-115">The emails need to be set up and updated by the admins by using [School Data Sync (SDS)](https://docs.microsoft.com/schooldatasync/).</span></span> <span data-ttu-id="fac69-116">Cette fonctionnalité remplit automatiquement des classes pour les équipes avec les listes des étudiants du système d’information sur les étudiants (SIS) de l’établissement scolaire.</span><span class="sxs-lookup"><span data-stu-id="fac69-116">This feature automatically populates classes for Teams with student rosters from the school's student information system (SIS).</span></span> <span data-ttu-id="fac69-117">Pour activer cette fonctionnalité, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="fac69-117">The steps to enable this feature are:</span></span>

1. <span data-ttu-id="fac69-118">Importez des informations de contact parent via une synchronisation parent et tuteur dans SDS.</span><span class="sxs-lookup"><span data-stu-id="fac69-118">Import parent contact information via Parent and Guardian Sync in SDS.</span></span> <span data-ttu-id="fac69-119">Pour obtenir des instructions sur l’activation de la synchronisation parent et tuteur, voir activation de la [synchronisation parent et tuteur](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).</span><span class="sxs-lookup"><span data-stu-id="fac69-119">For instructions on how to enable Parent and Guardian Sync, see [Enabling Parent and Guardian Sync](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).</span></span>

2. <span data-ttu-id="fac69-120">Activez le paramètre Guardian dans le centre d’administration de Microsoft Teams, car ce paramètre est désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="fac69-120">Turn on the Guardian Setting in the Microsoft Teams admin center, as the setting is turned off by default.</span></span> <span data-ttu-id="fac69-121">Cela permettra aux enseignants d’envoyer un résumé hebdomadaire.</span><span class="sxs-lookup"><span data-stu-id="fac69-121">This will enable teachers to send out a weekly digest.</span></span>

   > [!NOTE]
   > <span data-ttu-id="fac69-122">Les enseignants peuvent annuler le résumé en désélectionnant le paramètre au sein de leur équipe de classe personnelle (**paramètres d’affectation > messages parent/tuteur**).</span><span class="sxs-lookup"><span data-stu-id="fac69-122">Teachers can opt-out of the digest by deselecting the setting inside their own personal class team (**Assignment Settings > Parent/Guardian Emails**).</span></span>

<span data-ttu-id="fac69-123">Pour vérifier que les parents obtiennent le message électronique, les trois éléments suivants doivent être vrais :</span><span class="sxs-lookup"><span data-stu-id="fac69-123">To verify that Parents will get the email the following three items must be true:</span></span>

 - <span data-ttu-id="fac69-124">Adresse de messagerie liée au profil d’étudiant dans SDS et balisée comme _parent_ ou _tuteur_.</span><span class="sxs-lookup"><span data-stu-id="fac69-124">Email address attached to the student profile in SDS and tagged as _Parent_ or _Guardian_.</span></span> <span data-ttu-id="fac69-125">Pour plus d’informations, consultez [format de fichier de synchronisation parent et Guardian](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format).</span><span class="sxs-lookup"><span data-stu-id="fac69-125">For details, see [Parent and Guardian Sync File Format](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format).</span></span>

 - <span data-ttu-id="fac69-126">Les étudiants appartiennent à au moins une classe dans laquelle les messages ne sont pas désactivés par l’enseignant dans les [paramètres d’affectation](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).</span><span class="sxs-lookup"><span data-stu-id="fac69-126">Students belong to at least one class in which e-mail is not disabled by the teacher in [assignment settings](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).</span></span>

 - <span data-ttu-id="fac69-127">Le message électronique contient des informations sur les affectations ayant une date d’échéance au cours de la semaine précédente ou de la semaine prochaine.</span><span class="sxs-lookup"><span data-stu-id="fac69-127">The emails will contain information about assignments that had a due date in the previous week or in the upcoming week.</span></span>

<span data-ttu-id="fac69-128">Ce paramètre est désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="fac69-128">This setting is off by default.</span></span>


<span data-ttu-id="fac69-129"><a name="bkmakecode"> </a></span><span class="sxs-lookup"><span data-stu-id="fac69-129"><a name="bkmakecode"> </a></span></span>
### <a name="makecode"></a><span data-ttu-id="fac69-130">MakeCode</span><span class="sxs-lookup"><span data-stu-id="fac69-130">MakeCode</span></span>
<span data-ttu-id="fac69-131">Microsoft MakeCode est une plate-forme de codage basée sur blocs qui donne vie aux sciences de l’ordinateur pour tous les étudiants.</span><span class="sxs-lookup"><span data-stu-id="fac69-131">Microsoft MakeCode is a block-based coding platform that brings computer science to life for all students.</span></span> 

<span data-ttu-id="fac69-132">MakeCode est un produit Microsoft soumis aux [conditions d’utilisation](https://go.microsoft.com/fwlink/?LinkID=206977) et aux politiques de [confidentialité](https://go.microsoft.com/fwlink/?LinkId=521839) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fac69-132">MakeCode is a Microsoft product that is subject to the Microsoft [terms of use](https://go.microsoft.com/fwlink/?LinkID=206977) and [privacy](https://go.microsoft.com/fwlink/?LinkId=521839) policies.</span></span>

<span data-ttu-id="fac69-133">Ce paramètre est désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="fac69-133">This setting is off by default.</span></span> <span data-ttu-id="fac69-134">Pour activer les affectations MakeCode dans Teams, dans le **Centre d’administration teams**, accédez à la section **affectations** , puis activez l’option bascule **MakeCode.**</span><span class="sxs-lookup"><span data-stu-id="fac69-134">To enable MakeCode assignments in Teams, in the **Teams Admin Center**, navigate to the **Assignments** section and turn the MakeCode toggle option to **On**.</span></span> <span data-ttu-id="fac69-135">Cliquez sur **Enregistrer** et autorisez quelques heures pour que les paramètres soient pris en compte.</span><span class="sxs-lookup"><span data-stu-id="fac69-135">Click **Save** and allow a few hours for these settings to take effect.</span></span>

<span data-ttu-id="fac69-136">Pour plus d’informations sur le fonctionnement de cette fonctionnalité, consultez cette [démonstration vidéo](https://makecode.com/blog/teams/teams-assignments).</span><span class="sxs-lookup"><span data-stu-id="fac69-136">For more information on how this feature works, see this [video demonstration](https://makecode.com/blog/teams/teams-assignments).</span></span>

<span data-ttu-id="fac69-137">[En savoir plus sur MakeCode](https://aka.ms/makecode).</span><span class="sxs-lookup"><span data-stu-id="fac69-137">[Learn more about MakeCode](https://aka.ms/makecode).</span></span>

<span data-ttu-id="fac69-138"><a name="#turnitin"> </a></span><span class="sxs-lookup"><span data-stu-id="fac69-138"><a name="#turnitin"> </a></span></span>
### <a name="turnitin"></a><span data-ttu-id="fac69-139">Turnitin</span><span class="sxs-lookup"><span data-stu-id="fac69-139">Turnitin</span></span>

<span data-ttu-id="fac69-140">Turnitin est un service de détection Plagiarism.</span><span class="sxs-lookup"><span data-stu-id="fac69-140">Turnitin is a plagiarism detection service.</span></span> <span data-ttu-id="fac69-141">Il s’agit d’un produit ou service tiers soumis à ses propres modalités et politique de confidentialité.</span><span class="sxs-lookup"><span data-stu-id="fac69-141">This is a third-party product or service that is subject to its own terms and privacy policy.</span></span> <span data-ttu-id="fac69-142">Vous êtes responsable de l’utilisation des produits et services tiers.</span><span class="sxs-lookup"><span data-stu-id="fac69-142">You are responsible for your use of any third-party products and services.</span></span>

<span data-ttu-id="fac69-143">Ce paramètre est désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="fac69-143">This setting is off by default.</span></span>

<span data-ttu-id="fac69-144">Pour pouvoir activer Turnitin pour votre organisation, vous devez déjà disposer d’un abonnement Turnitin.</span><span class="sxs-lookup"><span data-stu-id="fac69-144">In order to successfully enable Turnitin for your organization, you will need to already have a Turnitin subscription.</span></span> <span data-ttu-id="fac69-145">Vous devrez entrer les informations supplémentaires suivantes, qui se trouvent dans votre console d’administration Turnitin :</span><span class="sxs-lookup"><span data-stu-id="fac69-145">You will need to enter the following additional information, which can be found in your Turnitin admin console:</span></span>

  * <span data-ttu-id="fac69-146">**TurnitinApiKey**: il s’agit d’un GUID de 32 caractères qui se trouve dans la console d’administration sous intégrations.</span><span class="sxs-lookup"><span data-stu-id="fac69-146">**TurnitinApiKey**: This is a 32-character GUID found in the admin console under Integrations.</span></span>
  * <span data-ttu-id="fac69-147">**TurnitinApiUrl**: il s’agit de l’URL HTTPS de votre console d’administration Turnitin.</span><span class="sxs-lookup"><span data-stu-id="fac69-147">**TurnitinApiUrl**: This is the HTTPS URL of your Turnitin admin console.</span></span>

<span data-ttu-id="fac69-148">Voici quelques instructions pour vous aider à obtenir ces informations.</span><span class="sxs-lookup"><span data-stu-id="fac69-148">Here are some instructions to help you obtain this information.</span></span>

<span data-ttu-id="fac69-149">**TurnitinApiUrl** est l’adresse d’hôte de votre console d’administration.</span><span class="sxs-lookup"><span data-stu-id="fac69-149">The **TurnitinApiUrl** is the host address of your admin console.</span></span>
<span data-ttu-id="fac69-150">Example `https://your-tenant-name.turnitin.com`</span><span class="sxs-lookup"><span data-stu-id="fac69-150">Example: `https://your-tenant-name.turnitin.com`</span></span>

<span data-ttu-id="fac69-151">La console d’administration est l’endroit où vous pouvez créer une intégration et une clé d’API associée à l’intégration.</span><span class="sxs-lookup"><span data-stu-id="fac69-151">The admin console is where you can create an integration and an API key associated with the integration.</span></span>

<span data-ttu-id="fac69-152">Sélectionnez **intégrations** dans le menu latéral, sélectionnez **Ajouter une intégration** et attribuez un nom à l’intégration.</span><span class="sxs-lookup"><span data-stu-id="fac69-152">Select **Integrations** from the side menu, then select **Add Integration** and give the integration a name.</span></span>

![Capture d’écran montrant l’ajout d’une nouvelle intégration](./educationImages/Assignments_mopo_turnitin2.png)

<span data-ttu-id="fac69-154">Le **TurnitinApiKey** vous sera fourni une fois que vous aurez suivi les invites.</span><span class="sxs-lookup"><span data-stu-id="fac69-154">The **TurnitinApiKey** will be given to you after you follow the prompts.</span></span> <span data-ttu-id="fac69-155">Copiez la clé de l’API et collez-la dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fac69-155">Copy the API key and paste it into the Microsoft Teams admin center.</span></span>  <span data-ttu-id="fac69-156">C’est la seule fois où vous pouvez afficher la clé.</span><span class="sxs-lookup"><span data-stu-id="fac69-156">This is the only time you can view the key.</span></span>

![Capture d’écran montrant la copie de la clé de l’API](./educationImages/Assignments_mopo_turnitin3.png)

<span data-ttu-id="fac69-158">Lorsque vous cliquez sur le bouton **Enregistrer** dans le centre d’administration pour ce paramètre, patientez quelques heures pour que ces paramètres soient pris en compte.</span><span class="sxs-lookup"><span data-stu-id="fac69-158">Upon clicking the **Save** button in the admin center for this setting, please allow a few hours for these settings to take effect.</span></span>

<span data-ttu-id="fac69-159">Vous êtes prêt à commencer à utiliser l’intégration de Turnitin dans Microsoft teams ?</span><span class="sxs-lookup"><span data-stu-id="fac69-159">Ready to start using the Turnitin integration in Teams?</span></span> <span data-ttu-id="fac69-160">Inscrivez-vous au [programme d’accès en avant](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration).</span><span class="sxs-lookup"><span data-stu-id="fac69-160">Sign up for the [early access program](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration).</span></span>
