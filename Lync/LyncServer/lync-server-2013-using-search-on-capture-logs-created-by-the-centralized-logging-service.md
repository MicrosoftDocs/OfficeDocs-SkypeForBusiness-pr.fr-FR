---
title: "Ut. Rech. sur les journaux de capture créés par le service de journ. centr."
TOCtitle: "Ut. Rech. sur les journaux de capture créés par le service de journ. centr."
ms:assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ687982(v=OCS.15)
ms:contentKeyID: 49891251
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Utilisation de la recherche sur les journaux de capture créés par le service de journalisation centralisée

 

_**Dernière rubrique modifiée :** 2013-02-21_

Les fonctionnalités de recherche du service de journalisation centralisée sont utiles et puissantes pour les raisons suivantes :

  - Vos recherches et les résultats sont exécutés sur un seul ordinateur, un pool, un site ou une étendue globale, en fonction des critères que vous définissez.

  - Vos recherches peuvent être larges à l’origine, puis s’affiner sur des critères plus ciblés, tels que l’heure, le composant ou l’ordinateur. Vous effectuez vos recherches sur les mêmes journaux et n’avez pas besoin d’exécuter une autre session de journalisation lorsque vos critères de recherche changent.

  - Les résultats de votre recherche sont recueillis sur tous les ordinateurs et pools de l’étendue, collectés et regroupés dans un seul fichier de sortie qui représente tous les résultats des critères de recherche (limités aux scénarios qui ont été exécutés et aux données capturées par les scénarios). Vous utilisez des outils familiers, tels que **Snooper** ou le **Bloc-notes** pour lire le fichier de sortie et les messages de suivi de tout votre déploiement.

Le CLSAgent sur chaque ordinateur individuel crée les journaux en fonction du ou des scénarios (deux scénarios par ordinateur peuvent s’exécuter en même temps). Les journaux, ainsi que leurs fichiers d’index et de cache associés, sont gérés par le CLSAgent. Lorsque vous définissez et exécutez une recherche, la commande de recherche indique au CLSAgent quelles informations extraire. Le CLSAgent exécute la requête sur les fichiers journaux, les fichiers de cache et les fichiers d’index et renvoie les résultats de la recherche au CLSController. Le CLSController reçoit les résultats de la recherche en provenance de tous les ordinateurs et pools dans l’étendue de la recherche. Le CLSController regroupe ensuite (combine) les journaux et les classe en fonction de l’écart de temps : l’entrée la plus ancienne en premier et l’entrée la plus récente en dernier.

Au terme de chaque recherche, l’applet de commande **Sync-CsClsLogging** est exécutée et vide le cache utilisé par les recherches (à ne pas confondre avec les fichiers de cache gérés par le CLSAgent). Le fait de vider le cache permet de s’assurer que la prochaine opération de recherche bénéficie d’une mémoire tampon nette de capture du fichier journal et du fichier de suivi sur le CLSController.

Pour tirer le meilleur parti du service de journalisation centralisée, vous devez bien comprendre comment configurer la recherche afin de renvoyer uniquement les messages de suivi provenant des journaux d’ordinateur et de pool qui sont appropriés à l’objet de votre recherche.

Pour exécuter les fonctions de recherche du service de journalisation centralisée à l’aide de Lync Server Management Shell, vous devez être membre des groupes de sécurité RBAC (Contrôle d’accès basé sur un rôle) CsAdministrator ou CsServerAdministrator ou d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes. Pour renvoyer une liste de tous les rôles RBAC (Contrôle d’accès basé sur un rôle) auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés créés par vos soins), exécutez la commande suivante à l’invite Lync Server Management Shell ou Windows PowerShell :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Par exemple :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

Le reste de cette rubrique se concentre sur la définition d’une recherche en vue d’optimiser la résolution des problèmes.

## Pour exécuter une recherche de base à l’aide du service de journalisation centralisée

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Assurez-vous que le scénario AlwaysOn s’exécute dans votre déploiement au niveau de l’étendue globale, puis tapez ce qui suit dans une invite de commandes :
    
        Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
    
    > [!NOTE]  
    > Par défaut, Search-CsClsLogging envoie les résultats de la recherche à la console. Si vous souhaitez enregistrer les résultats de la recherche dans un fichier, utilisez –OutputFilePath <em>&lt;chaîne de chemin d’accès complet&gt;</em>. Pour définir le paramètre –OutputFilePath, indiquez un chemin d’accès et un nom de fichier dans un format de chaîne entouré de guillemets (par exemple ; C:\LogFiles\SearchOutput.txt). Dans cet exemple, vous devez vous assurer que le répertoire C:\LogFiles existe et que vous disposez des autorisations en lecture et en écriture (autorisation NTFS Modifier) sur le dossier. Les résultats sont ajoutés et ne sont pas remplacés. Si vous souhaitez des fichiers séparés, définissez un nom de fichier distinct pour chaque recherche.    
    Par exemple :
    
        Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"

## Pour exécuter une recherche de base sur un pool ou sur un ordinateur à l’aide du service de journalisation centralisée

1.  Pour limiter la recherche à un pool ou à un ordinateur en particulier, utilisez le paramètre –Computers en définissant l’ordinateur par un nom complet, entouré de guillemets et séparé par une virgule, comme suit :
    
        Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
    
    Par exemple :
    
        Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

2.  Pour rechercher plusieurs ordinateurs, tapez le nom de plusieurs ordinateurs en les entourant de guillemets et en les séparant par une virgule, comme suit :
    
        Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

3.  Pour effectuer une recherche dans un pool entier au lieu d’un seul ordinateur, modifiez le paramètre –Computers en –Pools, supprimez le nom de l’ordinateur et remplacez-le par le ou les pools entourés de guillemets et séparés par des virgules.
    
    Par exemple :
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  Lorsque vous utilisez les commandes de recherche, vous pouvez désigner n’importe quel pool de votre déploiement, tel que les pools de serveurs frontaux, pools de serveurs Edge, les pools de serveurs de conversations permanentes ou d’autres pools définis en tant que pool dans votre déploiement.
    
    Par exemple :
    
        Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

## Pour exécuter une recherche à l’aide des paramètres d’heure

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Par défaut, l’heure de début pour les paramètres temporels d’une recherche est définie sur 30 minutes avant le moment où vous lancez la recherche. En d’autres termes, si vous lancez votre recherche à 16 h 00 00, la recherche parcourt les journaux des ordinateurs et des pools que vous définissez entre 15 h 30 00 et 16 h 00 00. Si vous devez effectuer une recherche 60 minutes ou 3 heures avant l’heure actuelle, utilisez le paramètre –StartTime et définissez la date et l’heure de manière à indiquer l’heure à laquelle vous souhaitez que la recherche débute.
    
    Par exemple, en utilisant –StartTime et –EndTime pour définir une plage horaire et de dates, vous pouvez définir une recherche entre 8 h 00 00 et 9 h 00 00 le 20/11/2012 sur votre pool. Vous pouvez configurer le chemin d’accès de sortie de manière à écrire les résultats dans un fichier nommé c:\\logfile.txt comme suit :
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    > [!NOTE]  
    > La chaîne d’heure et de date que vous spécifiez peut être « date time » ou « time date ». La commande analysera la chaîne et utilisera les valeurs appropriées pour la date et l’heure.

3.  Si vous souhaitez extraire les journaux à partir de 11 h 00 00 le 20/11/2012, définissez l’heure de début (paramètre –StartTime). La plage horaire par défaut pour la recherche est de 30 minutes sauf si vous définissez une heure de fin ( paramètre –EndTime) spécifique. La recherche obtenue renverra les journaux des ordinateurs ou pools définis entre 11 h 00 00 et 11 h 30 00.
    
    Par exemple :
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  Pour réaliser une recherche sur des journaux dans une période donnée, définissez une heure de début (paramètre –StartTime) et une heure de fin (paramètre –EndTime). Les journaux entre 13 h 00 et 14 h 45 doivent être présents sur l’ordinateur edge01.contoso.net.
    
    Par exemple :
    
        Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"

## Pour exécuter une recherche avancée à l’aide d’autres critères et options de correspondance

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Pour exécuter une commande visant à collecter les suivis pour des composants en particulier, tapez ce qui suit :
    
        Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
    
    Par exemple :
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    La recherche obtenue renvoie toutes les entrées de journaux qui possèdent des composants de suivi pour SIPStack, S4 et UserServices sur tous les ordinateurs et pools de votre déploiement au cours des 30 dernières minutes.

3.  Pour limiter la recherche avec les mêmes composants à seulement votre pool de serveurs frontaux nommé pool01.contoso.net, tapez :
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  La logique de recherche par défaut pour les commandes comprenant plusieurs paramètres utilise l’opérateur logique OR avec chacun des paramètres définis. Vous pouvez modifier ce comportement en indiquant le paramètre **–MatchAll**. Pour ce faire, tapez ce qui suit :
    
        Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"

5.  Si vos scénarios sont définis de manière à s’exécuter constamment (par exemple AlwaysOn) ou si vous avez défini un scénario à long terme, les journaux peuvent s’étendre de l’ordinateur local au partage de fichiers. Pour définir le partage de fichiers, utilisez le paramètre CacheFileNetworkFolder à l’aide de New-CsClsConfiguration pour créer une nouvelle configuration ou modifiez une configuration existante avec Set-CsClsConfiguration. Si vous ne souhaitez pas que la recherche englobe le partage de fichiers dans la collection des journaux à parcourir, utilisez le paramètre SkipNetworkLogs comme suit :
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

