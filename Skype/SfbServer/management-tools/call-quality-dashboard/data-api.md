---
title: API de données pour l’appel de tableau de bord qualité (CQD) dans Skype pour Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Résumé : Découvrez l’API Rata pour le tableau de bord de qualité des appels. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.'
ms.openlocfilehash: 0af168c46e8b2732d5c967550391ab52459ddf95
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531756"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="cf24b-104">API de données pour l’appel de tableau de bord qualité (CQD) dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="cf24b-104">Data API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="cf24b-105">**Résumé :** Découvrez l’API Rata pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="cf24b-105">**Summary:** Learn about the Rata API for Call Quality Dashboard.</span></span> <span data-ttu-id="cf24b-106">Tableau de bord de qualité des appels est un outil de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="cf24b-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="cf24b-107">L’API de données fournit l’accès par programme pour appeler le tableau de bord qualité pour Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="cf24b-107">The Data API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="data-api-for-call-quality-dashboard"></a><span data-ttu-id="cf24b-108">API de données pour le tableau de bord de qualité des appels</span><span class="sxs-lookup"><span data-stu-id="cf24b-108">Data API for Call Quality Dashboard</span></span>

<span data-ttu-id="cf24b-109">L’API de données offre une interface de requête au QoE Cube.</span><span class="sxs-lookup"><span data-stu-id="cf24b-109">The Data API offers a query interface to the QoE Cube.</span></span> <span data-ttu-id="cf24b-110">L’API de données est une API REST pour travailler avec une base de données multidimensionnelle qui fournit les mesures QoE agrégées selon les filtres et les dimensions spécifiées.</span><span class="sxs-lookup"><span data-stu-id="cf24b-110">The Data API is a REST API for working with multi-dimensional database that provides aggregated QoE metrics based on specified dimensions and filters.</span></span>
  
<span data-ttu-id="cf24b-111">Les opérations REST sont incluses dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="cf24b-111">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="cf24b-112">**Opération**</span><span class="sxs-lookup"><span data-stu-id="cf24b-112">**Operation**</span></span>|<span data-ttu-id="cf24b-113">**Description**</span><span class="sxs-lookup"><span data-stu-id="cf24b-113">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="cf24b-114">Obtenir le Cube</span><span class="sxs-lookup"><span data-stu-id="cf24b-114">Get Cube</span></span>](get-cube.md) <br/> |<span data-ttu-id="cf24b-115">Obtenir la liste des dimensions disponibles et des mesures.</span><span class="sxs-lookup"><span data-stu-id="cf24b-115">Get the list of available dimensions and measurements.</span></span>  <br/> |
|[<span data-ttu-id="cf24b-116">Obtenir les membres de Dimension</span><span class="sxs-lookup"><span data-stu-id="cf24b-116">Get Dimension Members</span></span>](get-dimension-members.md) <br/> |<span data-ttu-id="cf24b-117">Opération de membres de Dimension Get renvoie la liste des membres d’une dimension spécifique.</span><span class="sxs-lookup"><span data-stu-id="cf24b-117">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="cf24b-118">Cela donne aussi la possibilité de filtrer la liste des membres et obtenir un sous-ensemble, afin de réduire le coût de transfert filaire.</span><span class="sxs-lookup"><span data-stu-id="cf24b-118">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>  <br/> |
|[<span data-ttu-id="cf24b-119">Exécuter la requête</span><span class="sxs-lookup"><span data-stu-id="cf24b-119">Run Query</span></span>](run-query.md) <br/> |<span data-ttu-id="cf24b-120">Exécuter la requête d’opération offre la possibilité d’exécuter une requête sur le cube basé sur des filtres, des mesures et dimensions spécifiées et renvoyer dans les données.</span><span class="sxs-lookup"><span data-stu-id="cf24b-120">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>  <br/> |
|[<span data-ttu-id="cf24b-121">Vider le Cache</span><span class="sxs-lookup"><span data-stu-id="cf24b-121">Clear Cache</span></span>](clear-cache.md) <br/> |<span data-ttu-id="cf24b-122">Opération de Cache Clear supprime le cache sur le serveur pour les requêtes et les données.</span><span class="sxs-lookup"><span data-stu-id="cf24b-122">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="cf24b-123">Le cache seront réinitialisés et nous allons les données du cube QoE ultérieurement pour de nouvelles demandes.</span><span class="sxs-lookup"><span data-stu-id="cf24b-123">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>  <br/> |
|[<span data-ttu-id="cf24b-124">Obtenir le journal d’intégration</span><span class="sxs-lookup"><span data-stu-id="cf24b-124">Get Integration Log</span></span>](get-integration-log.md) <br/> |<span data-ttu-id="cf24b-125">Obtenir le journal d’intégration opération retourne une liste d’entrées de journal décrivant les activités dans le QoE Cube.</span><span class="sxs-lookup"><span data-stu-id="cf24b-125">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>  <br/> |
|[<span data-ttu-id="cf24b-126">Obtenir des données de l’intégration de la dernières</span><span class="sxs-lookup"><span data-stu-id="cf24b-126">Get Last Integration Data</span></span>](get-last-integration-data.md) <br/> |<span data-ttu-id="cf24b-127">Obtenir les dernières données de l’intégration du cube.</span><span class="sxs-lookup"><span data-stu-id="cf24b-127">Get the last integration data from the cube.</span></span>  <br/> |
   
 <span data-ttu-id="cf24b-128">**Ressources Cross-Origin (CORS) prise en charge pour les API de données de partage**</span><span class="sxs-lookup"><span data-stu-id="cf24b-128">**Cross-Origin Resource Sharing (CORS) Support for Data API**</span></span>
  
<span data-ttu-id="cf24b-129">API de données prend en charge le partage de ressources Cross-Origin (CORS).</span><span class="sxs-lookup"><span data-stu-id="cf24b-129">Data API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="cf24b-130">CORS est une fonctionnalité HTTP qui permet à une application web en cours d’exécution dans un domaine d’accéder aux ressources dans un autre domaine.</span><span class="sxs-lookup"><span data-stu-id="cf24b-130">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="cf24b-131">Navigateurs Web implémentent une restriction de sécurité de stratégie de même origine [Stratégie de même origine](https://www.w3.org/Security/wiki/Same_Origin_Policy) qui empêche une page web d’appeler des API dans un domaine différent.</span><span class="sxs-lookup"><span data-stu-id="cf24b-131">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="cf24b-132">CORS fournit un moyen sécurisé pour autoriser un domaine (le domaine d’origine) appeler des API dans un autre domaine.</span><span class="sxs-lookup"><span data-stu-id="cf24b-132">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="cf24b-133">Voir les [spécifications CORS](https://www.w3.org/TR/cors/) pour plus d’informations sur CORS.</span><span class="sxs-lookup"><span data-stu-id="cf24b-133">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="cf24b-134">**Activer CORS d’API de données**</span><span class="sxs-lookup"><span data-stu-id="cf24b-134">**Enabling CORS for Data API**</span></span>
  
 <span data-ttu-id="cf24b-135">Voici un extrait du fichier web.config API de données, affichant deux domaines répertoriés dans les paramètres de l’application corsTrustedOrigin.</span><span class="sxs-lookup"><span data-stu-id="cf24b-135">The following is an excerpt of Data API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="cf24b-136">Toutes les demandes effectuées par les scripts chargés à partir de ces serveurs sont approuvés par l’API de données.</span><span class="sxs-lookup"><span data-stu-id="cf24b-136">All requests made by the scripts loaded from these servers are trusted by Data API.</span></span>
  
<span data-ttu-id="cf24b-137">N’oubliez pas d’inclure le protocole exact, le nom d’hôte et le port (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="cf24b-137">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="cf24b-138">Ne pas pour mettre les oblique (/) de caractères à la fin.</span><span class="sxs-lookup"><span data-stu-id="cf24b-138">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="cf24b-139">Plusieurs entrées peuvent être spécifiées en séparant par des virgules.</span><span class="sxs-lookup"><span data-stu-id="cf24b-139">Multiple entries can be specified by separating with commas.</span></span>
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


