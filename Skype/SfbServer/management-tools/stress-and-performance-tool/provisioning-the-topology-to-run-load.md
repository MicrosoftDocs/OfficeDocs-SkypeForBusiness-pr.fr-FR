---
title: Mise en service de la topologie pour exécuter la charge dans les scénarios de contrainte et de performances
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
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Modifications ou approvisionnement de la topologie de Skype Entreprise Server 2015 pour permettre aux utilisateurs d’exécuter correctement l’outil Stress and Performance.
ms.openlocfilehash: 8d422497d11c9e56e4d5b205269a09f96dffc136
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814934"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a><span data-ttu-id="48f90-103">Mise en service de la topologie pour exécuter la charge dans les scénarios de contrainte et de performances</span><span class="sxs-lookup"><span data-stu-id="48f90-103">Provisioning the topology to run load in Stress and Performance scenarios</span></span>
 
<span data-ttu-id="48f90-104">Modifications ou approvisionnement de la topologie de Skype Entreprise Server 2015 pour permettre aux utilisateurs d’exécuter correctement l’outil Stress and Performance.</span><span class="sxs-lookup"><span data-stu-id="48f90-104">Skype for Business Server 2015 topology changes or provisioning to allow users to successfully run the Stress and Performance tool.</span></span>
  
<span data-ttu-id="48f90-105">En fonction de vos paramètres existants et de la configuration de votre déploiement de Skype Entreprise Server 2015, vous devrez peut-être apporter des modifications à votre environnement.</span><span class="sxs-lookup"><span data-stu-id="48f90-105">Depending on your existing settings and configuration for your deployment of Skype for Business Server 2015, you might need to make some changes in your environment.</span></span> <span data-ttu-id="48f90-106">Voici une liste de ces modifications :</span><span class="sxs-lookup"><span data-stu-id="48f90-106">The following is a list of those changes:</span></span>
  
1. <span data-ttu-id="48f90-107">Définissez la stratégie Windows PowerShell’exécution sur Non restreint.</span><span class="sxs-lookup"><span data-stu-id="48f90-107">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="48f90-108">Si vous ne savez pas exactement ce qu’il est actuellement, vous pouvez ouvrir Skype Entreprise Server Management Shell et exécuter la commande ci-après :</span><span class="sxs-lookup"><span data-stu-id="48f90-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span></span>
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   <span data-ttu-id="48f90-109">Si la valeur Unrestricted n’est pas renvoyée, vous devez exécuter cette suivante :</span><span class="sxs-lookup"><span data-stu-id="48f90-109">If the value Unrestricted is not returned, you'll need to run this next:</span></span>
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. <span data-ttu-id="48f90-110">Pour configurer Efficacement Skype Entreprise Server, vous devez :</span><span class="sxs-lookup"><span data-stu-id="48f90-110">To effectively configure Skype for Business Server, you'll need to:</span></span>
    
    - <span data-ttu-id="48f90-111">Familiarisez-vous avec votre topologie Skype Entreprise Server 2015 (par exemple, les noms d’ordinateur, les instances de service, les noms de site et les stratégies).</span><span class="sxs-lookup"><span data-stu-id="48f90-111">Be familiar with your Skype for Business Server 2015 topology (such as computer names, service instances, site names, and policies).</span></span>
    
    - <span data-ttu-id="48f90-112">Attribuez certains des utilisateurs créés à des groupes, tels que des groupements de recherche Response Group (par exemple, des URI SIP).</span><span class="sxs-lookup"><span data-stu-id="48f90-112">Assign some of the users that are created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>
    
3. <span data-ttu-id="48f90-113">Pour exécuter un script à partir d’une ligne de commande, vous pouvez utiliser :</span><span class="sxs-lookup"><span data-stu-id="48f90-113">To run a script from command line, you can use:</span></span>
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. <span data-ttu-id="48f90-114">En règle générale, une fois que vous avez exécuté un script à partir de ce package, les suivis qui en résultent sont stockés dans un fichier dans le même chemin d’accès à partir de l’endroit où le script a été exécuté.</span><span class="sxs-lookup"><span data-stu-id="48f90-114">Typically, after you've run a script from this package, the resulting traces will be stored in a file in the same path from where the script was run.</span></span> <span data-ttu-id="48f90-115">Il existe également un format d’attribution de noms, \<scriptname\> $h$m$s.txt.</span><span class="sxs-lookup"><span data-stu-id="48f90-115">There's a naming format as well, \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="48f90-116">Ainsi, si vous avez ArchivingPolicy.ps1 à 12:15 PM, vous obtenez un fichier journal nommé ArchivingPolicy121500.txt.</span><span class="sxs-lookup"><span data-stu-id="48f90-116">So if you ran the ArchivingPolicy.ps1 at 12:15 PM, you'll get a log file named ArchivingPolicy121500.txt.</span></span>
    
5. <span data-ttu-id="48f90-117">Même si nous avons fourni ces exemples pour la configuration de votre serveur, il vous revient à la fois de modifier votre configuration et de la restaurer ou de la restaurer une fois que vous avez terminé l’exécution du test de charge.</span><span class="sxs-lookup"><span data-stu-id="48f90-117">While we've provided these examples for your server configuration, it's up to you to both modify your configuration and restore or roll it back after you've finished running the load testing.</span></span>
    

