---
title: Gestion de la configuration de l’ordinateur, du site et du service de journalisation centralisée
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing computer, site and global Centralized Logging Service configuration
ms:assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688138(v=OCS.15)
ms:contentKeyID: 49733738
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 868005d0a719bc8bc021f1a0b82260037c1f6ea6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218120"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a><span data-ttu-id="e2db7-102">Gestion de la configuration de l’ordinateur, du site et du service de journalisation centralisée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2db7-102">Managing computer, site and global Centralized Logging Service configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2db7-103">_**Dernière modification de la rubrique :** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="e2db7-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="e2db7-104">Le service de journalisation centralisée peut être exécuté au niveau d’un ordinateur unique, d’un pool d’ordinateurs, au niveau d’une étendue de site (c’est-à-dire un site défini tel que Redmond qui contient un ensemble d’ordinateurs et de pools dans votre déploiement), ou à une étendue globale ( , tous les ordinateurs et pools de votre déploiement).</span><span class="sxs-lookup"><span data-stu-id="e2db7-104">The Centralized Logging Service can be run at a scope that includes a single computer, a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="e2db7-105">Pour configurer l’étendue du service de journalisation centralisée à l’aide de Lync Server Management Shell, vous devez être membre des groupes de sécurité CsAdministrator ou RBAC (contrôle d’accès basé sur le rôle CsServerAdministrator), ou d’un rôle RBAC personnalisé contenant l’un de ces deux groupes.</span><span class="sxs-lookup"><span data-stu-id="e2db7-105">To configure the Centralized Logging Service scope by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="e2db7-106">Pour renvoyer la liste de tous les rôles RBAC auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de Lync Server Management Shell ou de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="e2db7-106">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

<span data-ttu-id="e2db7-107">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="e2db7-107">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> <span data-ttu-id="e2db7-108">Windows PowerShell fournit des options supplémentaires et des options de configuration supplémentaires qui ne sont pas disponibles à l’aide de CLSController. exe.</span><span class="sxs-lookup"><span data-stu-id="e2db7-108">Windows PowerShell provides you more options and additional configuration options that are not available by using CLSController.exe.</span></span> <span data-ttu-id="e2db7-109">CLSController offre une méthode rapide et concise pour exécuter des commandes, mais l’ensemble de commandes disponibles pour CLSController est limité.</span><span class="sxs-lookup"><span data-stu-id="e2db7-109">CLSController offers a quick, concise method to run commands, but is limited to the set of commands available for the CLSController.</span></span> <span data-ttu-id="e2db7-110">Windows PowerShell n’est pas limité à la seule commande disponible pour le processeur de commandes du CLSController, et fournit un ensemble plus large de commandes et un ensemble d’options plus riche.</span><span class="sxs-lookup"><span data-stu-id="e2db7-110">Windows PowerShell is not limited to just the command available to the command processor of the CLSController, and provides a wider set of commands and a richer set of options.</span></span> <span data-ttu-id="e2db7-111">Par exemple, CLSController.exe fournit des options d’étendue pour les ordinateurs et les pools.</span><span class="sxs-lookup"><span data-stu-id="e2db7-111">For example, CLSController.exe does provide you with a scope options for –computers and –pools.</span></span> <span data-ttu-id="e2db7-112">Avec Windows PowerShell, vous pouvez indiquer des ordinateurs ou des pools dans la plupart des commandes, et lorsque vous définissez de nouveaux scénarios (CLSController dispose d’un nombre limité de scénarios qui ne peuvent pas être modifiés par l’utilisateur), vous pouvez définir un site ou une étendue globale.</span><span class="sxs-lookup"><span data-stu-id="e2db7-112">With Windows PowerShell, you can indicate computers or pools in most commands, and when you define new scenarios (CLSController has a finite number of scenarios that are not user modifiable) you can define a site or global scope.</span></span> <span data-ttu-id="e2db7-113">Cette fonctionnalité puissante de Windows PowerShell vous permet de définir un scénario de site ou une étendue globale, mais de limiter la journalisation réelle à un ordinateur ou un pool.</span><span class="sxs-lookup"><span data-stu-id="e2db7-113">This powerful feature of Windows PowerShell enables you to define a scenario a site or global scope, but limit the actual logging to a computer or pool.</span></span><BR><span data-ttu-id="e2db7-114">Il existe des différences fondamentales entre les commandes de ligne de commande que vous pouvez exécuter dans Windows PowerShell ou CLSController.</span><span class="sxs-lookup"><span data-stu-id="e2db7-114">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="e2db7-115">Windows PowerShell fournit une méthode riche pour configurer et définir des scénarios, et pour réutiliser ces scénarios de manière significative pour les scénarios de dépannage.</span><span class="sxs-lookup"><span data-stu-id="e2db7-115">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="e2db7-116">CLSController fournit un moyen rapide et efficace d’émettre des commandes et d’obtenir des résultats, l’ensemble de commandes pour CLSController est limité à un nombre fini de commandes disponibles à partir de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="e2db7-116">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="e2db7-117">Contrairement aux applets de commande Windows PowerShell, CLSController ne peut pas définir de nouveaux scénarios, gérer l’étendue au niveau d’un site ou d’un niveau global et de nombreuses autres limitations d’un jeu de commandes finies qui ne peuvent pas être configurés dynamiquement.</span><span class="sxs-lookup"><span data-stu-id="e2db7-117">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="e2db7-118">Bien que CLSController offre un moyen pour une exécution rapide, Windows PowerShell permet d’étendre la fonctionnalité du service de journalisation centralisée au-delà de ce qui est possible avec CLSController.</span><span class="sxs-lookup"><span data-stu-id="e2db7-118">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>



</div>

<span data-ttu-id="e2db7-119">Une seule étendue d’ordinateur peut être définie lors de l’exécution d’une commande [Search-CsClsLogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15)), [Show-CsClsLogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15)), [Start-CsClsLogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15)), [Stop-CsClsLogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15)), [Sync-CsClsLogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15)) et [Update-CsClsLogging](https://technet.microsoft.com/library/JJ619170(v=OCS.15)) à l’aide du paramètre – Computers.</span><span class="sxs-lookup"><span data-stu-id="e2db7-119">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15)), [Show-CsClsLogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15)), [Start-CsClsLogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15)), [Stop-CsClsLogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15)), [Sync-CsClsLogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15)) and [Update-CsClsLogging](https://technet.microsoft.com/library/JJ619170(v=OCS.15)) command using the –Computers parameter.</span></span> <span data-ttu-id="e2db7-120">Le paramètre –Computers accepte une liste de noms de domaine complets séparée par des virgules pour l’ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="e2db7-120">The –Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="e2db7-121">Vous pouvez également définir –Pools et une liste de pools séparée par des virgules sur laquelle exécuter les commandes de journalisation.</span><span class="sxs-lookup"><span data-stu-id="e2db7-121">You can also define –Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>



</div>

<span data-ttu-id="e2db7-122">Les étendues de site et global sont définies dans les cmdlets **New-**, **Set-** et **Remove-** Centralized Logging Service.</span><span class="sxs-lookup"><span data-stu-id="e2db7-122">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="e2db7-123">Les exemples suivants montrent comment définir une étendue globale ou de site.</span><span class="sxs-lookup"><span data-stu-id="e2db7-123">The following examples demonstrate how to set a site and a global scope.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="e2db7-124">Les commandes indiquées peuvent contenir des paramètres et des concepts décrits dans d’autres sections.</span><span class="sxs-lookup"><span data-stu-id="e2db7-124">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="e2db7-125">Les exemples de commandes sont conçus pour décrire l’utilisation du paramètre <STRONG>–Identity</STRONG> pour définir l’étendue, et les autres paramètres sont inclus pour être exhaustif et pour spécifier l’étendue.</span><span class="sxs-lookup"><span data-stu-id="e2db7-125">The example commands are intended to demonstrate the use of the <STRONG>–Identity</STRONG> parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="e2db7-126">Pour plus d’informations sur les applets de commande <STRONG>Set-CsClsConfiguration</STRONG>, voir <A href="https://technet.microsoft.com/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A> dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="e2db7-126">For details about the <STRONG>Set-CsClsConfiguration</STRONG> cmdlets, see <A href="https://technet.microsoft.com/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="e2db7-127">Pour récupérer la configuration actuelle du service de journalisation centralisée</span><span class="sxs-lookup"><span data-stu-id="e2db7-127">To retrieve the current Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="e2db7-128">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e2db7-128">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e2db7-129">Tapez ce qui suit à l’invite de ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="e2db7-129">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration

<span data-ttu-id="e2db7-130">Utilisez les applets de commande **New-CsClsConfiguration** et **Set-CsClsConfiguration** pour créer une nouvelle configuration ou pour mettre à jour une configuration existante.</span><span class="sxs-lookup"><span data-stu-id="e2db7-130">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.</span></span>

<span data-ttu-id="e2db7-131">Lorsque vous exécutez **Get-CsClsConfiguration**, il affiche des informations similaires à la capture d’écran suivante, dans laquelle le déploiement dispose actuellement de la configuration globale par défaut, mais aucune configuration de site n’est définie :</span><span class="sxs-lookup"><span data-stu-id="e2db7-131">When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

<span data-ttu-id="e2db7-132">![Exemple de sortie de Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Exemple de sortie de Get-CsClsConfiguration.")</span><span class="sxs-lookup"><span data-stu-id="e2db7-132">![Sample output from Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Sample output from Get-CsClsConfiguration.")</span></span>

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="e2db7-133">Pour récupérer la configuration actuelle du service de journalisation centralisée dans le magasin local de l’ordinateur</span><span class="sxs-lookup"><span data-stu-id="e2db7-133">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1.  <span data-ttu-id="e2db7-134">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e2db7-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e2db7-135">Tapez ce qui suit à l’invite de ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="e2db7-135">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration -LocalStore

<span data-ttu-id="e2db7-136">Lorsque vous utilisez le premier exemple où **Get-CsClsConfiguration** ne spécifie aucun paramètre, la commande fait référence au magasin central de gestion pour les données.</span><span class="sxs-lookup"><span data-stu-id="e2db7-136">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="e2db7-137">Si vous spécifiez le paramètre – LocalStore, la commande fait référence à l’ordinateur LocalStore à la place du magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="e2db7-137">If you specify the parameter –LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="e2db7-138">Pour récupérer une liste des scénarios actuellement définis</span><span class="sxs-lookup"><span data-stu-id="e2db7-138">To retrieve a listing of scenarios currently defined</span></span>

1.  <span data-ttu-id="e2db7-139">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e2db7-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e2db7-140">Tapez ce qui suit à l’invite de ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="e2db7-140">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    <span data-ttu-id="e2db7-141">Pour exemple, pour récupérer les scénarios définis au niveau global :</span><span class="sxs-lookup"><span data-stu-id="e2db7-141">For example, to retrieve the scenarios that is defined at the global scope:</span></span>
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

<span data-ttu-id="e2db7-142">L’applet de commande **Get-CsClsConfiguration** affiche toujours les scénarios qui font partie d’une configuration donnée.</span><span class="sxs-lookup"><span data-stu-id="e2db7-142">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope’s configuration.</span></span> <span data-ttu-id="e2db7-143">Dans la plupart des cas, tous les scénarios ne sont pas affichés, et sont tronqués.</span><span class="sxs-lookup"><span data-stu-id="e2db7-143">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="e2db7-144">La commande utilisée ici répertorie tous les scénarios et des informations partielles sur les fournisseurs, les paramètres et les indicateurs utilisés.</span><span class="sxs-lookup"><span data-stu-id="e2db7-144">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="e2db7-145">Pour mettre à jour une étendue globale pour le service de journalisation centralisée à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2db7-145">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1.  <span data-ttu-id="e2db7-146">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e2db7-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e2db7-147">Tapez ce qui suit à l’invite de ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="e2db7-147">Type the following at the command-line prompt:</span></span>
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    <span data-ttu-id="e2db7-148">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="e2db7-148">For example:</span></span>
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

<span data-ttu-id="e2db7-p109">La commande indique au CLSAgent de chaque ordinateur et pool du déploiement de définir la valeur de substitution dans le fichier de suivi à 40 mégaoctets. Les ordinateurs et les pools de tous les sites sont affectés par cette commande, et définiront la valeur de substitution du journal de suivi configuré à 40 mégaoctets.</span><span class="sxs-lookup"><span data-stu-id="e2db7-p109">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="e2db7-151">Pour mettre à jour une étendue de site pour le service de journalisation centralisée à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2db7-151">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1.  <span data-ttu-id="e2db7-152">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e2db7-152">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e2db7-153">Tapez ce qui suit à l’invite de ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="e2db7-153">Type the following at the command-line prompt:</span></span>
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    <span data-ttu-id="e2db7-154">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="e2db7-154">For example:</span></span>
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="e2db7-p110">Comme indiqué dans l’exemple, l’emplacement par défaut des fichiers journaux est %TEMP%\Tracing. Cependant, dans la mesure où CLSAgent écrit dans le fichier et qu’il s’exécute en tant que service réseau, la variable %TEMP% devient %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span><span class="sxs-lookup"><span data-stu-id="e2db7-p110">As noted in the example, the default location of the log files is %TEMP%\Tracing. However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

    
    </div>

<span data-ttu-id="e2db7-p111">Cette commande indique au CLSAgent de chaque ordinateur et pool du site Redmond de définir la taille de la valeur de substitution du fichier de suivi à 40 mégaoctets. Les ordinateurs et les pools des autres sites ne sont pas affectés par cette commande, et continueront d’utiliser la valeur de substitution du journal de suivi configurée actuellement et définie par défaut (20 mégaoctets) ou lors du démarrage de la session de journalisation.</span><span class="sxs-lookup"><span data-stu-id="e2db7-p111">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="e2db7-159">Pour créer une nouvelle configuration de service de journalisation centralisée</span><span class="sxs-lookup"><span data-stu-id="e2db7-159">To create a new Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="e2db7-160">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e2db7-160">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e2db7-161">Tapez ce qui suit à l’invite de ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="e2db7-161">Type the following at the command-line prompt:</span></span>
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="e2db7-162">New-CsClsConfiguration fournit un accès à de nombreux paramètres de configuration supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="e2db7-162">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="e2db7-163">Pour plus d’informations sur les options de configuration, voir <A href="https://technet.microsoft.com/library/JJ619179(v=OCS.15)">Get-CsClsConfiguration</A> et <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Présentation des paramètres de configuration du service de journalisation centralisée dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e2db7-163">For details about the configuration options, see <A href="https://technet.microsoft.com/library/JJ619179(v=OCS.15)">Get-CsClsConfiguration</A> and <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Understanding Centralized Logging Service configuration settings in Lync Server 2013</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="e2db7-164">Par exemple, pour créer une configuration qui définit un dossier réseau pour les fichiers en cache, la période de substitution pour les fichiers journaux et la taille de la substitution pour les fichiers journaux, tapez :</span><span class="sxs-lookup"><span data-stu-id="e2db7-164">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

<span data-ttu-id="e2db7-165">Vous devez planifier avec soin la création de nouvelles configurations et la définition de nouvelles propriétés pour le service de journalisation centralisée.</span><span class="sxs-lookup"><span data-stu-id="e2db7-165">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="e2db7-166">Faites attention lorsque vous apportez des modifications et assurez-vous de bien comprendre l’impact sur la journalisation des scénarios.</span><span class="sxs-lookup"><span data-stu-id="e2db7-166">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="e2db7-167">Apportez des modifications à la configuration pour améliorer la résolution des problèmes en permettant une meilleure gestion des tailles de journaux et de la période de substitution.</span><span class="sxs-lookup"><span data-stu-id="e2db7-167">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="e2db7-168">Pour supprimer une configuration de service de journalisation centralisée existante</span><span class="sxs-lookup"><span data-stu-id="e2db7-168">To remove an existing Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="e2db7-169">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e2db7-169">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e2db7-170">Tapez ce qui suit à l’invite de ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="e2db7-170">Type the following at the command-line prompt:</span></span>
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    <span data-ttu-id="e2db7-171">Par exemple, pour supprimer une configuration de service de journalisation centralisée que vous avez créée pour augmenter le temps de substitution du fichier journal, augmentez la taille du fichier journal de survol et définissez l’emplacement du cache du fichier journal sur un partage réseau comme suit :</span><span class="sxs-lookup"><span data-stu-id="e2db7-171">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="e2db7-172">Il s’agit de la nouvelle configuration qui a été créée dans la procédure « pour créer une nouvelle configuration de service de journalisation centralisée ».</span><span class="sxs-lookup"><span data-stu-id="e2db7-172">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

    
    </div>

<span data-ttu-id="e2db7-173">Si vous choisissez de supprimer une configuration au niveau du site, le site utilisera les paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="e2db7-173">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e2db7-174">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e2db7-174">See Also</span></span>


[<span data-ttu-id="e2db7-175">Vue d’ensemble du service de journalisation centralisée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2db7-175">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[<span data-ttu-id="e2db7-176">Gestion des paramètres de configuration du service de journalisation centralisée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2db7-176">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
<span data-ttu-id="e2db7-177">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2db7-177">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span></span>  
<span data-ttu-id="e2db7-178">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2db7-178">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span></span>  
<span data-ttu-id="e2db7-179">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2db7-179">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span></span>  
<span data-ttu-id="e2db7-180">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e2db7-180">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

