---
title: Gérer les paramètres de configuration du service de journalisation centralisée dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: 'Résumé : Découvrez comment récupérer, mettre à jour et créer des paramètres de configuration pour le service de journalisation centralisée dans Skype Entreprise Server 2015.'
ms.openlocfilehash: dd292465d65116dc1f497a733ca8e010e57b9137
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835154"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="7537b-103">Gérer les paramètres de configuration du service de journalisation centralisée dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="7537b-103">Manage Centralized Logging Service configuration settings in Skype for Business Server 2015</span></span>

<span data-ttu-id="7537b-104">**Résumé :** Découvrez comment récupérer, mettre à jour et créer des paramètres de configuration pour le service de journalisation centralisée dans Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7537b-104">**Summary:** Learn how to retrieve, update, and create configuration settings for the Centralized Logging Service in Skype for Business Server 2015.</span></span>

<span data-ttu-id="7537b-105">Le service de journalisation centralisée est contrôlé et configuré par des paramètres et des paramètres créés et utilisés par le contrôleur de service de journalisation centralisée (CLSController) pour envoyer des commandes à l’agent CLSAgent (Centralized Logging Service Agent) de l’ordinateur individuel.</span><span class="sxs-lookup"><span data-stu-id="7537b-105">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer's Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="7537b-106">L’agent traite les commandes qui lui sont envoyées et (dans le cas d’une commande De démarrage) utilise la configuration des scénarios, des fournisseurs, de la durée du suivi et des indicateurs pour commencer à collecter les journaux de suivi en fonction des informations de configuration fournies.</span><span class="sxs-lookup"><span data-stu-id="7537b-106">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="7537b-107">Les cmdlets Windows PowerShell répertoriées pour le service de journalisation centralisée ne sont pas toutes destinées à être utilisés avec les déploiements locaux de Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7537b-107">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Skype for Business Server 2015 on-premises deployments.</span></span> <span data-ttu-id="7537b-108">Bien qu’elles semblent fonctionner, les cmdlets suivantes ne sont pas conçues pour fonctionner avec les déploiements locaux de Skype Entreprise Server 2015 :</span><span class="sxs-lookup"><span data-stu-id="7537b-108">Although they may appear to work, the following cmdlets are not designed to function with Skype for Business Server 2015 on-premises deployments:</span></span>

-  <span data-ttu-id="7537b-109">**Cmdlets CsClsRegion :** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)et [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="7537b-109">**CsClsRegion cmdlets:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps), and [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span></span>
-  <span data-ttu-id="7537b-110">**Cmdlets CsClsSearchTerm** : [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) et [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="7537b-110">**CsClsSearchTerm cmdlets:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) and [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span></span>
-  <span data-ttu-id="7537b-111">**Cmdlets CsClsSecurityGroup :** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps),  [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)et [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="7537b-111">**CsClsSecurityGroup cmdlets:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps),  [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps), and [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span></span>

<span data-ttu-id="7537b-112">Les paramètres définis dans ces cmdlets n’empêchent pas ou ne provoquent aucun comportement indésirable, mais ils sont conçus pour être utilisés avec Microsoft 365 ou Office 365 et ne donnent pas les résultats attendus dans les déploiements locaux.</span><span class="sxs-lookup"><span data-stu-id="7537b-112">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft 365 or Office 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="7537b-113">Cela ne veut pas dire qu’il n’est pas nécessaire d’utiliser ces cmdlets dans les déploiements locaux, mais leur utilisation est un sujet plus avancé qui n’est pas abordé dans cette documentation.</span><span class="sxs-lookup"><span data-stu-id="7537b-113">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>

<span data-ttu-id="7537b-114">Le service de journalisation centralisée peut être exécuté dans une étendue comprenant un seul ordinateur ou un pool d’ordinateurs, au niveau d’un site (autrement dit, un site défini tel que le site Redmond qui contient une collection d’ordinateurs et de pools dans votre déploiement) ou au niveau global (c’est-à-dire, tous les ordinateurs et pools de votre déploiement).</span><span class="sxs-lookup"><span data-stu-id="7537b-114">The Centralized Logging Service can be run at a scope that includes a single computer or a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="7537b-115">Pour configurer l’étendue du service de journalisation centralisée à l’aide de Skype Entreprise Server Management Shell, vous devez être membre des groupes de sécurité RBAC CsAdministrator ou CsServerAdministrator, ou d’un rôle RBAC personnalisé contenant l’un de ces deux groupes.</span><span class="sxs-lookup"><span data-stu-id="7537b-115">To configure the Centralized Logging Service scope by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="7537b-116">Pour retourner la liste de tous les rôles RBAC attribués à cette cmdlet (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de Skype Entreprise Server Management Shell ou de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="7537b-116">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

<span data-ttu-id="7537b-117">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="7537b-117">For example:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> <span data-ttu-id="7537b-118">Il existe des différences fondamentales entre les commandes de ligne de commande que vous pouvez exécuter dans Windows PowerShell ou CLSController.</span><span class="sxs-lookup"><span data-stu-id="7537b-118">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="7537b-119">Windows PowerShell fournit une méthode enrichie pour configurer et définir des scénarios, et pour réutiliser ces scénarios de manière significative pour vos scénarios de dépannage.</span><span class="sxs-lookup"><span data-stu-id="7537b-119">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="7537b-120">CLSController fournit un moyen rapide et efficace d’émettre des commandes et d’obtenir des résultats, l’ensemble de commandes pour CLSController est limité à un nombre fini de commandes disponibles à partir de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="7537b-120">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="7537b-121">Contrairement aux cmdlets Windows PowerShell, CLSController ne peut pas définir de nouveaux scénarios, gérer l’étendue au niveau global ou d’un site, ni de nombreuses autres limitations d’un jeu de commandes fini qui ne peut pas être configuré dynamiquement.</span><span class="sxs-lookup"><span data-stu-id="7537b-121">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="7537b-122">Bien que CLSController offre un moyen d’une exécution rapide, Windows PowerShell permet d’étendre la fonctionnalité du service de journalisation centralisée au-delà de ce qui est possible avec CLSController.</span><span class="sxs-lookup"><span data-stu-id="7537b-122">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>

<span data-ttu-id="7537b-123">Une étendue d’ordinateur unique peut être définie lors de l’exécution d’une commande [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) et [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) à l’aide du paramètre -Computers.</span><span class="sxs-lookup"><span data-stu-id="7537b-123">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) and [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) command using the -Computers parameter.</span></span> <span data-ttu-id="7537b-124">Le paramètre -Computers accepte une liste séparée par des virgules de noms de domaine complets (FQDN) pour l’ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="7537b-124">The -Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

> [!TIP]
> <span data-ttu-id="7537b-125">Vous pouvez également définir -Pools et une liste séparée par des virgules des pools sur qui vous souhaitez exécuter les commandes de journalisation.</span><span class="sxs-lookup"><span data-stu-id="7537b-125">You can also define -Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>

<span data-ttu-id="7537b-126">Les étendues de site et globales sont définies dans les cmdlets **New-**, **Set-** et **Remove-** Centralized Logging Service.</span><span class="sxs-lookup"><span data-stu-id="7537b-126">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="7537b-127">Les exemples suivants montrent comment définir une étendue globale ou de site.</span><span class="sxs-lookup"><span data-stu-id="7537b-127">The following examples demonstrate how to set a site and a global scope.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7537b-128">Les commandes indiquées peuvent contenir des paramètres et des concepts décrits dans d’autres sections.</span><span class="sxs-lookup"><span data-stu-id="7537b-128">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="7537b-129">Les exemples de commandes sont destinés à démontrer l’utilisation du paramètre **-Identity** pour définir l’étendue, et les autres paramètres sont inclus pour l’intégralité et pour spécifier l’étendue.</span><span class="sxs-lookup"><span data-stu-id="7537b-129">The example commands are intended to demonstrate the use of the **-Identity** parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="7537b-130">Pour plus d’informations sur les applets de commande **Set-CsClsConfiguration**, voir [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="7537b-130">For details about the **Set-CsClsConfiguration** cmdlets, see [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) in the Operations documentation.</span></span>

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="7537b-131">Pour récupérer la configuration actuelle du service de journalisation centralisée</span><span class="sxs-lookup"><span data-stu-id="7537b-131">To retrieve the current Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="7537b-132">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="7537b-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="7537b-133">Tapez ce qui suit à l’invite de ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="7537b-133">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration
   ```

<span data-ttu-id="7537b-134">Utilisez les cmdlets **New-CsClsConfiguration** et **Set-CsClsConfiguration** pour créer une configuration ou mettre à jour une configuration existante. Lorsque vous exécutez **Get-CsClsConfiguration,** elle affiche des informations similaires à la capture d’écran suivante, où le déploiement a actuellement la configuration globale par défaut, mais aucune configuration de site définie :</span><span class="sxs-lookup"><span data-stu-id="7537b-134">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

![Exemple de sortie de Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="7537b-136">Pour récupérer la configuration actuelle du service de journalisation centralisée à partir du magasin local de l’ordinateur</span><span class="sxs-lookup"><span data-stu-id="7537b-136">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1. <span data-ttu-id="7537b-137">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="7537b-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="7537b-138">Tapez ce qui suit à l’invite de ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="7537b-138">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

<span data-ttu-id="7537b-139">Lorsque vous utilisez le premier exemple où **Get-CsClsConfiguration** ne spécifie aucun paramètre, la commande fait référence au magasin central de gestion pour les données.</span><span class="sxs-lookup"><span data-stu-id="7537b-139">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="7537b-140">Si vous spécifiez le paramètre -LocalStore, la commande fait référence à l’ordinateur LocalStore au lieu du magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="7537b-140">If you specify the parameter -LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="7537b-141">Pour récupérer une liste des scénarios actuellement définis</span><span class="sxs-lookup"><span data-stu-id="7537b-141">To retrieve a listing of scenarios currently defined</span></span>

1. <span data-ttu-id="7537b-142">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="7537b-142">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="7537b-143">Tapez ce qui suit à l’invite de ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="7537b-143">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    <span data-ttu-id="7537b-144">Pour exemple, pour récupérer les scénarios définis au niveau global :</span><span class="sxs-lookup"><span data-stu-id="7537b-144">For example, to retrieve the scenarios that is defined at the global scope:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

<span data-ttu-id="7537b-145">L’cmdlet **Get-CsClsConfiguration** affiche toujours les scénarios qui font partie de la configuration d’une étendue donnée.</span><span class="sxs-lookup"><span data-stu-id="7537b-145">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope's configuration.</span></span> <span data-ttu-id="7537b-146">Dans la plupart des cas, tous les scénarios ne sont pas affichés, et sont tronqués.</span><span class="sxs-lookup"><span data-stu-id="7537b-146">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="7537b-147">La commande utilisée ici répertorie tous les scénarios et des informations partielles sur les fournisseurs, les paramètres et les indicateurs utilisés.</span><span class="sxs-lookup"><span data-stu-id="7537b-147">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="7537b-148">Pour mettre à jour une étendue globale pour le service de journalisation centralisée à l’aide Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7537b-148">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="7537b-149">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="7537b-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="7537b-150">Tapez ce qui suit à l’invite de ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="7537b-150">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="7537b-151">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="7537b-151">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

<span data-ttu-id="7537b-p111">La commande indique au CLSAgent de chaque ordinateur et pool du déploiement de définir la valeur de substitution dans le fichier de suivi à 40 mégaoctets. Les ordinateurs et les pools de tous les sites sont affectés par cette commande, et définiront la valeur de substitution du journal de suivi configuré à 40 mégaoctets.</span><span class="sxs-lookup"><span data-stu-id="7537b-p111">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="7537b-154">Pour mettre à jour une étendue de site pour le service de journalisation centralisée à l’aide Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7537b-154">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="7537b-155">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="7537b-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="7537b-156">Tapez ce qui suit à l’invite de ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="7537b-156">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="7537b-157">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="7537b-157">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> <span data-ttu-id="7537b-p112">Comme indiqué dans l’exemple, l’emplacement par défaut des fichiers journaux est %TEMP%\Tracing. Cependant, dans la mesure où CLSAgent écrit dans le fichier et qu’il s’exécute en tant que service réseau, la variable %TEMP% devient %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span><span class="sxs-lookup"><span data-stu-id="7537b-p112">As noted in the example, the default location of the log files is %TEMP%\Tracing. However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

<span data-ttu-id="7537b-p113">Cette commande indique au CLSAgent de chaque ordinateur et pool du site Redmond de définir la taille de la valeur de substitution du fichier de suivi à 40 mégaoctets. Les ordinateurs et les pools des autres sites ne sont pas affectés par cette commande, et continueront d’utiliser la valeur de substitution du journal de suivi configurée actuellement et définie par défaut (20 mégaoctets) ou lors du démarrage de la session de journalisation.</span><span class="sxs-lookup"><span data-stu-id="7537b-p113">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>
### <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="7537b-162">Pour créer une configuration du service de journalisation centralisée</span><span class="sxs-lookup"><span data-stu-id="7537b-162">To create a new Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="7537b-163">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="7537b-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="7537b-164">Tapez ce qui suit à l’invite de ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="7537b-164">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > <span data-ttu-id="7537b-165">New-CsClsConfiguration fournit un accès à de nombreux paramètres de configuration supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="7537b-165">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="7537b-166">Pour plus d’informations sur les options de configuration, voir [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Settings](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).</span><span class="sxs-lookup"><span data-stu-id="7537b-166">For details about the configuration options, see [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Settings](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).</span></span>

<span data-ttu-id="7537b-167">Par exemple, pour créer une configuration qui définit un dossier réseau pour les fichiers en cache, la période de substitution pour les fichiers journaux et la taille de la substitution pour les fichiers journaux, tapez :</span><span class="sxs-lookup"><span data-stu-id="7537b-167">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

<span data-ttu-id="7537b-168">Vous devez soigneusement planifier la création de nouvelles configurations et la façon dont vous définissez de nouvelles propriétés pour le service de journalisation centralisée.</span><span class="sxs-lookup"><span data-stu-id="7537b-168">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="7537b-169">Faites attention lorsque vous apportez des modifications et assurez-vous de bien comprendre l’impact sur la journalisation des scénarios.</span><span class="sxs-lookup"><span data-stu-id="7537b-169">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="7537b-170">Apportez des modifications à la configuration pour améliorer la résolution des problèmes en permettant une meilleure gestion des tailles de journaux et de la période de substitution.</span><span class="sxs-lookup"><span data-stu-id="7537b-170">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="7537b-171">Pour supprimer une configuration existante du service de journalisation centralisée</span><span class="sxs-lookup"><span data-stu-id="7537b-171">To remove an existing Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="7537b-172">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="7537b-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="7537b-173">Tapez ce qui suit à l’invite de ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="7537b-173">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

<span data-ttu-id="7537b-174">Par exemple, pour supprimer une configuration du service de journalisation centralisée que vous avez créée pour augmenter le temps de déploiement des fichiers journaux, augmentez la taille du fichier journal de rollover et définissez l’emplacement du cache des fichiers journaux sur un partage réseau comme suit :</span><span class="sxs-lookup"><span data-stu-id="7537b-174">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> <span data-ttu-id="7537b-175">Il s’agit de la nouvelle configuration qui a été créée dans la procédure « Pour créer une nouvelle configuration du service de journalisation centralisée ».</span><span class="sxs-lookup"><span data-stu-id="7537b-175">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

<span data-ttu-id="7537b-176">Si vous choisissez de supprimer une configuration au niveau du site, le site utilisera les paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="7537b-176">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>
## <a name="see-also"></a><span data-ttu-id="7537b-177">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7537b-177">See also</span></span>

[<span data-ttu-id="7537b-178">Configuration des fournisseurs pour le service de journalisation centralisée dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="7537b-178">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-providers.md)

[<span data-ttu-id="7537b-179">Configurer des scénarios pour le service de journalisation centralisée dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="7537b-179">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-scenarios.md)

[<span data-ttu-id="7537b-180">Service de journalisation centralisée dans Skype Entreprise 2015</span><span class="sxs-lookup"><span data-stu-id="7537b-180">Centralized Logging Service in Skype for Business 2015</span></span>](centralized-logging-service.md)

[<span data-ttu-id="7537b-181">Set-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="7537b-181">Set-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="7537b-182">Get-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="7537b-182">Get-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="7537b-183">New-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="7537b-183">New-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="7537b-184">Remove-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="7537b-184">Remove-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
