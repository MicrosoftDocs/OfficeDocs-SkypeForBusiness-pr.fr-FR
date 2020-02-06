---
title: Exemples de développement du tableau de bord de qualité des appels
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8ca9bf7a-2d6f-48d5-a821-531009726525
description: 'Résumé : examinez un didacticiel et des exemples de développement pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 22b0e44ca3bf2e80d8d2674d0af1e6a8f157dc23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816873"
---
# <a name="cqd-development-samples"></a><span data-ttu-id="67898-104">Exemples de développement du tableau de bord de qualité des appels</span><span class="sxs-lookup"><span data-stu-id="67898-104">CQD Development Samples</span></span>

<span data-ttu-id="67898-105">**Résumé :** Consulter un didacticiel et des exemples de développement pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="67898-105">**Summary:** Review a tutorial and development samples for Call Quality Dashboard.</span></span> <span data-ttu-id="67898-106">Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="67898-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="67898-107">Cet article propose un didacticiel et des exemples sur le développement du tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="67898-107">This article provides a tutorial and samples on development for Call Quality Dashboard (CQD).</span></span>

## <a name="call-quality-dashboard-cqd-development-samples"></a><span data-ttu-id="67898-108">Exemples de développement du tableau de bord de qualité des appels</span><span class="sxs-lookup"><span data-stu-id="67898-108">Call Quality Dashboard (CQD) Development Samples</span></span>

<span data-ttu-id="67898-109">Didacticiel : créez une présentation de rapport personnalisé à l’aide des API du service de données et du service de référentiel du tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="67898-109">Tutorial: Building Customized Report Presentation using the CQD Data Service and Repository Service API's.</span></span>

### <a name="introduction-to-cqd"></a><span data-ttu-id="67898-110">Présentation du tableau de bord de qualité des appels</span><span class="sxs-lookup"><span data-stu-id="67898-110">Introduction to CQD</span></span>

<span data-ttu-id="67898-111">Le tableau de bord de qualité des appels contient des informations agrégées, accessibles rapidement, sur la qualité des appels pour les déploiements Skype Entreprise Server locaux.</span><span class="sxs-lookup"><span data-stu-id="67898-111">CQD offers quick and easy access to aggregated call quality information for on-premise Skype for Business Server deployments.</span></span> <span data-ttu-id="67898-112">Le tableau de bord de qualité des appels comprend trois éléments : la base de données d’archivage QoE, le cube et le portail.</span><span class="sxs-lookup"><span data-stu-id="67898-112">CQD consists of three components: the QoE Archive database, the Cube, and the Portal.</span></span> <span data-ttu-id="67898-113">Le portail, qui est la principale couche de présentation, peut également être divisé en trois composants :</span><span class="sxs-lookup"><span data-stu-id="67898-113">The Portal is the main presentation layer and can be further divided into the following three components:</span></span>

1. <span data-ttu-id="67898-114">Service de données accessible aux utilisateurs authentifiés via l' [API de données du tableau de bord de qualité des appels (bord) dans Skype entreprise Server](data-api.md).</span><span class="sxs-lookup"><span data-stu-id="67898-114">Data Service, which is accessible for authenticated users through the [Data API for Call Quality Dashboard (CQD) in Skype for Business Server](data-api.md).</span></span>

2. <span data-ttu-id="67898-115">Service de référentiel qui est accessible pour les utilisateurs authentifiés via l' [API du référentiel pour le tableau de bord de qualité des appels (bord) dans Skype entreprise Server](repository-api.md).</span><span class="sxs-lookup"><span data-stu-id="67898-115">Repository Service, which is accessible for authenticated users through the [Repository API for Call Quality Dashboard (CQD) in Skype for Business Server](repository-api.md).</span></span>

3. <span data-ttu-id="67898-116">Portail Web, qui est l’interface basée sur HTML5 que bord les utilisateurs voient et interagissent.</span><span class="sxs-lookup"><span data-stu-id="67898-116">Web portal, which is the HTML5 based interface that CQD users see and interact with.</span></span> <span data-ttu-id="67898-117">Cette opération est accessible pour les utilisateurs authentifiés.</span><span class="sxs-lookup"><span data-stu-id="67898-117">This is accessible for authenticated users.</span></span>

<span data-ttu-id="67898-118">Les rapports figurant sur le portail Web sont regroupés en « ensembles de rapports ».</span><span class="sxs-lookup"><span data-stu-id="67898-118">The reports shown on the web portal are grouped into "report sets".</span></span> <span data-ttu-id="67898-119">L’illustration représente un ensemble de rapports contenant deux rapports.</span><span class="sxs-lookup"><span data-stu-id="67898-119">The figure shows a report set with two reports.</span></span> <span data-ttu-id="67898-120">Chaque rapport dans le tableau de bord ci-dessous indique le nombre d’appels satisfaisants, le nombre d’appels insatisfaisants et le pourcentage d’appels insatisfaisants sur plusieurs mois, avec différents filtres appliqués.</span><span class="sxs-lookup"><span data-stu-id="67898-120">Each report in this dashboard below shows query results on number of good calls, poor calls and poor call percentage for several months, with various filters applied.</span></span> 

![Exemple de rapport du tableau de bord de qualité des appels](../../media/9e0723f7-f850-4d11-9ecd-7e8e013a8bed.png)

<span data-ttu-id="67898-p106">Le tableau de bord de qualité des appels est créé après la Méthodologie de qualité des appels (CQM). L’ensemble de rapports par défaut est conçu pour respecter les flux d’analyse de la méthodologie de qualité des appels. Les utilisateurs ont également la possibilité de modifier ou de créer des rapports personnalisés selon leurs besoins. Toutefois, comme les données peuvent être visualisées de différentes façons, l’affichage des données du tableau de bord de qualité des appels ne répond peut-être pas intégralement aux besoins de chaque utilisateur. En pareils cas, un utilisateur peut tirer parti des API de données et des API de référentiel pour créer des pages de rapport. Dans ce didacticiel, nous en étudierons différents exemples.</span><span class="sxs-lookup"><span data-stu-id="67898-p106">CQD is created following the Call Quality Methodology (CQM), so the default set of reports is designed to align with the investigation flow introduced by CQM. Users also have the flexibility to edit or create custom reports to meet their needs. However, since there are multiple ways to visualize the data, the visualization provided by CQD may not fully address the needs of every user. In such situations, a user can leverage the Data APIs and Repository APIs to create custom report pages. We will go through a series of examples in this tutorial.</span></span>

### <a name="how-the-dashboard-consumes-the-data-service"></a><span data-ttu-id="67898-127">Utilisation du service de données dans le tableau de bord</span><span class="sxs-lookup"><span data-stu-id="67898-127">How the dashboard consumes the data service</span></span>

<span data-ttu-id="67898-128">Lorsque vous naviguez jusqu’à la page d’accueil http://localhost/cqd)bord (par exemple, le jeu de rapports et les rapports correspondants pour un utilisateur authentifié et autorisé sont récupérés auprès du service de référentiel.</span><span class="sxs-lookup"><span data-stu-id="67898-128">When navigating to the CQD homepage (e.g. http://localhost/cqd), the report set and corresponding reports for an authenticated and authorized user will be retrieved from the Repository Service.</span></span> <span data-ttu-id="67898-129">Une URL complète est construite à partir de l’ID du jeu de rapports et de l’année-mois (ID du jeu de rapports est le nombre entier après la section'/#/'dans l’URL, et par défaut, l’année en cours est ajoutée à la fin de l’ID du jeu de rapports après la barre oblique).</span><span class="sxs-lookup"><span data-stu-id="67898-129">A full URL will be constructed from the report-set ID and the year-month (report-set ID is the integer number after '/#/' section in URL, and by default the current year-month is appended at the end of the report-set ID after the slash).</span></span> <span data-ttu-id="67898-130">Les définitions de rapport sont stockées au format JSON et extraites à partir du service de référentiel, puis transmises au service de données.</span><span class="sxs-lookup"><span data-stu-id="67898-130">The report definitions are stored in JSON format and when retrieved from the Repository Service, will then be used as input to the Data Service.</span></span> <span data-ttu-id="67898-131">Le service de données génère des requêtes avec des expressions Multi-Dimension (MDX) basé sur les valeurs transmises, puis il les exécute sur le cube afin d’extraire les données pour chaque rapport.</span><span class="sxs-lookup"><span data-stu-id="67898-131">The Data Service generates Multi-Dimension expressions (MDX) queries based on the input and then run these MDX queries against the Cube to retrieve data for each report.</span></span> 

### <a name="building-customized-reports"></a><span data-ttu-id="67898-132">Création de rapports personnalisés</span><span class="sxs-lookup"><span data-stu-id="67898-132">Building customized reports</span></span>

<span data-ttu-id="67898-p108">La personnalisation des rapports de tableau de bord de qualité des appels est très flexible, mais dans certaines situations, les utilisateurs peuvent souhaiter agréger des données de différents rapports créés dans le tableau de bord de qualité des appels. Par exemple, il peut être nécessaire de créer un rapport qui indique les pourcentages d’appels insatisfaisants de toutes les combinaisons d’appels filaires dans un tableau (dont le résultat s’apparente aux données de la figure) :</span><span class="sxs-lookup"><span data-stu-id="67898-p108">CQD already has a lot of flexibility in customizing reports, but there could be situations where users may want to aggregate data across multiple reports created in CQD. For example, there could be a need to create a report that shows the poor call percentages of all possible combinations of wired calls in a table (a result like the figure):</span></span>

![Table du tableau de bord de qualité des appels](../../media/ef19d535-5da6-44a9-91f6-1ed3f30b96f1.png)

<span data-ttu-id="67898-p109">À l’aide du portail du tableau de bord de qualité des appels, un utilisateur devrait accéder à différents rapports pour extraire et enregistrer le pourcentage d’appels insatisfaisants pour chacun d’eux, ce qui peut être fastidieux si les données à recueillir sont nombreuses. L’API de données permet aux utilisateurs de créer des programmes pour effectuer ces opérations, en extrayant les données à partir du service de données (à l’aide d’appels AJAX, par ex.).</span><span class="sxs-lookup"><span data-stu-id="67898-p109">Using the Portal provided by CQD, a user would have to navigate to multiple reports to extract and record the poor call % for each one, which can be laborious if there are many data points that need to be collected. The Data APIs provide users with a programmatic way to accomplish this, by retrieving data from the Data Service (e.g. via AJAX calls).</span></span> 

 <span data-ttu-id="67898-138">**Exemple 1 : rapport simple**</span><span class="sxs-lookup"><span data-stu-id="67898-138">**Example 1: Simple report sample**</span></span>

<span data-ttu-id="67898-p110">Commençons par un exemple simple. Si nous voulons afficher le nombre de flux Audio Good Stream et Audio Bad Stream de février 2015 dans une page HTML, comme sur l’illustration :</span><span class="sxs-lookup"><span data-stu-id="67898-p110">Let us take a simple example first. If we want to show the Audio Good Stream and the Audio Bad stream count of February 2015 on an HTML page like the figure:</span></span>

![Exemple de rapport du tableau de bord de qualité des appels](../../media/f0e4e61f-1fa5-4d69-b192-f19e9612bf1c.png)

<span data-ttu-id="67898-p111">Nous devons envoyer un appel au service de données avec les paramètres appropriés et afficher les résultats de la requête dans un tableau HTML. Vous trouverez ci-dessous un exemple de code JavaScript :</span><span class="sxs-lookup"><span data-stu-id="67898-p111">What we need is to send a call to the Data Service with the proper parameters, and show the query results in an HTML table. The following is a sample of the JavaScript code:</span></span>

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

<span data-ttu-id="67898-144">Cet exemple peut être divisé en trois étapes :</span><span class="sxs-lookup"><span data-stu-id="67898-144">This example can be further deconstructed into three steps:</span></span>

1. <span data-ttu-id="67898-145">Construisez la requête (dans l’exemple, elle est définie dans la variable’requête').</span><span class="sxs-lookup"><span data-stu-id="67898-145">Construct the query (in the example this is defined in the variable 'query').</span></span> <span data-ttu-id="67898-146">La requête est définie comme objet JSON, qui inclut les données suivantes :</span><span class="sxs-lookup"><span data-stu-id="67898-146">The query is defined as a JSON object, which includes the following data:</span></span>

   <span data-ttu-id="67898-147">a.</span><span class="sxs-lookup"><span data-stu-id="67898-147">a.</span></span> <span data-ttu-id="67898-148">Zéro, une ou plusieurs dimensions.</span><span class="sxs-lookup"><span data-stu-id="67898-148">Zero or more dimensions.</span></span> <span data-ttu-id="67898-149">Chaque dimension est indiquée par un objet DataModelName.</span><span class="sxs-lookup"><span data-stu-id="67898-149">Each dimension is indicated by a DataModelName.</span></span>

   <span data-ttu-id="67898-150">b.</span><span class="sxs-lookup"><span data-stu-id="67898-150">b.</span></span> <span data-ttu-id="67898-151">Zéro, un ou plusieurs filtres.</span><span class="sxs-lookup"><span data-stu-id="67898-151">Zero or more filters.</span></span> <span data-ttu-id="67898-152">Chaque filtre possède :</span><span class="sxs-lookup"><span data-stu-id="67898-152">Each filter has:</span></span>

   - <span data-ttu-id="67898-153">DataModelName (la dimension qui définit l’ensemble de filtres)</span><span class="sxs-lookup"><span data-stu-id="67898-153">DataModelName (the dimension that will have the filter set).</span></span>

   - <span data-ttu-id="67898-154">Valeur (valeur comparée par l’opérande)</span><span class="sxs-lookup"><span data-stu-id="67898-154">Value (the value that will be compared by the operand).</span></span>

   - <span data-ttu-id="67898-155">Opérande (type de comparaison, 0 signifie "égal").</span><span class="sxs-lookup"><span data-stu-id="67898-155">Operand (comparison type, 0 means "Equal").</span></span>

     <span data-ttu-id="67898-156">c.</span><span class="sxs-lookup"><span data-stu-id="67898-156">c.</span></span> <span data-ttu-id="67898-157">Une ou plusieurs mesures</span><span class="sxs-lookup"><span data-stu-id="67898-157">One or more measurements.</span></span>

2. <span data-ttu-id="67898-158">Envoyez la requête au service de données par le biais de l’appel AJAX.</span><span class="sxs-lookup"><span data-stu-id="67898-158">Send the query to Data Service via AJAX call.</span></span> <span data-ttu-id="67898-159">Les paramètres de demande ci-dessous doivent être indiqués :</span><span class="sxs-lookup"><span data-stu-id="67898-159">The following request parameters need to be provided:</span></span>

   <span data-ttu-id="67898-160">a.</span><span class="sxs-lookup"><span data-stu-id="67898-160">a.</span></span> <span data-ttu-id="67898-161">url (qui doit être http://[NomServeur]/QoEDataService/RunQuery)</span><span class="sxs-lookup"><span data-stu-id="67898-161">url (which should be http://[ServerName]/QoEDataService/RunQuery).</span></span>

   <span data-ttu-id="67898-162">b.</span><span class="sxs-lookup"><span data-stu-id="67898-162">b.</span></span> <span data-ttu-id="67898-163">Data (il s’agit de la représentation sous forme de chaîne de l’objet JSON défini dans la variable « requête »).</span><span class="sxs-lookup"><span data-stu-id="67898-163">data (this is the string representation of the JSON object defined in the 'query' variable).</span></span> <span data-ttu-id="67898-164">Le service de données renverra les résultats d’une requête dans un paramètre de la fonction de rappel pour que l’opération réussisse.</span><span class="sxs-lookup"><span data-stu-id="67898-164">Data Service will return the query results as a parameter of the call back function for success.</span></span>

   <span data-ttu-id="67898-165">c.</span><span class="sxs-lookup"><span data-stu-id="67898-165">c.</span></span> <span data-ttu-id="67898-166">type (pour QoEDataService, RunQuery n’accepte que les demandes POST).</span><span class="sxs-lookup"><span data-stu-id="67898-166">type (for QoEDataService, RunQuery only accepts 'POST' requests).</span></span>

   <span data-ttu-id="67898-167">d.</span><span class="sxs-lookup"><span data-stu-id="67898-167">d.</span></span> <span data-ttu-id="67898-168">async (indicateur signalant si l’appel AJAX doit être synchrone ou asynchrone)</span><span class="sxs-lookup"><span data-stu-id="67898-168">async (a flag indicating whether the AJAX call should be synchronous or asynchronous).</span></span>

   <span data-ttu-id="67898-169">e.</span><span class="sxs-lookup"><span data-stu-id="67898-169">e.</span></span> <span data-ttu-id="67898-170">contentType (doit être « application/JSON »).</span><span class="sxs-lookup"><span data-stu-id="67898-170">contentType (should be "application/json").</span></span>

   <span data-ttu-id="67898-171">touche.</span><span class="sxs-lookup"><span data-stu-id="67898-171">f.</span></span> <span data-ttu-id="67898-172">success (fonction de rappel lorsque l’appel AJAX réussit)</span><span class="sxs-lookup"><span data-stu-id="67898-172">success (call-back function for when the AJAX call finishes successfully).</span></span>

   <span data-ttu-id="67898-173">grand.</span><span class="sxs-lookup"><span data-stu-id="67898-173">g.</span></span> <span data-ttu-id="67898-174">error (fonction de gestion des erreurs lorsque l’appel AJAX échoue)</span><span class="sxs-lookup"><span data-stu-id="67898-174">error (error handling function for when AJAX call fails).</span></span>

3. <span data-ttu-id="67898-175">Placez les données dans les éléments div du code HTML (dans l’exemple de code, cette opération est effectuée par le biais de l’appel de fonction anonyme une fois que la demande AJAX a réussi).</span><span class="sxs-lookup"><span data-stu-id="67898-175">Put data into div elements in the HTML (in the example in the code, this is done via the anonymous function call after the AJAX request is completed successfully).</span></span>

<span data-ttu-id="67898-p124">L’insertion de code JavaScript dans une page HTML aboutit à un rapport comme celui de la figure. Le code HTML complet est le suivant :</span><span class="sxs-lookup"><span data-stu-id="67898-p124">Enclosing the JavaScript code into an HTML page, and the page will show a report like the one shown in the figure. The full html is as follows:</span></span>

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

<span data-ttu-id="67898-p125">Jusque-là, le rapport est toujours très simple. L’utilisateur peut ajouter d’autres mesures, dimensions ou filtres pour personnaliser ce rapport. Par exemple, si vous souhaitez afficher le pourcentage d’appels médiocres du partage d’application, il est nécessaire d’ajouter une nouvelle mesure s’y rapportant. Pour afficher tous les appels TCP et les appels UDP, vous devez ajouter une nouvelle dimension relative au type de transport. Si vous souhaitez afficher le nombre d’appels insatisfaisants dans un bâtiment spécifique, un nouveau filtre doit être ajouté pour sélectionner les appels à destination de ce bâtiment et en provenance de celui-ci.</span><span class="sxs-lookup"><span data-stu-id="67898-p125">So far, the report is still very simple. The user can add more measurements, dimensions, or filters to customize the report. For example, if you want to show AppSharing poor call percentage, then a new measurement regarding AppSharing needs to be added. If you want to show all TCP calls v.s. UDP calls, a new dimension regarding transportation type should be added. If you want to show the number of poor calls within a specific building, then a new filter should be added to select the calls to and from that building.</span></span>

 <span data-ttu-id="67898-184">**Exemple 2 : définition de rapport**</span><span class="sxs-lookup"><span data-stu-id="67898-184">**Example 2: Report definition sample**</span></span>

<span data-ttu-id="67898-p126">Il peut être difficile de déterminer comment rédiger la liste complète des mesures/dimensions/filtres et leurs valeurs correspondantes lors de la construction d’une requête. Dans ce cas, vous pouvez accéder au portail, créer un rapport à l’aide de l’éditeur de rapport et afficher la chaîne JSON de la définition de rapport, puis copier cette définition dans un rapport personnalisé.</span><span class="sxs-lookup"><span data-stu-id="67898-p126">It might be difficult for someone to figure out how to write the full list of measurements/dimensions/filters and their corresponding values when constructing a query. In this case, you can go to the Portal, build a report using the report editor, and view the JSON string of the report definition, and then copy the definition into a custom report.</span></span> 

<span data-ttu-id="67898-p127">Dans cet exemple, nous allons créer une page web, comme celle présentée sur la figure suivante, dans laquelle un utilisateur peut entrer la référence d’un ensemble de rapports (ou d’un rapport) et afficher la définition de l’ensemble de rapports ou du rapport dans la page web. L’utilisateur peut alors insérer la chaîne JSON dans du code similaire à celui de l’exemple 1 et construire un rapport personnalisé en fonction des besoins.</span><span class="sxs-lookup"><span data-stu-id="67898-p127">In this example, we will create a web page like the one shown in the figure where a user can enter the ID of any existing report set (or report) and show the definition of the report set or report on the web page. The user can then plug the JSON string of each report into code similar to the one shown in Example 1 and construct any customized report the user desires.</span></span> 

![Exemple de tableau de bord de qualité des appels](../../media/01c45c23-c4d2-47b8-819f-0888cf71260f.png)

<span data-ttu-id="67898-p128">Pour créer l’outil visionneuse de définition de rapport, nous devons envoyer des appels au service de référentiel pour extraire des représentations de chaîne JSON des définitions de chaque report-set souhaité. L’API de référentiel renverra la définition report-set basée sur un ID d’ensemble de rapports donné.</span><span class="sxs-lookup"><span data-stu-id="67898-p128">To create the report definition viewer tool, we need to send calls to Repository Service to retrieve the JSON string representations of the definitions of every report-set we want. The Repository API will return report-set definition based on a given report set ID.</span></span> 

<span data-ttu-id="67898-192">Un exemple rapide est le suivant : le code contient un bloc qui est un exemple simple d’envoyer une requête au service du référentiel pour obtenir le contenu d’un élément de référentiel basé sur son identificateur.</span><span class="sxs-lookup"><span data-stu-id="67898-192">A quick example is as follows, the code contains a block that is a simple example to send a query to the Repository service to get the contents of a repository item based on its identifier.</span></span> <span data-ttu-id="67898-193">La partie suivante du code (méthode processReportSetData) envoie des appels AJAX pour obtenir la définition de chaque rapport dans ce jeu de rapports.</span><span class="sxs-lookup"><span data-stu-id="67898-193">And the next portion of code (processReportSetData method) is sending AJAX calls to get the definition of each report within that report set.</span></span> <span data-ttu-id="67898-194">Dans la mesure où l’ID du portail Web bord est l’ID d’un ensemble de rapports, l’appel AJAX renvoie un élément de jeu de rapports.</span><span class="sxs-lookup"><span data-stu-id="67898-194">Since the ID in the CQD web portal is the ID of a report set, the AJAX call will return a report set item.</span></span> <span data-ttu-id="67898-195">Vous trouverez plus d’informations sur l’API du référentiel et plus précisément sur GetItems dans la section [obtenir des éléments](get-items.md).</span><span class="sxs-lookup"><span data-stu-id="67898-195">More detail on the Repository API and specifically, GetItems, can be found in the [Get Items](get-items.md).</span></span> 

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

<span data-ttu-id="67898-196">Les éléments ci-dessus aboutiront à une page Web semblable à celle figurant dans la figure (sans la définition de rapport lors de la visite initiale).</span><span class="sxs-lookup"><span data-stu-id="67898-196">The above will result in a web page like the one in the figure (without the report definition upon initial visit).</span></span> <span data-ttu-id="67898-197">Obtenez l’ID du jeu de rapports sur le portail bord (il est après'/#/'connexion bord URL du portail (par exemple,</span><span class="sxs-lookup"><span data-stu-id="67898-197">Get the report set ID from CQD portal (it is after '/#/' sign in CQD portal URL (E.g.</span></span> <span data-ttu-id="67898-198">dans la première figure, l’ID du jeu de rapports est 3024) et il est placé dans la section entrée de cette page Web.</span><span class="sxs-lookup"><span data-stu-id="67898-198">in the first figure the report set ID is 3024), and put this report set ID into the input section of this web page.</span></span> <span data-ttu-id="67898-199">Appuyez sur le bouton « charger » et observez la définition complète (mesures, dimensions, filtres listes) du jeu de rapports.</span><span class="sxs-lookup"><span data-stu-id="67898-199">Press the "load" button and see the full definition (measurements, dimensions, filters lists) of the report set.</span></span>

<span data-ttu-id="67898-200">En résumé, afin d’obtenir rapidement la définition complète d’un rapport/ensemble de rapports.</span><span class="sxs-lookup"><span data-stu-id="67898-200">In summary, in order to quickly get the full definition of a report/report set.</span></span> <span data-ttu-id="67898-201">Les étapes à suivre sont :</span><span class="sxs-lookup"><span data-stu-id="67898-201">The steps are:</span></span>

1. <span data-ttu-id="67898-202">Accédez au portail et servez-vous de l’éditeur de requête pour personnaliser un rapport (cliquez sur le bouton « modifier » au-dessus d’un rapport pour modifier, ajouter ou supprimer des mesures/dimensions/filtres, puis enregistrez le rapport).</span><span class="sxs-lookup"><span data-stu-id="67898-202">Go to the Portal and use the query editor to customize a report (click the "Edit" button above a report to edit, add, remove measurements/dimensions/filters, and then save the report).</span></span>

2. <span data-ttu-id="67898-203">Obtenez l’ID du jeu de rapports à partir de l’URL (il s’agit de l’URL de connexion de type'/#/').</span><span class="sxs-lookup"><span data-stu-id="67898-203">Get the report set ID from URL (the integer after '/#/' sign in URL).</span></span>

3. <span data-ttu-id="67898-204">Lancez cette page web de définition de rapport créée lors de l’exemple 2, entrez l’ID de l’ensemble de rapports, puis extrayez la définition complète d’un ensemble de rapports (à utiliser dans les appels de l’API de données).</span><span class="sxs-lookup"><span data-stu-id="67898-204">Launch this Report Definition web page created in Example 2, and enter the report set ID and retrieve the full definition of a report set (to use in Data API calls).</span></span>

   <span data-ttu-id="67898-205">**Exemple 3 : carte de performance**</span><span class="sxs-lookup"><span data-stu-id="67898-205">**Example 3: Scorecard sample**</span></span>

<span data-ttu-id="67898-p132">Voici une tâche plus compliquée. Que faire si nous voulons créer une page web comme celle qui est présentée ? Nous devons mettre à jour l’exemple 1 (à l’aide de de la page web générée lors de l’exemple 2 pour extraire la définition complète d’un rapport) afin de traiter davantage de données.</span><span class="sxs-lookup"><span data-stu-id="67898-p132">Time for a more complicated task. What if we want to create a web page like the figure? We need to update Example 1, (with the help of the web page generated in Example 2 to retrieve the full definition of any report) so that we can handle larger amount of data.</span></span>

<span data-ttu-id="67898-p133">Dans ce cas, nous devons mettre à jour la liste de mesures et de dimensions. Pour déterminer comment ajouter/modifier une mesure et/ou une dimension, suivez les instructions de l’exemple 2 et extrayez la définition complète du rapport, dont les listes complètes de mesures et de dimensions. Insérez cette définition complète dans l’exemple de code.</span><span class="sxs-lookup"><span data-stu-id="67898-p133">In this case, we need to update the measurement and dimension list. The way to figure out how to add/edit a measurement and/or a dimension is to follow the instructions in Example 2, and retrieve the full report definition, including the full measurement and dimension lists. Plug the full report definition into the sample code.</span></span> 

<span data-ttu-id="67898-212">Voici la procédure détaillée permettant d’accéder à la page de la carte de performance dans la figure de l’exemple 1 :</span><span class="sxs-lookup"><span data-stu-id="67898-212">Here are the detailed steps to get to the scorecard page in the figure from the sample provided in Example 1:</span></span>

1. <span data-ttu-id="67898-213">Mettre à jour les mesures dans la variable « `[Measures].[Audio Good Streams JPDR Count]` requête `[Measures].[Audio Poor Streams JPDR Count]` » `[Measures].[AudioPoorJPDRPercentage]`de et à.</span><span class="sxs-lookup"><span data-stu-id="67898-213">Update Measurements in the 'query' variable from  `[Measures].[Audio Good Streams JPDR Count]` and `[Measures].[Audio Poor Streams JPDR Count]` to `[Measures].[AudioPoorJPDRPercentage]`.</span></span> 

2. <span data-ttu-id="67898-214">Mettez à jour les filtres.</span><span class="sxs-lookup"><span data-stu-id="67898-214">Update the filters.</span></span> <span data-ttu-id="67898-215">Dans l’exemple 1, les données JSON pour les filtres ont un filtre, qui est défini `[StartDate].[Month]`sur la dimension.</span><span class="sxs-lookup"><span data-stu-id="67898-215">The JSON data for Filters in Example 1 has one filter, which is set on the dimension  `[StartDate].[Month]`.</span></span> <span data-ttu-id="67898-216">Dans la mesure où les filtres sont regroupés dans un tableau JSON, il est possible d’ajouter des dimensions à la cette liste.</span><span class="sxs-lookup"><span data-stu-id="67898-216">Since Filters is a JSON array, additional dimensions can be added to the list of filters.</span></span> <span data-ttu-id="67898-217">Par exemple, pour obtenir le client serveur dans les appels filaires pour le « currentMonth », nous devons disposer des filtres suivants :</span><span class="sxs-lookup"><span data-stu-id="67898-217">For example, to get the server-client inside wired calls for the "currentMonth", we should have the following filters:</span></span>

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

   <span data-ttu-id="67898-218">Ici, la `[Scenarios].[ScenarioPair]` dimension est définie sur `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`égal.</span><span class="sxs-lookup"><span data-stu-id="67898-218">Here the dimension  `[Scenarios].[ScenarioPair]` is set to equal `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`.</span></span> <span data-ttu-id="67898-219">Il `[Scenario.][ScenarioPair]` s’agit d’une dimension spéciale créée pour simplifier la création de rapports.</span><span class="sxs-lookup"><span data-stu-id="67898-219">The  `[Scenario.][ScenarioPair]` is a special dimension created to simplify report creation.</span></span> <span data-ttu-id="67898-220">Il a six valeurs correspondant à `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]`.</span><span class="sxs-lookup"><span data-stu-id="67898-220">It has six values corresponding to `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]`.</span></span> <span data-ttu-id="67898-221">Par exemple, il suffit d’utiliser un filtre au lieu d’une combinaison de six filtres.</span><span class="sxs-lookup"><span data-stu-id="67898-221">So instead of using a combination of 6 filters to define a scenario, we only need to use 1 filter.</span></span> <span data-ttu-id="67898-222">Dans notre exemple, la valeur `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` se TransType vers le scénario dans lequel : First est Server, second n’est pas serveur, le premier est l’intérieur, le second est l’intérieur, le premier type de connexion est filaire et le second type de connexion est câblé, qui correspond à la définition exacte de « serveur-client-intégré ».</span><span class="sxs-lookup"><span data-stu-id="67898-222">In our example, the value  `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` translates to the scenario where: first is server, second is not server, first is inside, second is inside, first connection type is wired, and second connection type is wired, which is the exact definition of "Server-Client-Inside Wired".</span></span>

3. <span data-ttu-id="67898-p136">Créez un ensemble de filtres par scénario. Sur la figure, chaque ligne de la carte de performance représente un autre scénario, qui sera un filtre différent (alors que les dimensions et les mesures sont identiques).</span><span class="sxs-lookup"><span data-stu-id="67898-p136">Create one filter set per scenario. Each row in the scorecard, in the figure, represents a different scenario, which will be a different filter (while the dimensions and measurements stay the same).</span></span> 

4. <span data-ttu-id="67898-p137">Analysez les résultats des appels AJAX pour les placer à la position appropriée dans le tableau. Comme il s’agit principalement de manipulation de code HTML et JavaScript, nous n’entrerons pas ici dans les détails. Le code est disponible à l’annexe A.</span><span class="sxs-lookup"><span data-stu-id="67898-p137">Parse the results from the AJAX calls and place them in the correct position of the table. Since this is mostly HTML and JavaScript manipulation, we will not go into the details here. Instead, the code is provided in Appendix A.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="67898-228">Si le partage de ressources à l’origine (CORS) est activé, les utilisateurs peuvent rencontrer des erreurs telles que « aucun » en-tête de contrôle d’accès</span><span class="sxs-lookup"><span data-stu-id="67898-228">If Cross-Origin Resource Sharing (CORS) is enabled, users may encounter errors like "No 'Access-Control-Allow-Origin' header is present on the requested resource.</span></span> <span data-ttu-id="67898-229">L’origine « NULL » n’est donc pas autorisée.</span><span class="sxs-lookup"><span data-stu-id="67898-229">Origin 'null' is therefore not allowed access".</span></span> <span data-ttu-id="67898-230">Pour résoudre ce problème, placez le fichier HTML sous le dossier dans lequel le portail est installé (par défaut, il devrait `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`être.</span><span class="sxs-lookup"><span data-stu-id="67898-230">To resolve the issue, place the HTML file under the folder where the Portal is installed (by default, it should be `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`.</span></span> <span data-ttu-id="67898-231">Accédez ensuite au code HTML par le biais d’un `http://<servername>/cqd/<html_file_name>`navigateur doté de l’URL.</span><span class="sxs-lookup"><span data-stu-id="67898-231">Then access the html through any browser with the URL  `http://<servername>/cqd/<html_file_name>`.</span></span> <span data-ttu-id="67898-232">(L’URL par défaut du tableau de bord `http://<servername>/cqd.`de bord local est)</span><span class="sxs-lookup"><span data-stu-id="67898-232">(The default URL for local CQD dashboard is  `http://<servername>/cqd.`)</span></span> 

### <a name="appendix-a"></a><span data-ttu-id="67898-233">Annexe A</span><span class="sxs-lookup"><span data-stu-id="67898-233">Appendix A</span></span>

<span data-ttu-id="67898-234">Code HTML de l’exemple 3 (carte de performance) :</span><span class="sxs-lookup"><span data-stu-id="67898-234">HTML code for Example 3 (Scorecard sample):</span></span>

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
