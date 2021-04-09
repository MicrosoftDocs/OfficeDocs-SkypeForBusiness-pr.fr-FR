---
title: Azure Sentinel et Microsoft Teams
author: MicrosoftHeidi
ms.author: tracyp
manager: dansimp
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Conseils de sécurité et apprentissage pour les administrateurs informatiques sur l'utilisation de Sentinel pour surveiller et repérer les menaces qui peuvent survenir dans Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1075a2c345bd866266b175a4b62432e9f819b330
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598523"
---
# <a name="azure-sentinel-and-microsoft-teams"></a><span data-ttu-id="d6852-103">Azure Sentinel et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d6852-103">Azure Sentinel and Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d6852-104">Azure Sentinel dispose désormais d'un connecteur intégré.</span><span class="sxs-lookup"><span data-stu-id="d6852-104">Azure Sentinel now has an integrated connector.</span></span> <span data-ttu-id="d6852-105">Pour plus d'informations, voir [Connecter les journaux d'Office 365 à Azure Sentinel](/azure/sentinel/connect-office-365) .</span><span class="sxs-lookup"><span data-stu-id="d6852-105">For more information, see [Connect Office 365 Logs to Azure Sentinel](/azure/sentinel/connect-office-365).</span></span> <span data-ttu-id="d6852-106">Il s'agit de la méthode recommandée pour collecter ces journaux et elle remplace les méthodes de collecte décrites ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="d6852-106">This is the recommended route for collecting these logs and supersedes the collection methods described below.</span></span>

<span data-ttu-id="d6852-107">Teams joue un rôle central dans la communication et le partage des données dans le cloud Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d6852-107">Teams serves a central role in both communication and data sharing in the Microsoft 365 Cloud.</span></span> <span data-ttu-id="d6852-108">Étant donné que le service Teams s’accompagne de nombreuses technologies sous-jacentes dans le cloud, celui-ci peut tirer parti d’une analyse humaine et automatisée, non seulement lorsqu’il s’agit de *le repérage dans les journaux*, mais également dans *la surveillance en temps réel des réunions*.</span><span class="sxs-lookup"><span data-stu-id="d6852-108">Because the Teams service touches on so many underlying technologies in the Cloud, it can benefit from human and automated analysis not only when it comes to *hunting in logs*, but also in *real-time monitoring of meetings*.</span></span> <span data-ttu-id="d6852-109">Azure Sentinel offre aux administrateurs ces solutions.</span><span class="sxs-lookup"><span data-stu-id="d6852-109">Azure Sentinel offers admins these solutions.</span></span>

> [!NOTE]
> <span data-ttu-id="d6852-110">Vous avez besoin d’un rappel sur Azure Sentinel ?</span><span class="sxs-lookup"><span data-stu-id="d6852-110">Need a refresher on Azure Sentinel?</span></span> <span data-ttu-id="d6852-111">[Cet article](/azure/sentinel/overview) est exactement ce qu'il faut.</span><span class="sxs-lookup"><span data-stu-id="d6852-111">[This article](/azure/sentinel/overview) is just the thing.</span></span>

## <a name="sentinel-and-microsoft-teams-activity-logs"></a><span data-ttu-id="d6852-112">Journaux d’activité Sentinel et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d6852-112">Sentinel and Microsoft Teams Activity Logs</span></span>

<span data-ttu-id="d6852-113">Cet article traite de la collecte des journaux d’activité Teams dans Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="d6852-113">This article focuses on collecting Teams activity logs in Azure Sentinel.</span></span> <span data-ttu-id="d6852-114">En plus d'autoriser les administrateurs à placer la gestion de la sécurité dans un volet de verre (y compris les appareils tiers sélectionnés, protection Microsoft contre les menaces et d’autres charges de travail Microsoft 365), les classeurs sentinelles et runbooks peuvent rendre la surveillance de la sécurité systématique.</span><span class="sxs-lookup"><span data-stu-id="d6852-114">Aside from allowing administrators to put security management under one pane of glass (including any selected 3rd party devices, Microsoft Threat Protection, and other Microsoft 365 Workloads), Sentinel workbooks, and runbooks can make security monitoring systematic.</span></span> <span data-ttu-id="d6852-115">La première étape de ce processus consiste à collecter les journaux nécessaires à l’analyse.</span><span class="sxs-lookup"><span data-stu-id="d6852-115">A good first step in this process is collecting the needed logs for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="d6852-116">Plusieurs abonnements Microsoft 365 peuvent être exposés dans la même instance d’Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="d6852-116">More than one Microsoft 365 subscription can be surfaced in the same instance of Azure Sentinel.</span></span> <span data-ttu-id="d6852-117">Cela permet de [surveillance en temps réel](/azure/sentinel/livestream) et de le repérage de menaces dans les fichiers journaux historiques.</span><span class="sxs-lookup"><span data-stu-id="d6852-117">This will allow for [realtime monitoring](/azure/sentinel/livestream) and hunting for threats in historical log file s.</span></span> <span data-ttu-id="d6852-118">Les administrateurs pourront repérer à l’aide des [requêtes de ressources croisées](/azure/azure-monitor/log-query/cross-workspace-query), au sein d’un même groupe de ressources, au sein de groupes de ressources ou dans un autre abonnement.</span><span class="sxs-lookup"><span data-stu-id="d6852-118">Administrators will be able to hunt using [cross-resource queries](/azure/azure-monitor/log-query/cross-workspace-query), that is within a single resource group, across resource groups, or in another subscription.</span></span>

## <a name="step-1-collect-teams-logs"></a><span data-ttu-id="d6852-119">Étape 1 : collecter les journaux Teams</span><span class="sxs-lookup"><span data-stu-id="d6852-119">Step 1: Collect Teams logs</span></span>

<span data-ttu-id="d6852-120">Cette section se compose de trois parties :</span><span class="sxs-lookup"><span data-stu-id="d6852-120">This section has three parts:</span></span>

1. <span data-ttu-id="d6852-121">Activation des journaux d'audit dans **Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="d6852-121">Enabling Audit Logs in **Microsoft 365**.</span></span>
2. <span data-ttu-id="d6852-122">Enregistrement d'une application dans **Microsoft Azure** pour permettre l'authentification et l'autorisation de la collecte des journaux.</span><span class="sxs-lookup"><span data-stu-id="d6852-122">Registering an App in **Microsoft Azure** to permit authentication and authorization for log collection.</span></span>
3. <span data-ttu-id="d6852-123">Enregistrement de l'abonnement à l'API qui permettra la collecte des journaux via l'API Microsoft 365 via **PowerShell** .</span><span class="sxs-lookup"><span data-stu-id="d6852-123">Registering the API subscription that will allow log collection via Microsoft 365 API via **PowerShell**.</span></span>

### <a name="enable-audit-logs-in-microsoft-365"></a><span data-ttu-id="d6852-124">Activer les journaux d'audit dans Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d6852-124">Enable Audit logs in Microsoft 365</span></span>

<span data-ttu-id="d6852-125">Étant donné que Teams enregistre l'activité par le biais de Microsoft 365, les journaux d'audit ne sont pas collectés par défaut.</span><span class="sxs-lookup"><span data-stu-id="d6852-125">Because Teams logs activity through Microsoft 365, audit logs aren't collected by default.</span></span> <span data-ttu-id="d6852-126">Activez [cette fonction en procédant comme suit](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%c2%a0).</span><span class="sxs-lookup"><span data-stu-id="d6852-126">Turn on this feature via [these steps](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%c2%a0).</span></span> <span data-ttu-id="d6852-127">Les données relatives de Teams sont collectées dans l'audit Microsoft 365 sous *Audit.General*.</span><span class="sxs-lookup"><span data-stu-id="d6852-127">Teams data is collected in the Microsoft 365 audit under *Audit.General*.</span></span>

### <a name="register-an-app-in-microsoft-azure-for-log-collection"></a><span data-ttu-id="d6852-128">Inscrire une application dans Microsoft Azure pour la collecte des journaux</span><span class="sxs-lookup"><span data-stu-id="d6852-128">Register an App in Microsoft Azure for log collection</span></span>

> [!TIP]
> <span data-ttu-id="d6852-129">Avant de commencer, vous devez vous enregistrer votre **ID d’application/ID client**, et votre **ID du locataire** pour une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="d6852-129">Before you begin, you will need to record you **Application ID / Client ID**, and your **Tenant ID** for later use.</span></span> <span data-ttu-id="d6852-130">Veillez à les capturer au fur et à mesure que vous parcourez les étapes d’inscription ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="d6852-130">Be sure to capture them as you walk through app registration steps below.</span></span> <span data-ttu-id="d6852-131">Les deux ID s’affichent.</span><span class="sxs-lookup"><span data-stu-id="d6852-131">You will see both IDs.</span></span>
>- <span data-ttu-id="d6852-132">Une fois que vous avez créé votre application, cliquez sur inscription de l’application dans la barre latérale de lancement rapide > Recherchez le nom complet de votre nouvelle application > Copiez l’ID de l’application (client).</span><span class="sxs-lookup"><span data-stu-id="d6852-132">After your app is created, click App Registration on the quick launch side-bar > Find your new app's display name > copy the Application (client) ID.</span></span>
>- <span data-ttu-id="d6852-133">Cliquez sur vue d’ensemble sur la barre de lancement rapide > copier l’ID d’annuaire (locataire).</span><span class="sxs-lookup"><span data-stu-id="d6852-133">Click Overview on the quick launch side-bar > copy the Directory (tenant) ID.</span></span>

<span data-ttu-id="d6852-134">Authentifiez et autorisez une application Azure Active Directory (Azure AD) pour collecter des données de journal à partir de l’API.</span><span class="sxs-lookup"><span data-stu-id="d6852-134">Authenticate and authorize an Azure Active Directory (Azure AD) app to collect log data from the API.</span></span>

1. <span data-ttu-id="d6852-135">Accédez à votre panneau *Azure AD* dans le portail Azure.</span><span class="sxs-lookup"><span data-stu-id="d6852-135">Navigate to your *Azure AD* blade in the Azure portal.</span></span>
2. <span data-ttu-id="d6852-136">Cliquez sur *Inscriptions des applications* dans la barre latérale lancement rapide.</span><span class="sxs-lookup"><span data-stu-id="d6852-136">Click on *App registrations* in the quick launch side-bar.</span></span>
3. <span data-ttu-id="d6852-137">Sélectionnez *Nouvelle inscription*.</span><span class="sxs-lookup"><span data-stu-id="d6852-137">Select *New registration*.</span></span>
4. <span data-ttu-id="d6852-138">Nommez l’application de collecte de journal Teams, puis cliquez sur *Inscrire*.</span><span class="sxs-lookup"><span data-stu-id="d6852-138">Name your Teams log collecting app and click *Register*.</span></span>
5. <span data-ttu-id="d6852-139">Cliquez sur le long de ce chemin d’accès : *Autorisations d’API* > *Ajouter une autorisation* > *API de gestion Office 365* > *Autorisations d’application*.</span><span class="sxs-lookup"><span data-stu-id="d6852-139">Click along this path: *API Permissions* > *Add a permission* > *Office 365 Management APIs* > *Application permissions*.</span></span>
6. <span data-ttu-id="d6852-140">Développez flux d’activités et cochez *ActivityFeed.Read*.</span><span class="sxs-lookup"><span data-stu-id="d6852-140">Expand Activity Feed and check *ActivityFeed.Read*.</span></span>
7. <span data-ttu-id="d6852-141">Sélectionnez *Consentement de l’administrateur général* ici.</span><span class="sxs-lookup"><span data-stu-id="d6852-141">Choose *Grand admin consent* here.</span></span> <span data-ttu-id="d6852-142">Cliquez sur Oui lorsque vous êtes invité à confirmer votre signification.</span><span class="sxs-lookup"><span data-stu-id="d6852-142">Click Yes when prompted asking if you mean it.</span></span>
8. <span data-ttu-id="d6852-143">Cliquez sur *Certificats et secrets* dans la barre latérale > bouton *Nouvelle clé secrète client*.</span><span class="sxs-lookup"><span data-stu-id="d6852-143">Click *Certificates and Secrets* in the side-bar> *New client secret* button.</span></span>
9. <span data-ttu-id="d6852-144">Dans la fenêtre Nouvelle clé secrète client, entrez une description pour la nouvelle clé secrète client, assurez-vous de choisir « Jamais » pour l’expiration, puis cliquez sur *Ajouter*.</span><span class="sxs-lookup"><span data-stu-id="d6852-144">On the New client secret window, enter a description for the new Client Secret, make sure you choose 'Never' for Expiration, and click *Add*.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d6852-145">Il est **critique** de copier la nouvelle clé secrète client dans une entrée du gestionnaire de mots de passe qui s’affiche sous le nom de l’application nouvellement créée.</span><span class="sxs-lookup"><span data-stu-id="d6852-145">It's **critical** to copy the new client secret into a password manager entry that goes under the name of the newly created app.</span></span> <span data-ttu-id="d6852-146">Vous ne serez pas en mesure de revenir sur ce secret une fois la fermeture du panneau Azure (*Panneau* étant le terme azur pour fenêtre).</span><span class="sxs-lookup"><span data-stu-id="d6852-146">You won't be able to get back to look at this secret after the closing out of the Azure blade (*blade* being the Azure term for window).</span></span>

### <a name="register-the-api-with-powershell-to-collect-teams-logs"></a><span data-ttu-id="d6852-147">Inscrire l’API avec PowerShell pour collecter les journaux Teams</span><span class="sxs-lookup"><span data-stu-id="d6852-147">Register the API with PowerShell to collect Teams logs</span></span>

<span data-ttu-id="d6852-148">La dernière étape de l’installation consiste à collecter et enregistrer l’abonnement API de sorte que vous puissiez recueillir vos données de journal.</span><span class="sxs-lookup"><span data-stu-id="d6852-148">The final step in setup is to collect and register the API subscription so that you can collect your log data.</span></span> <span data-ttu-id="d6852-149">Cela se fait par le biais d'appels REST PowerShell à l'API Microsoft 365 pour les activités de gestion.</span><span class="sxs-lookup"><span data-stu-id="d6852-149">This is done via PowerShell REST calls to the Microsoft 365 Management Activity API.</span></span>

<span data-ttu-id="d6852-150">Vous êtes prêt à fournir **ID d’application (client)**, la nouvelle **clé secrète client** votre **domaine d’URL pour M365** et **ID d’annuaire (locataire)** les valeurs dans l’applet de commande PowerShell ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="d6852-150">Be ready to supply **Application (client) ID**, the new **Client Secret**, your **URL domain for M365**, and **Directory (tenant) ID** values in the PowerShell cmdlet below.</span></span>

```PowerShell
$ClientID = "<Application (client) ID>"  
$ClientSecret = "<Client secret>"  
$loginURL = "https://login.microsoftonline.com/"  
$tenantdomain = "<domain>.onmicrosoft.com"  

$TenantGUID = "<Directory (tenant) ID>"  
$resource = "https://manage.office.com"  
$body = @{grant_type="client_credentials";resource=$resource;client_id=$ClientID;client_secret=$ClientSecret}
$oauth = Invoke-RestMethod -Method Post -Uri $loginURL/$tenantdomain/oauth2/token?api-version=1.0 -Body $body  
$headerParams = @{'Authorization'="$($oauth.token_type) $($oauth.access_token)"}
$publisher = New-Guid
Invoke-WebRequest -Method Post -Headers $headerParams -Uri "https://manage.office.com/api/v1.0/$tenantGuid/activity/feed/subscriptions/start?contentType=Audit.General&PublisherIdentifier=$Publisher"
```

## <a name="step-2-deploy-a-sentinel-playbook-to-ingest-the-teams-logs"></a><span data-ttu-id="d6852-151">Étape 2 : déployer un guide opérationnel Sentinel pour réceptionner les journaux Teams</span><span class="sxs-lookup"><span data-stu-id="d6852-151">Step 2: Deploy a Sentinel Playbook to ingest the Teams logs</span></span>

<span data-ttu-id="d6852-152">Les guides opérationnels Azure Sentinel (également appelées applications logiques) permettront à Azure d’absorber vos données Teams collectées.</span><span class="sxs-lookup"><span data-stu-id="d6852-152">Azure Sentinel Playbooks (also called Logic Apps) will allow Azure to ingest your collected Teams data.</span></span> <span data-ttu-id="d6852-153">L’application logique interroge Office 365 pour rechercher les données d’audit qu’elle écrit dans l’espace de travail Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="d6852-153">The Logic App queries Office 365 to find the audit data it writes into the Azure Sentinel workspace.</span></span>

<span data-ttu-id="d6852-154">Utilisez [ce](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) modèle ARM pour déployer votre guide opérationnel Sentinel.</span><span class="sxs-lookup"><span data-stu-id="d6852-154">Use [this](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) ARM template to deploy your Sentinel Playbook.</span></span>

<span data-ttu-id="d6852-155">Éléments à retenir :</span><span class="sxs-lookup"><span data-stu-id="d6852-155">Things to remember:</span></span>

1. <span data-ttu-id="d6852-156">Vous devez parcourir le modèle ARM et remplacer certaines valeurs par des valeurs adaptées à votre environnement.</span><span class="sxs-lookup"><span data-stu-id="d6852-156">You will need to walk through the ARM template and replace certain of the values with values appropriate for your own environment.</span></span>
2. <span data-ttu-id="d6852-157">Vous devez autoriser l’interconnexion des journaux et examiner les résultats dans Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="d6852-157">You will need to allow time between the ingestion of logs and looking at the results in Azure Sentinel.</span></span>

   <span data-ttu-id="d6852-158">Patientez 5 à 10 minutes, en sachant qu’en l’absence de données au cours des 5 dernières minutes, un message d’erreur s’affiche.</span><span class="sxs-lookup"><span data-stu-id="d6852-158">Wait for 5 to 10 minutes, understanding that if there is no data within the past 5 minutes you will see an error message.</span></span> <span data-ttu-id="d6852-159">Consultez les journaux d’audit et gardez à l’esprit que, comme les informations relatives à Teams se trouvent dans l’audit. Les événements généraux, qui collectent plus que les journaux Teams, apparaissent dans les 5 à 10 minutes sur les systèmes en cours d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="d6852-159">Check Audit logs and keep in mind that because Teams information is in the Audit.General events, which collects more than Teams logs, results should appear within 5 to 10 minutes on systems that are in use.</span></span> <span data-ttu-id="d6852-160">Si vous utilisez un environnement de texte, veillez à utiliser Teams pour générer la journalisation.</span><span class="sxs-lookup"><span data-stu-id="d6852-160">If using a text environment, be certain to use Teams in order to generate logging.</span></span>

![Graphique montrant les classes d’application logiques.](media/tracyp-teams-sentinel-logic-app.png#thumbnail)

 <p><details><summary> <span data-ttu-id="d6852-162">Explication des actions dans le graphique :</span><span class="sxs-lookup"><span data-stu-id="d6852-162">Explanation of actions in the graphic:</span></span> 
  </summary>

  <span data-ttu-id="d6852-163">• La périodicité est le déclencheur d’application logique qui indique au flux de travail de s’exécuter toutes les heures.</span><span class="sxs-lookup"><span data-stu-id="d6852-163">• Recurrence is the Logic App Trigger that tells the workflow to run every hour.</span></span>
  <p>
<span data-ttu-id="d6852-164">• L’action actuelle est très simple et permet d’obtenir l’heure actuelle.</span><span class="sxs-lookup"><span data-stu-id="d6852-164">• The Current Time action is very basic and just gets the current time.</span></span>
  <p>
<span data-ttu-id="d6852-165">• Initialiser la variable crée une variable appelée NextPage et la définit sur 1.</span><span class="sxs-lookup"><span data-stu-id="d6852-165">• Initialize Variable creates a variable called NextPage and sets it to 1.</span></span> <span data-ttu-id="d6852-166">Celle-ci sera utilisée plus tard pour gérer la pagination à partir de l’API Office 365.</span><span class="sxs-lookup"><span data-stu-id="d6852-166">This will be used later in order to handle pagination from the O365 API.</span></span>
  <p>
<span data-ttu-id="d6852-167">• Initialiser la variable 2 crée une variable vide appelée heure de début.</span><span class="sxs-lookup"><span data-stu-id="d6852-167">• Initialize Variable 2 creates an empty variable called Start Time.</span></span>
  <p>
<span data-ttu-id="d6852-168">• L’exécution de la requête et des résultats de liste est une action Azure Monitor qui interroge l’espace de travail pour rechercher le dernier journal Office 365 entré à partir de l’application logique.</span><span class="sxs-lookup"><span data-stu-id="d6852-168">• Run Query and list results is an Azure Monitor action that will query the workspace for the last O365 log that was entered from the Logic App.</span></span>
  <p>
<span data-ttu-id="d6852-169">• La condition 4 permet de vérifier si la requête Exécuter la requête et les résultats de liste a renvoyé des données.</span><span class="sxs-lookup"><span data-stu-id="d6852-169">• Condition 4 is used to check whether the Run Query and list results query returned any data.</span></span> <span data-ttu-id="d6852-170">Pour vérifier si c’est la première fois que l’application logique a été utilisée.</span><span class="sxs-lookup"><span data-stu-id="d6852-170">This is done to check if this is the very first time the Logic App has been used.</span></span> <span data-ttu-id="d6852-171">Si aucune donnée n’est renvoyée, la variable StartTime est paramétrée sur Maintenant - 24 heures.</span><span class="sxs-lookup"><span data-stu-id="d6852-171">If no data is returned, StartTime variable is set to Now – 24 hours.</span></span> <span data-ttu-id="d6852-172">Si des données sont renvoyées, StartTime est paramétrée sur le dernier enregistrement TimeGenerated.</span><span class="sxs-lookup"><span data-stu-id="d6852-172">If data is returned, StartTime is set to the last record TimeGenerated.</span></span> <span data-ttu-id="d6852-173">Cette opération permet à la requête de récupérer les données de la dernière entrée jusqu’à présent dans le sondage de l’API Office 365, ou au cours des dernières 24 heures, s’il s’agit de la première exécution.</span><span class="sxs-lookup"><span data-stu-id="d6852-173">This is done so that the query can get data from the last entry till now in the poll against the O365 API, or in the last 24 hours if this is the first run.</span></span>
  <p>
<span data-ttu-id="d6852-174">• Initialiser la variable 3 crée une variable appelée AvailableUri.</span><span class="sxs-lookup"><span data-stu-id="d6852-174">• Initialize Variable 3 creates a variable called AvailableUri.</span></span> <span data-ttu-id="d6852-175">Il s’agit d’une chaîne avec l’URL créée à l’aide de StartTime et CurrentTime comme heures de début et de fin, respectivement.</span><span class="sxs-lookup"><span data-stu-id="d6852-175">This is a string with the URL built using the StartTime and CurrentTime as start and end times, respectively.</span></span>
  <p>
<span data-ttu-id="d6852-176">• La condition « Until » est une boucle qui permet à l'application logique de continuer à interroger l'API pour voir s'il y a davantage de données (pagination).</span><span class="sxs-lookup"><span data-stu-id="d6852-176">• The Until condition is a loop that allows the logic app to keep polling the API to see if there is more data (pagination).</span></span> <span data-ttu-id="d6852-177">Tant que la variable NextPage a la valeur 1, la boucle continue.</span><span class="sxs-lookup"><span data-stu-id="d6852-177">As long as NextPage variable is 1 the loop will continue.</span></span> <span data-ttu-id="d6852-178">Plus tard, cette variable sera mise à jour s’il n’y a plus de pages à récupérer.</span><span class="sxs-lookup"><span data-stu-id="d6852-178">Later this variable will be updated if there are no more pages left to retrieve.</span></span>
  <p>
<span data-ttu-id="d6852-179">• À l’intérieur de la boucle Until, la première étape HTTP se connecte au AvailableURI.</span><span class="sxs-lookup"><span data-stu-id="d6852-179">• Inside the Until loop, the first HTTP step Connects to the AvailableURI.</span></span> <span data-ttu-id="d6852-180">Cet URI renvoie la liste du contenu disponible et de chaque URI de contenu.</span><span class="sxs-lookup"><span data-stu-id="d6852-180">This URI returns a list of available content and each contents URI.</span></span> <span data-ttu-id="d6852-181">Pour plus d’informations sur l’utilisation de cette URL, consultez : https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span><span class="sxs-lookup"><span data-stu-id="d6852-181">There's more on how this works at this URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span></span>
  <p>
<span data-ttu-id="d6852-182">• Une fois le contrôle exécuté, assurez-vous que les données sont renvoyées.</span><span class="sxs-lookup"><span data-stu-id="d6852-182">• Next a check is run to make sure data is returned.</span></span> <span data-ttu-id="d6852-183">La condition vérifie si la longueur du corps est 0.</span><span class="sxs-lookup"><span data-stu-id="d6852-183">The Condition checks if the length of the body is 0.</span></span> <span data-ttu-id="d6852-184">Si c’est le cas, il n’y a pas de données à écrire dans l’analytique des journaux d'activité.</span><span class="sxs-lookup"><span data-stu-id="d6852-184">If so there is no data to write to Log Analytics.</span></span> <span data-ttu-id="d6852-185">Si la valeur est supérieure à 0, il y a des données à traiter.</span><span class="sxs-lookup"><span data-stu-id="d6852-185">If the value is greater than 0, there is data to process.</span></span>
  <p>
<span data-ttu-id="d6852-186">• Si des données sont détectées, elles doivent être traitées ensuite.</span><span class="sxs-lookup"><span data-stu-id="d6852-186">• If data is detected, it must next be processed.</span></span> <span data-ttu-id="d6852-187">L’analyse JSON définit un schéma des données renvoyées.</span><span class="sxs-lookup"><span data-stu-id="d6852-187">Parse JSON defines a schema of the returned data.</span></span> <span data-ttu-id="d6852-188">Cela permet aux applications logiques d’utiliser les données analysées en tant que contenu dynamique dans les étapes ultérieures.</span><span class="sxs-lookup"><span data-stu-id="d6852-188">This allows logic apps to use the parsed data as Dynamic content in later steps.</span></span>
  <p>
<span data-ttu-id="d6852-189">• Étant donné que la liste renvoyée des données disponibles est une matrice, une pour chaque action est utilisée pour parcourir la liste de contenu disponible.</span><span class="sxs-lookup"><span data-stu-id="d6852-189">• Since the returned list of available data is an Array, a For Each action is used to loop through the list of available content.</span></span>
  <p>
<span data-ttu-id="d6852-190">• L’étape suivante consiste à saisir le contenu.</span><span class="sxs-lookup"><span data-stu-id="d6852-190">• Next is grabbing the content.</span></span>  <span data-ttu-id="d6852-191">Le protocole HTTP est de nouveau utilisé pour obtenir le contentUri (une propriété dynamique créée à partir de l'analyse JSON), qui est l'URL des données à récupérer.</span><span class="sxs-lookup"><span data-stu-id="d6852-191">HTTP is used again to get the contentUri (a dynamic property created from Parse JSON), which is the URL of the data to retrieve.</span></span>
  <p>
<span data-ttu-id="d6852-192">• L’analyse JSON permet également d’analyser les données renvoyées.</span><span class="sxs-lookup"><span data-stu-id="d6852-192">• Parse JSON is also used to parse the returned data.</span></span> <span data-ttu-id="d6852-193">Vous pouvez trouver un exemple de contenu sur cette URL : https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span><span class="sxs-lookup"><span data-stu-id="d6852-193">You can find some sample content at this URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span></span>
  <p>
<span data-ttu-id="d6852-194">• Les données renvoyées sont également une matrice.</span><span class="sxs-lookup"><span data-stu-id="d6852-194">• The data returned is also an array.</span></span> <span data-ttu-id="d6852-195">Une boucle « For Each » peut également être utilisée ici.</span><span class="sxs-lookup"><span data-stu-id="d6852-195">A For Each loop can be used here as well.</span></span> <span data-ttu-id="d6852-196">Dans cette boucle, le flux de travail prend l’élément actuel de données et utilise l’action d’envoi de données pour écrire les données dans les données de l’analytique des journaux d'activité.</span><span class="sxs-lookup"><span data-stu-id="d6852-196">In this loop, the workflow takes the current item of data and uses the Send Data action to write the data to Log Analytics.</span></span>
  <p>
<span data-ttu-id="d6852-197">• Dans la mesure où il peut y avoir plusieurs pages de contenu disponible, une condition est vérifiée si NextPageUri n’est pas NULL.</span><span class="sxs-lookup"><span data-stu-id="d6852-197">• Since there may be multiple pages of available content, a condition checks if the NextPageUri is not NULL.</span></span> <span data-ttu-id="d6852-198">Si la valeur est NULL ou vide, NextPage est définit à 0, ce qui met fin à la boucle Until.</span><span class="sxs-lookup"><span data-stu-id="d6852-198">If it is NULL, or empty, NextPage is set to 0, which ends the Until loop.</span></span> <span data-ttu-id="d6852-199">S’il contient une URL, la variable AvaibleUri est mise à jour vers cette URL.</span><span class="sxs-lookup"><span data-stu-id="d6852-199">If it contains a URL, the AvaibleUri variable is updated to that URL.</span></span> <span data-ttu-id="d6852-200">Ainsi, l’exécution suivante de la boucle Until utilise une URL suivante disponible, et non l’URL de départ.</span><span class="sxs-lookup"><span data-stu-id="d6852-200">This way, the next run of the Until loop uses a next available URL, and not the starting URL.</span></span>

  </details>

> [!TIP]
> <span data-ttu-id="d6852-201">Vous pouvez choisir d’utiliser une fonction *Azure* pour réceptionner ces journaux. si c’est le cas, les informations relatives au déploiement sont [ici](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data)ou [ici](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp), selon vos préférences.</span><span class="sxs-lookup"><span data-stu-id="d6852-201">You may choose to use an *Azure Function* to ingest those logs, instead, and if you do, the information on how to deploy is [here](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data), or [here](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp), depending on your preference.</span></span>

<span data-ttu-id="d6852-202">Lorsque le connecteur (selon les options ci-dessus choisi) est en cours d’exécution, un tableau personnalisée appelée O365API_CL s’affiche dans l’espace de travail Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="d6852-202">With the connector (whichever of the options above you chose) running, you should see a custom table called O365API_CL in the Azure Sentinel workspace.</span></span> <span data-ttu-id="d6852-203">Cette opération permet de loger vos journaux Teams.</span><span class="sxs-lookup"><span data-stu-id="d6852-203">This will house your Teams logs.</span></span>

## <a name="step-3-use-sentinel-to-monitor-microsoft-teams"></a><span data-ttu-id="d6852-204">Étape 3 : utiliser Sentinel pour surveiller Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d6852-204">Step 3: Use Sentinel to monitor Microsoft Teams</span></span>

<span data-ttu-id="d6852-205">L’identité est un vecteur d’attaque important pour surveiller le moment auquel Microsoft Teams est destiné.</span><span class="sxs-lookup"><span data-stu-id="d6852-205">Identity is an important attack vector to monitor when it comes to Microsoft Teams.</span></span> <span data-ttu-id="d6852-206">Dans la mesure où Azure Active Directory (Azure AD) sous-tend le répertoire de Microsoft 365 (qui inclut Teams), il est utile de collecter et de repérer les menaces figurant dans les journaux Azure AD concernant l’authentification, afin de détecter les comportements suspects relatifs à l’identité.</span><span class="sxs-lookup"><span data-stu-id="d6852-206">Because Azure Active Directory (Azure AD) is the underpinning of Microsoft 365's directory, including Teams, collecting and hunting for threats in Azure AD logs around authentication will be useful in capturing suspicious behavior around identity.</span></span> <span data-ttu-id="d6852-207">Vous pouvez utiliser le connecteur intégré pour extraire les données Azure AD dans Azure Sentinel, et utiliser ces requêtes [détection](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs) et [repérage](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs) pour rechercher les problèmes.</span><span class="sxs-lookup"><span data-stu-id="d6852-207">You can use the built-in connector to pull Azure AD data into Azure Sentinel, and use these [detection](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs) and [hunting](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs) queries to look for problems.</span></span>

<span data-ttu-id="d6852-208">En ce qui concerne les attaques propres à Microsoft Teams, les menaces pesant sur les données (par exemple, Azure Sentinel) permettent également de contrôler celles-ci et de les repérer.</span><span class="sxs-lookup"><span data-stu-id="d6852-208">Regarding attacks specific to Microsoft Teams, threats to data, for example, Azure Sentinel also has means to monitor for them and hunt them down.</span></span>

### <a name="create-a-parser-for-your-data"></a><span data-ttu-id="d6852-209">Créer un analyseur pour vos données</span><span class="sxs-lookup"><span data-stu-id="d6852-209">Create a parser for your data</span></span>

<span data-ttu-id="d6852-210">La première chose à faire pour déterminer la logique d’un ensemble important de données collectées est de donner du sens à l’analyse.</span><span class="sxs-lookup"><span data-stu-id="d6852-210">The first thing to do in order to make sense of the large set of collected data is to give it meaning by parsing it.</span></span> <span data-ttu-id="d6852-211">Cette opération s’effectue à l’aide d’une fonction Kusto Query Language (KQL) qui simplifie l’utilisation des données.</span><span class="sxs-lookup"><span data-stu-id="d6852-211">This is done with a Kusto Query Language (KQL) Function that makes the data easier to use.</span></span>

> [!NOTE]
> <span data-ttu-id="d6852-212">Les fonctions KQL sont des requêtes KQL enregistrées sous la forme d’un type de données appelé « fonction ».</span><span class="sxs-lookup"><span data-stu-id="d6852-212">KQL functions are KQL queries saved as a data-type called 'function'.</span></span> <span data-ttu-id="d6852-213">Les fonctions KQL possèdent un alias qui peut être entré dans la zone de requête de Sentinel pour réexécuter rapidement la requête.</span><span class="sxs-lookup"><span data-stu-id="d6852-213">KQL functions have an alias that can be entered into the query box in Sentinel to quickly run the query again.</span></span> <span data-ttu-id="d6852-214">Pour plus d’informations sur les fonctions KQL et la création d’une fonction d’analyse, consultez [cet article de la communauté technique](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span><span class="sxs-lookup"><span data-stu-id="d6852-214">For more about KQL functions and how to build a parser function, read [this Tech Community article](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span></span>
 
 <span data-ttu-id="d6852-215">L’analyseur ci-dessous est un exemple personnalisable destiné à sélectionner un sous-ensemble des champs de l’API de gestion d’Office 365 pertinents pour *Teams*.</span><span class="sxs-lookup"><span data-stu-id="d6852-215">The parser below is a customizable example aimed at selecting a subset of the Office 365 Management API fields relevant to *Teams*.</span></span> <span data-ttu-id="d6852-216">Il existe également un analyseur suggéré [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt), mais vous pouvez modifier l’analyseur ci-dessous pour l’adapter à vos besoins et préférences.</span><span class="sxs-lookup"><span data-stu-id="d6852-216">There is also a suggested parser [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt), but the parser below can be modified to fit different needs and preferences.</span></span>

```kusto
O365API_CL
| where Workload_s =~ "MicrosoftTeams"
| project TimeGenerated,
          Workload=Workload_s,
          Operation=Operation_s,
          TeamName=columnifexists('TeamName_s', ""),
          UserId=columnifexists('UserId_s', ""),
          AddOnName=columnifexists('AddOnName_s', AddOnGuid_g),
          Members=columnifexists('Members_s', ""),
          Settings=iif(Operation_s contains "Setting", pack("Name", columnifexists('Name_s', ""), "Old Value", columnifexists('OldValue_s', ""), "New Value", columnifexists('NewValue_s', "")),""),
          Details=pack("Id", columnifexists('Id_g', ""),  "OrganizationId", columnifexists('OrganizationId_g', ""), "UserType", columnifexists('UserType_d', ""), "UserKey", columnifexists('UserKey_g', ""), "TeamGuid", columnifexists('TeamGuid_s', "")) 
```
 <span data-ttu-id="d6852-217">Enregistrez l’analyseur sous la forme d’une fonction KQL, avec un alias de TeamsData.</span><span class="sxs-lookup"><span data-stu-id="d6852-217">Save the parser as a KQL function, with an alias of TeamsData.</span></span> <span data-ttu-id="d6852-218">Elle sera utilisée pour les requêtes à suivre.</span><span class="sxs-lookup"><span data-stu-id="d6852-218">It will be used for the queries to follow.</span></span> <span data-ttu-id="d6852-219">Pour plus d’informations sur la configuration et l’utilisation d’une fonction KQL comme analyseur, consultez cet [Article de la communauté technique](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span><span class="sxs-lookup"><span data-stu-id="d6852-219">Details on configuring and using a KQL function as a parser can be found in this [Tech Community article](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span></span>

## <a name="helpful-hunting-kql-queries"></a><span data-ttu-id="d6852-220">Requêtes KQL utiles pour le repérage</span><span class="sxs-lookup"><span data-stu-id="d6852-220">Helpful hunting KQL queries</span></span>

<span data-ttu-id="d6852-221">Utilisez ces requêtes pour vous familiariser avec vos données et l’environnement Teams.</span><span class="sxs-lookup"><span data-stu-id="d6852-221">Use these queries to familiarize yourself with your Teams data and Teams environment.</span></span> <span data-ttu-id="d6852-222">Il est recommandé de connaître l’apparence et le comportement de l’environnement afin de reconnaître les activités suspectes.</span><span class="sxs-lookup"><span data-stu-id="d6852-222">Knowing how the environment should look and behave is a good first step in recognizing suspicious activity.</span></span> <span data-ttu-id="d6852-223">À partir de là, vous pouvez vous brancher au repérage de menaces.</span><span class="sxs-lookup"><span data-stu-id="d6852-223">From there, you can branch out into threat hunting.</span></span>

#### <a name="federated-external-users-query"></a><span data-ttu-id="d6852-224">Requête utilisateur externe fédérée</span><span class="sxs-lookup"><span data-stu-id="d6852-224">Federated external users query</span></span>

<span data-ttu-id="d6852-225">Obtenez la liste des sites Teams qui ont des utilisateurs externes fédérés.</span><span class="sxs-lookup"><span data-stu-id="d6852-225">Get the list of Teams sites that have federated external users.</span></span> <span data-ttu-id="d6852-226">Ces utilisateurs disposent d'un nom de domaine / suffixe UPN qui n'appartient *pas* à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d6852-226">These users will have a domain name / UPN suffix that *isn't* owned by your organization.</span></span> <span data-ttu-id="d6852-227">Dans cet exemple de requête, l’organisation possède contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d6852-227">In this example query, the organization owns contoso.com.</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| extend UPN = tostring(parse_json(Members)[0].Upn)
| where UPN !endswith "contoso.com"
| where parse_json(Members)[0].Role == 3
| project TeamName, Operation, UserId, Members, UPN
```

> [!TIP]
> <span data-ttu-id="d6852-228">Pour en savoir plus sur les types d’accès externe et invité dans Teams, consultez [cet article](./communicate-with-users-from-other-organizations.md)ou la section *Types de participants* dans le [Guide de la sécurité Teams](./teams-security-guide.md).</span><span class="sxs-lookup"><span data-stu-id="d6852-228">To learn more about External and Guest access types in Teams see [this article](./communicate-with-users-from-other-organizations.md), or the *Participant Types* section in the [Teams Security Guide](./teams-security-guide.md).</span></span>

#### <a name="who-recently-joined--whose-role-changed"></a><span data-ttu-id="d6852-229">Les personnes qui ont récemment rejoint/dont le rôle a changé</span><span class="sxs-lookup"><span data-stu-id="d6852-229">Who recently joined / Whose role changed</span></span>

<span data-ttu-id="d6852-230">Interrogez un utilisateur spécifique pour vérifier s’il a été ajouté à un canal Teams au cours des 7 derniers jours ou dans une semaine :</span><span class="sxs-lookup"><span data-stu-id="d6852-230">Query a specific user to check if they were added to a Teams channel in the last 7 days, or within a week:</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members contains "UserName"
```

<span data-ttu-id="d6852-231">Le rôle d’un utilisateur a changé pour une équipe au cours des 7 derniers jours :</span><span class="sxs-lookup"><span data-stu-id="d6852-231">Was a user's role changed for a Team in the last 7 days:</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| where Members contains "Role" and Members contains "1"
```

#### <a name="external-users-from-unknown-or-new-organizations"></a><span data-ttu-id="d6852-232">Utilisateurs externes provenant d’organisations inconnues ou nouvelles</span><span class="sxs-lookup"><span data-stu-id="d6852-232">External users from unknown or new organizations</span></span>

<span data-ttu-id="d6852-233">Dans Teams, vous pouvez ajouter des utilisateurs externes à votre environnement ou canaux.</span><span class="sxs-lookup"><span data-stu-id="d6852-233">In Teams, you can add external users to your environment or channels.</span></span> <span data-ttu-id="d6852-234">Les organisations ont souvent un nombre limité de partenariats clés et ajoutent des utilisateurs parmi ces partenaires.</span><span class="sxs-lookup"><span data-stu-id="d6852-234">Organizations often have a limited number of key partnerships and add users from among these partners.</span></span> <span data-ttu-id="d6852-235">Cet KQL examine les utilisateurs externes ajoutés à des équipes qui proviennent d’organisations qui n’ont pas encore été consultées ou ajoutées.</span><span class="sxs-lookup"><span data-stu-id="d6852-235">This KQL looks at external users added to teams who come from organizations that haven't been seen or added before.</span></span>

```kusto
// If you have more than 14 days worth of Teams data change this value 
let data_date = 14d; 
// If you want to look at users further back than the last day change this value 
let lookback_data = 1d; 
let known_orgs = ( 
TeamsData  
| where TimeGenerated > ago(data_date) 
| where Operation =~ "MemberAdded" or Operation =~ "TeamsSessionStarted" 
// Extract the correct UPN and parse our external organization domain 
| extend UPN = iif(Operation == "MemberAdded", tostring(parse_json(Members)[0].UPN), UserId) 
| extend Organization = tostring(split(split(UPN, "_")[1], "#")[0]) 
| where isnotempty(Organization) 
| summarize by Organization); 
TeamsData  
| where TimeGenerated > ago(lookback_data) 
| where Operation =~ "MemberAdded" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| extend Organization = tostring(split(split(UPN, "_")[1], "#")[0]) 
| where isnotempty(Organization) 
| where Organization !in (known_orgs) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = UPN 
```

#### <a name="external-users-who-were-added-and-then-removed"></a><span data-ttu-id="d6852-236">Utilisateurs externes ajoutés et supprimés</span><span class="sxs-lookup"><span data-stu-id="d6852-236">External users who were added and then removed</span></span>

<span data-ttu-id="d6852-237">Les intrus disposant d’un niveau d’accès existant peuvent ajouter un nouveau compte externe à Teams pour accéder aux données et les exfiltrer.</span><span class="sxs-lookup"><span data-stu-id="d6852-237">Attackers with some level of existing access may add a new external account to Teams to access and exfiltrate data.</span></span> <span data-ttu-id="d6852-238">Ils peuvent également supprimer rapidement cet utilisateur afin de masquer le fait qu’il ait rendu l’accès.</span><span class="sxs-lookup"><span data-stu-id="d6852-238">They may also quickly remove that user to hide that they made access.</span></span> <span data-ttu-id="d6852-239">Cette requête recherche les comptes externes ajoutés à Teams et supprimés rapidement pour vous permettre d’identifier le comportement suspect.</span><span class="sxs-lookup"><span data-stu-id="d6852-239">This query hunts for external accounts that are added to Teams and swiftly removed to help identify suspicious behavior.</span></span>

```kusto
// If you want to look at user added further than 7 days ago adjust this value 
let time_ago = 7d; 
// If you want to change the timeframe of how quickly accounts need to be added and removed change this value 
let time_delta = 1h; 
TeamsData  
| where TimeGenerated > ago(time_ago) 
| where Operation =~ "MemberAdded" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| project TimeAdded=TimeGenerated, Operation, UPN, UserWhoAdded = UserId, TeamName, TeamGuid = tostring(Details.TeamGuid) 
| join ( 
TeamsData  
| where TimeGenerated > ago(time_ago) 
| where Operation =~ "MemberRemoved" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| project TimeDeleted=TimeGenerated, Operation, UPN, UserWhoDeleted = UserId, TeamName, TeamGuid = tostring(Details.TeamGuid)) on UPN, TeamGuid 
| where TimeDeleted < (TimeAdded + time_delta) 
| project TimeAdded, TimeDeleted, UPN, UserWhoAdded, UserWhoDeleted, TeamName, TeamGuid 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeAdded, AccountCustomEntity = UPN 
```

#### <a name="new-bot-or-application-added"></a><span data-ttu-id="d6852-240">Nouveau bot ou application ajouté</span><span class="sxs-lookup"><span data-stu-id="d6852-240">New bot or application added</span></span>

<span data-ttu-id="d6852-241">Teams a la possibilité d'inclure des applications ou des bots au sein d'une équipe pour étendre l'ensemble des fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="d6852-241">Teams has the ability to include apps or bots in a Team to extend the feature set.</span></span> <span data-ttu-id="d6852-242">Cela inclut les applications et bots personnalisés.</span><span class="sxs-lookup"><span data-stu-id="d6852-242">This includes custom apps and bots.</span></span> <span data-ttu-id="d6852-243">Dans certains cas, une application ou un bot peut être utilisé pour établir une persistance dans Teams sans avoir besoin d’un compte d’utilisateur, mais également d’accéder à des fichiers et d’autres données.</span><span class="sxs-lookup"><span data-stu-id="d6852-243">In some cases, an app or bot could be used to establish persistence in Teams without needing a user account, as well as access files and other data.</span></span> <span data-ttu-id="d6852-244">Cette requête permet de repérer les applications ou les bots qui sont nouveaux pour Teams.</span><span class="sxs-lookup"><span data-stu-id="d6852-244">This query hunts for apps or bots that are new to Teams.</span></span>

```kusto
// If you have more than 14 days worth of Teams data change this value 
let data_date = 14d; 
let historical_bots = ( 
TeamsData 
| where TimeGenerated > ago(data_date) 
| where isnotempty(AddOnName) 
| project AddOnName); 
TeamsData 
| where TimeGenerated > ago(1d) 
// Look for add-ins we have never seen before 
| where AddOnName in (historical_bots) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = UserId 
```

#### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a><span data-ttu-id="d6852-245">Comptes d’utilisateur propriétaires d’un grand nombre d’équipes</span><span class="sxs-lookup"><span data-stu-id="d6852-245">User accounts who are Owners of large numbers of Teams</span></span>

<span data-ttu-id="d6852-246">Les attaquants cherchant à élever leur privilège s’attribuent généralement les privilèges de propriétaire de nombreuses équipes, tandis que, généralement, les utilisateurs normaux créent et possèdent un petit nombre d’équipes centrées sur certains sujets.</span><span class="sxs-lookup"><span data-stu-id="d6852-246">Attackers looking to elevate their privileges may assign themselves Owner privileges of a large number of diverse teams, when, usually, users create and own a small number of teams around specific topics.</span></span> <span data-ttu-id="d6852-247">Cette requête KQL recherche un comportement suspect.</span><span class="sxs-lookup"><span data-stu-id="d6852-247">This KQL query looks for suspicious behavior.</span></span>

```kusto
// Adjust this value to change how many teams a user is made owner of before detecting 
let max_owner_count = 3; 
// Change this value to adjust how larger timeframe the query is run over. 
let time_window = 1d; 
let high_owner_count = (TeamsData 
| where TimeGenerated > ago(time_window) 
| where Operation =~ "MemberRoleChanged" 
| extend Member = tostring(parse_json(Members)[0].UPN)  
| extend NewRole = toint(parse_json(Members)[0].Role)  
| where NewRole == 2 
| summarize dcount(TeamName) by Member 
| where dcount_TeamName > max_owner_count 
| project Member); 
TeamsData 
| where TimeGenerated > ago(time_window) 
| where Operation =~ "MemberRoleChanged" 
| extend Member = tostring(parse_json(Members)[0].UPN)  
| extend NewRole = toint(parse_json(Members)[0].Role)  
| where NewRole == 2 
| where Member in (high_owner_count) 
| extend TeamGuid = tostring(Details.TeamGuid) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = Member 
```

#### <a name="many-team-deletions-by-a-single-user"></a><span data-ttu-id="d6852-248">Nombreuses suppressions d’équipe effectuées par un seul utilisateur</span><span class="sxs-lookup"><span data-stu-id="d6852-248">Many Team deletions by a single user</span></span>

<span data-ttu-id="d6852-249">Les agresseurs peuvent provoquer des interruptions et compromettre les projets et les données en supprimant plusieurs équipes.</span><span class="sxs-lookup"><span data-stu-id="d6852-249">Attackers can cause disruptions and jeopardize projects and data by deleting multiple teams.</span></span> <span data-ttu-id="d6852-250">Les équipes étant généralement supprimées par des propriétaires individuels, une suppression centrale de nombreuses équipes peut poser problème.</span><span class="sxs-lookup"><span data-stu-id="d6852-250">Because teams are generally deleted by individual Owners, a central deletion of many teams can be a sign of trouble.</span></span> <span data-ttu-id="d6852-251">Ce KQL recherche les utilisateurs individuels qui suppriment plusieurs équipes.</span><span class="sxs-lookup"><span data-stu-id="d6852-251">This KQL looks for single users who delete multiple teams.</span></span>

```kusto
 // Adjust this value to change how many Teams should be deleted before including
 let max_delete = 3;
 // Adjust this value to change the timewindow the query runs over
 let time_window = 1d;
 let deleting_users = (
 TeamsData 
 | where TimeGenerated > ago(time_window)
 | where Operation =~ "TeamDeleted"
 | summarize count() by UserId
 | where count_ > max_delete
 | project UserId);
 TeamsData
 | where TimeGenerated > ago(time_window)
 | where Operation =~ "TeamDeleted"
 | where UserId in (deleting_users)
 | extend TeamGuid = tostring(Details.TeamGuid)
 | project-away AddOnName, Members, Settings
 // Uncomment the following line to map query entities is you plan to use this as a detection query
 //| extend timestamp = TimeGenerated, AccountCustomEntity = UserId
```

#### <a name="expanding-your-thread-hunting-opportunities"></a><span data-ttu-id="d6852-252">Développez vos opportunités de repérage de menaces</span><span class="sxs-lookup"><span data-stu-id="d6852-252">Expanding your thread hunting opportunities</span></span>

<span data-ttu-id="d6852-253">Vous pouvez développer votre repérage en combinant des requêtes provenant de ressources telles qu’Azure Active Directory (Azure AD), ou d’autres charges de travail Office 365 avec vos requêtes Teams.</span><span class="sxs-lookup"><span data-stu-id="d6852-253">You can expand your hunting by combining queries from resources like Azure Active Directory (Azure AD), or other Office 365 workloads with your Teams queries.</span></span> <span data-ttu-id="d6852-254">Par exemple, vous combinez la détection de modèles suspects dans Azure AD SigninLogs et vous utilisez ces informations pendant la recherche de propriétaires Teams.</span><span class="sxs-lookup"><span data-stu-id="d6852-254">One example is combining detection of suspicious patterns in Azure AD SigninLogs, and using that information while hunting for Team Owners.</span></span>

```kusto
let timeRange = 1d;
let lookBack = 7d;
let threshold_Failed = 5;
let threshold_FailedwithSingleIP = 20;
let threshold_IPAddressCount = 2;
let isGUID = "[0-9a-z]{8}-[0-9a-z]{4}-[0-9a-z]{4}-[0-9a-z]{4}-[0-9a-z]{12}";
let azPortalSignins = SigninLogs
| where TimeGenerated >= ago(timeRange)
// Azure Portal only and exclude non-failure Result Types
| where AppDisplayName has "Azure Portal" and ResultType !in ("0", "50125", "50140")
// Tagging identities not resolved to friendly names
| extend Unresolved = iff(Identity matches regex isGUID, true, false);
// Lookup up resolved identities from last 7 days
let identityLookup = SigninLogs
| where TimeGenerated >= ago(lookBack)
| where not(Identity matches regex isGUID)
| summarize by UserId, lu_UserDisplayName = UserDisplayName, lu_UserPrincipalName = UserPrincipalName;
// Join resolved names to unresolved list from portal signins
let unresolvedNames = azPortalSignins | where Unresolved == true | join kind= inner (
   identityLookup ) on UserId
| extend UserDisplayName = lu_UserDisplayName, UserPrincipalName = lu_UserPrincipalName
| project-away lu_UserDisplayName, lu_UserPrincipalName;
// Join Signins that had resolved names with list of unresolved that now have a resolved name
let u_azPortalSignins = azPortalSignins | where Unresolved == false | union unresolvedNames;
let failed_signins = (u_azPortalSignins
| extend Status = strcat(ResultType, ": ", ResultDescription), OS = tostring(DeviceDetail.operatingSystem), Browser = tostring(DeviceDetail.browser)
| extend FullLocation = strcat(Location,'|', LocationDetails.state, '|', LocationDetails.city)
| summarize TimeGenerated = makelist(TimeGenerated), Status = makelist(Status), IPAddresses = makelist(IPAddress), IPAddressCount = dcount(IPAddress), FailedLogonCount = count()
by UserPrincipalName, UserId, UserDisplayName, AppDisplayName, Browser, OS, FullLocation
| mvexpand TimeGenerated, IPAddresses, Status
| extend TimeGenerated = todatetime(tostring(TimeGenerated)), IPAddress = tostring(IPAddresses), Status = tostring(Status)
| project-away IPAddresses
| summarize StartTime = min(TimeGenerated), EndTime = max(TimeGenerated) by UserPrincipalName, UserId, UserDisplayName, Status, FailedLogonCount, IPAddress, IPAddressCount, AppDisplayName, Browser, OS, FullLocation
| where (IPAddressCount >= threshold_IPAddressCount and FailedLogonCount >= threshold_Failed) or FailedLogonCount >= threshold_FailedwithSingleIP
| project UserPrincipalName);
TeamsData
| where TimeGenerated > ago(time_window)
| where Operation =~ "MemberRoleChanged"
| extend Member = tostring(parse_json(Members)[0].UPN) 
| extend NewRole = toint(parse_json(Members)[0].Role) 
| where NewRole == 2
| where Member in (failed_signins)
| extend TeamGuid = tostring(Details.TeamGuid)
```

<span data-ttu-id="d6852-255">De plus, vous pouvez rendre les détections SigninLogs spécifiques à Teams en ajoutant un filtre pour les connexions basées sur Teams uniquement à l’aide des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="d6852-255">Also, you can make the SigninLogs detections specific to Teams by adding a filter for only Teams-based sign-ins by using:</span></span>

```kusto
| where AppDisplayName startswith "Microsoft Teams"
```

<span data-ttu-id="d6852-256">Pour vous aider à expliquer `where AppDisplayName starts with "Microsoft Teams"` plus loin, la KQL ci-dessous montre une connexion réussie à partir d’une adresse IP avec un échec provenant d’une adresse IP différente, mais réservé uniquement aux connexions Teams :</span><span class="sxs-lookup"><span data-stu-id="d6852-256">To help explain using `where AppDisplayName starts with "Microsoft Teams"` further, the KQL below demonstrates a successful logon from one IP address with failure from a different IP address, but scoped only to Teams sign-ins:</span></span>

```kusto
let timeFrame = 1d;
let logonDiff = 10m;
SigninLogs 
  | where TimeGenerated >= ago(timeFrame) 
  | where ResultType == "0" 
  | where AppDisplayName startswith "Microsoft Teams"
  | project SuccessLogonTime = TimeGenerated, UserPrincipalName, SuccessIPAddress = IPAddress, AppDisplayName, SuccessIPBlock = strcat(split(IPAddress, ".")[0], ".", split(IPAddress, ".")[1])
  | join kind= inner (
      SigninLogs 
      | where TimeGenerated >= ago(timeFrame) 
      | where ResultType !in ("0", "50140") 
      | where ResultDescription !~ "Other"  
      | where AppDisplayName startswith "Microsoft Teams"
      | project FailedLogonTime = TimeGenerated, UserPrincipalName, FailedIPAddress = IPAddress, AppDisplayName, ResultType, ResultDescription
  ) on UserPrincipalName, AppDisplayName 
  | where SuccessLogonTime < FailedLogonTime and FailedLogonTime - SuccessLogonTime <= logonDiff and FailedIPAddress !startswith SuccessIPBlock
  | summarize FailedLogonTime = max(FailedLogonTime), SuccessLogonTime = max(SuccessLogonTime) by UserPrincipalName, SuccessIPAddress, AppDisplayName, FailedIPAddress, ResultType, ResultDescription 
  | extend timestamp = SuccessLogonTime, AccountCustomEntity = UserPrincipalName, IPCustomEntity = SuccessIPAddress
```

## <a name="important-information-and-updates"></a><span data-ttu-id="d6852-257">Informations et mises à jour importantes</span><span class="sxs-lookup"><span data-stu-id="d6852-257">Important information and updates</span></span>

<span data-ttu-id="d6852-258">**Nous vous remercions pour la collaboration au contenu, Pete Bryan, Nicholas DiCola et Matthew Martin.**</span><span class="sxs-lookup"><span data-stu-id="d6852-258">**Thank you for content collaboration, Pete Bryan, Nicholas DiCola, and Matthew Lowe.**</span></span> <span data-ttu-id="d6852-259">Pete Bryan et les personnes avec lesquelles il collabore continueront à développer des requêtes de détection et de repérage pour Teams. Veillez donc à rester en contact avec ce référentiel [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) pour les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="d6852-259">Pete Bryan and the people he collaborates with will continue to develop detection and hunting queries for Teams, so keep in touch with this [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) repository for updates.</span></span>  <span data-ttu-id="d6852-260">Surveiller les mises à jour de l’[analyseur](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) et [ application logique](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) utilisés dans cet article.</span><span class="sxs-lookup"><span data-stu-id="d6852-260">Monitor for updates to the [parser](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) and [logic app](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) used in this article.</span></span> <span data-ttu-id="d6852-261">Vous pouvez également participer et contribuer à la [communauté Azure Sentinel](https://github.com/Azure/Azure-Sentinel/wiki).</span><span class="sxs-lookup"><span data-stu-id="d6852-261">You can also join and contribute to the [Azure Sentinel community](https://github.com/Azure/Azure-Sentinel/wiki).</span></span> <span data-ttu-id="d6852-262">Merci !</span><span class="sxs-lookup"><span data-stu-id="d6852-262">Thank you!</span></span> <span data-ttu-id="d6852-263">Bon repérage.</span><span class="sxs-lookup"><span data-stu-id="d6852-263">Happy hunting.</span></span>

[<span data-ttu-id="d6852-264">Inscrire votre application dans Azure AD</span><span class="sxs-lookup"><span data-stu-id="d6852-264">Registering your application in Azure AD</span></span>](/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[<span data-ttu-id="d6852-265">Activer ou désactiver la recherche dans le journal d’audit</span><span class="sxs-lookup"><span data-stu-id="d6852-265">Turn audit log search on or off</span></span>](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%c2%a0)

[<span data-ttu-id="d6852-266">Qu’est-ce que Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="d6852-266">What is Azure Sentinel</span></span>](/azure/sentinel/overview)
