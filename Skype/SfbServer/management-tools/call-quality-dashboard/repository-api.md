---
title: API de référentiel pour le tableau de bord (CQD) appel qualité dans Skype pour Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 'Résumé : Découvrez l’API de référentiel pour le tableau de bord de qualité des appels. Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 7881766de0daf05c85c7dfe8bb85a0ef1344c7c9
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374722"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server-2015"></a><span data-ttu-id="d889b-104">API de référentiel pour le tableau de bord (CQD) appel qualité dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d889b-104">Repository API for Call Quality Dashboard (CQD) in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d889b-105">**Résumé :** Découvrez l’API de référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="d889b-105">**Summary:** Learn about the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="d889b-106">Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d889b-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="d889b-107">L’API de référentiel fournit l’accès par programme pour appeler le tableau de bord qualité pour Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d889b-107">The Repository API provides programmatic access for Call Quality Dashboard for Skype for Business Server 2015.</span></span>
  
## <a name="repository-api-for-call-quality-dashboard"></a><span data-ttu-id="d889b-108">API de référentiel pour le tableau de bord de qualité des appels</span><span class="sxs-lookup"><span data-stu-id="d889b-108">Repository API for Call Quality Dashboard</span></span>

<span data-ttu-id="d889b-109">API de référentiel offre une interface d’accès de données pour la base de données de référentiel.</span><span class="sxs-lookup"><span data-stu-id="d889b-109">Repository API offers a data access interface to repository database.</span></span> <span data-ttu-id="d889b-110">Le référentiel permet au contenu d’être organisées dans une structure d’arborescence ou graphique tels que les utilisateurs peuvent regrouper les façons que pertinent pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d889b-110">The repository allows the contents to be organized in a tree or graph structure such that users can group them in the ways that make sense to the users.</span></span> <span data-ttu-id="d889b-111">Le référentiel prend en charge deux types généraux d’utilisateurs : utilisateur du système, qui est un utilisateur intégrée représentant le référentiel et les utilisateurs régulières qui représentent les utilisateurs autorisés du référentiel.</span><span class="sxs-lookup"><span data-stu-id="d889b-111">The repository supports two general types of users: system user, which is a built-in user representing the repository, and regular users that represent the authorized users of the repository.</span></span>
  
<span data-ttu-id="d889b-112">API de référentiel se compose de trois services généraux :</span><span class="sxs-lookup"><span data-stu-id="d889b-112">Repository API consists of three general services:</span></span> 
  
- <span data-ttu-id="d889b-113">[Service utilisateur pour CQD](user-service.md) - pour l’accès aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d889b-113">[User Service for CQD](user-service.md) - for accessing Users.</span></span>
    
- <span data-ttu-id="d889b-114">[Service de l’élément de tableau de bord de qualité des appels (CQD)](item-service.md) - pour accéder aux éléments et le contenu stocké dans les éléments.</span><span class="sxs-lookup"><span data-stu-id="d889b-114">[Item Service for Call Quality Dashboard (CQD)](item-service.md) - for accessing Items and the contents stored in Items.</span></span>
    
- <span data-ttu-id="d889b-115">[Service de paramètres utilisateur de tableau de bord de qualité des appels (CQD)](user-settings-service.md) - pour accéder aux paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d889b-115">[User Settings Service for Call Quality Dashboard (CQD)](user-settings-service.md) - for accessing User Settings.</span></span>
    
<span data-ttu-id="d889b-116">Tableau de bord qualité appel utilise l’API de référentiel pour gérer les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="d889b-116">Call Quality Dashboard uses Repository API to manage the following information:</span></span> 
  
- <span data-ttu-id="d889b-117">**Utilisateur** : représentation des utilisateurs qui ont accès au référentiel.</span><span class="sxs-lookup"><span data-stu-id="d889b-117">**User** - representation of Users who have access to the repository.</span></span>
    
- <span data-ttu-id="d889b-118">**Rapport** - contient une liste de requêtes, stockées en tant que contenu dans les éléments du référentiel.</span><span class="sxs-lookup"><span data-stu-id="d889b-118">**Report** - contains a list of Queries, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="d889b-119">**Requête** - permet de récupérer des données à partir des API de données stockées en tant que contenu dans les éléments du référentiel.</span><span class="sxs-lookup"><span data-stu-id="d889b-119">**Query** - used to retrieve data from Data API, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="d889b-120">Le **Paramètre utilisateur** - décrit un comportement d’application facultative pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d889b-120">**User Setting** - describes an optional application behavior for the user.</span></span>
    
  <span data-ttu-id="d889b-121">**Ressources Cross-Origin (CORS) prise en charge pour l’API de référentiel de partage**</span><span class="sxs-lookup"><span data-stu-id="d889b-121">**Cross-Origin Resource Sharing (CORS) Support for Repository API**</span></span>
  
<span data-ttu-id="d889b-122">API de référentiel prend en charge le partage de ressources Cross-Origin (CORS).</span><span class="sxs-lookup"><span data-stu-id="d889b-122">Repository API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="d889b-123">CORS est une fonctionnalité HTTP qui permet à une application web en cours d’exécution dans un domaine d’accéder aux ressources dans un autre domaine.</span><span class="sxs-lookup"><span data-stu-id="d889b-123">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="d889b-124">Navigateurs Web implémentent une restriction de sécurité de stratégie de même origine [Stratégie de même origine](https://www.w3.org/Security/wiki/Same_Origin_Policy) qui empêche une page web d’appeler des API dans un domaine différent.</span><span class="sxs-lookup"><span data-stu-id="d889b-124">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="d889b-125">CORS fournit un moyen sécurisé pour autoriser un domaine (le domaine d’origine) appeler des API dans un autre domaine.</span><span class="sxs-lookup"><span data-stu-id="d889b-125">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="d889b-126">Voir les [spécifications CORS](https://www.w3.org/TR/cors/) pour plus d’informations sur CORS.</span><span class="sxs-lookup"><span data-stu-id="d889b-126">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="d889b-127">**Activer CORS d’API de référentiel**</span><span class="sxs-lookup"><span data-stu-id="d889b-127">**Enabling CORS for Repository API**</span></span>
  
 <span data-ttu-id="d889b-128">Voici un extrait du fichier web.config API de référentiel, affichant deux domaines répertoriés dans les paramètres de l’application corsTrustedOrigin.</span><span class="sxs-lookup"><span data-stu-id="d889b-128">The following is an excerpt of Repository API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="d889b-129">Toutes les demandes effectuées par les scripts chargés à partir de ces serveurs sont approuvés par l’API de référentiel.</span><span class="sxs-lookup"><span data-stu-id="d889b-129">All requests made by the scripts loaded from these servers are trusted by Repository API.</span></span>
  
<span data-ttu-id="d889b-130">N’oubliez pas d’inclure le protocole exact, le nom d’hôte et le port (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="d889b-130">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="d889b-131">Ne pas pour mettre les oblique (/) de caractères à la fin.</span><span class="sxs-lookup"><span data-stu-id="d889b-131">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="d889b-132">Plusieurs entrées peuvent être spécifiées en séparant par des virgules.</span><span class="sxs-lookup"><span data-stu-id="d889b-132">Multiple entries can be specified by separating with commas.</span></span>
  
```
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


