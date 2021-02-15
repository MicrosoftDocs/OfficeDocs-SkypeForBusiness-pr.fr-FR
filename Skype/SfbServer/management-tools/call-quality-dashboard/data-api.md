---
title: API de données pour le tableau de bord de qualité des appels (CQD) dans Skype Entreprise Server
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
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Résumé : Découvrez l’API de données pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: 367aa1bf1103863fff37fbcd4f8d9fa379de7c1d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832694"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="38d30-104">API de données pour le tableau de bord de qualité des appels (CQD) dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="38d30-104">Data API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="38d30-105">**Résumé :** Découvrez l’API de données pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="38d30-105">**Summary:** Learn about the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="38d30-106">Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="38d30-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="38d30-107">L’API de données fournit un accès par programme pour le Tableau de bord de qualité des appels pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="38d30-107">The Data API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="data-api-for-call-quality-dashboard"></a><span data-ttu-id="38d30-108">API de données pour le tableau de bord de qualité des appels</span><span class="sxs-lookup"><span data-stu-id="38d30-108">Data API for Call Quality Dashboard</span></span>

<span data-ttu-id="38d30-109">L’API données offre une interface de requête au cube QoE.</span><span class="sxs-lookup"><span data-stu-id="38d30-109">The Data API offers a query interface to the QoE Cube.</span></span> <span data-ttu-id="38d30-110">L’API de données est une API REST permettant d’travailler avec une base de données multidimensionnelle qui fournit des mesures QoE agrégées basées sur des dimensions et des filtres spécifiés.</span><span class="sxs-lookup"><span data-stu-id="38d30-110">The Data API is a REST API for working with multi-dimensional database that provides aggregated QoE metrics based on specified dimensions and filters.</span></span>
  
<span data-ttu-id="38d30-111">Les opérations REST sont incluses dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="38d30-111">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="38d30-112">**Opération**</span><span class="sxs-lookup"><span data-stu-id="38d30-112">**Operation**</span></span>|<span data-ttu-id="38d30-113">**Description**</span><span class="sxs-lookup"><span data-stu-id="38d30-113">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="38d30-114">Obtenir un cube</span><span class="sxs-lookup"><span data-stu-id="38d30-114">Get Cube</span></span>](get-cube.md) <br/> |<span data-ttu-id="38d30-115">Obtenir la liste des dimensions et mesures disponibles.</span><span class="sxs-lookup"><span data-stu-id="38d30-115">Get the list of available dimensions and measurements.</span></span>  <br/> |
|[<span data-ttu-id="38d30-116">Obtenir les membres de dimension</span><span class="sxs-lookup"><span data-stu-id="38d30-116">Get Dimension Members</span></span>](get-dimension-members.md) <br/> |<span data-ttu-id="38d30-117">L’opération Obtenir les membres de dimension renvoie la liste des membres d’une dimension spécifique.</span><span class="sxs-lookup"><span data-stu-id="38d30-117">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="38d30-118">Il permet également de filtrer la liste des membres et d’obtenir un sous-ensemble, afin de réduire le coût de transfert de câblage.</span><span class="sxs-lookup"><span data-stu-id="38d30-118">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>  <br/> |
|[<span data-ttu-id="38d30-119">Exécuter la requête</span><span class="sxs-lookup"><span data-stu-id="38d30-119">Run Query</span></span>](run-query.md) <br/> |<span data-ttu-id="38d30-120">L’opération Exécuter une requête permet d’exécuter une requête sur le cube en fonction des dimensions, mesures et filtres spécifiés et de renvoyer les données.</span><span class="sxs-lookup"><span data-stu-id="38d30-120">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>  <br/> |
|[<span data-ttu-id="38d30-121">Vider le cache</span><span class="sxs-lookup"><span data-stu-id="38d30-121">Clear Cache</span></span>](clear-cache.md) <br/> |<span data-ttu-id="38d30-122">L’opération Effacer le cache supprime le cache sur le serveur pour les requêtes et les données.</span><span class="sxs-lookup"><span data-stu-id="38d30-122">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="38d30-123">Cela réinitialise le cache et nous allons obtenir des données à jour à partir du cube QoE par la suite pour les nouvelles demandes.</span><span class="sxs-lookup"><span data-stu-id="38d30-123">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>  <br/> |
|[<span data-ttu-id="38d30-124">Obtenir le journal d’intégration</span><span class="sxs-lookup"><span data-stu-id="38d30-124">Get Integration Log</span></span>](get-integration-log.md) <br/> |<span data-ttu-id="38d30-125">L’opération Obtenir le journal d’intégration renvoie une liste d’entrées de journal décrivant les activités dans le traitement du cube QoE.</span><span class="sxs-lookup"><span data-stu-id="38d30-125">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>  <br/> |
|[<span data-ttu-id="38d30-126">Obtenir les données de la dernière intégration</span><span class="sxs-lookup"><span data-stu-id="38d30-126">Get Last Integration Data</span></span>](get-last-integration-data.md) <br/> |<span data-ttu-id="38d30-127">Obtenez les dernières données d’intégration à partir du cube.</span><span class="sxs-lookup"><span data-stu-id="38d30-127">Get the last integration data from the cube.</span></span>  <br/> |
   
 <span data-ttu-id="38d30-128">**Prise en charge du partage de ressources d’origine croisée (CORS) pour l’API de données**</span><span class="sxs-lookup"><span data-stu-id="38d30-128">**Cross-Origin Resource Sharing (CORS) Support for Data API**</span></span>
  
<span data-ttu-id="38d30-129">L’API de données prend en charge le partage de ressources d’origine croisée (CORS).</span><span class="sxs-lookup"><span data-stu-id="38d30-129">Data API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="38d30-130">CORS est une fonctionnalité HTTP qui permet à une application web s’exécutant sous un domaine d’accéder aux ressources d’un autre domaine.</span><span class="sxs-lookup"><span data-stu-id="38d30-130">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="38d30-131">Les navigateurs web implémentent une restriction de sécurité appelée stratégie de même origine qui empêche une page web d’appeler des API dans un autre domaine. [](https://www.w3.org/Security/wiki/Same_Origin_Policy)</span><span class="sxs-lookup"><span data-stu-id="38d30-131">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="38d30-132">CORS offre un moyen sécurisé d’autoriser un domaine (le domaine d’origine) à appeler des API dans un autre domaine.</span><span class="sxs-lookup"><span data-stu-id="38d30-132">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="38d30-133">Pour plus [d’informations sur CORS,](https://www.w3.org/TR/cors/) voir la spécification CORS.</span><span class="sxs-lookup"><span data-stu-id="38d30-133">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="38d30-134">**Activation de CORS pour l’API de données**</span><span class="sxs-lookup"><span data-stu-id="38d30-134">**Enabling CORS for Data API**</span></span>
  
 <span data-ttu-id="38d30-135">Voici un extrait de données api web.config, montrant deux domaines répertoriés dans les paramètres de l’application corsTrustedOrigin.</span><span class="sxs-lookup"><span data-stu-id="38d30-135">The following is an excerpt of Data API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="38d30-136">Toutes les demandes faites par les scripts chargés à partir de ces serveurs sont fiables par l’API de données.</span><span class="sxs-lookup"><span data-stu-id="38d30-136">All requests made by the scripts loaded from these servers are trusted by Data API.</span></span>
  
<span data-ttu-id="38d30-137">N’oubliez pas d’inclure le protocole exact, le nom d’hôte et le port (le cas contraire).</span><span class="sxs-lookup"><span data-stu-id="38d30-137">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="38d30-138">Ne placez pas de barre oblique (/) à la fin.</span><span class="sxs-lookup"><span data-stu-id="38d30-138">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="38d30-139">Plusieurs entrées peuvent être spécifiées en les séparant par des virgules.</span><span class="sxs-lookup"><span data-stu-id="38d30-139">Multiple entries can be specified by separating with commas.</span></span>
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


