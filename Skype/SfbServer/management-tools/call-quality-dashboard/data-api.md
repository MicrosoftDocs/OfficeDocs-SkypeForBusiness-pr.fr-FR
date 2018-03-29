---
title: Données API pour le tableau de bord (CQD) appel qualité dans Skype pour Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Résumé : Découvrez le Rata API d’appel de tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 038324064177c110c0736092985e9da1b330ea8b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server-2015"></a><span data-ttu-id="8e84e-104">Données API pour le tableau de bord (CQD) appel qualité dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8e84e-104">Data API for Call Quality Dashboard (CQD) in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8e84e-105">**Résumé :** Obtenir des informations sur l’API de Rata pour tableau de bord qualité appel.</span><span class="sxs-lookup"><span data-stu-id="8e84e-105">**Summary:** Learn about the Rata API for Call Quality Dashboard.</span></span> <span data-ttu-id="8e84e-106">Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8e84e-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="8e84e-107">L’API de données permet d’accéder par programmation pour appeler le tableau de bord qualité pour Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8e84e-107">The Data API provides programmatic access for Call Quality Dashboard for Skype for Business Server 2015.</span></span>
  
## <a name="data-api-for-call-quality-dashboard"></a><span data-ttu-id="8e84e-108">API de données pour le tableau de bord qualité appel</span><span class="sxs-lookup"><span data-stu-id="8e84e-108">Data API for Call Quality Dashboard</span></span>

<span data-ttu-id="8e84e-109">L’API de données offre une interface de requête au QoE Cube.</span><span class="sxs-lookup"><span data-stu-id="8e84e-109">The Data API offers a query interface to the QoE Cube.</span></span> <span data-ttu-id="8e84e-110">L’API de données est une API REST pour travailler avec une base de données multidimensionnelle qui fournit des métriques de QoE agrégées en fonction des filtres et des dimensions spécifiées.</span><span class="sxs-lookup"><span data-stu-id="8e84e-110">The Data API is a REST API for working with multi-dimensional database that provides aggregated QoE metrics based on specified dimensions and filters.</span></span>
  
<span data-ttu-id="8e84e-111">Les opérations de repos sont incluses dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="8e84e-111">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="8e84e-112">**Opération**</span><span class="sxs-lookup"><span data-stu-id="8e84e-112">**Operation**</span></span>|<span data-ttu-id="8e84e-113">**Description**</span><span class="sxs-lookup"><span data-stu-id="8e84e-113">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="8e84e-114">Obtenir le Cube</span><span class="sxs-lookup"><span data-stu-id="8e84e-114">Get Cube</span></span>](get-cube.md) <br/> |<span data-ttu-id="8e84e-115">Obtenir la liste des dimensions disponibles et des mesures.</span><span class="sxs-lookup"><span data-stu-id="8e84e-115">Get the list of available dimensions and measurements.</span></span>  <br/> |
|[<span data-ttu-id="8e84e-116">Obtenir les membres de Dimension</span><span class="sxs-lookup"><span data-stu-id="8e84e-116">Get Dimension Members</span></span>](get-dimension-members.md) <br/> |<span data-ttu-id="8e84e-117">Opération d’obtention de membres de Dimension renvoie la liste des membres d’une dimension spécifique.</span><span class="sxs-lookup"><span data-stu-id="8e84e-117">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="8e84e-118">Cela donne aussi la possibilité de filtrer la liste des membres et obtenir un sous-ensemble, afin de réduire le coût de transfert de fil.</span><span class="sxs-lookup"><span data-stu-id="8e84e-118">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>  <br/> |
|[<span data-ttu-id="8e84e-119">Exécuter requête</span><span class="sxs-lookup"><span data-stu-id="8e84e-119">Run Query</span></span>](run-query.md) <br/> |<span data-ttu-id="8e84e-120">Exécuter la requête d’opération fournit la possibilité d’exécuter une requête sur le cube basé sur les filtres, les mesures et les dimensions spécifiées et renvoyer de nouveau les données.</span><span class="sxs-lookup"><span data-stu-id="8e84e-120">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>  <br/> |
|[<span data-ttu-id="8e84e-121">Vider le Cache</span><span class="sxs-lookup"><span data-stu-id="8e84e-121">Clear Cache</span></span>](clear-cache.md) <br/> |<span data-ttu-id="8e84e-122">Opération d’effacement du Cache supprime le cache sur le serveur pour les requêtes et les données.</span><span class="sxs-lookup"><span data-stu-id="8e84e-122">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="8e84e-123">Cela réinitialisera le cache et nous allons les données actualisées QoE cube par la suite pour les nouvelles demandes.</span><span class="sxs-lookup"><span data-stu-id="8e84e-123">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>  <br/> |
|[<span data-ttu-id="8e84e-124">Obtenir le journal d’intégration</span><span class="sxs-lookup"><span data-stu-id="8e84e-124">Get Integration Log</span></span>](get-integration-log.md) <br/> |<span data-ttu-id="8e84e-125">Obtenir le journal d’intégration opération retourne une liste d’entrées de journal décrivant les activités QoE cube de traitement.</span><span class="sxs-lookup"><span data-stu-id="8e84e-125">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>  <br/> |
|[<span data-ttu-id="8e84e-126">Obtenir les dernières données d’intégration</span><span class="sxs-lookup"><span data-stu-id="8e84e-126">Get Last Integration Data</span></span>](get-last-integration-data.md) <br/> |<span data-ttu-id="8e84e-127">Obtenir les dernières données d’intégration à partir du cube.</span><span class="sxs-lookup"><span data-stu-id="8e84e-127">Get the last integration data from the cube.</span></span>  <br/> |
   
 <span data-ttu-id="8e84e-128">**La prise en charge des données API (CORS) le partage des ressources entre-origine**</span><span class="sxs-lookup"><span data-stu-id="8e84e-128">**Cross-Origin Resource Sharing (CORS) Support for Data API**</span></span>
  
<span data-ttu-id="8e84e-129">API de données prend en charge le partage de ressources entre origine (CORS).</span><span class="sxs-lookup"><span data-stu-id="8e84e-129">Data API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="8e84e-130">CORS est une fonctionnalité HTTP qui permet à une application web en cours d’exécution dans un domaine d’accéder aux ressources dans un autre domaine.</span><span class="sxs-lookup"><span data-stu-id="8e84e-130">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="8e84e-131">Navigateurs Web implémentent une restriction de sécurité appelée stratégie de même origine [Stratégie de même origine](https://www.w3.org/Security/wiki/Same_Origin_Policy) qui empêche une page web à partir de l’appel d’API dans un autre domaine.</span><span class="sxs-lookup"><span data-stu-id="8e84e-131">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="8e84e-132">CORS offre un moyen sécurisé pour permettre à un domaine (le domaine d’origine) appeler des API dans un autre domaine.</span><span class="sxs-lookup"><span data-stu-id="8e84e-132">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="8e84e-133">Consultez la [spécification de CORS](https://www.w3.org/TR/cors/) pour plus de détails sur les CORS.</span><span class="sxs-lookup"><span data-stu-id="8e84e-133">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="8e84e-134">**L’activation de CORS pour données API**</span><span class="sxs-lookup"><span data-stu-id="8e84e-134">**Enabling CORS for Data API**</span></span>
  
 <span data-ttu-id="8e84e-135">Voici un extrait du fichier web.config de données API, montrant deux domaines répertoriés dans les paramètres de l’application corsTrustedOrigin.</span><span class="sxs-lookup"><span data-stu-id="8e84e-135">The following is an excerpt of Data API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="8e84e-136">Toutes les demandes effectuées par les scripts chargés à partir de ces serveurs sont approuvés par les API de données.</span><span class="sxs-lookup"><span data-stu-id="8e84e-136">All requests made by the scripts loaded from these servers are trusted by Data API.</span></span>
  
<span data-ttu-id="8e84e-137">N’oubliez pas d’inclure le protocole exact, le nom d’hôte et le port (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="8e84e-137">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="8e84e-138">Ne pas pour placer les oblique (/) de caractère à la fin.</span><span class="sxs-lookup"><span data-stu-id="8e84e-138">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="8e84e-139">Plusieurs entrées peuvent être spécifiées en les séparant par des virgules.</span><span class="sxs-lookup"><span data-stu-id="8e84e-139">Multiple entries can be specified by separating with commas.</span></span>
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>

```


