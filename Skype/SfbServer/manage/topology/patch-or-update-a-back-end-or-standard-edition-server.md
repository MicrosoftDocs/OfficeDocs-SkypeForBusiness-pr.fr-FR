---
title: Correctif ou mise à jour d’un serveur principal ou d’un serveur Standard Edition dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Résumé : Découvrez comment installer une mise à jour ou un correctif sur un serveur principal dans Skype entreprise Server.'
ms.openlocfilehash: a88224c508426d16217adb87693515314b03e40f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991499"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a><span data-ttu-id="1eb52-103">Correctif ou mise à jour d’un serveur principal ou d’un serveur Standard Edition dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1eb52-103">Patch or update a Back End Server or Standard Edition server in Skype for Business Server</span></span>
 
<span data-ttu-id="1eb52-104">**Résumé :** Découvrez comment installer une mise à jour ou un correctif sur un serveur principal dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1eb52-104">**Summary:** Learn how to install an update or patch on a Back End Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="1eb52-105">Cette rubrique explique comment installer une mise à jour sur un serveur principal Enterprise Edition ou un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="1eb52-105">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>
  
<span data-ttu-id="1eb52-106">Si un serveur principal est arrêté pendant au moins 30 minutes lors de la mise à niveau, les utilisateurs peuvent alors basculer en mode de résilience.</span><span class="sxs-lookup"><span data-stu-id="1eb52-106">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="1eb52-107">Lorsque la mise à niveau est terminée et que les serveurs dorsaux sont à nouveau connectés avec les serveurs frontaux de la liste, les utilisateurs sont retournés à toutes les fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="1eb52-107">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="1eb52-108">Si la mise à niveau dure moins de 30 minutes, les utilisateurs ne sont pas affectés.</span><span class="sxs-lookup"><span data-stu-id="1eb52-108">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="1eb52-109">Pour mettre à jour un serveur principal ou un serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="1eb52-109">To update a back end server or Standard Edition server</span></span>

1. <span data-ttu-id="1eb52-110">Connectez-vous au serveur que vous mettez à niveau en tant que membre du rôle CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1eb52-110">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>
    
2. <span data-ttu-id="1eb52-111">Téléchargez la mise à jour et extrayez-la sur le disque dur local.</span><span class="sxs-lookup"><span data-stu-id="1eb52-111">Download the update and extract it to the local hard disk.</span></span>
    
3. <span data-ttu-id="1eb52-112">Démarrer Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1eb52-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**..</span></span>
    
4. <span data-ttu-id="1eb52-113">Arrêtez les services Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1eb52-113">Stop Skype for Business Server services.</span></span> <span data-ttu-id="1eb52-114">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="1eb52-114">At the command line, type:</span></span>
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. <span data-ttu-id="1eb52-115">Arrêtez les services World Wide Web.</span><span class="sxs-lookup"><span data-stu-id="1eb52-115">Stop the World Wide Web service.</span></span> <span data-ttu-id="1eb52-116">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="1eb52-116">At the command line, type:</span></span>
    
    ```PowerShell
    net stop w3svc
   ```

6. <span data-ttu-id="1eb52-117">Fermez toutes les fenêtres de Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="1eb52-117">Close all Skype for Business Server Management Shell windows.</span></span>
    
7. <span data-ttu-id="1eb52-118">Installez la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="1eb52-118">Install the update.</span></span>
    
8. <span data-ttu-id="1eb52-119">Démarrer Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1eb52-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
9. <span data-ttu-id="1eb52-120">Arrêtez de nouveau les services Skype entreprise Server pour intercepter les assemblys du cache d’assembly global.</span><span class="sxs-lookup"><span data-stu-id="1eb52-120">Stop Skype for Business Server services again to catch Global Assembly Cache (GAC) -d assemblies.</span></span> <span data-ttu-id="1eb52-121">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="1eb52-121">At the command line, type:</span></span>
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. <span data-ttu-id="1eb52-p105">Redémarrez les services World Wide Web. À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="1eb52-p105">Restart the World Wide Web service. At the command line, type:</span></span>
    
    ```PowerShell
    net start w3svc
    ```

11. <span data-ttu-id="1eb52-124">Appliquez les modifications apportées aux bases de données SQL Server en effectuant l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="1eb52-124">Apply the changes made to the SQL Server databases by doing one of the following:</span></span>
    
    - <span data-ttu-id="1eb52-125">S’il s’agit d’un serveur principal Enterprise Edition et qu’il n’y a pas de bases de données colocalisées sur ce serveur, telles que des bases de données d’archivage ou de surveillance, tapez les informations suivantes dans une ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="1eb52-125">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - <span data-ttu-id="1eb52-126">S’il s’agit d’une base de données serveur principal de la version Enterprise Edition et de bases de données colocalisées sur ce serveur, tapez les informations suivantes à partir de la ligne de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="1eb52-126">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - <span data-ttu-id="1eb52-127">S’il s’agit d’un serveur Standard Edition Server, tapez les informations suivantes dans une ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="1eb52-127">If this is an Standard Edition server, type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```
