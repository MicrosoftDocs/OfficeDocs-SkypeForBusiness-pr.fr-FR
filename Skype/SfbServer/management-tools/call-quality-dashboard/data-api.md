---
title: API de données pour le tableau de bord de qualité des appels (bord) dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Résumé : en savoir plus sur l’API de données pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 016cc1be9f5cd5506f8ee7d8ddbe2765e0015ffd
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2019
ms.locfileid: "36571918"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="5345d-104">API de données pour le tableau de bord de qualité des appels (bord) dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="5345d-104">Data API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="5345d-105">**Résumé :** En savoir plus sur l’API de données du tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="5345d-105">**Summary:** Learn about the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="5345d-106">Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="5345d-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="5345d-107">L’API de données fournit un accès par programmation pour le tableau de bord de qualité des appels pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="5345d-107">The Data API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="data-api-for-call-quality-dashboard"></a><span data-ttu-id="5345d-108">API de données pour le tableau de bord de qualité des appels</span><span class="sxs-lookup"><span data-stu-id="5345d-108">Data API for Call Quality Dashboard</span></span>

<span data-ttu-id="5345d-109">L’API de données fournit une interface de requête au cube QoE.</span><span class="sxs-lookup"><span data-stu-id="5345d-109">The Data API offers a query interface to the QoE Cube.</span></span> <span data-ttu-id="5345d-110">L’API de données est une API REST pour l’utilisation d’une base de données multidimensionnelle qui fournit des métriques QoE agrégées en fonction des dimensions et filtres spécifiés.</span><span class="sxs-lookup"><span data-stu-id="5345d-110">The Data API is a REST API for working with multi-dimensional database that provides aggregated QoE metrics based on specified dimensions and filters.</span></span>
  
<span data-ttu-id="5345d-111">Les opérations REST sont comprises dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="5345d-111">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="5345d-112">**Opération**</span><span class="sxs-lookup"><span data-stu-id="5345d-112">**Operation**</span></span>|<span data-ttu-id="5345d-113">**Description**</span><span class="sxs-lookup"><span data-stu-id="5345d-113">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="5345d-114">Obtenir un cube</span><span class="sxs-lookup"><span data-stu-id="5345d-114">Get Cube</span></span>](get-cube.md) <br/> |<span data-ttu-id="5345d-115">Obtenez la liste des dimensions et mesures disponibles.</span><span class="sxs-lookup"><span data-stu-id="5345d-115">Get the list of available dimensions and measurements.</span></span>  <br/> |
|[<span data-ttu-id="5345d-116">Obtenir les membres de dimension</span><span class="sxs-lookup"><span data-stu-id="5345d-116">Get Dimension Members</span></span>](get-dimension-members.md) <br/> |<span data-ttu-id="5345d-117">Opération obtenir les membres d’une dimension renvoie la liste des membres d’une dimension spécifique.</span><span class="sxs-lookup"><span data-stu-id="5345d-117">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="5345d-118">Vous pouvez également filtrer la liste des membres et obtenir un sous-ensemble afin de réduire le coût de transfert bancaire.</span><span class="sxs-lookup"><span data-stu-id="5345d-118">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>  <br/> |
|[<span data-ttu-id="5345d-119">Exécuter la requête</span><span class="sxs-lookup"><span data-stu-id="5345d-119">Run Query</span></span>](run-query.md) <br/> |<span data-ttu-id="5345d-120">L’opération exécuter une requête permet d’exécuter une requête sur le cube en fonction de dimensions, mesures et filtres spécifiés, puis de renvoyer les données.</span><span class="sxs-lookup"><span data-stu-id="5345d-120">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>  <br/> |
|[<span data-ttu-id="5345d-121">Vider le cache</span><span class="sxs-lookup"><span data-stu-id="5345d-121">Clear Cache</span></span>](clear-cache.md) <br/> |<span data-ttu-id="5345d-122">L’opération d’effacement du cache supprime le cache du serveur pour les requêtes et les données.</span><span class="sxs-lookup"><span data-stu-id="5345d-122">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="5345d-123">Cette opération a pour réinitialisation le cache et nous obtiendrons de nouvelles données du cube QoE par la suite pour de nouvelles demandes.</span><span class="sxs-lookup"><span data-stu-id="5345d-123">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>  <br/> |
|[<span data-ttu-id="5345d-124">Obtenir le journal d’intégration</span><span class="sxs-lookup"><span data-stu-id="5345d-124">Get Integration Log</span></span>](get-integration-log.md) <br/> |<span data-ttu-id="5345d-125">L’opération d’obtention du journal d’intégration renvoie une liste des entrées du journal décrivant les activités du traitement du cube QoE.</span><span class="sxs-lookup"><span data-stu-id="5345d-125">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>  <br/> |
|[<span data-ttu-id="5345d-126">Obtenir les données de la dernière intégration</span><span class="sxs-lookup"><span data-stu-id="5345d-126">Get Last Integration Data</span></span>](get-last-integration-data.md) <br/> |<span data-ttu-id="5345d-127">Obtenez les dernières données d’intégration du cube.</span><span class="sxs-lookup"><span data-stu-id="5345d-127">Get the last integration data from the cube.</span></span>  <br/> |
   
 <span data-ttu-id="5345d-128">**Prise en charge du partage de ressources intersession pour l’API de données**</span><span class="sxs-lookup"><span data-stu-id="5345d-128">**Cross-Origin Resource Sharing (CORS) Support for Data API**</span></span>
  
<span data-ttu-id="5345d-129">API de données prend en charge le partage de ressources à l’origine.</span><span class="sxs-lookup"><span data-stu-id="5345d-129">Data API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="5345d-130">CORS est une fonctionnalité HTTP qui permet à une application Web exécutée sous un domaine d’accéder aux ressources d’un autre domaine.</span><span class="sxs-lookup"><span data-stu-id="5345d-130">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="5345d-131">Les navigateurs Web mettent en œuvre une restriction de sécurité connue sous le nom de stratégie de [même origine qui](https://www.w3.org/Security/wiki/Same_Origin_Policy) empêche une page Web d’appeler des API dans un domaine différent.</span><span class="sxs-lookup"><span data-stu-id="5345d-131">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="5345d-132">CORS fournit un moyen sécurisé pour permettre à un domaine (domaine d’origine) d’appeler des API dans un autre domaine.</span><span class="sxs-lookup"><span data-stu-id="5345d-132">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="5345d-133">Pour plus d’informations sur l’affichage de l’une des [caractéristiques](https://www.w3.org/TR/cors/) de cors.</span><span class="sxs-lookup"><span data-stu-id="5345d-133">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="5345d-134">**Activation de l’API CORS pour les données**</span><span class="sxs-lookup"><span data-stu-id="5345d-134">**Enabling CORS for Data API**</span></span>
  
 <span data-ttu-id="5345d-135">Voici un extrait de l’API de données Web. config, montrant deux domaines répertoriés dans les paramètres de l’application corsTrustedOrigin.</span><span class="sxs-lookup"><span data-stu-id="5345d-135">The following is an excerpt of Data API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="5345d-136">Toutes les demandes effectuées par les scripts chargés à partir de ces serveurs sont approuvées par l’API de données.</span><span class="sxs-lookup"><span data-stu-id="5345d-136">All requests made by the scripts loaded from these servers are trusted by Data API.</span></span>
  
<span data-ttu-id="5345d-137">N’oubliez pas d’inclure le protocole, le nom d’hôte et le port exacts (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="5345d-137">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="5345d-138">Ne placez aucun caractère barre oblique (/) à la fin.</span><span class="sxs-lookup"><span data-stu-id="5345d-138">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="5345d-139">Plusieurs entrées peuvent être spécifiées en les séparant par des virgules.</span><span class="sxs-lookup"><span data-stu-id="5345d-139">Multiple entries can be specified by separating with commas.</span></span>
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


