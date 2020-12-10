---
title: Utiliser le planificateur de réseaux pour Microsoft teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: L’administrateur peut en savoir plus sur l’utilisation du planificateur de réseau pour déterminer la configuration requise pour le réseau de Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.networkplanner.overview
- ms.teamsadmincenter.networkplanner.personas
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9351c37c96e4bc11f0e5f93041f7e024158d7564
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611798"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a><span data-ttu-id="01aa7-103">Utiliser le planificateur de réseaux pour Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="01aa7-103">Use the Network planner for Microsoft Teams</span></span>

<span data-ttu-id="01aa7-104">Le planificateur de réseaux est un nouvel outil disponible dans le centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="01aa7-104">Network Planner is a new tool that is available in the Teams admin center.</span></span> <span data-ttu-id="01aa7-105">Ce service est disponible en accédant à **Planning**  >  **Network Planner**.</span><span class="sxs-lookup"><span data-stu-id="01aa7-105">It can be found by going to **Planning** > **Network planner**.</span></span> <span data-ttu-id="01aa7-106">En quelques étapes seulement, le planificateur de réseaux peut vous aider à déterminer et organiser les exigences réseau pour la connexion des utilisateurs Microsoft teams au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="01aa7-106">In just a few steps, the Network Planner can help you determine and organize network requirements for connecting Microsoft Teams users across your organization.</span></span> <span data-ttu-id="01aa7-107">Lorsque vous fournissez les informations relatives à votre réseau et à l’utilisation des équipes, le planificateur réseau calcule la configuration requise pour le déploiement d’équipes et de la voix Cloud dans les emplacements physiques de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="01aa7-107">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span>

![Capture d’écran du planificateur de réseaux](media/network-planner.png)

<span data-ttu-id="01aa7-109">Le planificateur réseau vous permet d’effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="01aa7-109">Network planner allows you to:</span></span>

- <span data-ttu-id="01aa7-110">Créer des représentations de votre organisation à l’aide de sites et de personnes recommandées Microsoft (travailleurs Office, travailleurs à distance et systèmes de salle Teams).</span><span class="sxs-lookup"><span data-stu-id="01aa7-110">Create representations of your organization using sites and Microsoft recommended personas (office workers, remote workers, and Teams room system).</span></span>

    > [!NOTE]
    > <span data-ttu-id="01aa7-111">Les personnes recommandées ont été développées en fonction des données des scénarios d’utilisation et de modèles d’utilisation les plus courants.</span><span class="sxs-lookup"><span data-stu-id="01aa7-111">The recommended personas were developed based on data from Teams best use scenarios and typical usage patterns.</span></span> <span data-ttu-id="01aa7-112">Toutefois, vous pouvez créer jusqu’à trois personnages personnalisés en plus des trois personnages recommandés.</span><span class="sxs-lookup"><span data-stu-id="01aa7-112">However, you can create up to three custom personas in addition to the three recommended personas.</span></span>

- <span data-ttu-id="01aa7-113">Générez des rapports et calculez les besoins en bande passante pour l’utilisation des équipes.</span><span class="sxs-lookup"><span data-stu-id="01aa7-113">Generate reports and calculate bandwidth requirements for Teams usage.</span></span>

<span data-ttu-id="01aa7-114">Pour utiliser le planificateur réseau, vous devez être administrateur général, administrateur de service teams ou administrateur de communications Teams.</span><span class="sxs-lookup"><span data-stu-id="01aa7-114">To use Network planner, you must be a Global Administrator, Teams Service Administrator, or Teams Communications Administrator.</span></span>

## <a name="create-a-custom-persona"></a><span data-ttu-id="01aa7-115">Créer un personnage personnalisé</span><span class="sxs-lookup"><span data-stu-id="01aa7-115">Create a custom persona</span></span>

<span data-ttu-id="01aa7-116">Pour créer un personnage personnalisé, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="01aa7-116">Follow these steps to create a custom persona:</span></span>

1. <span data-ttu-id="01aa7-117">Accédez au planificateur de réseau dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="01aa7-117">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="01aa7-118">Dans l’onglet **personnages** , cliquez sur **+ personnalisé**.</span><span class="sxs-lookup"><span data-stu-id="01aa7-118">On the **Personas** tab, click **+ Custom persona**.</span></span> 

3. <span data-ttu-id="01aa7-119">Dans le **nouveau volet de personnages personnalisé** , ajoutez un nom et une description pour le nouveau personnage.</span><span class="sxs-lookup"><span data-stu-id="01aa7-119">In the **New custom persona** pane, add a name and description for the new persona.</span></span>

4. <span data-ttu-id="01aa7-120">Sélectionnez les autorisations que ce personnage utilisera au sein de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="01aa7-120">Select the permissions that this persona will use within the organization.</span></span>

5. <span data-ttu-id="01aa7-121">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="01aa7-121">Click **Save**.</span></span>

## <a name="build-your-plan"></a><span data-ttu-id="01aa7-122">Créer votre plan</span><span class="sxs-lookup"><span data-stu-id="01aa7-122">Build your plan</span></span>

<span data-ttu-id="01aa7-123">Pour commencer à créer votre plan réseau, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="01aa7-123">Follow these steps to begin building your network plan:</span></span>

1. <span data-ttu-id="01aa7-124">Accédez au planificateur de réseau dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="01aa7-124">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="01aa7-125">Dans l’onglet **plan réseau** , cliquez sur **Ajouter un plan réseau**.</span><span class="sxs-lookup"><span data-stu-id="01aa7-125">On the **Network Plan** tab, click **Add a network plan**.</span></span>

3. <span data-ttu-id="01aa7-126">Entrez le nom et la description de votre plan réseau.</span><span class="sxs-lookup"><span data-stu-id="01aa7-126">Enter a name and description for your network plan.</span></span> <span data-ttu-id="01aa7-127">Le plan du réseau doit apparaître dans la liste des offres disponibles.</span><span class="sxs-lookup"><span data-stu-id="01aa7-127">The network plan will appear in the list of available plans.</span></span>

4. <span data-ttu-id="01aa7-128">Cliquez sur le nom du plan pour sélectionner le nouveau plan.</span><span class="sxs-lookup"><span data-stu-id="01aa7-128">Click the plan name to select the new plan.</span></span>

5. <span data-ttu-id="01aa7-129">Ajoutez des sites pour créer une représentation de la configuration réseau de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="01aa7-129">Add sites to create a representation of your organization's network setup.</span></span>

    <span data-ttu-id="01aa7-130">En fonction du réseau de votre organisation, vous souhaiterez peut-être utiliser des sites pour représenter un bâtiment, un emplacement de bureau ou un autre emplacement.</span><span class="sxs-lookup"><span data-stu-id="01aa7-130">Depending on your organization's network, you may want to use sites to represent a building, an office location, or something else.</span></span> <span data-ttu-id="01aa7-131">Les sites peuvent être connectés par un réseau étendu pour autoriser le partage de connexions Internet et/ou PSTN.</span><span class="sxs-lookup"><span data-stu-id="01aa7-131">Sites might be connected by a WAN to allow sharing of internet and/or PSTN connections.</span></span> <span data-ttu-id="01aa7-132">Pour obtenir de meilleurs résultats, créez des sites avec des connexions locales avant de créer des sites qui se connectent à distance à Internet ou PSTN.</span><span class="sxs-lookup"><span data-stu-id="01aa7-132">For best results, create sites with local connections before you create sites that remotely connect to the internet or PSTN.</span></span>

    <span data-ttu-id="01aa7-133">Pour créer un site :</span><span class="sxs-lookup"><span data-stu-id="01aa7-133">To create a site:</span></span>

    1. <span data-ttu-id="01aa7-134">Ajoutez un nom et une description pour votre site.</span><span class="sxs-lookup"><span data-stu-id="01aa7-134">Add a name and description for your site.</span></span>

    2. <span data-ttu-id="01aa7-135">Sous **paramètres réseau**, ajoutez le nombre d’utilisateurs du réseau sur ce site (obligatoire).</span><span class="sxs-lookup"><span data-stu-id="01aa7-135">Under **Network settings**, add the number of network users at that site (required).</span></span>

    3. <span data-ttu-id="01aa7-136">Ajoutez des informations sur le réseau : accès WAN, capacités WAN, sortie Internet (**locale** ou **distante**), sortie PSTN (aucun, local ou distant).</span><span class="sxs-lookup"><span data-stu-id="01aa7-136">Add network details: WAN-enabled, WAN capacity, internet egress (**Local** or **Remote**), and PSTN egress (none, local, or remote).</span></span>

      > [!NOTE]
      > <span data-ttu-id="01aa7-137">Vous devez ajouter des numéros de capacités WAN et Internet pour afficher des recommandations en matière de bande passante spécifiques lors de la génération d’un rapport.</span><span class="sxs-lookup"><span data-stu-id="01aa7-137">You must add WAN and internet capacity numbers to see specific bandwidth recommendations when you generate a report.</span></span>

    4. <span data-ttu-id="01aa7-138">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="01aa7-138">Click **Save**.</span></span>

## <a name="create-a-report"></a><span data-ttu-id="01aa7-139">Créer un rapport</span><span class="sxs-lookup"><span data-stu-id="01aa7-139">Create a report</span></span>

<span data-ttu-id="01aa7-140">Après avoir ajouté tous les sites, vous pouvez créer un rapport, comme suit.</span><span class="sxs-lookup"><span data-stu-id="01aa7-140">After you add all sites, you can create a report, as follows.</span></span>

1. <span data-ttu-id="01aa7-141">Dans l’onglet **rapports** , cliquez sur **Démarrer un rapport**.</span><span class="sxs-lookup"><span data-stu-id="01aa7-141">On the **Reports** tab, click **Start a report**.</span></span>

2. <span data-ttu-id="01aa7-142">Pour chaque site que vous créez, distribuez le nombre d’utilisateurs au sein des personnages disponibles.</span><span class="sxs-lookup"><span data-stu-id="01aa7-142">For each site you create, distribute the number of users across the available personas.</span></span> <span data-ttu-id="01aa7-143">Si vous utilisez les personnages recommandés par Microsoft, le numéro sera distribué automatiquement (80% du travailleur et 20% du travailleur distant).</span><span class="sxs-lookup"><span data-stu-id="01aa7-143">If you use the Microsoft recommended personas, the number will be distributed automatically (80% office worker and 20% remote worker).</span></span>

3. <span data-ttu-id="01aa7-144">Lorsque vous avez terminé la distribution, cliquez sur **générer le rapport**.</span><span class="sxs-lookup"><span data-stu-id="01aa7-144">After you complete the distribution, click **Generate report**.</span></span>

    <span data-ttu-id="01aa7-145">Le rapport généré affiche les exigences de bande passante dans plusieurs affichages de sorte que vous puissiez clairement comprendre la sortie :</span><span class="sxs-lookup"><span data-stu-id="01aa7-145">The generated report will show the bandwidth requirements in several different views so that you can clearly understand the output:</span></span>
    - <span data-ttu-id="01aa7-146">Une table avec des calculs individuels affichera les exigences de bande passante pour chaque activité autorisée.</span><span class="sxs-lookup"><span data-stu-id="01aa7-146">A table with individual calculations will display bandwidth requirements for each permitted activity.</span></span>
    - <span data-ttu-id="01aa7-147">Un affichage supplémentaire affiche les recommandations globales en matière de bande passante.</span><span class="sxs-lookup"><span data-stu-id="01aa7-147">An additional view will show the overall bandwidth needs with recommendations.</span></span>

4. <span data-ttu-id="01aa7-148">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="01aa7-148">Click **Save**.</span></span> <span data-ttu-id="01aa7-149">Votre rapport sera disponible dans la liste des rapports pour un affichage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="01aa7-149">Your report will be available on the reports list for later viewing.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="01aa7-150">Exemple de scénario</span><span class="sxs-lookup"><span data-stu-id="01aa7-150">Example scenario</span></span>

<span data-ttu-id="01aa7-151">Pour obtenir un exemple de l’utilisation du planificateur de réseaux pour configurer un plan réseau et générer un rapport à l’aide de ces étapes, téléchargez le [Planificateur de réseaux How-To présentation PowerPoint](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (en anglais uniquement).</span><span class="sxs-lookup"><span data-stu-id="01aa7-151">For an example of how to use the Network planner to set up a network plan and generate a report using these steps, download the [Network planner How-To PowerPoint deck](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (English only).</span></span>
