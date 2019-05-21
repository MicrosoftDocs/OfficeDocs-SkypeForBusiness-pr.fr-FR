---
title: Scénarios de performances de l’outil de stress et de performances de Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Tâches que vous devez effectuer pour configurer Skype entreprise Server 2015 de façon à effectuer des opérations de performance et de test de charge à l’aide de l’outil stress et performance.
ms.openlocfilehash: 2aedb43a6b7214aaf582e1dfd4754e626a602508
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299382"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="b5b39-103">Scénarios de performances de l’outil de stress et de performances de Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="b5b39-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="b5b39-104">Tâches que vous devez effectuer pour configurer Skype entreprise Server 2015 de façon à effectuer des opérations de performance et de test de charge à l’aide de l’outil stress et performance.</span><span class="sxs-lookup"><span data-stu-id="b5b39-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="b5b39-105">Pour exécuter l’outil de stress et de performance 2015 de Skype entreprise Server (LyncPerfTool), la topologie de Skype entreprise Server 2015 doit d’abord être configurée pour les scénarios qui vous intéressent.</span><span class="sxs-lookup"><span data-stu-id="b5b39-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="b5b39-106">Si Skype entreprise Server 2015 n’est pas configuré ou s’il est configuré de manière incorrecte, votre simulation de charge risque de ne pas fonctionner.</span><span class="sxs-lookup"><span data-stu-id="b5b39-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="b5b39-107">Grâce à l’outil de stress et de performances de Skype entreprise Server 2015, nous proposons des exemples de scripts et de fichiers de ressources de base de Skype entreprise [](https://www.microsoft.com/download/details.aspx?id=50367)Server Management Server.</span><span class="sxs-lookup"><span data-stu-id="b5b39-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="b5b39-108">Ils peuvent servir de point de départ pour configurer votre déploiement de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b5b39-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="b5b39-109">Cet article décrit les exemples Windows PowerShell proposés.</span><span class="sxs-lookup"><span data-stu-id="b5b39-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b5b39-110">Dans cette rubrique, vous ne pourrez pas décrire la configuration de Skype entreprise Server 2015 en règle générale, nous avons d’autres rubriques de planification et de déploiement pour cela.</span><span class="sxs-lookup"><span data-stu-id="b5b39-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="b5b39-111">Pour plus d’informations sur l’utilisation de Windows PowerShell dans Skype entreprise Server 2015, voir la documentation Skype entreprise Server Management Shell dans la section insérer une présentation ici.</span><span class="sxs-lookup"><span data-stu-id="b5b39-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="b5b39-112">À propos de l’utilisation de scripts de gestion de Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="b5b39-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="b5b39-113">Nous vous proposons des exemples de scripts PowerShell que vous pouvez utiliser pour préparer votre simulation de charge.</span><span class="sxs-lookup"><span data-stu-id="b5b39-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="b5b39-114">Dans la mesure où ces scripts sont destinés à une simulation de charge, vous pouvez les rendre plus simples et permissifs.</span><span class="sxs-lookup"><span data-stu-id="b5b39-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="b5b39-115">Qui n’est pas approprié pour votre environnement de production.</span><span class="sxs-lookup"><span data-stu-id="b5b39-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="b5b39-116">Dans de nombreux cas, nous faisons en sorte que ces scripts soient des exemples, vous devez les revoir et, dans de nombreux cas, apporter des modifications pertinentes à votre environnement avant de pouvoir les utiliser.</span><span class="sxs-lookup"><span data-stu-id="b5b39-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="b5b39-117">Pour le moment, vous devez modifier le script de groupe de service de réponse (RSG) en tenant compte de votre topologie (pour spécifier les agents affectés aux groupes d’agents).</span><span class="sxs-lookup"><span data-stu-id="b5b39-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="b5b39-118">Toutefois, vous n’avez pas besoin de l’exécuter, si ce n’est pas le cas.</span><span class="sxs-lookup"><span data-stu-id="b5b39-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="b5b39-119">Prenez soin de revoir et de comprendre ces exemples.</span><span class="sxs-lookup"><span data-stu-id="b5b39-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="b5b39-120">Les scripts écraseront tout paramètre existant dans la topologie lors de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="b5b39-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="b5b39-121">Nom des versions du client de l’outil stress et performance</span><span class="sxs-lookup"><span data-stu-id="b5b39-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="b5b39-122">Vous devrez peut-être configurer la stratégie de vérification de la version du client si vous avez déjà modifié les paramètres des valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="b5b39-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="b5b39-123">Si vous n’êtes pas sûr de cela, consultez la [documentation relative à la version du client](https://msdn.microsoft.com/en-us/vsto/jj923060).</span><span class="sxs-lookup"><span data-stu-id="b5b39-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/en-us/vsto/jj923060).</span></span>
  
<span data-ttu-id="b5b39-124">L’outil stress and performance utilise par défaut les versions d’agent utilisateur suivantes lors de la communication avec Skype entreprise Server 2015:</span><span class="sxs-lookup"><span data-stu-id="b5b39-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="b5b39-125">LSPT/15.0.0.0 (outil de stress et de performance de Skype entreprise Server 2015)</span><span class="sxs-lookup"><span data-stu-id="b5b39-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="b5b39-126">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="b5b39-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="b5b39-127">Pour le client Mobility (UCWA) dans LyncPerfTool:</span><span class="sxs-lookup"><span data-stu-id="b5b39-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="b5b39-128">Outil de performance/conférence Web UCWA</span><span class="sxs-lookup"><span data-stu-id="b5b39-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="b5b39-129">Outil perf UCWA/mobile</span><span class="sxs-lookup"><span data-stu-id="b5b39-129">UCWA Perf Tool/Mobile</span></span>
    

