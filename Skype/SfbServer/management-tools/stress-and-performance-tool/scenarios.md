---
title: Scénarios de performances pour l’outil de contrainte et de performances de Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Les tâches que vous devez effectuer pour configurer Skype entreprise Server 2015 pour effectuer des tests de performances et de chargement à l’aide de l’outil stress and performance.
ms.openlocfilehash: 5531627ab7d5072d32dfcf60fed41eac47f5373f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983849"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="aa8a9-103">Scénarios de performances pour l’outil de contrainte et de performances de Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="aa8a9-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="aa8a9-104">Les tâches que vous devez effectuer pour configurer Skype entreprise Server 2015 pour effectuer des tests de performances et de chargement à l’aide de l’outil stress and performance.</span><span class="sxs-lookup"><span data-stu-id="aa8a9-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="aa8a9-105">Pour exécuter l’outil de contrainte et de performances de Skype entreprise Server 2015 (LyncPerfTool), la topologie de Skype entreprise Server 2015 doit d’abord être configurée pour les scénarios qui vous concernent.</span><span class="sxs-lookup"><span data-stu-id="aa8a9-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="aa8a9-106">Si Skype entreprise Server 2015 n’est pas configuré ou qu’il est configuré de manière incorrecte, votre simulation de charge risque d’échouer.</span><span class="sxs-lookup"><span data-stu-id="aa8a9-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="aa8a9-107">Avec l’outil de contrainte et de performances de Skype entreprise Server 2015, nous fournissons des exemples de scripts Skype entreprise Server Management Shell et des fichiers de ressources de base dans le cadre du téléchargement de l' [outil](https://www.microsoft.com/download/details.aspx?id=50367).</span><span class="sxs-lookup"><span data-stu-id="aa8a9-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="aa8a9-108">Ces éléments peuvent être utilisés comme point de départ pour la configuration de votre déploiement de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="aa8a9-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="aa8a9-109">Cet article décrit les exemples Windows PowerShell fournis.</span><span class="sxs-lookup"><span data-stu-id="aa8a9-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="aa8a9-110">Cette rubrique ne vous aidera pas à décrire la configuration de Skype entreprise Server 2015 généralement, nous avons d’autres rubriques de planification et de déploiement pour cela.</span><span class="sxs-lookup"><span data-stu-id="aa8a9-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="aa8a9-111">Pour plus d’informations sur l’utilisation de Windows PowerShell dans Skype entreprise Server 2015, reportez-vous à la documentation de Skype entreprise Server Management Shell dans insérer Introduction ici.</span><span class="sxs-lookup"><span data-stu-id="aa8a9-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="aa8a9-112">À propos de l’exécution de scripts Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="aa8a9-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="aa8a9-113">Nous fournissons des exemples de scripts PowerShell que vous pouvez utiliser pour vous préparer à vos simulations de charge.</span><span class="sxs-lookup"><span data-stu-id="aa8a9-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="aa8a9-114">Étant donné que ces scripts sont destinés à la simulation de charge, vous les trouverez comme simples et permissants.</span><span class="sxs-lookup"><span data-stu-id="aa8a9-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="aa8a9-115">Cela n’est peut-être pas approprié pour votre environnement de production.</span><span class="sxs-lookup"><span data-stu-id="aa8a9-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="aa8a9-116">À nouveau, nous insistons sur le fait que ces scripts sont des exemples, que vous devez les examiner et, dans de nombreux cas, effectuer des modifications pertinentes pour votre environnement avant de pouvoir les utiliser.</span><span class="sxs-lookup"><span data-stu-id="aa8a9-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="aa8a9-117">Au minimum, il est nécessaire de modifier le script de groupe de service de réponse (RSG) en tenant compte de votre topologie (pour spécifier les agents affectés aux groupes d’agents).</span><span class="sxs-lookup"><span data-stu-id="aa8a9-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="aa8a9-118">Toutefois, si vous n’avez pas besoin de le faire, il n’est pas nécessaire de l’exécuter.</span><span class="sxs-lookup"><span data-stu-id="aa8a9-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="aa8a9-119">Veillez à examiner et à comprendre ces exemples.</span><span class="sxs-lookup"><span data-stu-id="aa8a9-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="aa8a9-120">Les scripts remplaceront les paramètres existants dans la topologie lors de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="aa8a9-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="aa8a9-121">Noms des versions du client outil de stress et de performances</span><span class="sxs-lookup"><span data-stu-id="aa8a9-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="aa8a9-122">Vous devrez peut-être configurer la stratégie de vérification de la version du client si vous avez déjà modifié les valeurs par défaut des paramètres.</span><span class="sxs-lookup"><span data-stu-id="aa8a9-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="aa8a9-123">Si vous n’êtes pas sûr de ce sujet, consultez la documentation de vérification de la [version du client](https://msdn.microsoft.com/vsto/jj923060).</span><span class="sxs-lookup"><span data-stu-id="aa8a9-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/vsto/jj923060).</span></span>
  
<span data-ttu-id="aa8a9-124">L’outil stress and performance utilise par défaut les versions suivantes de l’agent utilisateur lors de la communication avec Skype entreprise Server 2015 :</span><span class="sxs-lookup"><span data-stu-id="aa8a9-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="aa8a9-125">LSPT/15.0.0.0 (outil de contrainte et de performances de Skype entreprise Server 2015)</span><span class="sxs-lookup"><span data-stu-id="aa8a9-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="aa8a9-126">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="aa8a9-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="aa8a9-127">Pour le client Mobility (UCWA) dans LyncPerfTool :</span><span class="sxs-lookup"><span data-stu-id="aa8a9-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="aa8a9-128">Outil perf UCWA/conférence Web</span><span class="sxs-lookup"><span data-stu-id="aa8a9-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="aa8a9-129">Outil de performances UCWA/mobile</span><span class="sxs-lookup"><span data-stu-id="aa8a9-129">UCWA Perf Tool/Mobile</span></span>
    

