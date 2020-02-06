---
title: Approvisionnement de la topologie pour exécuter des scénarios de stress et de performance
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
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Les modifications ou la mise en service de la topologie de Skype entreprise Server 2015 pour permettre aux utilisateurs d’exécuter avec succès l’outil de stress et de performance.
ms.openlocfilehash: 2156616fac98d1e6fad08d2036f4bc2def3e98b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816163"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a><span data-ttu-id="15a26-103">Approvisionnement de la topologie pour exécuter des scénarios de stress et de performance</span><span class="sxs-lookup"><span data-stu-id="15a26-103">Provisioning the topology to run load in Stress and Performance scenarios</span></span>
 
<span data-ttu-id="15a26-104">Les modifications ou la mise en service de la topologie de Skype entreprise Server 2015 pour permettre aux utilisateurs d’exécuter avec succès l’outil de stress et de performance.</span><span class="sxs-lookup"><span data-stu-id="15a26-104">Skype for Business Server 2015 topology changes or provisioning to allow users to successfully run the Stress and Performance tool.</span></span>
  
<span data-ttu-id="15a26-105">Selon vos paramètres et votre configuration existants pour votre déploiement de Skype entreprise Server 2015, vous devrez peut-être apporter quelques modifications à votre environnement.</span><span class="sxs-lookup"><span data-stu-id="15a26-105">Depending on your existing settings and configuration for your deployment of Skype for Business Server 2015, you might need to make some changes in your environment.</span></span> <span data-ttu-id="15a26-106">Voici une liste de ces modifications :</span><span class="sxs-lookup"><span data-stu-id="15a26-106">The following is a list of those changes:</span></span>
  
1. <span data-ttu-id="15a26-107">Définissez la stratégie d’exécution Windows PowerShell sur non restreinte.</span><span class="sxs-lookup"><span data-stu-id="15a26-107">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="15a26-108">Si vous n’êtes pas sûr de l’option définie pour le moment, vous pouvez ouvrir Skype entreprise Server Management Shell et exécuter cette commande :</span><span class="sxs-lookup"><span data-stu-id="15a26-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span></span>
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   <span data-ttu-id="15a26-109">Si la valeur Unrestricted n’est pas renvoyée, vous devez l’exécuter suivante :</span><span class="sxs-lookup"><span data-stu-id="15a26-109">If the value Unrestricted is not returned, you'll need to run this next:</span></span>
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. <span data-ttu-id="15a26-110">Pour configurer efficacement Skype entreprise Server, vous devez :</span><span class="sxs-lookup"><span data-stu-id="15a26-110">To effectively configure Skype for Business Server, you'll need to:</span></span>
    
    - <span data-ttu-id="15a26-111">Familiarisez-vous avec la topologie de Skype entreprise Server 2015 (par exemple, les noms d’ordinateurs, les instances de service, les noms de sites et les stratégies).</span><span class="sxs-lookup"><span data-stu-id="15a26-111">Be familiar with your Skype for Business Server 2015 topology (such as computer names, service instances, site names, and policies).</span></span>
    
    - <span data-ttu-id="15a26-112">Assignez certains utilisateurs créés à des groupes, tels que les groupes de recherche de Response Group (par exemple, URI SIP).</span><span class="sxs-lookup"><span data-stu-id="15a26-112">Assign some of the users that are created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>
    
3. <span data-ttu-id="15a26-113">Pour exécuter le script à partir de la ligne de commande, vous pouvez utiliser les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="15a26-113">To run a script from command line, you can use:</span></span>
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. <span data-ttu-id="15a26-114">En règle générale, une fois que vous avez exécuté un script depuis ce package, les traces obtenues seront stockées dans un fichier dans le même chemin à partir duquel le script est exécuté.</span><span class="sxs-lookup"><span data-stu-id="15a26-114">Typically, after you've run a script from this package, the resulting traces will be stored in a file in the same path from where the script was run.</span></span> <span data-ttu-id="15a26-115">Il existe également un format d’appellation \<scriptname\>$h $ m $ s. txt.</span><span class="sxs-lookup"><span data-stu-id="15a26-115">There's a naming format as well, \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="15a26-116">Par conséquent, si vous avez exécuté ArchivingPolicy. ps1 au 12:15 PM, vous obtiendrez un fichier journal nommé ArchivingPolicy121500. txt.</span><span class="sxs-lookup"><span data-stu-id="15a26-116">So if you ran the ArchivingPolicy.ps1 at 12:15 PM, you'll get a log file named ArchivingPolicy121500.txt.</span></span>
    
5. <span data-ttu-id="15a26-117">Même si vous avez fourni ces exemples pour la configuration de votre serveur, vous devez modifier votre configuration et le restaurer ou le réactiver une fois que vous avez terminé d’exécuter le test de charge.</span><span class="sxs-lookup"><span data-stu-id="15a26-117">While we've provided these examples for your server configuration, it's up to you to both modify your configuration and restore or roll it back after you've finished running the load testing.</span></span>
    

