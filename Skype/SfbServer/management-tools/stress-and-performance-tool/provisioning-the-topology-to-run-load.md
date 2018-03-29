---
title: Mise en service de la topologie pour exécuter la charge dans les scénarios de contrainte et de performances
ms.author: heidip
author: microsoftheidi
ms.date: 12/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Skype pour les modifications de la topologie Business Server 2015 ou la mise en service pour permettre aux utilisateurs d’exécuter l’outil de Stress et de performances.
ms.openlocfilehash: 825dd56a7f2cb343eddd8cbed7e811cdc5154b9c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a><span data-ttu-id="fe738-103">Mise en service de la topologie pour exécuter la charge dans les scénarios de contrainte et de performances</span><span class="sxs-lookup"><span data-stu-id="fe738-103">Provisioning the topology to run load in Stress and Performance scenarios</span></span>
 
<span data-ttu-id="fe738-104">Skype pour les modifications de la topologie Business Server 2015 ou la mise en service pour permettre aux utilisateurs d’exécuter l’outil de Stress et de performances.</span><span class="sxs-lookup"><span data-stu-id="fe738-104">Skype for Business Server 2015 topology changes or provisioning to allow users to successfully run the Stress and Performance tool.</span></span>
  
<span data-ttu-id="fe738-105">Selon vos paramètres existants et la configuration de votre déploiement de Skype pour Business Server 2015, vous devrez peut-être effectuer des modifications dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="fe738-105">Depending on your existing settings and configuration for your deployment of Skype for Business Server 2015, you might need to make some changes in your environment.</span></span> <span data-ttu-id="fe738-106">Voici une liste de ces modifications :</span><span class="sxs-lookup"><span data-stu-id="fe738-106">The following is a list of those changes:</span></span>
  
1. <span data-ttu-id="fe738-107">Définir la stratégie d’exécution Windows PowerShell non restreint.</span><span class="sxs-lookup"><span data-stu-id="fe738-107">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="fe738-108">Si vous n’êtes pas sûr qu’il est la valeur actuellement, vous pouvez ouvrir le Skype pour Business Server Management Shell et exécutez cette commande :</span><span class="sxs-lookup"><span data-stu-id="fe738-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span></span>
    
  ```
  Get-ExecutionPolicy
  ```

  <span data-ttu-id="fe738-109">Si la valeur non restreint n’est pas retournée, vous devez exécuter ce suivant :</span><span class="sxs-lookup"><span data-stu-id="fe738-109">If the value Unrestricted is not returned, you'll need to run this next:</span></span>
    
  ```
  Set-ExecutionPolicy -Unrestricted
  ```

2. <span data-ttu-id="fe738-110">Pour configurer efficacement Skype pour Business Server, vous devez :</span><span class="sxs-lookup"><span data-stu-id="fe738-110">To effectively configure Skype for Business Server, you'll need to:</span></span>
    
    - <span data-ttu-id="fe738-111">Être familiarisé avec votre Skype pour la topologie 2015 de serveur d’entreprise (par exemple, les noms d’ordinateur, les instances de service, les noms de site et stratégies).</span><span class="sxs-lookup"><span data-stu-id="fe738-111">Be familiar with your Skype for Business Server 2015 topology (such as computer names, service instances, site names, and policies).</span></span>
    
    - <span data-ttu-id="fe738-112">Affecter certains utilisateurs qui sont créées à des groupes, tels que les groupes (par exemple, URI SIP) de recherche de groupe de la réponse.</span><span class="sxs-lookup"><span data-stu-id="fe738-112">Assign some of the users that are created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>
    
3. <span data-ttu-id="fe738-113">Pour exécuter un script à partir de la ligne de commande, vous pouvez utiliser :</span><span class="sxs-lookup"><span data-stu-id="fe738-113">To run a script from command line, you can use:</span></span>
    
  ```
  PowerShell.exe -file <path to the file>
  ```

4. <span data-ttu-id="fe738-114">En général, après avoir exécuté un script à partir de ce package, les traces qui en résulte seront stockées dans un fichier dans le même chemin d’accès à partir duquel le script a été exécuté.</span><span class="sxs-lookup"><span data-stu-id="fe738-114">Typically, after you've run a script from this package, the resulting traces will be stored in a file in the same path from where the script was run.</span></span> <span data-ttu-id="fe738-115">Il existe également un format de dénomination \<nom_script\>$h$m$s.txt.</span><span class="sxs-lookup"><span data-stu-id="fe738-115">There's a naming format as well, \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="fe738-116">Par conséquent, si vous exécutez le ArchivingPolicy.ps1 à 12 h 15, vous obtiendrez un fichier journal nommé ArchivingPolicy121500.txt.</span><span class="sxs-lookup"><span data-stu-id="fe738-116">So if you ran the ArchivingPolicy.ps1 at 12:15 PM, you'll get a log file named ArchivingPolicy121500.txt.</span></span>
    
5. <span data-ttu-id="fe738-117">Alors que nous vous avons fourni ces exemples de configuration de votre serveur, c’est à vous des modifier votre configuration et restaurer ou déployer une fois vous avez fini d’exécuter le test de charge.</span><span class="sxs-lookup"><span data-stu-id="fe738-117">While we've provided these examples for your server configuration, it's up to you to both modify your configuration and restore or roll it back after you've finished running the load testing.</span></span>
    

