---
title: Configuration des scénarios du service de journalisation centralisée dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: 'Résumé: Découvrez comment créer, modifier et supprimer des scénarios pour le service de journalisation centralisé dans Skype entreprise Server 2015.'
ms.openlocfilehash: 89aa0c37dfb13f7614067b64e37ee9c9fb376331
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274435"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="03c88-103">Configuration des scénarios du service de journalisation centralisée dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="03c88-103">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="03c88-104">**Résumé:** Découvrez comment créer, modifier et supprimer des scénarios pour le service de journalisation centralisé dans Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="03c88-104">**Summary:** Learn how to create, modify, and remove scenarios for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="03c88-105">Les scénarios définissent l’étendue (c’est-à-dire, le site, le pool ou l’ordinateur) et les fournisseurs à utiliser dans le service de journalisation centralisé.</span><span class="sxs-lookup"><span data-stu-id="03c88-105">Scenarios define the scope (that is, global, site, pool, or computer) and what providers to use in the Centralized Logging Service.</span></span> <span data-ttu-id="03c88-106">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span><span class="sxs-lookup"><span data-stu-id="03c88-106">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span></span> <span data-ttu-id="03c88-107">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span><span class="sxs-lookup"><span data-stu-id="03c88-107">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span></span> <span data-ttu-id="03c88-108">Si vous constatez qu’un scénario doit être modifié en fonction de vos besoins en matière de résolution des problèmes et de journalisation, les outils de débogage de Skype entreprise Server 2015 vous fournissent un module Windows PowerShell intitulé ClsScenarioEdit. psm1 qui contient une fonction namedEdit-CsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="03c88-108">If you find that a scenario needs to be modified to meet your troubleshooting and logging needs, the Skype for Business Server 2015 Debug Tools provides you a Windows PowerShell module named ClsScenarioEdit.psm1 that contains a function namedEdit-CsClsScenario.</span></span> <span data-ttu-id="03c88-109">The purpose of the module is to edit the properties of the named scenario.</span><span class="sxs-lookup"><span data-stu-id="03c88-109">The purpose of the module is to edit the properties of the named scenario.</span></span> <span data-ttu-id="03c88-110">Examples of how this module works are provided in this topic.</span><span class="sxs-lookup"><span data-stu-id="03c88-110">Examples of how this module works are provided in this topic.</span></span> <span data-ttu-id="03c88-111">Téléchargez les [Outils](https://go.microsoft.com/fwlink/p/?LinkId=285257) de débogage de Skype entreprise Server 2015 avant d’aller plus loin.</span><span class="sxs-lookup"><span data-stu-id="03c88-111">Download the Skype for Business Server 2015 [Debugging Tools](https://go.microsoft.com/fwlink/p/?LinkId=285257) before going any further.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="03c88-112">Pour une étendue donnée (globale, site, pool ou ordinateur), deux scénarios au maximum peuvent être exécutés en même temps.</span><span class="sxs-lookup"><span data-stu-id="03c88-112">For any given scope—site, global, pool or computer—you can run a maximum of two scenarios at any given time.</span></span> <span data-ttu-id="03c88-113">Pour déterminer les scénarios actuellement en cours d’exécution, utilisez Windows PowerShell et [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="03c88-113">To determine which scenarios are currently running, use Windows PowerShell and [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span> <span data-ttu-id="03c88-114">L’utilisation de Windows PowerShell et [de Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)vous permet de changer dynamiquement les scénarios qui s’exécutent.</span><span class="sxs-lookup"><span data-stu-id="03c88-114">By using Windows PowerShell and [Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps), you can dynamically change which scenarios are running.</span></span> <span data-ttu-id="03c88-115">Cette opération peut s’avérer utile lors d’une session de journalisation pour ajuster ou affiner les données que vous collectez et les fournisseurs d’où ces données sont issues.</span><span class="sxs-lookup"><span data-stu-id="03c88-115">You can modify which scenarios are running during a logging session to adjust or refine the data you are collecting and from which providers.</span></span> 
  
<span data-ttu-id="03c88-116">Pour exécuter les fonctions de service de journalisation centralisées à l’aide de Skype entreprise Server Management Shell, vous devez être membre des groupes de sécurité CsAdministrator ou CsServerAdministrator de contrôle d’accès basé sur les rôles (RBAC), ou un rôle RBAC personnalisé qui contient l’un de ces deux groupes.</span><span class="sxs-lookup"><span data-stu-id="03c88-116">To run the Centralized Logging Service functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="03c88-117">Pour renvoyer la liste de tous les rôles RBAC attribués à cette applet de commande, y compris les rôles RBAC personnalisés que vous avez créés vous-même, exécutez la commande suivante à partir de Skype entreprise Server Management Shell ou de l’invite Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="03c88-117">To return a list of all the RBAC roles this cmdlet has been assigned to, including any custom RBAC roles you have created yourself, run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="03c88-118">Exemple :</span><span class="sxs-lookup"><span data-stu-id="03c88-118">For example:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="03c88-119">Le reste de cette rubrique porte sur la façon de définir, de modifier, de supprimer un scénario, de récupérer des scénarios en cours dʼexécution et de spécifier les éléments dʼun scénario afin dʼoptimiser la résolution de problèmes.</span><span class="sxs-lookup"><span data-stu-id="03c88-119">The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting.</span></span> <span data-ttu-id="03c88-120">Vous pouvez utiliser Skype entreprise Server Management Shell pour exécuter les commandes Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="03c88-120">You can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="03c88-121">Lorsque vous utilisez Windows PowerShell, vous pouvez définir de nouveaux scénarios à utiliser dans vos sessions de journalisation.</span><span class="sxs-lookup"><span data-stu-id="03c88-121">When you use Windows PowerShell, you can define new scenarios for use in your logging sessions.</span></span>
  
<span data-ttu-id="03c88-122">Comme nous l’avons introduit dans le [service de journalisation centralisée de Skype entreprise 2015](centralized-logging-service.md), les éléments d’un scénario sont les suivants:</span><span class="sxs-lookup"><span data-stu-id="03c88-122">As introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the elements of a scenario are:</span></span>
  
- <span data-ttu-id="03c88-123">**Fournisseurs** Si vous avez l’habitude d’utiliser OCSLogger, les fournisseurs sont les composants que vous choisissez pour indiquer à OCSLogger ce sur quoi le moteur de suivi doit collecter les journaux.</span><span class="sxs-lookup"><span data-stu-id="03c88-123">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="03c88-124">Les fournisseurs sont les mêmes composants et, dans de nombreux cas, ont le même nom que les composants dans OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="03c88-124">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="03c88-125">Si vous n’êtes pas familiarisé avec OCSLogger, les fournisseurs sont des composants spécifiques du rôle serveur, que le service de journalisation centralisé peut collecter dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="03c88-125">If you are not familiar with OCSLogger, providers are server role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="03c88-126">Pour plus d’informations sur la configuration des fournisseurs, voir [configurer des fournisseurs pour le service de journalisation centralisé dans Skype entreprise Server 2015](configure-providers.md).</span><span class="sxs-lookup"><span data-stu-id="03c88-126">For details about the configuration of providers, see [Configure providers for Centralized Logging Service in Skype for Business Server 2015](configure-providers.md).</span></span>
    
- <span data-ttu-id="03c88-127">**Identité** Le paramètre-Identity définit l’étendue et le nom du scénario.</span><span class="sxs-lookup"><span data-stu-id="03c88-127">**Identity** The parameter -Identity sets the scope and name of the scenario.</span></span> <span data-ttu-id="03c88-128">Par exemple, vous pouvez définir une étendue de «global» et identifier le scénario avec «LyssServiceScenario».</span><span class="sxs-lookup"><span data-stu-id="03c88-128">For example, you could set a scope of "global" and identify the scenario with "LyssServiceScenario".</span></span> <span data-ttu-id="03c88-129">Lorsque vous combinez les deux, vous définissez l’identité (par exemple, «Global/LyssServiceScenario»).</span><span class="sxs-lookup"><span data-stu-id="03c88-129">When you combine the two, you define the Identity (for example, "global/LyssServiceScenario").</span></span>
    
    <span data-ttu-id="03c88-130">Vous pouvez également utiliser les paramètres-nom et parent.</span><span class="sxs-lookup"><span data-stu-id="03c88-130">Optionally, you can use the -Name and -Parent parameters.</span></span> <span data-ttu-id="03c88-131">Le paramètre Name permet d’identifier le scénario de manière unique.</span><span class="sxs-lookup"><span data-stu-id="03c88-131">You define the Name parameter to uniquely identify the scenario.</span></span> <span data-ttu-id="03c88-132">Si vous utilisez Name, vous devez également utiliser Parent pour ajouter le scénario à global ou site.</span><span class="sxs-lookup"><span data-stu-id="03c88-132">If you use Name, you must also use Parent to add the scenario to either global or site.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="03c88-133">Si vous utilisez les paramètres nom et parent, vous ne pouvez pas utiliser le paramètre **-Identity** .</span><span class="sxs-lookup"><span data-stu-id="03c88-133">If you use the Name and Parent parameters, you cannot use the **-Identity** parameter.</span></span>
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="03c88-134">Pour créer un scénario avec l’applet de commande New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="03c88-134">To create a new scenario with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="03c88-135">Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="03c88-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="03c88-p108">Pour créer un nouveau scénario pour une session de journalisation, utilisez [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) et définissez le nom du scénario (cʼest-à-dire comment il va être identifié de manière unique). Choisissez un type de format de journalisation dans WPP (cʼest-à-dire le préprocesseur de suivi Windows défini par défaut), EventLog (format de journal des événements Windows) ou IISLog (fichier au format ASCII basé sur le format de fichier journal IIS). Ensuite, définissez Level (voir la définition sous Niveaux de journalisation de cette rubrique) et Flags (voir la définition sous Indicateurs dans cette rubrique).</span><span class="sxs-lookup"><span data-stu-id="03c88-p108">To create a new scenario for a logging session, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) and define the name of the scenario (that is, how it will be uniquely identified). Choose a type of logging format from WPP (that is, Windows software tracing preprocessor and is the default), EventLog (that is, Windows event log format), or IISLog (that is, ASCII format file based on the IIS log file format). Next, define Level (as the defined under Logging Levels in this topic), and Flags (as defined under Flags in this topic).</span></span>
    
    <span data-ttu-id="03c88-139">Dans cet exemple de scénario, nous utilisons LyssProvider comme exemple de variable de fournisseur.</span><span class="sxs-lookup"><span data-stu-id="03c88-139">For this example scenario, we use LyssProvider as the example provider variable.</span></span>
    
    <span data-ttu-id="03c88-140">Pour créer un scénario en utilisant les options définies, tapez :</span><span class="sxs-lookup"><span data-stu-id="03c88-140">To create a scenario using the options defined, type:</span></span>
    
   ```
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    <span data-ttu-id="03c88-141">Exemple :</span><span class="sxs-lookup"><span data-stu-id="03c88-141">For example:</span></span>
    
   ```
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    <span data-ttu-id="03c88-142">Le format alternatif utilise-Name et-parent:</span><span class="sxs-lookup"><span data-stu-id="03c88-142">The alternate format using -Name and -Parent:</span></span>
    
   ```
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="03c88-143">Pour créer un scénario avec plusieurs fournisseurs à l’aide de l’applet de commande New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="03c88-143">To create a new scenario with multiple providers with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="03c88-144">Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="03c88-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="03c88-145">Vous êtes limité à deux scénarios par étendue.</span><span class="sxs-lookup"><span data-stu-id="03c88-145">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="03c88-146">Cependant, le nombre de fournisseurs n’est pas limité.</span><span class="sxs-lookup"><span data-stu-id="03c88-146">However, you are not limited to a set number of providers.</span></span> <span data-ttu-id="03c88-147">Dans cet exemple, supposons que vous avez créé trois fournisseurs et que vous souhaitez les affecter tous les trois au scénario que vous définissez.</span><span class="sxs-lookup"><span data-stu-id="03c88-147">In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining.</span></span> <span data-ttu-id="03c88-148">Les noms des variables de fournisseur sont LyssProvider, ABServerProvider et SIPStackProvider.</span><span class="sxs-lookup"><span data-stu-id="03c88-148">The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider.</span></span> <span data-ttu-id="03c88-149">Pour définir et affecter plusieurs fournisseurs à un scénario, tapez ce qui suit dans une invite de commandes Skype entreprise Server Management Shell ou Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="03c88-149">To define and assign multiple providers to a scenario, type the following at a Skype for Business Server Management Shell or Windows PowerShell command prompt:</span></span>
    
   ```
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > <span data-ttu-id="03c88-150">Comme il est connu dans Windows PowerShell, la Convention de création d’une table de hachage de `@{<variable>=<value1>, <value2>, <value>…}` valeurs à l’aide de assplatting est connue.</span><span class="sxs-lookup"><span data-stu-id="03c88-150">As it is known in Windows PowerShell, the convention for creating a hash table of values using  `@{<variable>=<value1>, <value2>, <value>…}` is known assplatting.</span></span> <span data-ttu-id="03c88-151">Pour plus d’informations sur la projection dans Windows PowerShell, [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760)reportez-vous à la rubrique.</span><span class="sxs-lookup"><span data-stu-id="03c88-151">For details about splatting in Windows PowerShell, see [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760).</span></span> 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a><span data-ttu-id="03c88-152">Pour modifier un scénario existant avec l’applet de commande Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="03c88-152">To modify an existing scenario with the Set-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="03c88-153">Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="03c88-153">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="03c88-154">Vous êtes limité à deux scénarios par étendue.</span><span class="sxs-lookup"><span data-stu-id="03c88-154">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="03c88-155">Vous pouvez modifier les scénarios qui s’ exécutent à tout moment, même lorsqu’une session de capture de journalisation est en cours.</span><span class="sxs-lookup"><span data-stu-id="03c88-155">You can change which scenarios are running at any time, even when a logging capture session is in process.</span></span> <span data-ttu-id="03c88-156">Si vous redéfinissez les scénarios en cours d’exécution, la session de journalisation actuelle cesse d’utiliser le scénario qui a été supprimé et utilise ensuite le nouveau scénario.</span><span class="sxs-lookup"><span data-stu-id="03c88-156">If you redefine the running scenarios, the current logging session will stop using the scenario that was removed and then begin using the new scenario.</span></span> <span data-ttu-id="03c88-157">Toutefois, les informations de journalisation qui ont été capturées avec le scénario supprimé sont conservées dans les journaux capturés.</span><span class="sxs-lookup"><span data-stu-id="03c88-157">However, the logging information that was captured with the removed scenario remains in the captured logs.</span></span> <span data-ttu-id="03c88-158">Pour définir un nouveau scénario, procédez comme suit (en partant du principe que l’ajout d’un fournisseur déjà défini appelé «S4Provider»):</span><span class="sxs-lookup"><span data-stu-id="03c88-158">To define a new scenario, do the following (that is, assuming the addition of an already defined provider named "S4Provider"):</span></span>
    
   ```
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    <span data-ttu-id="03c88-159">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="03c88-159">For example:</span></span>
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    <span data-ttu-id="03c88-p112">Si vous souhaitez remplacer des fournisseurs, définissez un fournisseur unique ou une liste séparée par des virgules des fournisseurs pour remplacer l’ensemble actuel. Si vous souhaitez seulement remplacer l’un des fournisseurs, ajoutez les fournisseurs actuels aux nouveaux fournisseurs pour créer un nouvel ensemble de fournisseurs contenant les nouveaux fournisseurs et les fournisseurs existants. Pour remplacer tous les fournisseurs par un nouvel ensemble, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="03c88-p112">If you want to replace providers, define a single provider or a comma separated list of providers to replace the current set. If you only want to replace one of many providers, add the current providers with the new providers to create a new set of providers that contains both new providers and existing providers. To replace all providers with a new set, type the following:</span></span>
    
   ```
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    <span data-ttu-id="03c88-163">Par exemple, pour remplacer l’ensemble actuel comprenant $LyssProvider, $ABServerProvider et $SIPStackProvider par $LyssServiceProvider :</span><span class="sxs-lookup"><span data-stu-id="03c88-163">For example, to replace the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider:</span></span>
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    <span data-ttu-id="03c88-164">Pour remplacer seulement le fournisseur $LyssProvider de l’ensemble actuel comprenant $LyssProvider, $ABServerProvider et $SIPStackProvider par $LyssServiceProvider, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="03c88-164">To replace just the $LyssProvider provider from the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider, type the following:</span></span>
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a><span data-ttu-id="03c88-165">Pour supprimer un scénario existant avec l’applet de commande Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="03c88-165">To remove an existing scenario with the Remove-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="03c88-166">Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="03c88-166">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="03c88-167">Si vous souhaitez supprimer un scénario précédemment défini, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="03c88-167">If you want to remove a scenario that has been previously defined, type the following:</span></span>
    
   ```
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    <span data-ttu-id="03c88-168">Par exemple, pour supprimer le scénario défini site:Redmond/LyssServiceScenario :</span><span class="sxs-lookup"><span data-stu-id="03c88-168">For example, to remove the defined scenario site:Redmond/LyssServiceScenario:</span></span>
    
   ```
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

<span data-ttu-id="03c88-169">L’applet de commande **Remove-CsClsScenario** supprime le scénario spécifié, mais vous pouvez toujours accéder aux suivis capturés dans les journaux et lancer des recherches dans ceux-ci.</span><span class="sxs-lookup"><span data-stu-id="03c88-169">The **Remove-CsClsScenario** cmdlet removes the specified scenario, but the traces that have been captured are still available in the logs for you to search on.</span></span>
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a><span data-ttu-id="03c88-170">Pour charger et décharger l’applet de commande Edit-CsClsScenario à l’aide du module ClsScenarioEdit.psm1</span><span class="sxs-lookup"><span data-stu-id="03c88-170">To load and unload the Edit-CsClsScenario cmdlet using the ClsScenarioEdit.psm1 module</span></span>

1. <span data-ttu-id="03c88-171">Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="03c88-171">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="03c88-172">Le module ClsScenarioEdit.psm1 est fourni sous forme d’un téléchargement web distinct.</span><span class="sxs-lookup"><span data-stu-id="03c88-172">The ClsScenarioEdit.psm1 module is provided as a separate Web download.</span></span> <span data-ttu-id="03c88-173">Le module fait partie des outils de débogage de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="03c88-173">The module is part of the Skype for Business Server 2015 Debugging tools.</span></span> <span data-ttu-id="03c88-174">Par défaut, les outils de débogage sont installés dans le répertoire C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span><span class="sxs-lookup"><span data-stu-id="03c88-174">By default, the debugging tools are installed in the directory C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> 
  
2. <span data-ttu-id="03c88-175">Dans Windows PowerShell, tapez:</span><span class="sxs-lookup"><span data-stu-id="03c88-175">From the Windows PowerShell, type:</span></span>
    
   ```
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > <span data-ttu-id="03c88-176">Le chargement réussi du module vous renvoie à l’invite de commandes Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="03c88-176">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="03c88-177">Pour vérifier que le module est chargé et que Edit-CsClsScenario est disponible, tapez `Get-Help Edit-CsClsScenario`.</span><span class="sxs-lookup"><span data-stu-id="03c88-177">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="03c88-178">Le résumé de base de la syntaxe pour EditCsClsScenario doit apparaître.</span><span class="sxs-lookup"><span data-stu-id="03c88-178">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="03c88-179">Pour décharger les modules, tapez :</span><span class="sxs-lookup"><span data-stu-id="03c88-179">To unload the modules, type:</span></span>
    
   ```
   Remove-Module ClsController
   ```

    > [!TIP]
    > <span data-ttu-id="03c88-180">Le déchargement réussi du module revient à l’invite de commandes Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="03c88-180">Successful unloading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="03c88-181">Pour vérifier que le module est déchargé, tapez `Get-Help Edit-CsClsScenario`.</span><span class="sxs-lookup"><span data-stu-id="03c88-181">To confirm that the module is unloaded, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="03c88-182">Windows PowerShell tente de Rechercher l’aide de l’applet de cmdlet et échoue.</span><span class="sxs-lookup"><span data-stu-id="03c88-182">Windows PowerShell will attempt to locate the help for the cmdlet and fail.</span></span> 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="03c88-183">Pour supprimer un fournisseur existant d’un scénario avec le module Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="03c88-183">To remove an existing provider from a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="03c88-184">Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="03c88-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="03c88-185">Dans Windows PowerShell, tapez:</span><span class="sxs-lookup"><span data-stu-id="03c88-185">From the Windows PowerShell, type:</span></span>
    
   ```
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > <span data-ttu-id="03c88-186">Le chargement réussi du module vous renvoie à l’invite de commandes Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="03c88-186">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="03c88-187">Pour vérifier que le module est chargé et que Edit-CsClsScenario est disponible, tapez `Get-Help Edit-CsClsScenario`.</span><span class="sxs-lookup"><span data-stu-id="03c88-187">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="03c88-188">Le résumé de base de la syntaxe pour EditCsClsScenario doit apparaître.</span><span class="sxs-lookup"><span data-stu-id="03c88-188">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="03c88-189">Pour supprimer un fournisseur du scénario AlwaysOn, tapez :</span><span class="sxs-lookup"><span data-stu-id="03c88-189">To remove a provider from the AlwaysOn scenario, type:</span></span>
    
   ```
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   <span data-ttu-id="03c88-190">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="03c88-190">For Example:</span></span>
    
   ```
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   <span data-ttu-id="03c88-p117">Les paramètres ScenarioName et ProviderName sont positionnels (c’est-à-dire qu’ils doivent être définis dans la position attendue dans la ligne de commande). Il n’est pas nécessaire de définir explicitement le nom du paramètre si le nom du scénario est en position deux et que le fournisseur est en position trois par rapport au nom de l’applet de commande (en position un). Compte tenu de ces informations, la commande précédente ressemble alors à ceci :</span><span class="sxs-lookup"><span data-stu-id="03c88-p117">The parameters ScenarioName and ProviderName are positional (that is, they must be defined in the expected position in the command line) parameters. The parameter name does not have to be explicitly defined if the scenario name is in position two and the provider is in position three, relative to the name of the cmdlet as position one. Using this information, the previous command would be typed as:</span></span>
    
   ```
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   <span data-ttu-id="03c88-194">La mise en place de valeurs de paramètres ne s’applique qu’aux fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="03c88-194">The positional placing of the parameter values applies only to -Scenario and -Provider.</span></span> <span data-ttu-id="03c88-195">Tous les autres paramètres doivent être définis explicitement.</span><span class="sxs-lookup"><span data-stu-id="03c88-195">All other parameters must be explicitly defined.</span></span>
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="03c88-196">Pour ajouter un fournisseur à un scénario avec le module Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="03c88-196">To add a provider to a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="03c88-197">Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="03c88-197">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="03c88-198">Pour ajouter un fournisseur au scénario AlwaysOn, tapez :</span><span class="sxs-lookup"><span data-stu-id="03c88-198">To add a provider to the AlwaysOn scenario, type:</span></span>
    
   ```
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    <span data-ttu-id="03c88-199">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="03c88-199">For Example:</span></span>
    
   ```
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    <span data-ttu-id="03c88-200">-Loglevel peut être du type Fatal, Error, Warning, Info, Verbose, Debug ou All.</span><span class="sxs-lookup"><span data-stu-id="03c88-200">-Loglevel can be of the type Fatal, Error, Warning, Info, Verbose, Debug, or All.</span></span> <span data-ttu-id="03c88-201">-Les indicateurs peuvent être tout indicateur pris en charge par le fournisseur (par exemple, TF_COMPONENT, TF_DIAG.</span><span class="sxs-lookup"><span data-stu-id="03c88-201">-Flags can be any of the flags that the provider supports, such as TF_COMPONENT, TF_DIAG.</span></span> <span data-ttu-id="03c88-202">-LES indicateurs peuvent également être de valeurs</span><span class="sxs-lookup"><span data-stu-id="03c88-202">-Flags can also be of value ALL</span></span>
    
   <span data-ttu-id="03c88-p120">Il est aussi possible de taper l’exemple précédent à l’aide de la fonctionnalité positionnelle de l’applet de commande. Par exemple, pour ajouter le fournisseur ChatServer au scénario AlwaysOn, tapez :</span><span class="sxs-lookup"><span data-stu-id="03c88-p120">The previous example can also be typed using the positional feature of the cmdlet. For example, to add the provider ChatServer to the AlwaysOn scenario, type:</span></span>
    
   ```
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```
