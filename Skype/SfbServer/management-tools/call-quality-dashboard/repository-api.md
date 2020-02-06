---
title: API du référentiel pour le tableau de bord de qualité des appels (bord) dans Skype entreprise Server
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
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 'Résumé : en savoir plus sur l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: a027cc7402bad7524343391f9bf7039dd077a46c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816693"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="d0e97-104">API du référentiel pour le tableau de bord de qualité des appels (bord) dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="d0e97-104">Repository API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="d0e97-105">**Résumé :** En savoir plus sur l’API du référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="d0e97-105">**Summary:** Learn about the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="d0e97-106">Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d0e97-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="d0e97-107">L’API du référentiel fournit un accès par programmation pour le tableau de bord de qualité des appels pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d0e97-107">The Repository API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="repository-api-for-call-quality-dashboard"></a><span data-ttu-id="d0e97-108">API du référentiel pour le tableau de bord de qualité des appels</span><span class="sxs-lookup"><span data-stu-id="d0e97-108">Repository API for Call Quality Dashboard</span></span>

<span data-ttu-id="d0e97-109">L’API du référentiel offre une interface d’accès aux données à la base de données du référentiel.</span><span class="sxs-lookup"><span data-stu-id="d0e97-109">Repository API offers a data access interface to repository database.</span></span> <span data-ttu-id="d0e97-110">Le référentiel permet d’organiser le contenu dans une arborescence ou une structure de graphique de telle sorte que les utilisateurs puissent les regrouper selon les besoins des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d0e97-110">The repository allows the contents to be organized in a tree or graph structure such that users can group them in the ways that make sense to the users.</span></span> <span data-ttu-id="d0e97-111">Le référentiel prend en charge deux types d’utilisateurs généraux : l’utilisateur système, qui est un utilisateur intégré représentant le référentiel, et les utilisateurs normaux qui représentent les utilisateurs autorisés du référentiel.</span><span class="sxs-lookup"><span data-stu-id="d0e97-111">The repository supports two general types of users: system user, which is a built-in user representing the repository, and regular users that represent the authorized users of the repository.</span></span>
  
<span data-ttu-id="d0e97-112">L’API du référentiel se compose de trois services généraux :</span><span class="sxs-lookup"><span data-stu-id="d0e97-112">Repository API consists of three general services:</span></span> 
  
- <span data-ttu-id="d0e97-113">[Service utilisateur pour bord](user-service.md) -pour accéder aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d0e97-113">[User Service for CQD](user-service.md) - for accessing Users.</span></span>
    
- <span data-ttu-id="d0e97-114">[Service d’article pour le tableau de bord de qualité des appels (bord)](item-service.md) -pour accéder aux éléments et au contenu stocké dans les éléments.</span><span class="sxs-lookup"><span data-stu-id="d0e97-114">[Item Service for Call Quality Dashboard (CQD)](item-service.md) - for accessing Items and the contents stored in Items.</span></span>
    
- <span data-ttu-id="d0e97-115">[Service de paramètres utilisateur pour le tableau de bord de qualité des appels (bord)](user-settings-service.md) -pour accéder aux paramètres de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d0e97-115">[User Settings Service for Call Quality Dashboard (CQD)](user-settings-service.md) - for accessing User Settings.</span></span>
    
<span data-ttu-id="d0e97-116">Le tableau de bord de qualité des appels utilise l’API du référentiel pour gérer les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="d0e97-116">Call Quality Dashboard uses Repository API to manage the following information:</span></span> 
  
- <span data-ttu-id="d0e97-117">Représentation **utilisateur** des utilisateurs qui ont accès au référentiel.</span><span class="sxs-lookup"><span data-stu-id="d0e97-117">**User** - representation of Users who have access to the repository.</span></span>
    
- <span data-ttu-id="d0e97-118">**Rapport** -contient une liste de requêtes, stockée en tant que contenu dans les éléments du référentiel.</span><span class="sxs-lookup"><span data-stu-id="d0e97-118">**Report** - contains a list of Queries, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="d0e97-119">**Requête** utilisée pour récupérer les données à partir de l’API de données, stockées en tant que contenu dans les éléments du référentiel.</span><span class="sxs-lookup"><span data-stu-id="d0e97-119">**Query** - used to retrieve data from Data API, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="d0e97-120">**Paramètre utilisateur** -décrit un comportement d’application facultatif pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d0e97-120">**User Setting** - describes an optional application behavior for the user.</span></span>
    
  <span data-ttu-id="d0e97-121">**Prise en charge du partage de ressources intersession pour l’API du référentiel**</span><span class="sxs-lookup"><span data-stu-id="d0e97-121">**Cross-Origin Resource Sharing (CORS) Support for Repository API**</span></span>
  
<span data-ttu-id="d0e97-122">L’API du référentiel prend en charge le partage de ressources de traversée.</span><span class="sxs-lookup"><span data-stu-id="d0e97-122">Repository API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="d0e97-123">CORS est une fonctionnalité HTTP qui permet à une application Web exécutée sous un domaine d’accéder aux ressources d’un autre domaine.</span><span class="sxs-lookup"><span data-stu-id="d0e97-123">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="d0e97-124">Les navigateurs Web mettent en œuvre une restriction de sécurité connue sous le nom de stratégie de [même origine qui](https://www.w3.org/Security/wiki/Same_Origin_Policy) empêche une page Web d’appeler des API dans un domaine différent.</span><span class="sxs-lookup"><span data-stu-id="d0e97-124">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="d0e97-125">CORS fournit un moyen sécurisé pour permettre à un domaine (domaine d’origine) d’appeler des API dans un autre domaine.</span><span class="sxs-lookup"><span data-stu-id="d0e97-125">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="d0e97-126">Pour plus d’informations sur l’affichage de l’une des [caractéristiques](https://www.w3.org/TR/cors/) de cors.</span><span class="sxs-lookup"><span data-stu-id="d0e97-126">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="d0e97-127">**Activation de CORS pour l’API du référentiel**</span><span class="sxs-lookup"><span data-stu-id="d0e97-127">**Enabling CORS for Repository API**</span></span>
  
 <span data-ttu-id="d0e97-128">Voici un extrait de l’API du référentiel Web. config, montrant deux domaines répertoriés dans les paramètres de l’application corsTrustedOrigin.</span><span class="sxs-lookup"><span data-stu-id="d0e97-128">The following is an excerpt of Repository API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="d0e97-129">Toutes les demandes effectuées par les scripts chargés à partir de ces serveurs sont approuvées par l’API du référentiel.</span><span class="sxs-lookup"><span data-stu-id="d0e97-129">All requests made by the scripts loaded from these servers are trusted by Repository API.</span></span>
  
<span data-ttu-id="d0e97-130">N’oubliez pas d’inclure le protocole, le nom d’hôte et le port exacts (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="d0e97-130">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="d0e97-131">Ne placez aucun caractère barre oblique (/) à la fin.</span><span class="sxs-lookup"><span data-stu-id="d0e97-131">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="d0e97-132">Plusieurs entrées peuvent être spécifiées en les séparant par des virgules.</span><span class="sxs-lookup"><span data-stu-id="d0e97-132">Multiple entries can be specified by separating with commas.</span></span>
  
```
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


