---
title: Scénarios de performances pour l’outil Stress and Performance de Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Tâches à effectuer pour configurer Skype Entreprise Server 2015 afin d’effectuer des tests de performances et de charge à l’aide de l’outil Stress and Performance.
ms.openlocfilehash: 3edc945f09ef5b2c7c6ecdefcbc66166f0945aec
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814704"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="77252-103">Scénarios de performances pour l’outil Stress and Performance de Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="77252-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="77252-104">Tâches à effectuer pour configurer Skype Entreprise Server 2015 afin d’effectuer des tests de performances et de charge à l’aide de l’outil Stress and Performance.</span><span class="sxs-lookup"><span data-stu-id="77252-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="77252-105">Pour exécuter l’outil Stress and Performance de Skype Entreprise Server 2015 (LyncPerfTool), la topologie Skype Entreprise Server 2015 doit d’abord être configurée pour les scénarios qui vous sont pertinents.</span><span class="sxs-lookup"><span data-stu-id="77252-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="77252-106">Si Skype Entreprise Server 2015 n’est pas configuré ou n’est pas configuré de manière incorrecte, votre simulation de charge est très susceptible d’échouer.</span><span class="sxs-lookup"><span data-stu-id="77252-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="77252-107">Avec l’outil Stress and Performance de Skype Entreprise Server 2015, nous fournissons des exemples de scripts Skype Entreprise Server Management Shell et des fichiers de ressources de base dans le cadre du téléchargement de [l’outil.](https://www.microsoft.com/download/details.aspx?id=50367)</span><span class="sxs-lookup"><span data-stu-id="77252-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="77252-108">Ceux-ci peuvent servir de point de départ pour la configuration de votre déploiement de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="77252-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="77252-109">Cet article décrit les exemples Windows PowerShell fournis.</span><span class="sxs-lookup"><span data-stu-id="77252-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="77252-110">Cette rubrique ne vous aidera pas à décrire comment configurer Skype Entreprise Server 2015 en général. Nous avons d’autres rubriques de planification et de déploiement à ce sujet.</span><span class="sxs-lookup"><span data-stu-id="77252-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="77252-111">Pour plus d’informations sur l’Windows PowerShell dans Skype Entreprise Server 2015, consultez la documentation de Skype Entreprise Server Management Shell à l’adresse Insert introduction HERE.</span><span class="sxs-lookup"><span data-stu-id="77252-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="77252-112">À propos de l’exécution des scripts de l’shell de gestion de Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="77252-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="77252-113">Nous fournissons des exemples de scripts PowerShell que vous pouvez utiliser pour préparer vos simulations de charge.</span><span class="sxs-lookup"><span data-stu-id="77252-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="77252-114">Étant donné que ces scripts sont conçus pour la simulation de chargement, ils sont simples et permissifs.</span><span class="sxs-lookup"><span data-stu-id="77252-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="77252-115">Cela peut ne pas être approprié pour votre environnement de production.</span><span class="sxs-lookup"><span data-stu-id="77252-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="77252-116">Là encore, nous souligneons que ces scripts sont des exemples, vous devez les examiner et, dans de nombreux cas, apporter des modifications pertinentes à votre environnement avant de pouvoir les utiliser.</span><span class="sxs-lookup"><span data-stu-id="77252-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="77252-117">Au minimum, nous nous attendons à ce que vous devrez modifier le script Response Service Group (RSG) en fonction de votre topologie (pour spécifier les agents affectés aux groupes d’agents).</span><span class="sxs-lookup"><span data-stu-id="77252-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="77252-118">Mais vous n’avez pas besoin d’exécuter cela, si vous n’en avez pas besoin.</span><span class="sxs-lookup"><span data-stu-id="77252-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="77252-119">Prenez soin de passer en revue et de comprendre ces exemples.</span><span class="sxs-lookup"><span data-stu-id="77252-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="77252-120">Les scripts riteront tous les paramètres existants de la topologie lors de l’exécuter.</span><span class="sxs-lookup"><span data-stu-id="77252-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="77252-121">Noms de version du client de l’outil Stress and Performance</span><span class="sxs-lookup"><span data-stu-id="77252-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="77252-122">Vous devrez peut-être configurer la stratégie de vérification de version du client si vous avez précédemment modifié les paramètres par rapport aux valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="77252-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="77252-123">Si vous n’êtes pas sûr de cela, consultez la [documentation de vérification de version du client.](https://msdn.microsoft.com/vsto/jj923060)</span><span class="sxs-lookup"><span data-stu-id="77252-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/vsto/jj923060).</span></span>
  
<span data-ttu-id="77252-124">L’outil Stress and Performance utilise les versions d’agent utilisateur suivantes par défaut lors de la communication avec Skype Entreprise Server 2015 :</span><span class="sxs-lookup"><span data-stu-id="77252-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="77252-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span><span class="sxs-lookup"><span data-stu-id="77252-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="77252-126">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="77252-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="77252-127">Pour le client mobility (UCWA) dans LyncPerfTool :</span><span class="sxs-lookup"><span data-stu-id="77252-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="77252-128">Outil de perf UCWA/conférence web</span><span class="sxs-lookup"><span data-stu-id="77252-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="77252-129">Outil de perf UCWA/Mobile</span><span class="sxs-lookup"><span data-stu-id="77252-129">UCWA Perf Tool/Mobile</span></span>
    

