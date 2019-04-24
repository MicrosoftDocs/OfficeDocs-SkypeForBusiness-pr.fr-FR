---
title: Scénarios de performances pour le Skype pour Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.date: 12/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Tâches que vous devez faire pour configurer Skype pour Business Server 2015 faire des performances et test de charge, à l’aide du Stress and Performance Tool.
ms.openlocfilehash: 53504b714304b4b3cd18e44397ce0f06fcc59b63
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32194617"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="c55e3-103">Scénarios de performances pour le Skype pour Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="c55e3-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="c55e3-104">Tâches que vous devez faire pour configurer Skype pour Business Server 2015 faire des performances et test de charge, à l’aide du Stress and Performance Tool.</span><span class="sxs-lookup"><span data-stu-id="c55e3-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="c55e3-105">Pour exécuter le Skype pour Business Server 2015 Stress and Performance Tool (LyncPerfTool), le Skype pour Business Server 2015 topologie doit d’abord être configuré pour les scénarios qui vous intéressent.</span><span class="sxs-lookup"><span data-stu-id="c55e3-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="c55e3-106">Si Skype pour Business Server 2015 n’est pas configuré ou est mal configuré, votre simulation de la charge est très risque d’échouer.</span><span class="sxs-lookup"><span data-stu-id="c55e3-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="c55e3-107">Avec Skype pour Business Server 2015 Stress and Performance Tool, nous vous fournissons exemple Skype pour les scripts de Business Server Management Shell et des fichiers de ressources de base dans le cadre de l' [outil de téléchargement](https://www.microsoft.com/download/details.aspx?id=50367).</span><span class="sxs-lookup"><span data-stu-id="c55e3-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="c55e3-108">Ces utilisable comme point de départ pour la configuration de votre Skype pour le déploiement de serveur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="c55e3-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="c55e3-109">Cet article décrit les exemples de Windows PowerShell fournis.</span><span class="sxs-lookup"><span data-stu-id="c55e3-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c55e3-110">Cette rubrique ne vous aidera à expliquent comment configurer Skype pour Business Server 2015 en règle générale, nous disposons d’autres rubriques de planification et de déploiement qui.</span><span class="sxs-lookup"><span data-stu-id="c55e3-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="c55e3-111">Pour plus d’informations sur l’utilisation de Windows PowerShell dans Skype pour Business Server 2015, voir le Skype pour la documentation Business Server Management Shell insérer introduction ici.</span><span class="sxs-lookup"><span data-stu-id="c55e3-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="c55e3-112">Sur l’exécution de scripts de shell Skype pour la gestion de serveur d’entreprise</span><span class="sxs-lookup"><span data-stu-id="c55e3-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="c55e3-113">Nous vous fournissons des exemples de scripts PowerShell que vous pouvez utiliser pour préparer votre simulations de charge.</span><span class="sxs-lookup"><span data-stu-id="c55e3-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="c55e3-114">Étant donné que ces scripts sont destinés à la simulation de charge, vous trouverez les simple et permissif.</span><span class="sxs-lookup"><span data-stu-id="c55e3-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="c55e3-115">Qui peut ne pas convenir pour votre environnement de production.</span><span class="sxs-lookup"><span data-stu-id="c55e3-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="c55e3-116">Nous une contrainte à nouveau que ces scripts sont des exemples, vous devez les consulter et dans de nombreux cas apporter des modifications appropriées à votre environnement avant de pouvoir les utiliser.</span><span class="sxs-lookup"><span data-stu-id="c55e3-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="c55e3-117">Nous attendriez au minimum, que vous devez modifier le script de groupe de Service Response Group (récupération) avec votre topologie esprit (pour spécifier les agents affectés à des groupes d’agents).</span><span class="sxs-lookup"><span data-stu-id="c55e3-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="c55e3-118">Mais vous n’avez à exécuter, si vous n’avez pas besoin.</span><span class="sxs-lookup"><span data-stu-id="c55e3-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="c55e3-119">Veuillez prendre en charge dans la révision et de présentation de ces exemples.</span><span class="sxs-lookup"><span data-stu-id="c55e3-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="c55e3-120">Scripts remplacera tous les paramètres existants dans la topologie lors de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="c55e3-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="c55e3-121">Noms de version de client Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="c55e3-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="c55e3-122">Vous devrez peut-être configurer la stratégie de vérification de Version du Client si vous avez précédemment modifié les paramètres par défaut.</span><span class="sxs-lookup"><span data-stu-id="c55e3-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="c55e3-123">Si vous avez des doutes quant à ce sujet, consultez la [documentation de vérification de Version du Client](https://msdn.microsoft.com/en-us/vsto/jj923060).</span><span class="sxs-lookup"><span data-stu-id="c55e3-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/en-us/vsto/jj923060).</span></span>
  
<span data-ttu-id="c55e3-124">Le Stress and Performance Tool utilise les versions suivantes de l’Agent utilisateur par défaut lors de la communication avec Skype pour Business Server 2015 :</span><span class="sxs-lookup"><span data-stu-id="c55e3-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="c55e3-125">LSPT/15.0.0.0 (Skype pour Business Server 2015 Stress and Performance Tool)</span><span class="sxs-lookup"><span data-stu-id="c55e3-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="c55e3-126">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="c55e3-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="c55e3-127">Pour le client de mobilité (UCWA) dans LyncPerfTool :</span><span class="sxs-lookup"><span data-stu-id="c55e3-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="c55e3-128">Conférence Web/outil Performance UCWA</span><span class="sxs-lookup"><span data-stu-id="c55e3-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="c55e3-129">Outil de performances UCWA/Mobile</span><span class="sxs-lookup"><span data-stu-id="c55e3-129">UCWA Perf Tool/Mobile</span></span>
    

