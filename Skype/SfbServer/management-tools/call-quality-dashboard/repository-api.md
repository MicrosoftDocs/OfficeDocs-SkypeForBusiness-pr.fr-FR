---
title: API de référentiel pour le tableau de bord (CQD) appel qualité dans Skype pour Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 'Résumé : En savoir plus sur l’API de référentiel pour l’appel du tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 0f84e3967bd4f78f8852dbcfed8ce5d59cbe4e8c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server-2015"></a><span data-ttu-id="61f57-104">API de référentiel pour le tableau de bord (CQD) appel qualité dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="61f57-104">Repository API for Call Quality Dashboard (CQD) in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="61f57-105">**Résumé :** Obtenir des informations sur l’API de référentiel pour l’appel du tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="61f57-105">**Summary:** Learn about the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="61f57-106">Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="61f57-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="61f57-107">L’API de référentiel permet d’accéder par programmation pour appeler le tableau de bord qualité pour Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="61f57-107">The Repository API provides programmatic access for Call Quality Dashboard for Skype for Business Server 2015.</span></span>
  
## <a name="repository-api-for-call-quality-dashboard"></a><span data-ttu-id="61f57-108">API de référentiel pour le tableau de bord qualité appel</span><span class="sxs-lookup"><span data-stu-id="61f57-108">Repository API for Call Quality Dashboard</span></span>

<span data-ttu-id="61f57-109">API de référentiel offre une interface d’accès de données de la base de données de référentiel.</span><span class="sxs-lookup"><span data-stu-id="61f57-109">Repository API offers a data access interface to repository database.</span></span> <span data-ttu-id="61f57-110">Le référentiel permet au contenu d’être organisées dans une structure d’arbre ou graphique tels que les utilisateurs peuvent regrouper les manières ayant un sens pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="61f57-110">The repository allows the contents to be organized in a tree or graph structure such that users can group them in the ways that make sense to the users.</span></span> <span data-ttu-id="61f57-111">Le référentiel prend en charge les deux types généraux d’utilisateurs : utilisateur du système, qui est un utilisateur du référentiel intégré et les utilisateurs ordinaires qui représentent les utilisateurs autorisés du référentiel.</span><span class="sxs-lookup"><span data-stu-id="61f57-111">The repository supports two general types of users: system user, which is a built-in user representing the repository, and regular users that represent the authorized users of the repository.</span></span>
  
<span data-ttu-id="61f57-112">API de référentiel est composé de trois services généraux :</span><span class="sxs-lookup"><span data-stu-id="61f57-112">Repository API consists of three general services:</span></span> 
  
- <span data-ttu-id="61f57-113">[Service utilisateur pour CQD](user-service.md) - pour l’accès à des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="61f57-113">[User Service for CQD](user-service.md) - for accessing Users.</span></span>
    
- <span data-ttu-id="61f57-114">[Service de l’élément de tableau de bord qualité appeler (CQD)](item-service.md) - pour accéder aux éléments et le contenu stocké dans des éléments.</span><span class="sxs-lookup"><span data-stu-id="61f57-114">[Item Service for Call Quality Dashboard (CQD)](item-service.md) - for accessing Items and the contents stored in Items.</span></span>
    
- <span data-ttu-id="61f57-115">[Service de paramètres utilisateur pour appeler qualité du tableau de bord (CQD)](user-settings-service.md) - pour l’accès aux paramètres de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="61f57-115">[User Settings Service for Call Quality Dashboard (CQD)](user-settings-service.md) - for accessing User Settings.</span></span>
    
<span data-ttu-id="61f57-116">Tableau de bord qualité appel utilise l’API de référentiel pour gérer les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="61f57-116">Call Quality Dashboard uses Repository API to manage the following information:</span></span> 
  
- <span data-ttu-id="61f57-117">**Utilisateur** : représentation des utilisateurs qui ont accès au référentiel.</span><span class="sxs-lookup"><span data-stu-id="61f57-117">**User** - representation of Users who have access to the repository.</span></span>
    
- <span data-ttu-id="61f57-118">**Rapport** - contient une liste de requêtes, stockées sous la forme d’un contenu d’éléments du référentiel.</span><span class="sxs-lookup"><span data-stu-id="61f57-118">**Report** - contains a list of Queries, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="61f57-119">**Requête** - permet de récupérer des données à partir des API de données stockées sous la forme d’un contenu d’éléments d’un référentiel.</span><span class="sxs-lookup"><span data-stu-id="61f57-119">**Query** - used to retrieve data from Data API, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="61f57-120">Le **Paramètre utilisateur** - décrit un comportement d’application facultative pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="61f57-120">**User Setting** - describes an optional application behavior for the user.</span></span>
    
 <span data-ttu-id="61f57-121">**La prise en charge pour l’API de référentiel (CORS) le partage des ressources entre-origine**</span><span class="sxs-lookup"><span data-stu-id="61f57-121">**Cross-Origin Resource Sharing (CORS) Support for Repository API**</span></span>
  
<span data-ttu-id="61f57-122">Partage de ressources entre origine (CORS) prend en charge les API de référentiel.</span><span class="sxs-lookup"><span data-stu-id="61f57-122">Repository API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="61f57-123">CORS est une fonctionnalité HTTP qui permet à une application web en cours d’exécution dans un domaine d’accéder aux ressources dans un autre domaine.</span><span class="sxs-lookup"><span data-stu-id="61f57-123">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="61f57-124">Navigateurs Web implémentent une restriction de sécurité appelée stratégie de même origine [Stratégie de même origine](https://www.w3.org/Security/wiki/Same_Origin_Policy) qui empêche une page web à partir de l’appel d’API dans un autre domaine.</span><span class="sxs-lookup"><span data-stu-id="61f57-124">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="61f57-125">CORS offre un moyen sécurisé pour permettre à un domaine (le domaine d’origine) appeler des API dans un autre domaine.</span><span class="sxs-lookup"><span data-stu-id="61f57-125">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="61f57-126">Consultez la [spécification de CORS](https://www.w3.org/TR/cors/) pour plus de détails sur les CORS.</span><span class="sxs-lookup"><span data-stu-id="61f57-126">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="61f57-127">**L’activation de CORS pour l’API de référentiel**</span><span class="sxs-lookup"><span data-stu-id="61f57-127">**Enabling CORS for Repository API**</span></span>
  
 <span data-ttu-id="61f57-128">Voici un extrait du fichier web.config de API de référentiel, montrant deux domaines répertoriés dans les paramètres de l’application corsTrustedOrigin.</span><span class="sxs-lookup"><span data-stu-id="61f57-128">The following is an excerpt of Repository API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="61f57-129">Toutes les demandes effectuées par les scripts chargés à partir de ces serveurs sont approuvés par les API de référentiel.</span><span class="sxs-lookup"><span data-stu-id="61f57-129">All requests made by the scripts loaded from these servers are trusted by Repository API.</span></span>
  
<span data-ttu-id="61f57-130">N’oubliez pas d’inclure le protocole exact, le nom d’hôte et le port (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="61f57-130">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="61f57-131">Ne pas pour placer les oblique (/) de caractère à la fin.</span><span class="sxs-lookup"><span data-stu-id="61f57-131">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="61f57-132">Plusieurs entrées peuvent être spécifiées en les séparant par des virgules.</span><span class="sxs-lookup"><span data-stu-id="61f57-132">Multiple entries can be specified by separating with commas.</span></span>
  
```
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>

```


