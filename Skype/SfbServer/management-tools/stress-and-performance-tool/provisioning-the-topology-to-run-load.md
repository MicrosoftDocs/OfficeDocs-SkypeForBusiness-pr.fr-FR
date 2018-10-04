---
title: Mise en service de la topologie pour exécuter la charge dans les scénarios de Stress and Performance
ms.author: heidip
author: microsoftheidi
ms.date: 12/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Skype pour Business Server 2015 les modifications ou la mise en service pour permettre aux utilisateurs d’exécuter correctement l’outil Stress and Performance.
ms.openlocfilehash: 6ff08a3b99f4dc1f05b56c2a1fa86733ccf4f852
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373777"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a><span data-ttu-id="f10f2-103">Mise en service de la topologie pour exécuter la charge dans les scénarios de Stress and Performance</span><span class="sxs-lookup"><span data-stu-id="f10f2-103">Provisioning the topology to run load in Stress and Performance scenarios</span></span>
 
<span data-ttu-id="f10f2-104">Skype pour Business Server 2015 les modifications ou la mise en service pour permettre aux utilisateurs d’exécuter correctement l’outil Stress and Performance.</span><span class="sxs-lookup"><span data-stu-id="f10f2-104">Skype for Business Server 2015 topology changes or provisioning to allow users to successfully run the Stress and Performance tool.</span></span>
  
<span data-ttu-id="f10f2-105">En fonction de vos paramètres existants et la configuration de votre déploiement de Skype pour Business Server 2015, vous devrez peut-être apporter quelques modifications dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="f10f2-105">Depending on your existing settings and configuration for your deployment of Skype for Business Server 2015, you might need to make some changes in your environment.</span></span> <span data-ttu-id="f10f2-106">Voici une liste de ces modifications :</span><span class="sxs-lookup"><span data-stu-id="f10f2-106">The following is a list of those changes:</span></span>
  
1. <span data-ttu-id="f10f2-107">Définir la stratégie d’exécution Windows PowerShell non restreint.</span><span class="sxs-lookup"><span data-stu-id="f10f2-107">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="f10f2-108">Si vous n’êtes pas certain qu’il est défini sur actuellement, vous pouvez ouvrir le Skype pour Business Server Management Shell et exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f10f2-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span></span>
    
   ```
   Get-ExecutionPolicy
   ```

   <span data-ttu-id="f10f2-109">Si la valeur non restreint n’est pas renvoyée, vous devez exécuter ce suivant :</span><span class="sxs-lookup"><span data-stu-id="f10f2-109">If the value Unrestricted is not returned, you'll need to run this next:</span></span>
    
   ```
   Set-ExecutionPolicy -Unrestricted
   ```

2. <span data-ttu-id="f10f2-110">Pour configurer efficacement Skype pour Business Server, vous devez :</span><span class="sxs-lookup"><span data-stu-id="f10f2-110">To effectively configure Skype for Business Server, you'll need to:</span></span>
    
    - <span data-ttu-id="f10f2-111">Être familiarisé avec votre Skype pour topologie Business Server 2015 (tels que les noms d’ordinateurs, des instances de service, les noms de site et des stratégies).</span><span class="sxs-lookup"><span data-stu-id="f10f2-111">Be familiar with your Skype for Business Server 2015 topology (such as computer names, service instances, site names, and policies).</span></span>
    
    - <span data-ttu-id="f10f2-112">Attribuer certains des utilisateurs qui sont créés à des groupes, tels que des groupes (par exemple, URI SIP) de recherche Response Group.</span><span class="sxs-lookup"><span data-stu-id="f10f2-112">Assign some of the users that are created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>
    
3. <span data-ttu-id="f10f2-113">Pour exécuter un script de ligne de commande, vous pouvez utiliser :</span><span class="sxs-lookup"><span data-stu-id="f10f2-113">To run a script from command line, you can use:</span></span>
    
   ```
   PowerShell.exe -file <path to the file>
   ```

4. <span data-ttu-id="f10f2-114">En règle générale, une fois que vous avez exécuter un script à partir de ce package, les suivis résultants seront stockés dans un fichier dans le même chemin d’accès à partir duquel le script a été exécuté.</span><span class="sxs-lookup"><span data-stu-id="f10f2-114">Typically, after you've run a script from this package, the resulting traces will be stored in a file in the same path from where the script was run.</span></span> <span data-ttu-id="f10f2-115">Il existe également un format de dénomination \<scriptname\>$h$m$s.txt.</span><span class="sxs-lookup"><span data-stu-id="f10f2-115">There's a naming format as well, \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="f10f2-116">Ainsi, si vous avez exécuté l’ArchivingPolicy.ps1 à 12 h 15, vous obtiendrez un fichier journal nommé ArchivingPolicy121500.txt.</span><span class="sxs-lookup"><span data-stu-id="f10f2-116">So if you ran the ArchivingPolicy.ps1 at 12:15 PM, you'll get a log file named ArchivingPolicy121500.txt.</span></span>
    
5. <span data-ttu-id="f10f2-117">Pendant que nous avons fourni ces exemples pour la configuration de votre serveur, il est à la fois modifier votre configuration et de restaurer ou de déployer en une fois que vous avez fini de s’exécuter le test de charge.</span><span class="sxs-lookup"><span data-stu-id="f10f2-117">While we've provided these examples for your server configuration, it's up to you to both modify your configuration and restore or roll it back after you've finished running the load testing.</span></span>
    

