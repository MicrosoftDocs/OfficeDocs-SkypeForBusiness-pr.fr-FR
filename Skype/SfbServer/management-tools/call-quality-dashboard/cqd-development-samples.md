---
title: Exemples de développement du tableau de bord de qualité des appels (TBQA)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8ca9bf7a-2d6f-48d5-a821-531009726525
description: 'Résumé : Examinez un didacticiel et des exemples de développement pour le Tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: 193a03662d6f771b19c57017d909cc6574a755ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832724"
---
# <a name="cqd-development-samples"></a><span data-ttu-id="15ae7-104">Exemples de développement du tableau de bord de qualité des appels (TBQA)</span><span class="sxs-lookup"><span data-stu-id="15ae7-104">CQD Development Samples</span></span>

<span data-ttu-id="15ae7-105">**Résumé :** Examinez un didacticiel et des exemples de développement pour le Tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="15ae7-105">**Summary:** Review a tutorial and development samples for Call Quality Dashboard.</span></span> <span data-ttu-id="15ae7-106">Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="15ae7-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="15ae7-107">Cet article fournit un didacticiel et des exemples sur le développement du tableau de bord de qualité des appels (CQD).</span><span class="sxs-lookup"><span data-stu-id="15ae7-107">This article provides a tutorial and samples on development for Call Quality Dashboard (CQD).</span></span>

## <a name="call-quality-dashboard-cqd-development-samples"></a><span data-ttu-id="15ae7-108">Exemples de développement du tableau de bord de qualité des appels</span><span class="sxs-lookup"><span data-stu-id="15ae7-108">Call Quality Dashboard (CQD) Development Samples</span></span>

<span data-ttu-id="15ae7-109">Didacticiel : création d’une présentation de rapport personnalisée à l’aide des API du service de données et du référentiel CQD.</span><span class="sxs-lookup"><span data-stu-id="15ae7-109">Tutorial: Building Customized Report Presentation using the CQD Data Service and Repository Service API's.</span></span>

### <a name="introduction-to-cqd"></a><span data-ttu-id="15ae7-110">Présentation du CQD</span><span class="sxs-lookup"><span data-stu-id="15ae7-110">Introduction to CQD</span></span>

<span data-ttu-id="15ae7-111">Le CQD offre un accès rapide et facile aux informations agrégées sur la qualité des appels pour les déploiements Skype Entreprise Server locaux.</span><span class="sxs-lookup"><span data-stu-id="15ae7-111">CQD offers quick and easy access to aggregated call quality information for on-premise Skype for Business Server deployments.</span></span> <span data-ttu-id="15ae7-112">Le CQD se compose de trois composants : la base de données d’archivage QoE, le cube et le portail.</span><span class="sxs-lookup"><span data-stu-id="15ae7-112">CQD consists of three components: the QoE Archive database, the Cube, and the Portal.</span></span> <span data-ttu-id="15ae7-113">Le portail est la couche de présentation principale et peut être divisé en trois composants :</span><span class="sxs-lookup"><span data-stu-id="15ae7-113">The Portal is the main presentation layer and can be further divided into the following three components:</span></span>

1. <span data-ttu-id="15ae7-114">Service de données, accessible pour les utilisateurs authentifiés via l’API de données pour le tableau de bord de qualité des appels [(CQD) dans Skype Entreprise Server.](data-api.md)</span><span class="sxs-lookup"><span data-stu-id="15ae7-114">Data Service, which is accessible for authenticated users through the [Data API for Call Quality Dashboard (CQD) in Skype for Business Server](data-api.md).</span></span>

2. <span data-ttu-id="15ae7-115">Service de référentiel, accessible pour les utilisateurs authentifiés via l’API de référentiel pour le tableau de bord de qualité des appels [(CQD) dans Skype Entreprise Server.](repository-api.md)</span><span class="sxs-lookup"><span data-stu-id="15ae7-115">Repository Service, which is accessible for authenticated users through the [Repository API for Call Quality Dashboard (CQD) in Skype for Business Server](repository-api.md).</span></span>

3. <span data-ttu-id="15ae7-116">Portail Web, qui est l’interface HTML5 que les utilisateurs de CQD voient et utilisent.</span><span class="sxs-lookup"><span data-stu-id="15ae7-116">Web portal, which is the HTML5 based interface that CQD users see and interact with.</span></span> <span data-ttu-id="15ae7-117">Ceci est accessible pour les utilisateurs authentifiés.</span><span class="sxs-lookup"><span data-stu-id="15ae7-117">This is accessible for authenticated users.</span></span>

<span data-ttu-id="15ae7-118">Les rapports affichés sur le portail web sont regroupés en « ensembles de rapports ».</span><span class="sxs-lookup"><span data-stu-id="15ae7-118">The reports shown on the web portal are grouped into "report sets".</span></span> <span data-ttu-id="15ae7-119">La figure montre un ensemble de rapports avec deux rapports.</span><span class="sxs-lookup"><span data-stu-id="15ae7-119">The figure shows a report set with two reports.</span></span> <span data-ttu-id="15ae7-120">Chaque rapport de ce tableau de bord ci-dessous présente les résultats des requêtes sur le nombre d’appels de qualité, les appels médiocres et le pourcentage d’appels médiocres pendant plusieurs mois, avec différents filtres appliqués.</span><span class="sxs-lookup"><span data-stu-id="15ae7-120">Each report in this dashboard below shows query results on number of good calls, poor calls and poor call percentage for several months, with various filters applied.</span></span> 

![Exemple de rapport CQD](../../media/9e0723f7-f850-4d11-9ecd-7e8e013a8bed.png)

<span data-ttu-id="15ae7-122">Le CQD est créé selon la méthodologie de qualité des appels (CQM), de sorte que l’ensemble de rapports par défaut est conçu pour s’aligner sur le flux d’examen introduit par CQM.</span><span class="sxs-lookup"><span data-stu-id="15ae7-122">CQD is created following the Call Quality Methodology (CQM), so the default set of reports is designed to align with the investigation flow introduced by CQM.</span></span> <span data-ttu-id="15ae7-123">Les utilisateurs ont également la possibilité de modifier ou de créer des rapports personnalisés pour répondre à leurs besoins.</span><span class="sxs-lookup"><span data-stu-id="15ae7-123">Users also have the flexibility to edit or create custom reports to meet their needs.</span></span> <span data-ttu-id="15ae7-124">Toutefois, étant donné qu’il existe plusieurs façons de visualiser les données, la visualisation fournie par CQD peut ne pas répondre entièrement aux besoins de chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="15ae7-124">However, since there are multiple ways to visualize the data, the visualization provided by CQD may not fully address the needs of every user.</span></span> <span data-ttu-id="15ae7-125">Dans de telles situations, un utilisateur peut tirer parti des API de données et des API de référentiel pour créer des pages de rapport personnalisées.</span><span class="sxs-lookup"><span data-stu-id="15ae7-125">In such situations, a user can leverage the Data APIs and Repository APIs to create custom report pages.</span></span> <span data-ttu-id="15ae7-126">Nous allons passer en suivant une série d’exemples dans ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="15ae7-126">We will go through a series of examples in this tutorial.</span></span>

### <a name="how-the-dashboard-consumes-the-data-service"></a><span data-ttu-id="15ae7-127">Consommation du service de données par le tableau de bord</span><span class="sxs-lookup"><span data-stu-id="15ae7-127">How the dashboard consumes the data service</span></span>

<span data-ttu-id="15ae7-128">Lorsque vous naviguez vers la page d’accueil du CQD (par exemple, l’ensemble de rapports et les rapports correspondants pour un utilisateur authentifié et autorisé sont récupérés à partir du service de http://localhost/cqd) référentiel.</span><span class="sxs-lookup"><span data-stu-id="15ae7-128">When navigating to the CQD homepage (e.g. http://localhost/cqd), the report set and corresponding reports for an authenticated and authorized user will be retrieved from the Repository Service.</span></span> <span data-ttu-id="15ae7-129">Une URL complète sera construite à partir de l’ID de l’ensemble de rapports et de l’ID de l’ensemble de rapports (l’ID de l’ensemble de rapports est le nombre entier après la section « /#/ » dans l’URL et, par défaut, le mois de l’année en cours est ajouté à la fin de l’ID de l’ensemble de rapports après la barre oblique).</span><span class="sxs-lookup"><span data-stu-id="15ae7-129">A full URL will be constructed from the report-set ID and the year-month (report-set ID is the integer number after '/#/' section in URL, and by default the current year-month is appended at the end of the report-set ID after the slash).</span></span> <span data-ttu-id="15ae7-130">Les définitions de rapport sont stockées au format JSON et lorsqu’elles sont récupérées à partir du service de référentiel, elles sont ensuite utilisées comme entrées pour le service de données.</span><span class="sxs-lookup"><span data-stu-id="15ae7-130">The report definitions are stored in JSON format and when retrieved from the Repository Service, will then be used as input to the Data Service.</span></span> <span data-ttu-id="15ae7-131">Le service de données génère des requêtes MDX (Multi-Dimension expressions) en fonction de l’entrée, puis exécute ces requêtes MDX sur le cube pour récupérer des données pour chaque rapport.</span><span class="sxs-lookup"><span data-stu-id="15ae7-131">The Data Service generates Multi-Dimension expressions (MDX) queries based on the input and then run these MDX queries against the Cube to retrieve data for each report.</span></span> 

### <a name="building-customized-reports"></a><span data-ttu-id="15ae7-132">Création de rapports personnalisés</span><span class="sxs-lookup"><span data-stu-id="15ae7-132">Building customized reports</span></span>

<span data-ttu-id="15ae7-133">Le CQD offre déjà beaucoup de flexibilité dans la personnalisation des rapports, mais il peut y avoir des situations dans lesquelles les utilisateurs peuvent vouloir agréger des données dans plusieurs rapports créés dans le CQD.</span><span class="sxs-lookup"><span data-stu-id="15ae7-133">CQD already has a lot of flexibility in customizing reports, but there could be situations where users may want to aggregate data across multiple reports created in CQD.</span></span> <span data-ttu-id="15ae7-134">Par exemple, il peut être nécessaire de créer un rapport qui indique les pourcentages d’appels médiocres de toutes les combinaisons possibles d’appels câblés dans une table (un résultat comme la figure) :</span><span class="sxs-lookup"><span data-stu-id="15ae7-134">For example, there could be a need to create a report that shows the poor call percentages of all possible combinations of wired calls in a table (a result like the figure):</span></span>

![CQD Table](../../media/ef19d535-5da6-44a9-91f6-1ed3f30b96f1.png)

<span data-ttu-id="15ae7-136">À l’aide du portail fourni par le CQD, un utilisateur doit accéder à plusieurs rapports pour extraire et enregistrer le pourcentage d’appels médiocres pour chacun d’eux, ce qui peut être laborieux si de nombreux points de données doivent être collectés.</span><span class="sxs-lookup"><span data-stu-id="15ae7-136">Using the Portal provided by CQD, a user would have to navigate to multiple reports to extract and record the poor call % for each one, which can be laborious if there are many data points that need to be collected.</span></span> <span data-ttu-id="15ae7-137">Les API de données permettent aux utilisateurs d’effectuer cette tâche par programme, en récupérant des données à partir du service de données (par exemple, via des appels AJAX).</span><span class="sxs-lookup"><span data-stu-id="15ae7-137">The Data APIs provide users with a programmatic way to accomplish this, by retrieving data from the Data Service (e.g. via AJAX calls).</span></span> 

 <span data-ttu-id="15ae7-138">**Exemple 1 : exemple de rapport simple**</span><span class="sxs-lookup"><span data-stu-id="15ae7-138">**Example 1: Simple report sample**</span></span>

<span data-ttu-id="15ae7-139">Prenons d’abord un exemple simple.</span><span class="sxs-lookup"><span data-stu-id="15ae7-139">Let us take a simple example first.</span></span> <span data-ttu-id="15ae7-140">Si nous voulons afficher le nombre de flux Audio Good Stream et Audio Bad de février 2015 sur une page HTML comme dans la figure :</span><span class="sxs-lookup"><span data-stu-id="15ae7-140">If we want to show the Audio Good Stream and the Audio Bad stream count of February 2015 on an HTML page like the figure:</span></span>

![Exemple de rapport de CQD](../../media/f0e4e61f-1fa5-4d69-b192-f19e9612bf1c.png)

<span data-ttu-id="15ae7-142">Nous devons envoyer un appel au service de données avec les paramètres appropriés et afficher les résultats de la requête dans une table HTML.</span><span class="sxs-lookup"><span data-stu-id="15ae7-142">What we need is to send a call to the Data Service with the proper parameters, and show the query results in an HTML table.</span></span> <span data-ttu-id="15ae7-143">Voici un exemple de code JavaScript :</span><span class="sxs-lookup"><span data-stu-id="15ae7-143">The following is a sample of the JavaScript code:</span></span>

```javascript        
$($.fn.freeFormReport = function (queries, urlApi, presentation) {
            var query = {
                Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                Filters: [{
                    DataModelName: '[StartDate].[Month]',
                    Value: '[2015-02-01T00:00:00]',
                    Operand: 0
                }],
                Measurements:
                    [{ DataModelName: '[Measures].[Audio Good Streams JPDR Count]' },
                     { DataModelName: '[Measures].[Audio Poor Streams JPDR Count]' },]
            };            

            $.ajax({
                url: 'http://localhost/QoEDataService/RunQuery',
                data: JSON.stringify(query),
                type: 'POST',
                async: true,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    //This is the jQuery syntax for document.GetElementById()
                    $('#AudioGoodStreamsJPDRCount').html(data.DataResult[0][1]);
                    $('#AudioPoorStreamsJPDRCount').html(data.DataResult[0][2]);
                }
                error: function (error) {
                    alert('Error getting data, check that the data service is running and that the URL is correct.');
           }
            });
        });
```

<span data-ttu-id="15ae7-144">Cet exemple peut être déconstruit en trois étapes :</span><span class="sxs-lookup"><span data-stu-id="15ae7-144">This example can be further deconstructed into three steps:</span></span>

1. <span data-ttu-id="15ae7-145">Construisez la requête (dans l’exemple, elle est définie dans la variable « query »).</span><span class="sxs-lookup"><span data-stu-id="15ae7-145">Construct the query (in the example this is defined in the variable 'query').</span></span> <span data-ttu-id="15ae7-146">La requête est définie comme un objet JSON, qui inclut les données suivantes :</span><span class="sxs-lookup"><span data-stu-id="15ae7-146">The query is defined as a JSON object, which includes the following data:</span></span>

   <span data-ttu-id="15ae7-147">a.</span><span class="sxs-lookup"><span data-stu-id="15ae7-147">a.</span></span> <span data-ttu-id="15ae7-148">Zéro ou plusieurs dimensions.</span><span class="sxs-lookup"><span data-stu-id="15ae7-148">Zero or more dimensions.</span></span> <span data-ttu-id="15ae7-149">Chaque dimension est indiquée par un DataModelName.</span><span class="sxs-lookup"><span data-stu-id="15ae7-149">Each dimension is indicated by a DataModelName.</span></span>

   <span data-ttu-id="15ae7-150">b.</span><span class="sxs-lookup"><span data-stu-id="15ae7-150">b.</span></span> <span data-ttu-id="15ae7-151">Zéro filtre ou plus.</span><span class="sxs-lookup"><span data-stu-id="15ae7-151">Zero or more filters.</span></span> <span data-ttu-id="15ae7-152">Chaque filtre a :</span><span class="sxs-lookup"><span data-stu-id="15ae7-152">Each filter has:</span></span>

   - <span data-ttu-id="15ae7-153">DataModelName (la dimension qui aura le jeu de filtres).</span><span class="sxs-lookup"><span data-stu-id="15ae7-153">DataModelName (the dimension that will have the filter set).</span></span>

   - <span data-ttu-id="15ae7-154">Valeur (valeur qui sera comparée par l’opérande).</span><span class="sxs-lookup"><span data-stu-id="15ae7-154">Value (the value that will be compared by the operand).</span></span>

   - <span data-ttu-id="15ae7-155">Opérande (type de comparaison, 0 signifie « Égal »).</span><span class="sxs-lookup"><span data-stu-id="15ae7-155">Operand (comparison type, 0 means "Equal").</span></span>

     <span data-ttu-id="15ae7-156">c.</span><span class="sxs-lookup"><span data-stu-id="15ae7-156">c.</span></span> <span data-ttu-id="15ae7-157">Une ou plusieurs mesures.</span><span class="sxs-lookup"><span data-stu-id="15ae7-157">One or more measurements.</span></span>

2. <span data-ttu-id="15ae7-158">Envoyez la requête au service de données via un appel AJAX.</span><span class="sxs-lookup"><span data-stu-id="15ae7-158">Send the query to Data Service via AJAX call.</span></span> <span data-ttu-id="15ae7-159">Les paramètres de requête suivants doivent être fournis :</span><span class="sxs-lookup"><span data-stu-id="15ae7-159">The following request parameters need to be provided:</span></span>

   <span data-ttu-id="15ae7-160">a.</span><span class="sxs-lookup"><span data-stu-id="15ae7-160">a.</span></span> <span data-ttu-id="15ae7-161">url (qui doit être http://[ServerName]/QoEDataService/RunQuery).</span><span class="sxs-lookup"><span data-stu-id="15ae7-161">url (which should be http://[ServerName]/QoEDataService/RunQuery).</span></span>

   <span data-ttu-id="15ae7-162">b.</span><span class="sxs-lookup"><span data-stu-id="15ae7-162">b.</span></span> <span data-ttu-id="15ae7-163">(il s’agit de la représentation sous la chaîne de l’objet JSON défini dans la variable « query »).</span><span class="sxs-lookup"><span data-stu-id="15ae7-163">data (this is the string representation of the JSON object defined in the 'query' variable).</span></span> <span data-ttu-id="15ae7-164">Le service de données retourne les résultats de la requête en tant que paramètre de la fonction de retour d’appel en cas de réussite.</span><span class="sxs-lookup"><span data-stu-id="15ae7-164">Data Service will return the query results as a parameter of the call back function for success.</span></span>

   <span data-ttu-id="15ae7-165">c.</span><span class="sxs-lookup"><span data-stu-id="15ae7-165">c.</span></span> <span data-ttu-id="15ae7-166">(pour QoEDataService, RunQuery accepte uniquement les demandes « POST »).</span><span class="sxs-lookup"><span data-stu-id="15ae7-166">type (for QoEDataService, RunQuery only accepts 'POST' requests).</span></span>

   <span data-ttu-id="15ae7-167">d.</span><span class="sxs-lookup"><span data-stu-id="15ae7-167">d.</span></span> <span data-ttu-id="15ae7-168">asynchrone (indicateur indiquant si l’appel AJAX doit être synchrone ou asynchrone).</span><span class="sxs-lookup"><span data-stu-id="15ae7-168">async (a flag indicating whether the AJAX call should be synchronous or asynchronous).</span></span>

   <span data-ttu-id="15ae7-169">e.</span><span class="sxs-lookup"><span data-stu-id="15ae7-169">e.</span></span> <span data-ttu-id="15ae7-170">contentType (doit être « application/json »).</span><span class="sxs-lookup"><span data-stu-id="15ae7-170">contentType (should be "application/json").</span></span>

   <span data-ttu-id="15ae7-171">f.</span><span class="sxs-lookup"><span data-stu-id="15ae7-171">f.</span></span> <span data-ttu-id="15ae7-172">réussite (fonction de call-back pour la fin de l’appel AJAX).</span><span class="sxs-lookup"><span data-stu-id="15ae7-172">success (call-back function for when the AJAX call finishes successfully).</span></span>

   <span data-ttu-id="15ae7-173">g.</span><span class="sxs-lookup"><span data-stu-id="15ae7-173">g.</span></span> <span data-ttu-id="15ae7-174">erreur (fonction de gestion des erreurs en cas d’échec de l’appel AJAX).</span><span class="sxs-lookup"><span data-stu-id="15ae7-174">error (error handling function for when AJAX call fails).</span></span>

3. <span data-ttu-id="15ae7-175">Placez les données dans des éléments div dans le code HTML (dans l’exemple du code, cette procédure est effectuée via l’appel de fonction anonyme une fois la demande AJAX terminée avec succès).</span><span class="sxs-lookup"><span data-stu-id="15ae7-175">Put data into div elements in the HTML (in the example in the code, this is done via the anonymous function call after the AJAX request is completed successfully).</span></span>

<span data-ttu-id="15ae7-176">Le code JavaScript est inclus dans une page HTML, et la page affiche un rapport comme celui illustré dans la figure.</span><span class="sxs-lookup"><span data-stu-id="15ae7-176">Enclosing the JavaScript code into an HTML page, and the page will show a report like the one shown in the figure.</span></span> <span data-ttu-id="15ae7-177">Le code HTML complet est le suivant :</span><span class="sxs-lookup"><span data-stu-id="15ae7-177">The full html is as follows:</span></span>

```javascript
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
</head>
<body>
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <script>
        $($.fn.freeFormReport = function (queries, urlApi, presentation) {

            var query = {
                Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                Filters: [{
                    DataModelName: '[StartDate].[Month]',
                    Value: '[2015-02-01T00:00:00]',
                    Operand: 0
                }],
                Measurements:
                    [{ DataModelName: '[Measures].[Audio Good Streams JPDR Count]' },
                     { DataModelName: '[Measures].[Audio Poor Streams JPDR Count]' },]
            };            

            $.ajax({
                url: 'http://localhost/QoEDataService/RunQuery',
                data: JSON.stringify(query),
                type: 'POST',
                async: true,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    //This is the jQuery syntax for document.GetElementById()
                    $('#AudioGoodStreamsJPDRCount').html(data.DataResult[0][1]);
                    $('#AudioPoorStreamsJPDRCount').html(data.DataResult[0][2]);
                }
                error: function (error) {
                    alert('Error getting data, check that the data service is running and that the URL is correct.');
           }

            });
        });
    </script>
    <table border="1">
        <tr>
            <td></td>
            <td><div>Audio Good Streams JPDR Count</div></td>
            <td><div>Audio Poor Streams JPDR Count</div></td>
        </tr>
        <tr>
            <td>February</td>
            <td><div id="AudioGoodStreamsJPDRCount"></div></td>
            <td><div id="AudioPoorStreamsJPDRCount"></div></td>
        </tr>
    </table>
</body>
</html>
```

<span data-ttu-id="15ae7-178">Jusqu’à présent, le rapport est toujours très simple.</span><span class="sxs-lookup"><span data-stu-id="15ae7-178">So far, the report is still very simple.</span></span> <span data-ttu-id="15ae7-179">L’utilisateur peut ajouter des mesures, des dimensions ou des filtres supplémentaires pour personnaliser le rapport.</span><span class="sxs-lookup"><span data-stu-id="15ae7-179">The user can add more measurements, dimensions, or filters to customize the report.</span></span> <span data-ttu-id="15ae7-180">Par exemple, si vous souhaitez afficher le pourcentage d’appels médiocres AppSharing, une nouvelle mesure concernant AppSharing doit être ajoutée.</span><span class="sxs-lookup"><span data-stu-id="15ae7-180">For example, if you want to show AppSharing poor call percentage, then a new measurement regarding AppSharing needs to be added.</span></span> <span data-ttu-id="15ae7-181">Si vous souhaitez afficher tous les appels TCP v.s.</span><span class="sxs-lookup"><span data-stu-id="15ae7-181">If you want to show all TCP calls v.s.</span></span> <span data-ttu-id="15ae7-182">Les appels UDP, une nouvelle dimension concernant le type de transport doit être ajoutée.</span><span class="sxs-lookup"><span data-stu-id="15ae7-182">UDP calls, a new dimension regarding transportation type should be added.</span></span> <span data-ttu-id="15ae7-183">Si vous souhaitez afficher le nombre d’appels médiocres dans un bâtiment spécifique, un nouveau filtre doit être ajouté pour sélectionner les appels vers et depuis ce bâtiment.</span><span class="sxs-lookup"><span data-stu-id="15ae7-183">If you want to show the number of poor calls within a specific building, then a new filter should be added to select the calls to and from that building.</span></span>

 <span data-ttu-id="15ae7-184">**Exemple 2 : exemple de définition de rapport**</span><span class="sxs-lookup"><span data-stu-id="15ae7-184">**Example 2: Report definition sample**</span></span>

<span data-ttu-id="15ae7-185">Il peut être difficile pour quelqu’un de déterminer comment écrire la liste complète des mesures/dimensions/filtres et leurs valeurs correspondantes lors de la construction d’une requête.</span><span class="sxs-lookup"><span data-stu-id="15ae7-185">It might be difficult for someone to figure out how to write the full list of measurements/dimensions/filters and their corresponding values when constructing a query.</span></span> <span data-ttu-id="15ae7-186">Dans ce cas, vous pouvez aller sur le portail, créer un rapport à l’aide de l’éditeur de rapport, afficher la chaîne JSON de la définition de rapport, puis copier la définition dans un rapport personnalisé.</span><span class="sxs-lookup"><span data-stu-id="15ae7-186">In this case, you can go to the Portal, build a report using the report editor, and view the JSON string of the report definition, and then copy the definition into a custom report.</span></span> 

<span data-ttu-id="15ae7-187">Dans cet exemple, nous allons créer une page web comme celle présentée dans la figure dans laquelle un utilisateur peut entrer l’ID de n’importe quel ensemble de rapports (ou rapport) existant et afficher la définition de l’ensemble de rapports ou du rapport sur la page web.</span><span class="sxs-lookup"><span data-stu-id="15ae7-187">In this example, we will create a web page like the one shown in the figure where a user can enter the ID of any existing report set (or report) and show the definition of the report set or report on the web page.</span></span> <span data-ttu-id="15ae7-188">L’utilisateur peut ensuite brancher la chaîne JSON de chaque rapport dans du code semblable à celui de l’exemple 1 et construire n’importe quel rapport personnalisé souhaité par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="15ae7-188">The user can then plug the JSON string of each report into code similar to the one shown in Example 1 and construct any customized report the user desires.</span></span> 

![Exemple de CQD](../../media/01c45c23-c4d2-47b8-819f-0888cf71260f.png)

<span data-ttu-id="15ae7-190">Pour créer l’outil visionneuse de définitions de rapports, nous devons envoyer des appels au service de référentiel pour récupérer les représentations de chaîne JSON des définitions de chaque ensemble de rapports de notre recherche.</span><span class="sxs-lookup"><span data-stu-id="15ae7-190">To create the report definition viewer tool, we need to send calls to Repository Service to retrieve the JSON string representations of the definitions of every report-set we want.</span></span> <span data-ttu-id="15ae7-191">L’API Référentiel retourne la définition de l’ensemble de rapports en fonction d’un ID d’ensemble de rapports donné.</span><span class="sxs-lookup"><span data-stu-id="15ae7-191">The Repository API will return report-set definition based on a given report set ID.</span></span> 

<span data-ttu-id="15ae7-192">Voici un exemple rapide : le code contient un bloc qui est un exemple simple d’envoi d’une requête au service référentiel pour obtenir le contenu d’un élément de référentiel en fonction de son identificateur.</span><span class="sxs-lookup"><span data-stu-id="15ae7-192">A quick example is as follows, the code contains a block that is a simple example to send a query to the Repository service to get the contents of a repository item based on its identifier.</span></span> <span data-ttu-id="15ae7-193">Et la partie suivante du code (méthode processReportSetData) envoie des appels AJAX pour obtenir la définition de chaque rapport au sein de cet ensemble de rapports.</span><span class="sxs-lookup"><span data-stu-id="15ae7-193">And the next portion of code (processReportSetData method) is sending AJAX calls to get the definition of each report within that report set.</span></span> <span data-ttu-id="15ae7-194">Étant donné que l’ID dans le portail web CQD est l’ID d’un ensemble de rapports, l’appel AJAX retourne un élément d’ensemble de rapports.</span><span class="sxs-lookup"><span data-stu-id="15ae7-194">Since the ID in the CQD web portal is the ID of a report set, the AJAX call will return a report set item.</span></span> <span data-ttu-id="15ae7-195">Vous pouvez trouver plus de détails sur l’API du référentiel et, plus spécifiquement, GetItems, dans [l’article Obtenir des éléments.](get-items.md)</span><span class="sxs-lookup"><span data-stu-id="15ae7-195">More detail on the Repository API and specifically, GetItems, can be found in the [Get Items](get-items.md).</span></span> 

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <meta http-equiv='cache-control' content='no-cache'>
    <meta http-equiv='expires' content='0'>
    <meta http-equiv='pragma' content='no-cache'>
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta http-equiv="x-content-type-options" content="nosniff">
    <title>CQD Report definition viewer</title>
</head>
<body>    
    <div style="font-size:32pt">CQD Report definition viewer</div>
        <p>ReportSet Id: <input id="reportSetId" /></p>
        <button onclick='loadReportSet()'>Load</button>
        <div id="Report"></div>
    <!-- Third party Libraries -->
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <script>
        var urlRepositoryApi = 'http://localhost/QoERepositoryService/repository/item/';

        var loadReportSet = function ()
        {
            var reportSetId = document.getElementById('reportSetId').value;

            $.ajax({
                url: urlRepositoryApi + reportSetId,
                data: '',
                type: 'GET',
                async: false,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    var reportSetDiv = document.getElementById('Report');
                    reportSetDiv.innerHTML = '';
                    processReportSetData(reportSetDiv, data);
                },
                error: function (error) {
                    alert('Error getting Report, check that the qoe data service is running and url is correct.');
                }
            });
        };

        var processReportSetData = function (divReportSet, reportSetDef) {
             //show the report set definition like Title, Description, etc
            showReportSetDefinition(divReportSet, reportSetDef);

            //for each Report in the Reportset, get the Report definition from the Repository Service
            for (var i = 0; i < reportSetDef.subItemIds.length; i++)
            {
                //the reportId is in the subItemIds array.  This is not shown in the CQD UI at all
                var reportId = reportSetDef.subItemIds[i];

                var divReport = document.createElement('div');
                divReport.style.margin = '12px';                
                divReportSet.appendChild(divReport);

                //retrieve the report definition with the reportId
                $.ajax({
                    url: urlRepositoryApi + reportId,
                    data: '',
                    type: 'GET',
                    async: false,
                    contentType: 'application/json;charset=utf-8',
                    success: function (reportData) {
                        processReportData(divReport, reportData, reportId);
                    },
                    error: function (error) {
                        alert('Error getting Report ' + reportId.toString() + ', check that the qoe data service is running and url is correct.');
                    }
                });
            }
        };

        //helper function to render the ReportSet definition
        var showReportSetDefinition = function (divReportSet, reportSetDef) {
            var div = document.createElement('div');
            ReportSetDefinition = reportSetDef.content;
            txt = document.createTextNode(ReportSetDefinition);
            div.style.margin = '12px';
            div.appendChild(txt);
            divReportSet.appendChild(div);
        };

        //show the report definition
        var processReportData = function (divReport, reportData, itemId) {
            if (divReport != undefined &amp;&amp; reportData.content != undefined) {
                var Report = JSON.parse(reportData.content);

                var divReportId = document.createElement('div');
                var subItemId = reportData.subItemIds.length > 0 ? reportData.subItemIds[0].toString() : 'none';
                divReportId.innerHTML = 'ItemId: ' + itemId.toString() + ' (' + Report.Title + ') [subItemId:' + subItemId + ']';
                divReport.appendChild(divReportId);

                var divReportDef = document.createElement('div');
                txt = document.createTextNode(JSON.stringify(Report));
                divReportDef.style.margin = '12px';
                divReportDef.appendChild(txt);                            
                divReport.appendChild(divReportDef);
            }
        };
    </script>
</body>
</html>
```

<span data-ttu-id="15ae7-196">La page web ci-dessus se présente comme celle de la figure (sans la définition du rapport lors de la visite initiale).</span><span class="sxs-lookup"><span data-stu-id="15ae7-196">The above will result in a web page like the one in the figure (without the report definition upon initial visit).</span></span> <span data-ttu-id="15ae7-197">Obtenir l’ID de l’ensemble de rapports à partir du portail CQD (après la signature « /# / » dans l’URL du portail CQD (par exemple,</span><span class="sxs-lookup"><span data-stu-id="15ae7-197">Get the report set ID from CQD portal (it is after '/#/' sign in CQD portal URL (E.g.</span></span> <span data-ttu-id="15ae7-198">dans la première figure, l’ID de l’ensemble de rapports est 3024, puis placez cet ID de jeu de rapports dans la section d’entrée de cette page web.</span><span class="sxs-lookup"><span data-stu-id="15ae7-198">in the first figure the report set ID is 3024), and put this report set ID into the input section of this web page.</span></span> <span data-ttu-id="15ae7-199">Appuyez sur le bouton « charger » et voir la définition complète (mesures, dimensions, listes de filtres) de l’ensemble de rapports.</span><span class="sxs-lookup"><span data-stu-id="15ae7-199">Press the "load" button and see the full definition (measurements, dimensions, filters lists) of the report set.</span></span>

<span data-ttu-id="15ae7-200">En résumé, afin d’obtenir rapidement la définition complète d’un ensemble de rapports/rapports.</span><span class="sxs-lookup"><span data-stu-id="15ae7-200">In summary, in order to quickly get the full definition of a report/report set.</span></span> <span data-ttu-id="15ae7-201">Voici comment procéder :</span><span class="sxs-lookup"><span data-stu-id="15ae7-201">The steps are:</span></span>

1. <span data-ttu-id="15ae7-202">Go to the Portal and use the query editor to customize a report (click the « Edit » button above a report to edit, add, remove measurements/dimensions/filters, and then save the report).</span><span class="sxs-lookup"><span data-stu-id="15ae7-202">Go to the Portal and use the query editor to customize a report (click the "Edit" button above a report to edit, add, remove measurements/dimensions/filters, and then save the report).</span></span>

2. <span data-ttu-id="15ae7-203">Obtenez l’ID de l’ensemble de rapports à partir de l’URL (l’nombre integer après l’URL de la signature « /# / »).</span><span class="sxs-lookup"><span data-stu-id="15ae7-203">Get the report set ID from URL (the integer after '/#/' sign in URL).</span></span>

3. <span data-ttu-id="15ae7-204">Lancez cette page web définition de rapport créée dans l’exemple 2, entrez l’ID de l’ensemble de rapports et récupérez la définition complète d’un ensemble de rapports (à utiliser dans les appels d’API de données).</span><span class="sxs-lookup"><span data-stu-id="15ae7-204">Launch this Report Definition web page created in Example 2, and enter the report set ID and retrieve the full definition of a report set (to use in Data API calls).</span></span>

   <span data-ttu-id="15ae7-205">**Exemple 3 : Exemple de carte de performance**</span><span class="sxs-lookup"><span data-stu-id="15ae7-205">**Example 3: Scorecard sample**</span></span>

<span data-ttu-id="15ae7-206">Temps pour une tâche plus complexe.</span><span class="sxs-lookup"><span data-stu-id="15ae7-206">Time for a more complicated task.</span></span> <span data-ttu-id="15ae7-207">Que se passe-t-il si nous voulons créer une page web comme la figure ?</span><span class="sxs-lookup"><span data-stu-id="15ae7-207">What if we want to create a web page like the figure?</span></span> <span data-ttu-id="15ae7-208">Nous devons mettre à jour l’exemple 1 (à l’aide de la page web générée dans l’exemple 2 pour récupérer la définition complète d’un rapport) afin de pouvoir gérer une plus grande quantité de données.</span><span class="sxs-lookup"><span data-stu-id="15ae7-208">We need to update Example 1, (with the help of the web page generated in Example 2 to retrieve the full definition of any report) so that we can handle larger amount of data.</span></span>

<span data-ttu-id="15ae7-209">Dans ce cas, nous devons mettre à jour la liste de mesures et de dimensions.</span><span class="sxs-lookup"><span data-stu-id="15ae7-209">In this case, we need to update the measurement and dimension list.</span></span> <span data-ttu-id="15ae7-210">Pour déterminer comment ajouter/modifier une mesure et/ou une dimension, suivez les instructions de l’exemple 2 et récupérez la définition complète du rapport, y compris les listes complètes de mesures et de dimensions.</span><span class="sxs-lookup"><span data-stu-id="15ae7-210">The way to figure out how to add/edit a measurement and/or a dimension is to follow the instructions in Example 2, and retrieve the full report definition, including the full measurement and dimension lists.</span></span> <span data-ttu-id="15ae7-211">Branchez la définition complète du rapport dans l’exemple de code.</span><span class="sxs-lookup"><span data-stu-id="15ae7-211">Plug the full report definition into the sample code.</span></span> 

<span data-ttu-id="15ae7-212">Voici les étapes détaillées pour obtenir la page de carte de performance dans la figure à partir de l’exemple fourni dans l’exemple 1 :</span><span class="sxs-lookup"><span data-stu-id="15ae7-212">Here are the detailed steps to get to the scorecard page in the figure from the sample provided in Example 1:</span></span>

1. <span data-ttu-id="15ae7-213">Mettre à jour les mesures dans la variable « requête » de  `[Measures].[Audio Good Streams JPDR Count]` et `[Measures].[Audio Poor Streams JPDR Count]` vers `[Measures].[AudioPoorJPDRPercentage]` .</span><span class="sxs-lookup"><span data-stu-id="15ae7-213">Update Measurements in the 'query' variable from  `[Measures].[Audio Good Streams JPDR Count]` and `[Measures].[Audio Poor Streams JPDR Count]` to `[Measures].[AudioPoorJPDRPercentage]`.</span></span> 

2. <span data-ttu-id="15ae7-214">Mettez à jour les filtres.</span><span class="sxs-lookup"><span data-stu-id="15ae7-214">Update the filters.</span></span> <span data-ttu-id="15ae7-215">Les données JSON pour filtres de l’exemple 1 ont un filtre, qui est définie sur la dimension  `[StartDate].[Month]` .</span><span class="sxs-lookup"><span data-stu-id="15ae7-215">The JSON data for Filters in Example 1 has one filter, which is set on the dimension  `[StartDate].[Month]`.</span></span> <span data-ttu-id="15ae7-216">Étant donné que Filtres est un tableau JSON, des dimensions supplémentaires peuvent être ajoutées à la liste des filtres.</span><span class="sxs-lookup"><span data-stu-id="15ae7-216">Since Filters is a JSON array, additional dimensions can be added to the list of filters.</span></span> <span data-ttu-id="15ae7-217">Par exemple, pour obtenir le client-serveur à l’intérieur d’appels câblés pour le « currentMonth », nous devons avoir les filtres suivants :</span><span class="sxs-lookup"><span data-stu-id="15ae7-217">For example, to get the server-client inside wired calls for the "currentMonth", we should have the following filters:</span></span>

   ```javascript
   Filters: [
     { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
    {
        "DataModelName": "[Scenarios].[ScenarioPair]",
         "Caption": " Server-Inside-wired,Client-Inside-wired",
         "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
         "Operand": 0,
         "UnionGroup": ""
     },

     { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
   ],
   ```

   <span data-ttu-id="15ae7-218">Ici, la dimension  `[Scenarios].[ScenarioPair]` est définie sur égal `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` .</span><span class="sxs-lookup"><span data-stu-id="15ae7-218">Here the dimension  `[Scenarios].[ScenarioPair]` is set to equal `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`.</span></span> <span data-ttu-id="15ae7-219">Il  `[Scenario.][ScenarioPair]` s’agit d’une dimension spéciale créée pour simplifier la création de rapports.</span><span class="sxs-lookup"><span data-stu-id="15ae7-219">The  `[Scenario.][ScenarioPair]` is a special dimension created to simplify report creation.</span></span> <span data-ttu-id="15ae7-220">Il a six valeurs correspondant à `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]` .</span><span class="sxs-lookup"><span data-stu-id="15ae7-220">It has six values corresponding to `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]`.</span></span> <span data-ttu-id="15ae7-221">Ainsi, au lieu d’utiliser une combinaison de 6 filtres pour définir un scénario, nous n’avons besoin que d’utiliser 1 filtre.</span><span class="sxs-lookup"><span data-stu-id="15ae7-221">So instead of using a combination of 6 filters to define a scenario, we only need to use 1 filter.</span></span> <span data-ttu-id="15ae7-222">Dans notre exemple, la valeur se traduit par le scénario dans lequel : le premier est serveur, le deuxième n’est pas le serveur, le premier est à l’intérieur, le deuxième est à l’intérieur, le premier type de connexion est câblé et le second type de connexion est câblé, qui est la définition exacte de «  `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` Serveur-Client-à-l’intérieur câblé ».</span><span class="sxs-lookup"><span data-stu-id="15ae7-222">In our example, the value  `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` translates to the scenario where: first is server, second is not server, first is inside, second is inside, first connection type is wired, and second connection type is wired, which is the exact definition of "Server-Client-Inside Wired".</span></span>

3. <span data-ttu-id="15ae7-223">Créez un ensemble de filtres par scénario.</span><span class="sxs-lookup"><span data-stu-id="15ae7-223">Create one filter set per scenario.</span></span> <span data-ttu-id="15ae7-224">Chaque ligne de la carte de performance, dans la figure, représente un scénario différent, qui sera un filtre différent (tandis que les dimensions et les mesures restent identiques).</span><span class="sxs-lookup"><span data-stu-id="15ae7-224">Each row in the scorecard, in the figure, represents a different scenario, which will be a different filter (while the dimensions and measurements stay the same).</span></span> 

4. <span data-ttu-id="15ae7-225">Parse the results from the AJAX calls and place them in the correct position of the table.</span><span class="sxs-lookup"><span data-stu-id="15ae7-225">Parse the results from the AJAX calls and place them in the correct position of the table.</span></span> <span data-ttu-id="15ae7-226">Étant donné qu’il s’agit principalement de manipulations HTML et JavaScript, nous n’allons pas entrer dans les détails ici.</span><span class="sxs-lookup"><span data-stu-id="15ae7-226">Since this is mostly HTML and JavaScript manipulation, we will not go into the details here.</span></span> <span data-ttu-id="15ae7-227">Au lieu de cela, le code est fourni dans l’Annexe A.</span><span class="sxs-lookup"><span data-stu-id="15ae7-227">Instead, the code is provided in Appendix A.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="15ae7-228">Si le partage des ressources d’origine croisée (CORS) est activé, les utilisateurs peuvent rencontrer des erreurs telles que « Aucun en-tête Access-Control-Allow-Origin » n’est présent sur la ressource demandée.</span><span class="sxs-lookup"><span data-stu-id="15ae7-228">If Cross-Origin Resource Sharing (CORS) is enabled, users may encounter errors like "No 'Access-Control-Allow-Origin' header is present on the requested resource.</span></span> <span data-ttu-id="15ae7-229">L’origine « null » n’est donc pas autorisée à accéder ».</span><span class="sxs-lookup"><span data-stu-id="15ae7-229">Origin 'null' is therefore not allowed access".</span></span> <span data-ttu-id="15ae7-230">Pour résoudre le problème, placez le fichier HTML sous le dossier où le portail est installé (par défaut, il doit `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)` l’être).</span><span class="sxs-lookup"><span data-stu-id="15ae7-230">To resolve the issue, place the HTML file under the folder where the Portal is installed (by default, it should be `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`.</span></span> <span data-ttu-id="15ae7-231">Accédez ensuite au code HTML via n’importe quel navigateur avec  `http://<servername>/cqd/<html_file_name>` l’URL.</span><span class="sxs-lookup"><span data-stu-id="15ae7-231">Then access the html through any browser with the URL  `http://<servername>/cqd/<html_file_name>`.</span></span> <span data-ttu-id="15ae7-232">(L’URL par défaut du tableau de bord CQD local est  `http://<servername>/cqd.` )</span><span class="sxs-lookup"><span data-stu-id="15ae7-232">(The default URL for local CQD dashboard is  `http://<servername>/cqd.`)</span></span> 

### <a name="appendix-a"></a><span data-ttu-id="15ae7-233">Annexe A</span><span class="sxs-lookup"><span data-stu-id="15ae7-233">Appendix A</span></span>

<span data-ttu-id="15ae7-234">Code HTML pour l’exemple 3 (exemple de carte de performance) :</span><span class="sxs-lookup"><span data-stu-id="15ae7-234">HTML code for Example 3 (Scorecard sample):</span></span>

```html
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <meta charset="utf-8" />
    <meta http-equiv='cache-control' content='no-cache'>
    <meta http-equiv='expires' content='0'>
    <meta http-equiv='pragma' content='no-cache'>
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <title>Scoreboard Sample</title>

    <style>
        .row {
            margin-right: -15px;
            margin-left: -15px;
            display: table-row;
        }
        .col-md-3 {
            width: 25%;
            display: table-cell;
        }
        .col-md-2 {
            width: 16.66666667%;
            display: table-cell;
        }
        .col-md-1 {
            width: 8.33333333%;
            display: table-cell;
        }

    </style>
</head>
<body>    

    <!-- Third party Libraries -->
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <table id="ScoreCardTable" style="margin:100px">
        <tr>
            <td width="250px" style="text-align: center; font-size: 24px; font-family: 'Segoe UI'; font-weight: lighter; color: white; background-color: #505050">
                <div style="margin:10px">Scoreboard Sample</div>
            </td>
            <td width="1200px">
                <div style="margin:10px;background-color:#D9D9D9" >
                    <div class="row" id="Header" style="font-size:24px;font-family:'Segoe UI';font-weight:lighter;color:white;background-color:#505050">
                        <div class="col-md-3">Poor Call %</div>
                        <div class="col-md-1">Month1</div>
                        <div class="col-md-1">Month2</div>
                        <div class="col-md-1">Month3</div>
                        <div class="col-md-1">Month4</div>
                        <div class="col-md-1">Month5</div>
                        <div class="col-md-1">Month6</div>
                    </div>                    
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Wired</div></div>
                    <div class="row" id="SS"><div class="col-md-3">Server-Server</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWI"><div class="col-md-3">Server-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWO"><div class="col-md-3">Server-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WWI"><div class="col-md-3">Client-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WIWO"><div class="col-md-3">Client-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Wireless</div></div>
                    <div class="row" id="SWFI"><div class="col-md-3">Server-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWFO"><div class="col-md-3">Server-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WFIWFI"><div class="col-md-3">Client-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WFOWFO"><div class="col-md-3">Client-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Mobile/Broadband</div></div>
                    <div class="row" id="SMP"><div class="col-md-3">Server-MobilePhone</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SMBB"><div class="col-md-3">Server-MobileBroadBand</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Lync Web App</div></div>
                    <div class="row" id="SLWA"><div class="col-md-3">Server-Client (inside &amp; outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                </div>
            </td>
        </tr>
        <tr>
            <td><br /></td>
        </tr>
    </table>

    <script>

        $(function () {
            var month_names_short = ['NAM', 'Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'];
            var currentMonth = '2015-3';

            //update the header with the month names
            var row = document.getElementById('Header');
            var numMonthsToShow = 6;
            for (var m = numMonthsToShow-1; m >= 0; m--) {
                var dateSplit = currentMonth.split('-');
                var monthInt = parseInt(dateSplit[1]);
                var yearInt = parseInt(dateSplit[0]);
                monthInt = monthInt - m;
                if (monthInt < 1)
                {
                    monthInt += 12;
                    yearInt--;
                }
                row.children[numMonthsToShow-m].innerHTML = month_names_short[monthInt];
            }

            var queries = [
            {
                Label: "Server-Server",
                ID: "SS",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]'}],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Server-Inside-wired",
                          "Value": "[1]&amp;[1]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: ""}
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]'}],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                 }
            },
            {
                Label: "Server-Client (inside)",
                ID: "SWI",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Client-Inside-wired",
                          "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (outside)",
                ID: "SWO",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Client-Outside-wired",
                          "Value": "[1]&amp;[0]&amp;[1]&amp;[0]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                 }
            },
            {
                Label: "Client-Client (inside)",
                ID: "WWI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Client-Inside-wired,Client-Inside-wired",
                            "Value": "[0]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            }
            ,
            {
                Label: "Client-Client (outside)",
                ID: "WIWO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": "Client-Outside-Wired,Client-Outside-Wired",
                          "Value": "[0]&amp;[0]&amp;[0]&amp;[0]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (inside)",
                ID: "SWFI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Server-Inside-wired,Client-Inside-wifi",
                            "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wifi]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (outside)",
                ID: "SWFO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                         {
                             "DataModelName": "[Scenarios].[ScenarioPair]",
                             "Caption": " Server-Inside-wired,Client-Outside-wifi",
                             "Value": "[1]&amp;[0]&amp;[1]&amp;[0]&amp;[Wired]&amp;[Wifi]",
                             "Operand": 0,
                             "UnionGroup": ""
                         },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Client-Client (inside)",
                ID: "WFIWFI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Client-Inside-Wifi,Client-Inside-Wifi",
                            "Value": "[0]&amp;[0]&amp;[1]&amp;[1]&amp;[Wifi]&amp;[Wifi]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Client-Client (outside)",
                ID: "WFOWFO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": "Client-Outside-Wifi,Client-Outside-Wifi",
                          "Value": "[0]&amp;[0]&amp;[0]&amp;[0]&amp;[Wifi]&amp;[Wifi]",
                          "Operand": 0,
                          "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-MobilePhone",
                ID: "SMP",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second User Agent].[User Agent Type]","Caption": "AndroidLync | iPhoneLync | WPLync","Value": "[AndroidLync],[iPhoneLync],[WPLync]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-MobileBroadBand",
                ID: "SMBB",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[Second Network Connection Type].[Network Connection Detail]","Caption": "MobileBB","Value": "[MobileBB]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second Is Server].[Agent]","Caption": "Client ","Value": "[0]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 }                       
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-LWA",
                ID: "SLWA",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second User Agent].[User Agent Type]","Caption": "LWA","Value": "[LWA]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 }                       
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            }

            ];

            //get the overall corpnet data
            for (var i = 0; i < queries.length; i++) {
                $.ajax({

                    url: 'http://localhost/QoEDataService/RunQuery',
                    data: JSON.stringify(queries[i].Query),
                    type: 'POST',
                    async: false,
                    withCredentials: true,
                    contentType: 'application/json;charset=utf-8',
                    success: function (data) {

                        //find the table row corresponding to the name of this query
                        var row = document.getElementById(queries[i].ID);

                        //update the values for each month
                        for (var m = 0; m < data.DataResult.length; m++)
                        {
                            row.children[m + 1].innerHTML = data.DataResult[m][1].toFixed(2).toString();
                        }

                    },
                    error: function (error) {
                        var row = document.getElementById(queries[i].ID);
                        row.children[1].innerHTML = 'error';
                    }
                });
            }
        });
    </script>
</body>
</html>
```
