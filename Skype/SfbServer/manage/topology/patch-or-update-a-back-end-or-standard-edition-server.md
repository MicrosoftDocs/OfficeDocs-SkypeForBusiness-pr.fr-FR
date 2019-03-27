---
title: Correctifs ou mise à jour d’un serveur principal ou Standard Edition server dans Skype pour Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Résumé : Découvrez comment installer une mise à jour ou un correctif sur un serveur principal Skype pour Business Server.'
ms.openlocfilehash: 7919d437e5111d32f3f51fa19a1880714800666b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884152"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a><span data-ttu-id="5befc-103">Correctifs ou mise à jour d’un serveur principal ou Standard Edition server dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="5befc-103">Patch or update a Back End Server or Standard Edition server in Skype for Business Server</span></span>
 
<span data-ttu-id="5befc-104">**Résumé :** Découvrez comment installer une mise à jour ou un correctif sur un serveur principal Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="5befc-104">**Summary:** Learn how to install an update or patch on a Back End Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="5befc-105">Cette rubrique explique comment installer une mise à jour sur un serveur Enterprise Edition Back ou un serveur Standard Edition server.</span><span class="sxs-lookup"><span data-stu-id="5befc-105">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>
  
<span data-ttu-id="5befc-106">Si un serveur principal est vers le bas au moins 30 minutes pendant que vous mettez à niveau il, les utilisateurs peuvent passer en mode résistance.</span><span class="sxs-lookup"><span data-stu-id="5befc-106">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="5befc-107">Lorsque la mise à niveau est terminée et les serveurs principaux est connecté à nouveau avec les serveurs frontaux du pool, les utilisateurs sont renvoyées pour toutes les fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="5befc-107">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="5befc-108">Si la mise à niveau dure moins de 30 minutes, les utilisateurs ne sont pas affectés.</span><span class="sxs-lookup"><span data-stu-id="5befc-108">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="5befc-109">Pour mettre à jour un serveur principal ou un serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="5befc-109">To update a back end server or Standard Edition server</span></span>

1. <span data-ttu-id="5befc-110">Connectez-vous au serveur que vous mettez à niveau en tant que membre du rôle CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="5befc-110">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>
    
2. <span data-ttu-id="5befc-111">Téléchargez la mise à jour et extrayez-la sur le disque dur local.</span><span class="sxs-lookup"><span data-stu-id="5befc-111">Download the update and extract it to the local hard disk.</span></span>
    
3. <span data-ttu-id="5befc-112">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour les entreprises**, puis cliquez sur **Skype pour Business Server Management Shell**...</span><span class="sxs-lookup"><span data-stu-id="5befc-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**..</span></span>
    
4. <span data-ttu-id="5befc-113">Arrêtez Skype pour les services Business Server.</span><span class="sxs-lookup"><span data-stu-id="5befc-113">Stop Skype for Business Server services.</span></span> <span data-ttu-id="5befc-114">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="5befc-114">At the command line, type:</span></span>
    
    ```
    Stop-CsWindowsService
    ```

5. <span data-ttu-id="5befc-115">Arrêtez les services World Wide Web.</span><span class="sxs-lookup"><span data-stu-id="5befc-115">Stop the World Wide Web service.</span></span> <span data-ttu-id="5befc-116">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="5befc-116">At the command line, type:</span></span>
    
    ```
    net stop w3svc
   ```

6. <span data-ttu-id="5befc-117">Fermez toutes les Skype pour windows Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5befc-117">Close all Skype for Business Server Management Shell windows.</span></span>
    
7. <span data-ttu-id="5befc-118">Installez la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="5befc-118">Install the update.</span></span>
    
8. <span data-ttu-id="5befc-119">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour les entreprises**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="5befc-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
9. <span data-ttu-id="5befc-120">Arrêtez Skype pour les services Business Server pour intercepter les assemblys -d Global Assembly Cache (GAC).</span><span class="sxs-lookup"><span data-stu-id="5befc-120">Stop Skype for Business Server services again to catch Global Assembly Cache (GAC) -d assemblies.</span></span> <span data-ttu-id="5befc-121">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="5befc-121">At the command line, type:</span></span>
    
    ```
    Stop-CsWindowsService
    ```

10. <span data-ttu-id="5befc-p105">Redémarrez les services World Wide Web. À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="5befc-p105">Restart the World Wide Web service. At the command line, type:</span></span>
    
    ```
    net start w3svc
    ```

11. <span data-ttu-id="5befc-124">Appliquez les modifications apportées aux bases de données SQL Server en effectuant l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="5befc-124">Apply the changes made to the SQL Server databases by doing one of the following:</span></span>
    
    - <span data-ttu-id="5befc-125">Si c’est un serveur Enterprise Edition fin et aucun des bases de données COLOCALISÉES sur ce serveur, telles que l’archivage ou les bases de données de surveillance, puis tapez ce qui suit sur la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="5befc-125">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - <span data-ttu-id="5befc-126">Si c’est un serveur Enterprise Edition fin et il existe des bases de données COLOCALISÉES sur ce serveur, puis tapez ce qui suit sur la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="5befc-126">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - <span data-ttu-id="5befc-127">S’il s’agit d’un serveur Standard Edition server, tapez ce qui suit sur la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="5befc-127">If this is an Standard Edition server, type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -LocalDatabases

    ```
