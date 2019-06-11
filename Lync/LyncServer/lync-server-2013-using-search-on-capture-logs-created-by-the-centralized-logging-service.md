---
title: Utilisation de la recherche dans les journaux de capture créés par le service de journalisation centralisé
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using search on capture logs created by the Centralized Logging Service
ms:assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687982(v=OCS.15)
ms:contentKeyID: 49733571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47b9d11713e874915fac0e4b67099ce3f7456546
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-search-on-capture-logs-created-by-the-centralized-logging-service-in-lync-server-2013"></a>Utilisation de la recherche dans les journaux de capture créés par le service de journalisation centralisé dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-21_

Les fonctionnalités de recherche du service de journalisation centralisée sont utiles et puissantes pour les raisons suivantes:

  - Vos recherches et les résultats sont exécutés sur un seul ordinateur, un pool, un site ou une étendue globale, en fonction des critères que vous définissez.

  - Vos recherches peuvent être larges à l’origine, puis s’affiner sur des critères plus ciblés, tels que l’heure, le composant ou l’ordinateur. Vous effectuez vos recherches sur les mêmes journaux et n’avez pas besoin d’exécuter une autre session de journalisation lorsque vos critères de recherche changent.

  - Les résultats de votre recherche sont issus de tous les ordinateurs et pools de l’étendue, collectés et regroupés en un seul fichier de sortie qui représente tous les résultats des critères de recherche (limités aux scénarios qui ont été exécutés et aux données capturées par les scénarios). Vous utilisez des outils familiers, tels que **Snooper** ou **Notepad**, pour lire le fichier de sortie et les messages de suivi de tout votre déploiement.

Le CLSAgent sur chaque ordinateur individuel crée les journaux en fonction du ou des scénarios (deux scénarios par ordinateur peuvent s’exécuter en même temps). Les journaux, ainsi que leurs fichiers d’index et de cache associés, sont gérés par le CLSAgent. Lorsque vous définissez et exécutez une recherche, la commande de recherche indique au CLSAgent quelles informations extraire. Le CLSAgent exécute la requête sur les fichiers journaux, les fichiers de cache et les fichiers d’index et renvoie les résultats de la recherche au CLSController. Le CLSController reçoit les résultats de la recherche en provenance de tous les ordinateurs et pools dans l’étendue de la recherche. Le CLSController regroupe ensuite (combine) les journaux et les classe en fonction de l’écart de temps : l’entrée la plus ancienne en premier et l’entrée la plus récente en dernier.

Après chaque recherche, l’applet de commande **Sync-CsClsLogging** est exécutée et vide le cache utilisé par les recherches (à ne pas confondre avec les fichiers cache gérés par CLSAgent). Le fait de vider le cache permet de garantir que la prochaine opération de recherche bénéficie d’une mémoire tampon nette de capture du fichier journal et du fichier de suivi sur le CLSController.

Pour tirer le meilleur parti du service de journalisation centralisé, vous devez comprendre comment configurer la recherche pour renvoyer uniquement les messages de suivi des journaux d’ordinateur et de pool pertinents pour le problème que vous recherchez. aspects

Pour exécuter les fonctions de recherche du service de journalisation centralisées à l’aide de Lync Server Management Shell, vous devez être membre du groupe de sécurité CsAdministrator ou CsServerAdministrator de contrôle d’accès basé sur les rôles (RBAC) ou d’un rôle RBAC personnalisé contenant l’un de ces deux groupes. Pour renvoyer la liste de tous les rôles RBAC auxquels cette cmdlet a été affectée (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de Lync Server Management Shell ou de l’invite Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Par exemple :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

Le reste de cette rubrique se concentre sur la définition d’une recherche en vue d’optimiser la résolution des problèmes.

<div>

## <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>Pour effectuer une recherche de base à l’aide du service de journalisation centralisé

1.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Assurez-vous que le scénario AlwaysOn s’exécute dans votre déploiement au niveau de l’étendue globale, puis tapez ce qui suit dans une invite de commandes :
    
        Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
    
    <div>
    

    > [!NOTE]
    > Par défaut, Search-CsClsLogging envoie les résultats de la recherche à la console. Si vous voulez enregistrer les résultats de la recherche dans un fichier, utilisez la &lt;chaîne-OutputFilePath de nom&gt;complet. Pour définir le paramètre –OutputFilePath, indiquez un chemin d’accès et un nom de fichier dans un format de chaîne entouré de guillemets (par exemple : C:\LogFiles\SearchOutput.txt). Dans cet exemple, vous devez vous assurer que le répertoire C:\LogFiles existe et que vous disposez des autorisations en lecture et en écriture (autorisation NTSF Modifier) sur le dossier. Les résultats sont ajoutés et ne sont pas remplacés. Si vous avez besoin de fichiers séparés, définissez un nom de fichier différent pour chaque recherche.

    
    </div>
    
    Par exemple :
    
        Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>Pour effectuer une recherche de base sur un pool ou un ordinateur à l’aide du service de journalisation centralisé

1.  Pour limiter la recherche à un pool ou à un ordinateur en particulier, utilisez le paramètre –Computers en définissant l’ordinateur par un nom complet, entouré de guillemets et séparé par une virgule, comme suit :
    
        Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
    
    Par exemple :
    
        Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

2.  Pour rechercher plusieurs ordinateurs, tapez le nom de plusieurs ordinateurs en les entourant de guillemets et en les séparant par une virgule, comme suit :
    
        Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

3.  Pour effectuer une recherche dans un pool entier au lieu d’un seul ordinateur, modifiez le paramètre –Computers en –Pools, supprimez le nom de l’ordinateur et remplacez-le par le ou les pools entourés de guillemets et séparés par des virgules.
    
    Par exemple :
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  Lors de l’utilisation des commandes de recherche, il peut s’agir de n’importe quel pool dans votre déploiement (par exemple, des pools frontaux, des pools de serveurs de chat permanent ou d’autres personnes définies comme pools dans votre déploiement).
    
    Par exemple :
    
        Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-search-by-using-time-parameters"></a>Pour exécuter une recherche à l’aide des paramètres d’heure

1.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Par défaut, l’heure de début des paramètres spécifiques d’une recherche est 30 minutes avant le moment où vous commencez la recherche. En d’autres termes, si vous lancez votre recherche sur 4:00:00 PM, la recherche effectue une recherche dans les journaux pour les ordinateurs et les groupes que vous définissez à partir de 3:30:00 PM jusqu’à 4:00:00 PM. Si vous devez effectuer une recherche 60 minutes ou 3 heures avant l’heure actuelle, utilisez le paramètre –StartTime et définissez la date et l’heure de manière à indiquer l’heure à laquelle vous souhaitez que la recherche débute.
    
    Par exemple, en utilisant –StartTime et –EndTime pour définir une plage horaire et de dates, vous pouvez définir une recherche entre 8 h 00 00 et 9 h 00 00 le 20/11/2012 sur votre pool. Vous pouvez définir le chemin de sortie pour écrire les résultats dans un fichier nommé c\\: logfile. txt comme suit:
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <div>
    

    > [!NOTE]
    > La date et l’heure que vous définissez peut s’appeler « date heure » ou « heure date ». "La commande analyse la chaîne et utilise les valeurs appropriées pour la date et l’heure.

    
    </div>

3.  Si vous souhaitez extraire les journaux à partir de 11 h 00 00 le 20/11/2012, définissez l’heure de début (paramètre –StartTime). La plage horaire par défaut pour la recherche est de 30 minutes sauf si vous définissez une heure de fin (paramètre –EndTime) spécifique. La recherche obtenue renverra les journaux des ordinateurs ou pools définis entre 11 h 00 00 et 11 h 30 00.
    
    Par exemple :
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  Pour réaliser une recherche sur des journaux dans une période donnée, définissez une heure de début (paramètre –StartTime) et une heure de fin (paramètre –EndTime). Les journaux entre 13 h 00 et 14 h 45 doivent être présents sur l’ordinateur edge01.contoso.net.
    
    Exemple :
    
        Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>Pour exécuter une recherche avancée à l’aide d’autres critères et options de correspondance

1.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Pour exécuter une commande visant à collecter les suivis pour des composants en particulier, tapez ce qui suit :
    
        Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
    
    Exemple :
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    La recherche obtenue renvoie toutes les entrées de journaux qui possèdent des composants de suivi pour SIPStack, S4 et UserServices sur tous les ordinateurs et pools de votre déploiement au cours des 30 dernières minutes.

3.  Pour limiter la recherche avec les mêmes composants uniquement au pool frontal nommé pool01.contoso.net, tapez:
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  La logique de recherche par défaut pour les commandes comprenant plusieurs paramètres utilise l’opérateur logique OR avec chacun des paramètres définis. Vous pouvez modifier ce comportement en spécifiant le paramètre **–MatchAll**. Pour ce faire, tapez ce qui suit :
    
        Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"

5.  Si vos scénarios sont définis de manière à s’exécuter constamment (par exemple AlwaysOn) ou si vous avez défini un scénario à long terme, les journaux peuvent s’étendre de l’ordinateur local au partage de fichiers. Pour définir le partage de fichiers, utilisez le paramètre CacheFileNetworkFolder à l’aide de New-CsClsConfiguration pour créer une nouvelle configuration ou modifiez une configuration existante avec Set-CsClsConfiguration. Si vous ne souhaitez pas que la recherche englobe le partage de fichiers dans la collection des journaux à parcourir, utilisez le paramètre SkipNetworkLogs comme suit :
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

</div>

<span> </span>

</div>

</div>

</div>

