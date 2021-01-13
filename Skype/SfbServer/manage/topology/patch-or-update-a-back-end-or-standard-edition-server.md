---
title: Correction ou mise à jour d’un serveur principal ou d’un serveur Standard Edition server dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Résumé : Découvrez comment installer une mise à jour ou un correctif sur un serveur principal dans Skype Entreprise Server.'
ms.openlocfilehash: 3e5e0cda1604f3144e853cfa3bf7bcc45e7d0c2f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826304"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a><span data-ttu-id="82199-103">Correction ou mise à jour d’un serveur principal ou d’un serveur Standard Edition server dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="82199-103">Patch or update a Back End Server or Standard Edition server in Skype for Business Server</span></span>
 
<span data-ttu-id="82199-104">**Résumé :** Découvrez comment installer une mise à jour ou un correctif sur un serveur principal dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="82199-104">**Summary:** Learn how to install an update or patch on a Back End Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="82199-105">Cette rubrique explique comment installer une mise à jour sur un serveur principal Enterprise Edition ou standard.</span><span class="sxs-lookup"><span data-stu-id="82199-105">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>
  
<span data-ttu-id="82199-p101">Si un serveur principal est arrêté durant au moins 30 minutes lors de sa mise à niveau, les utilisateurs peuvent être placés en mode Résilience. Lorsque la mise à mise à niveau est terminée et que les serveurs principaux sont encore connectés aux serveurs frontaux du pool, les utilisateurs repassent en fonctionnalité complète. Si la mise à niveau dure moins de 30 minutes, les utilisateurs ne seront pas affectés.</span><span class="sxs-lookup"><span data-stu-id="82199-p101">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode. When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality. If the upgrade takes less than 30 minutes, users will not be affected.</span></span>
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="82199-109">Pour mettre à jour un serveur principal ou un serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="82199-109">To update a back end server or Standard Edition server</span></span>

1. <span data-ttu-id="82199-110">Connectez-vous au serveur que vous mettez à niveau en tant que membre du rôle CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="82199-110">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>
    
2. <span data-ttu-id="82199-111">Téléchargez la mise à jour et extrayez-la sur le disque dur local.</span><span class="sxs-lookup"><span data-stu-id="82199-111">Download the update and extract it to the local hard disk.</span></span>
    
3. <span data-ttu-id="82199-112">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype** Entreprise, puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="82199-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**..</span></span>
    
4. <span data-ttu-id="82199-113">Arrêtez les services Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="82199-113">Stop Skype for Business Server services.</span></span> <span data-ttu-id="82199-114">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="82199-114">At the command line, type:</span></span>
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. <span data-ttu-id="82199-115">Arrêtez les services World Wide Web.</span><span class="sxs-lookup"><span data-stu-id="82199-115">Stop the World Wide Web service.</span></span> <span data-ttu-id="82199-116">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="82199-116">At the command line, type:</span></span>
    
    ```PowerShell
    net stop w3svc
   ```

6. <span data-ttu-id="82199-117">Fermez toutes les fenêtres Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="82199-117">Close all Skype for Business Server Management Shell windows.</span></span>
    
7. <span data-ttu-id="82199-118">Installez la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="82199-118">Install the update.</span></span>
    
8. <span data-ttu-id="82199-119">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype** Entreprise, puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="82199-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
9. <span data-ttu-id="82199-120">Arrêtez de nouveau les services Skype Entreprise Server pour capturer les assemblys GAC (Global Assembly Cache).</span><span class="sxs-lookup"><span data-stu-id="82199-120">Stop Skype for Business Server services again to catch Global Assembly Cache (GAC) -d assemblies.</span></span> <span data-ttu-id="82199-121">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="82199-121">At the command line, type:</span></span>
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. <span data-ttu-id="82199-122">Redémarrez le service World Wide Web.</span><span class="sxs-lookup"><span data-stu-id="82199-122">Restart the World Wide Web service.</span></span> <span data-ttu-id="82199-123">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="82199-123">At the command line, type:</span></span>
    
    ```PowerShell
    net start w3svc
    ```

11. <span data-ttu-id="82199-124">Appliquez les modifications apportées aux bases SQL Server données en faisant l’une des choses suivantes :</span><span class="sxs-lookup"><span data-stu-id="82199-124">Apply the changes made to the SQL Server databases by doing one of the following:</span></span>
    
    - <span data-ttu-id="82199-125">S’il s’agit d’un serveur principal Enterprise Edition et qu’il n’y a pas de bases de données cingl es sur ce serveur, telles que les bases de données d’archivage ou de surveillance, tapez ce qui suit sur une ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="82199-125">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - <span data-ttu-id="82199-126">S’il s’agit d’un serveur principal Enterprise Edition et qu’il existe des bases de données c c colloquées sur ce serveur, tapez ce qui suit sur une ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="82199-126">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - <span data-ttu-id="82199-127">S’il s’agit d’un serveur Standard Edition, tapez ce qui suit sur une ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="82199-127">If this is an Standard Edition server, type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```
