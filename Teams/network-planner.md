---
title: Utiliser le Planificateur réseau pour Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: Les administrateurs peuvent découvrir comment utiliser le Planificateur réseau pour déterminer les exigences réseau pour les Microsoft Teams.
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
ms.openlocfilehash: 1f05be30158cf934459f26965d7cef2dafbc708f
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240477"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a><span data-ttu-id="74e5e-103">Utiliser le Planificateur réseau pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="74e5e-103">Use the Network planner for Microsoft Teams</span></span>

<span data-ttu-id="74e5e-104">Network Planner est un nouvel outil disponible dans le Centre d’administration Teams’administration.</span><span class="sxs-lookup"><span data-stu-id="74e5e-104">Network Planner is a new tool that is available in the Teams admin center.</span></span> <span data-ttu-id="74e5e-105">Il est possible de le trouver en vous rendre dans **Planificateur**  >  **Réseau de planification.**</span><span class="sxs-lookup"><span data-stu-id="74e5e-105">It can be found by going to **Planning** > **Network planner**.</span></span> <span data-ttu-id="74e5e-106">En quelques étapes, le Planificateur réseau peut vous aider à déterminer et organiser la exigences réseau pour la connexion des Microsoft Teams utilisateurs au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="74e5e-106">In just a few steps, the Network Planner can help you determine and organize network requirements for connecting Microsoft Teams users across your organization.</span></span> <span data-ttu-id="74e5e-107">Lorsque vous indiquez les détails de votre réseau et de votre utilisation de Teams, le planificateur de réseau calcule les exigences réseau requises pour le déploiement de Teams et de Voix Cloud dans les emplacements physiques de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="74e5e-107">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span>

![Capture d’écran du Planificateur réseau](media/network-planner.png)

<span data-ttu-id="74e5e-109">Le Planificateur réseau vous permet d':</span><span class="sxs-lookup"><span data-stu-id="74e5e-109">Network planner allows you to:</span></span>

- <span data-ttu-id="74e5e-110">Créez des représentations de votre organisation à l’aide de sites et de personnage recommandés par Microsoft (employés de bureau, employés à distance Teams système de salles).</span><span class="sxs-lookup"><span data-stu-id="74e5e-110">Create representations of your organization using sites and Microsoft recommended personas (office workers, remote workers, and Teams room system).</span></span>

    > [!NOTE]
    > <span data-ttu-id="74e5e-111">Les personnage recommandés ont été développés sur la base de Teams de scénarios d’utilisation les plus utilisés et de modèles d’utilisation classiques.</span><span class="sxs-lookup"><span data-stu-id="74e5e-111">The recommended personas were developed based on data from Teams best use scenarios and typical usage patterns.</span></span> <span data-ttu-id="74e5e-112">Toutefois, vous pouvez créer jusqu’à trois personnage personnalisés en plus des trois personnage recommandés.</span><span class="sxs-lookup"><span data-stu-id="74e5e-112">However, you can create up to three custom personas in addition to the three recommended personas.</span></span>

- <span data-ttu-id="74e5e-113">Générez des rapports et calculez les besoins en bande passante Teams’utilisation.</span><span class="sxs-lookup"><span data-stu-id="74e5e-113">Generate reports and calculate bandwidth requirements for Teams usage.</span></span>

<span data-ttu-id="74e5e-114">Pour utiliser le Planificateur réseau, vous devez être administrateur général, administrateur Teams de projets ou administrateur de Teams communications.</span><span class="sxs-lookup"><span data-stu-id="74e5e-114">To use Network planner, you must be a Global Administrator, Teams Administrator, or Teams Communications Administrator.</span></span>

## <a name="create-a-custom-persona"></a><span data-ttu-id="74e5e-115">Créer un personnage personnalisé</span><span class="sxs-lookup"><span data-stu-id="74e5e-115">Create a custom persona</span></span>

<span data-ttu-id="74e5e-116">Pour créer un personnage personnalisé, suivez ces étapes :</span><span class="sxs-lookup"><span data-stu-id="74e5e-116">Follow these steps to create a custom persona:</span></span>

1. <span data-ttu-id="74e5e-117">Dans le Centre d’administration, Microsoft Teams au Planificateur réseau.</span><span class="sxs-lookup"><span data-stu-id="74e5e-117">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="74e5e-118">Sous **l’onglet Personnage,** cliquez **sur + Personnage personnalisé.**</span><span class="sxs-lookup"><span data-stu-id="74e5e-118">On the **Personas** tab, click **+ Custom persona**.</span></span> 

3. <span data-ttu-id="74e5e-119">Dans le **volet Nouveau personnage personnalisé,** ajoutez un nom et une description pour le nouveau personnage.</span><span class="sxs-lookup"><span data-stu-id="74e5e-119">In the **New custom persona** pane, add a name and description for the new persona.</span></span>

4. <span data-ttu-id="74e5e-120">Sélectionnez les autorisations que ce personnage utilisera au sein de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="74e5e-120">Select the permissions that this persona will use within the organization.</span></span>

5. <span data-ttu-id="74e5e-121">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="74e5e-121">Click **Save**.</span></span>

## <a name="build-your-plan"></a><span data-ttu-id="74e5e-122">Créez votre plan</span><span class="sxs-lookup"><span data-stu-id="74e5e-122">Build your plan</span></span>

<span data-ttu-id="74e5e-123">Pour commencer à créer votre plan réseau, suivez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="74e5e-123">Follow these steps to begin building your network plan:</span></span>

1. <span data-ttu-id="74e5e-124">Dans le Centre d’administration, Microsoft Teams au Planificateur réseau.</span><span class="sxs-lookup"><span data-stu-id="74e5e-124">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="74e5e-125">Sous **l’onglet Plan réseau,** cliquez **sur Ajouter un plan réseau.**</span><span class="sxs-lookup"><span data-stu-id="74e5e-125">On the **Network Plan** tab, click **Add a network plan**.</span></span>

3. <span data-ttu-id="74e5e-126">Entrez un nom et une description pour votre plan réseau.</span><span class="sxs-lookup"><span data-stu-id="74e5e-126">Enter a name and description for your network plan.</span></span> <span data-ttu-id="74e5e-127">Le plan réseau s’affiche dans la liste des plans disponibles.</span><span class="sxs-lookup"><span data-stu-id="74e5e-127">The network plan will appear in the list of available plans.</span></span>

4. <span data-ttu-id="74e5e-128">Cliquez sur le nom du plan pour sélectionner le nouveau plan.</span><span class="sxs-lookup"><span data-stu-id="74e5e-128">Click the plan name to select the new plan.</span></span>

5. <span data-ttu-id="74e5e-129">Ajoutez des sites pour créer une représentation de la configuration réseau de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="74e5e-129">Add sites to create a representation of your organization's network setup.</span></span>

    <span data-ttu-id="74e5e-130">En fonction du réseau de votre organisation, vous pouvez utiliser des sites pour représenter un bâtiment, un emplacement de bureau ou autre chose.</span><span class="sxs-lookup"><span data-stu-id="74e5e-130">Depending on your organization's network, you may want to use sites to represent a building, an office location, or something else.</span></span> <span data-ttu-id="74e5e-131">Les sites peuvent être connectés par un réseau WAN pour autoriser le partage des connexions Internet et/ou RSTN.</span><span class="sxs-lookup"><span data-stu-id="74e5e-131">Sites might be connected by a WAN to allow sharing of internet and/or PSTN connections.</span></span> <span data-ttu-id="74e5e-132">Pour de meilleurs résultats, créez des sites avec des connexions locales avant de créer des sites qui se connectent à distance à Internet ou au réseau PSTN.</span><span class="sxs-lookup"><span data-stu-id="74e5e-132">For best results, create sites with local connections before you create sites that remotely connect to the internet or PSTN.</span></span>

    <span data-ttu-id="74e5e-133">Pour créer un site :</span><span class="sxs-lookup"><span data-stu-id="74e5e-133">To create a site:</span></span>

    1. <span data-ttu-id="74e5e-134">Ajoutez un nom et une description pour votre site.</span><span class="sxs-lookup"><span data-stu-id="74e5e-134">Add a name and description for your site.</span></span>

    2. <span data-ttu-id="74e5e-135">Sous **Paramètres réseau,** ajoutez le nombre d’utilisateurs réseau sur ce site (obligatoire).</span><span class="sxs-lookup"><span data-stu-id="74e5e-135">Under **Network settings**, add the number of network users at that site (required).</span></span>

    3. <span data-ttu-id="74e5e-136">Ajoutez les détails du réseau : activé pour le réseau WAN, la capacité WAN, la sortie Internet **(locale** ou distante) et la sortie PSTN (aucune, locale ou distante).</span><span class="sxs-lookup"><span data-stu-id="74e5e-136">Add network details: WAN-enabled, WAN capacity, internet egress (**Local** or **Remote**), and PSTN egress (none, local, or remote).</span></span>

      > [!NOTE]
      > <span data-ttu-id="74e5e-137">Vous devez ajouter des numéros de réseau WAN et de capacité Internet pour consulter des recommandations spécifiques en matière de bande passante lorsque vous générez un rapport.</span><span class="sxs-lookup"><span data-stu-id="74e5e-137">You must add WAN and internet capacity numbers to see specific bandwidth recommendations when you generate a report.</span></span>

    4. <span data-ttu-id="74e5e-138">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="74e5e-138">Click **Save**.</span></span>

## <a name="create-a-report"></a><span data-ttu-id="74e5e-139">Créer un état</span><span class="sxs-lookup"><span data-stu-id="74e5e-139">Create a report</span></span>

<span data-ttu-id="74e5e-140">Après avoir ajouté tous les sites, vous pouvez créer un état comme suit.</span><span class="sxs-lookup"><span data-stu-id="74e5e-140">After you add all sites, you can create a report, as follows.</span></span>

1. <span data-ttu-id="74e5e-141">Sous **l’onglet** Rapports, cliquez **sur Démarrer un rapport.**</span><span class="sxs-lookup"><span data-stu-id="74e5e-141">On the **Reports** tab, click **Start a report**.</span></span>

2. <span data-ttu-id="74e5e-142">Pour chaque site que vous créez, distribuez le nombre d’utilisateurs aux différents personnage disponibles.</span><span class="sxs-lookup"><span data-stu-id="74e5e-142">For each site you create, distribute the number of users across the available personas.</span></span> <span data-ttu-id="74e5e-143">Si vous utilisez les personnage recommandés par Microsoft, le numéro est distribué automatiquement (80 % pour les travailleurs du bureau et 20 % pour les employés à distance).</span><span class="sxs-lookup"><span data-stu-id="74e5e-143">If you use the Microsoft recommended personas, the number will be distributed automatically (80% office worker and 20% remote worker).</span></span>

3. <span data-ttu-id="74e5e-144">Une fois la distribution terminée, cliquez sur **Générer un rapport.**</span><span class="sxs-lookup"><span data-stu-id="74e5e-144">After you complete the distribution, click **Generate report**.</span></span>

    <span data-ttu-id="74e5e-145">Le rapport généré affiche les besoins en bande passante dans plusieurs affichages différents, de sorte que vous pouvez clairement comprendre le résultat :</span><span class="sxs-lookup"><span data-stu-id="74e5e-145">The generated report will show the bandwidth requirements in several different views so that you can clearly understand the output:</span></span>
    - <span data-ttu-id="74e5e-146">Une table avec des calculs individuels affiche les besoins en bande passante pour chaque activité autorisée.</span><span class="sxs-lookup"><span data-stu-id="74e5e-146">A table with individual calculations will display bandwidth requirements for each permitted activity.</span></span>
    - <span data-ttu-id="74e5e-147">Un affichage supplémentaire présente les besoins globaux en bande passante avec des recommandations.</span><span class="sxs-lookup"><span data-stu-id="74e5e-147">An additional view will show the overall bandwidth needs with recommendations.</span></span>

4. <span data-ttu-id="74e5e-148">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="74e5e-148">Click **Save**.</span></span> <span data-ttu-id="74e5e-149">Votre rapport sera disponible dans la liste des rapports pour un affichage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="74e5e-149">Your report will be available on the reports list for later viewing.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="74e5e-150">Exemple de scénario</span><span class="sxs-lookup"><span data-stu-id="74e5e-150">Example scenario</span></span>

<span data-ttu-id="74e5e-151">Pour obtenir un exemple d’utilisation du Planificateur réseau pour configurer un plan réseau et générer un rapport à l’aide de ces étapes, téléchargez l’ensemble de How-To PowerPoint planificateur [réseau](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (en anglais uniquement).</span><span class="sxs-lookup"><span data-stu-id="74e5e-151">For an example of how to use the Network planner to set up a network plan and generate a report using these steps, download the [Network planner How-To PowerPoint deck](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (English only).</span></span>
