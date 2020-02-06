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
# <a name="cqd-development-samples"></a>Exemples de développement du tableau de bord de qualité des appels

**Résumé :** Consulter un didacticiel et des exemples de développement pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.

Cet article propose un didacticiel et des exemples sur le développement du tableau de bord de qualité des appels.

## <a name="call-quality-dashboard-cqd-development-samples"></a>Exemples de développement du tableau de bord de qualité des appels

Didacticiel : créez une présentation de rapport personnalisé à l’aide des API du service de données et du service de référentiel du tableau de bord de qualité des appels.

### <a name="introduction-to-cqd"></a>Présentation du tableau de bord de qualité des appels

Le tableau de bord de qualité des appels contient des informations agrégées, accessibles rapidement, sur la qualité des appels pour les déploiements Skype Entreprise Server locaux. Le tableau de bord de qualité des appels comprend trois éléments : la base de données d’archivage QoE, le cube et le portail. Le portail, qui est la principale couche de présentation, peut également être divisé en trois composants :

1. Service de données accessible aux utilisateurs authentifiés via l' [API de données du tableau de bord de qualité des appels (bord) dans Skype entreprise Server](data-api.md).

2. Service de référentiel qui est accessible pour les utilisateurs authentifiés via l' [API du référentiel pour le tableau de bord de qualité des appels (bord) dans Skype entreprise Server](repository-api.md).

3. Portail Web, qui est l’interface basée sur HTML5 que bord les utilisateurs voient et interagissent. Cette opération est accessible pour les utilisateurs authentifiés.

Les rapports figurant sur le portail Web sont regroupés en « ensembles de rapports ». L’illustration représente un ensemble de rapports contenant deux rapports. Chaque rapport dans le tableau de bord ci-dessous indique le nombre d’appels satisfaisants, le nombre d’appels insatisfaisants et le pourcentage d’appels insatisfaisants sur plusieurs mois, avec différents filtres appliqués. 

![Exemple de rapport du tableau de bord de qualité des appels](../../media/9e0723f7-f850-4d11-9ecd-7e8e013a8bed.png)

Le tableau de bord de qualité des appels est créé après la Méthodologie de qualité des appels (CQM). L’ensemble de rapports par défaut est conçu pour respecter les flux d’analyse de la méthodologie de qualité des appels. Les utilisateurs ont également la possibilité de modifier ou de créer des rapports personnalisés selon leurs besoins. Toutefois, comme les données peuvent être visualisées de différentes façons, l’affichage des données du tableau de bord de qualité des appels ne répond peut-être pas intégralement aux besoins de chaque utilisateur. En pareils cas, un utilisateur peut tirer parti des API de données et des API de référentiel pour créer des pages de rapport. Dans ce didacticiel, nous en étudierons différents exemples.

### <a name="how-the-dashboard-consumes-the-data-service"></a>Utilisation du service de données dans le tableau de bord

Lorsque vous naviguez jusqu’à la page d’accueil http://localhost/cqd)bord (par exemple, le jeu de rapports et les rapports correspondants pour un utilisateur authentifié et autorisé sont récupérés auprès du service de référentiel. Une URL complète est construite à partir de l’ID du jeu de rapports et de l’année-mois (ID du jeu de rapports est le nombre entier après la section'/#/'dans l’URL, et par défaut, l’année en cours est ajoutée à la fin de l’ID du jeu de rapports après la barre oblique). Les définitions de rapport sont stockées au format JSON et extraites à partir du service de référentiel, puis transmises au service de données. Le service de données génère des requêtes avec des expressions Multi-Dimension (MDX) basé sur les valeurs transmises, puis il les exécute sur le cube afin d’extraire les données pour chaque rapport. 

### <a name="building-customized-reports"></a>Création de rapports personnalisés

La personnalisation des rapports de tableau de bord de qualité des appels est très flexible, mais dans certaines situations, les utilisateurs peuvent souhaiter agréger des données de différents rapports créés dans le tableau de bord de qualité des appels. Par exemple, il peut être nécessaire de créer un rapport qui indique les pourcentages d’appels insatisfaisants de toutes les combinaisons d’appels filaires dans un tableau (dont le résultat s’apparente aux données de la figure) :

![Table du tableau de bord de qualité des appels](../../media/ef19d535-5da6-44a9-91f6-1ed3f30b96f1.png)

À l’aide du portail du tableau de bord de qualité des appels, un utilisateur devrait accéder à différents rapports pour extraire et enregistrer le pourcentage d’appels insatisfaisants pour chacun d’eux, ce qui peut être fastidieux si les données à recueillir sont nombreuses. L’API de données permet aux utilisateurs de créer des programmes pour effectuer ces opérations, en extrayant les données à partir du service de données (à l’aide d’appels AJAX, par ex.). 

 **Exemple 1 : rapport simple**

Commençons par un exemple simple. Si nous voulons afficher le nombre de flux Audio Good Stream et Audio Bad Stream de février 2015 dans une page HTML, comme sur l’illustration :

![Exemple de rapport du tableau de bord de qualité des appels](../../media/f0e4e61f-1fa5-4d69-b192-f19e9612bf1c.png)

Nous devons envoyer un appel au service de données avec les paramètres appropriés et afficher les résultats de la requête dans un tableau HTML. Vous trouverez ci-dessous un exemple de code JavaScript :

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

Cet exemple peut être divisé en trois étapes :

1. Construisez la requête (dans l’exemple, elle est définie dans la variable’requête'). La requête est définie comme objet JSON, qui inclut les données suivantes :

   a. Zéro, une ou plusieurs dimensions. Chaque dimension est indiquée par un objet DataModelName.

   b. Zéro, un ou plusieurs filtres. Chaque filtre possède :

   - DataModelName (la dimension qui définit l’ensemble de filtres)

   - Valeur (valeur comparée par l’opérande)

   - Opérande (type de comparaison, 0 signifie "égal").

     c. Une ou plusieurs mesures

2. Envoyez la requête au service de données par le biais de l’appel AJAX. Les paramètres de demande ci-dessous doivent être indiqués :

   a. url (qui doit être http://[NomServeur]/QoEDataService/RunQuery)

   b. Data (il s’agit de la représentation sous forme de chaîne de l’objet JSON défini dans la variable « requête »). Le service de données renverra les résultats d’une requête dans un paramètre de la fonction de rappel pour que l’opération réussisse.

   c. type (pour QoEDataService, RunQuery n’accepte que les demandes POST).

   d. async (indicateur signalant si l’appel AJAX doit être synchrone ou asynchrone)

   e. contentType (doit être « application/JSON »).

   touche. success (fonction de rappel lorsque l’appel AJAX réussit)

   grand. error (fonction de gestion des erreurs lorsque l’appel AJAX échoue)

3. Placez les données dans les éléments div du code HTML (dans l’exemple de code, cette opération est effectuée par le biais de l’appel de fonction anonyme une fois que la demande AJAX a réussi).

L’insertion de code JavaScript dans une page HTML aboutit à un rapport comme celui de la figure. Le code HTML complet est le suivant :

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

Jusque-là, le rapport est toujours très simple. L’utilisateur peut ajouter d’autres mesures, dimensions ou filtres pour personnaliser ce rapport. Par exemple, si vous souhaitez afficher le pourcentage d’appels médiocres du partage d’application, il est nécessaire d’ajouter une nouvelle mesure s’y rapportant. Pour afficher tous les appels TCP et les appels UDP, vous devez ajouter une nouvelle dimension relative au type de transport. Si vous souhaitez afficher le nombre d’appels insatisfaisants dans un bâtiment spécifique, un nouveau filtre doit être ajouté pour sélectionner les appels à destination de ce bâtiment et en provenance de celui-ci.

 **Exemple 2 : définition de rapport**

Il peut être difficile de déterminer comment rédiger la liste complète des mesures/dimensions/filtres et leurs valeurs correspondantes lors de la construction d’une requête. Dans ce cas, vous pouvez accéder au portail, créer un rapport à l’aide de l’éditeur de rapport et afficher la chaîne JSON de la définition de rapport, puis copier cette définition dans un rapport personnalisé. 

Dans cet exemple, nous allons créer une page web, comme celle présentée sur la figure suivante, dans laquelle un utilisateur peut entrer la référence d’un ensemble de rapports (ou d’un rapport) et afficher la définition de l’ensemble de rapports ou du rapport dans la page web. L’utilisateur peut alors insérer la chaîne JSON dans du code similaire à celui de l’exemple 1 et construire un rapport personnalisé en fonction des besoins. 

![Exemple de tableau de bord de qualité des appels](../../media/01c45c23-c4d2-47b8-819f-0888cf71260f.png)

Pour créer l’outil visionneuse de définition de rapport, nous devons envoyer des appels au service de référentiel pour extraire des représentations de chaîne JSON des définitions de chaque report-set souhaité. L’API de référentiel renverra la définition report-set basée sur un ID d’ensemble de rapports donné. 

Un exemple rapide est le suivant : le code contient un bloc qui est un exemple simple d’envoyer une requête au service du référentiel pour obtenir le contenu d’un élément de référentiel basé sur son identificateur. La partie suivante du code (méthode processReportSetData) envoie des appels AJAX pour obtenir la définition de chaque rapport dans ce jeu de rapports. Dans la mesure où l’ID du portail Web bord est l’ID d’un ensemble de rapports, l’appel AJAX renvoie un élément de jeu de rapports. Vous trouverez plus d’informations sur l’API du référentiel et plus précisément sur GetItems dans la section [obtenir des éléments](get-items.md). 

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

Les éléments ci-dessus aboutiront à une page Web semblable à celle figurant dans la figure (sans la définition de rapport lors de la visite initiale). Obtenez l’ID du jeu de rapports sur le portail bord (il est après'/#/'connexion bord URL du portail (par exemple, dans la première figure, l’ID du jeu de rapports est 3024) et il est placé dans la section entrée de cette page Web. Appuyez sur le bouton « charger » et observez la définition complète (mesures, dimensions, filtres listes) du jeu de rapports.

En résumé, afin d’obtenir rapidement la définition complète d’un rapport/ensemble de rapports. Les étapes à suivre sont :

1. Accédez au portail et servez-vous de l’éditeur de requête pour personnaliser un rapport (cliquez sur le bouton « modifier » au-dessus d’un rapport pour modifier, ajouter ou supprimer des mesures/dimensions/filtres, puis enregistrez le rapport).

2. Obtenez l’ID du jeu de rapports à partir de l’URL (il s’agit de l’URL de connexion de type'/#/').

3. Lancez cette page web de définition de rapport créée lors de l’exemple 2, entrez l’ID de l’ensemble de rapports, puis extrayez la définition complète d’un ensemble de rapports (à utiliser dans les appels de l’API de données).

   **Exemple 3 : carte de performance**

Voici une tâche plus compliquée. Que faire si nous voulons créer une page web comme celle qui est présentée ? Nous devons mettre à jour l’exemple 1 (à l’aide de de la page web générée lors de l’exemple 2 pour extraire la définition complète d’un rapport) afin de traiter davantage de données.

Dans ce cas, nous devons mettre à jour la liste de mesures et de dimensions. Pour déterminer comment ajouter/modifier une mesure et/ou une dimension, suivez les instructions de l’exemple 2 et extrayez la définition complète du rapport, dont les listes complètes de mesures et de dimensions. Insérez cette définition complète dans l’exemple de code. 

Voici la procédure détaillée permettant d’accéder à la page de la carte de performance dans la figure de l’exemple 1 :

1. Mettre à jour les mesures dans la variable « `[Measures].[Audio Good Streams JPDR Count]` requête `[Measures].[Audio Poor Streams JPDR Count]` » `[Measures].[AudioPoorJPDRPercentage]`de et à. 

2. Mettez à jour les filtres. Dans l’exemple 1, les données JSON pour les filtres ont un filtre, qui est défini `[StartDate].[Month]`sur la dimension. Dans la mesure où les filtres sont regroupés dans un tableau JSON, il est possible d’ajouter des dimensions à la cette liste. Par exemple, pour obtenir le client serveur dans les appels filaires pour le « currentMonth », nous devons disposer des filtres suivants :

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

   Ici, la `[Scenarios].[ScenarioPair]` dimension est définie sur `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`égal. Il `[Scenario.][ScenarioPair]` s’agit d’une dimension spéciale créée pour simplifier la création de rapports. Il a six valeurs correspondant à `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]`. Par exemple, il suffit d’utiliser un filtre au lieu d’une combinaison de six filtres. Dans notre exemple, la valeur `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` se TransType vers le scénario dans lequel : First est Server, second n’est pas serveur, le premier est l’intérieur, le second est l’intérieur, le premier type de connexion est filaire et le second type de connexion est câblé, qui correspond à la définition exacte de « serveur-client-intégré ».

3. Créez un ensemble de filtres par scénario. Sur la figure, chaque ligne de la carte de performance représente un autre scénario, qui sera un filtre différent (alors que les dimensions et les mesures sont identiques). 

4. Analysez les résultats des appels AJAX pour les placer à la position appropriée dans le tableau. Comme il s’agit principalement de manipulation de code HTML et JavaScript, nous n’entrerons pas ici dans les détails. Le code est disponible à l’annexe A.

    > [!NOTE]
    >  Si le partage de ressources à l’origine (CORS) est activé, les utilisateurs peuvent rencontrer des erreurs telles que « aucun » en-tête de contrôle d’accès L’origine « NULL » n’est donc pas autorisée. Pour résoudre ce problème, placez le fichier HTML sous le dossier dans lequel le portail est installé (par défaut, il devrait `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`être. Accédez ensuite au code HTML par le biais d’un `http://<servername>/cqd/<html_file_name>`navigateur doté de l’URL. (L’URL par défaut du tableau de bord `http://<servername>/cqd.`de bord local est) 

### <a name="appendix-a"></a>Annexe A

Code HTML de l’exemple 3 (carte de performance) :

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
