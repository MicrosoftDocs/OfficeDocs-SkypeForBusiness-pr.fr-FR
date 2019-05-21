---
title: Recherche dans les journaux de capture créés par le service de journalisation centralisée dans Skype Entreprise Server 2015
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
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: 'Résumé: Découvrez comment rechercher et lire les journaux de capture du service de journalisation centralisé dans Skype entreprise Server 2015.'
ms.openlocfilehash: 81bf539c6a06c52354db23bbeea97fb9525cbbd5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274372"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Recherche dans les journaux de capture créés par le service de journalisation centralisée dans Skype Entreprise Server 2015
 
**Résumé:** Découvrez comment rechercher et lire les journaux de capture du service de journalisation centralisé dans Skype entreprise Server 2015.
  
Les fonctionnalités de recherche du service de journalisation centralisée sont utiles et puissantes pour les raisons suivantes: 
  
- Vos recherches et les résultats sont exécutés sur un seul ordinateur, un pool, un site ou une étendue globale, en fonction des critères que vous définissez.
    
- Vos recherches peuvent être larges à l’origine, puis s’affiner sur des critères plus ciblés, tels que l’heure, le composant ou l’ordinateur. Vous recherchez les mêmes journaux et n’avez pas besoin de réexécuter une session de journalisation lorsque les critères de recherche changent.
    
- Les résultats de votre recherche sont issus de tous les ordinateurs et pools de l’étendue, collectés et regroupés en un seul fichier de sortie qui représente tous les résultats des critères de recherche (limités aux scénarios qui ont été exécutés et aux données capturées par les scénarios). Vous utilisez des outils familiers, tels que **Snooper** ou **Notepad**, pour lire le fichier de sortie et les messages de suivi de tout votre déploiement.
    
Le CLSAgent sur chaque ordinateur individuel crée les journaux en fonction du ou des scénarios (deux scénarios par ordinateur peuvent s’exécuter en même temps). Les journaux, ainsi que leurs fichiers d’index et de cache associés, sont gérés par le CLSAgent. Lorsque vous définissez et exécutez une recherche, la commande de recherche indique au CLSAgent quelles informations extraire. Le CLSAgent exécute la requête sur les fichiers journaux, les fichiers de cache et les fichiers d’index et renvoie les résultats de la recherche au CLSController. Le CLSController reçoit les résultats de la recherche en provenance de tous les ordinateurs et pools dans l’étendue de la recherche. Le CLSController regroupe ensuite (combine) les journaux et les classe en fonction de l’écart de temps : l’entrée la plus ancienne en premier et l’entrée la plus récente en dernier.
  
Après chaque recherche, l’applet de commande **Sync-CsClsLogging** est exécutée et vide le cache utilisé par les recherches (à ne pas confondre avec les fichiers cache gérés par CLSAgent). Le fait de vider le cache permet de garantir que la prochaine opération de recherche bénéficie d’une mémoire tampon nette de capture du fichier journal et du fichier de suivi sur le CLSController.
  
Pour tirer le meilleur parti du service de journalisation centralisé, vous devez comprendre comment configurer la recherche pour renvoyer uniquement les messages de suivi des journaux d’ordinateur et de pool pertinents pour le problème que vous recherchez. aspects
  
Pour exécuter les fonctions de recherche du service de journalisation centralisées à l’aide de Skype entreprise Server Management Shell, vous devez être membre des groupes de sécurité CsAdministrator ou CsServerAdministrator de contrôle d’accès basé sur les rôles (RBAC), ou un rôle RBAC personnalisé. Il contient l’un de ces deux groupes. Pour renvoyer la liste de tous les rôles RBAC auxquels est affectée cette applet de commande (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de Skype entreprise Server Management Shell ou de l’invite Windows PowerShell:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Par exemple :
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

Le reste de cette rubrique se concentre sur la définition d’une recherche en vue d’optimiser la résolution des problèmes.
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>Pour effectuer une recherche de base à l’aide du service de journalisation centralisé

1. Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
2. Assurez-vous que le scénario AlwaysOn s’exécute dans votre déploiement au niveau de l’étendue globale, puis tapez ce qui suit dans une invite de commandes :
    
   ```
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> Par défaut, Search-CsClsLogging envoie les résultats de la recherche à la console. Si vous voulez enregistrer les résultats de la recherche dans un fichier, utilisez le _ \<\>chemin de fichier complet_OutputFilePath. Pour définir le paramètre-OutputFilePath, spécifiez un chemin d’accès et un nom de fichier dans le cadre du paramètre sous forme de chaîne entre guillemets (par exemple, C:\LogFiles\SearchOutput.txt). Dans cet exemple, vous devez vous assurer que le répertoire C:\LogFiles existe et que vous disposez des autorisations en lecture et en écriture (autorisation NTSF Modifier) sur le dossier. Les résultats sont ajoutés et ne sont pas remplacés. Si vous avez besoin de fichiers séparés, définissez un nom de fichier différent pour chaque recherche. 
  
Par exemple :
    
  ```
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>Pour effectuer une recherche de base sur un pool ou un ordinateur à l’aide du service de journalisation centralisé

1. Pour limiter la recherche à un pool ou ordinateur spécifique, utilisez le paramètre-Computers avec l’ordinateur défini par un nom complet de l’ordinateur, placé entre guillemets et séparés par une virgule comme suit:
    
   ```
   Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
   ```

Par exemple :
    
  ```
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. Pour rechercher plusieurs ordinateurs, tapez le nom de plusieurs ordinateurs en les entourant de guillemets et en les séparant par une virgule, comme suit :
    
   ```
   Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
   ```

3. Si vous avez besoin d’effectuer une recherche dans l’intégralité d’un pool plutôt que sur un seul ordinateur, définissez le paramètre-ordinateurs sur-pools, supprimez le nom de l’ordinateur et remplacez-le par le ou les pools entre guillemets, séparés par des virgules.
    
    Par exemple :
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. Lors de l’utilisation des commandes de recherche, il peut s’agir de n’importe quel pool dans votre déploiement (par exemple, des pools frontaux, des pools de serveurs de chat permanent ou d’autres personnes définies comme pools dans votre déploiement).
    
    Par exemple :
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a>Pour exécuter une recherche à l’aide des paramètres d’heure

1. Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
2. Par défaut, l’heure de début pour les paramètres temporels d’une recherche est définie sur 25 minutes avant les cinq minutes après l’heure où vous lancez la recherche. En d’autres mots, si nous effectuons une recherche à 16 h 00 00, la recherche s’étendra alors de 15 h 35 00 à 16 h 05 00. Si vous avez besoin d’effectuer une recherche dans 60 minutes ou 3 heures avant la date actuelle, utilisez le paramètre-StartTime et définissez la date et l’heure pour indiquer l’heure de début de la recherche. 
    
    Par exemple, en utilisant-StartTime et-heure_fin pour définir une plage de dates et de heures, vous pouvez définir une recherche entre 8 AM et 9 AM sur 11/20/2012 de votre liste de choix. Vous pouvez configurer le chemin d’accès de sortie de manière à écrire les résultats dans un fichier nommé c:\logfile.txt comme suit :
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> La date et l’heure que vous définissez peut s’appeler « date heure » ou « heure date ». "La commande analyse la chaîne et utilise les valeurs appropriées pour la date et l’heure ainsi que les paramètres de paramètres régionaux et de culture de l’ordinateur à partir duquel vous exécutez l’applet de commande. 
  
3. Si vous souhaitez récupérer les journaux commençant à 11:00:00 AM sur 11/20/2012, vous devez définir le-StartTime. La période par défaut de la recherche est de 30 minutes, sauf si vous définissez une valeur de date/heure précise. La recherche obtenue renverra les journaux des ordinateurs ou pools définis entre 11 h 00 00 et 11 h 30 00.
    
Par exemple :
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. Pour effectuer une recherche de journaux au cours d’une période spécifique, définissez les propriétés a-StartTime et a-heure_fin. Les journaux entre 13 h 00 et 14 h 45 doivent être présents sur l’ordinateur edge01.contoso.net. 
    
Par exemple :
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>Pour exécuter une recherche avancée à l’aide d’autres critères et options de correspondance

1. Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
2. Pour exécuter une commande visant à collecter les suivis pour des composants en particulier, tapez ce qui suit :
    
   ```
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

Exemple :
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

La recherche obtenue renvoie toutes les entrées de journaux qui possèdent des composants de suivi pour SIPStack, S4 et UserServices sur tous les ordinateurs et pools de votre déploiement au cours des 30 dernières minutes.
    
3. Pour limiter la recherche avec les mêmes composants uniquement au pool frontal nommé pool01.contoso.net, tapez:
    
   ```
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. La logique de recherche par défaut pour les commandes comprenant plusieurs paramètres utilise l’opérateur logique OR avec chacun des paramètres définis. Vous pouvez modifier ce comportement en spécifiant le paramètre **-MatchAll** . Pour ce faire, tapez ce qui suit :
    
   ```
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. Si vos scénarios sont définis de manière à s’exécuter constamment (par exemple AlwaysOn) ou si vous avez défini un scénario à long terme, les journaux peuvent s’étendre de l’ordinateur local au partage de fichiers. Pour définir le partage de fichiers, utilisez le paramètre CacheFileNetworkFolder à l’aide de New-CsClsConfiguration pour créer une nouvelle configuration ou modifiez une configuration existante avec Set-CsClsConfiguration. Si vous ne souhaitez pas que la recherche englobe le partage de fichiers dans la collection des journaux à parcourir, utilisez le paramètre SkipNetworkLogs comme suit :
    
   ```
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a>Lire les journaux de capture à partir du Service de journalisation centralisée

Vous pouvez bénéficier de l’avantage réel du service de journalisation centralisé après avoir exécuté la recherche et disposer d’un fichier que vous pouvez utiliser pour effectuer le suivi d’un problème signalé. Il existe plusieurs façons de lire le fichier. Le fichier de sortie est au format texte standard et vous pouvez utiliser Notepad. exe ou tout autre programme qui vous permettra d’ouvrir et de lire un fichier texte. Pour les fichiers plus volumineux et les problèmes plus complexes, vous pouvez utiliser un outil comme Snooper. exe, conçu pour lire et analyser la sortie de la journalisation à partir du service de journalisation centralisé. La fonction Snoop est incluse dans les outils de débogage disponibles en téléchargement séparé. Vous pouvez télécharger les outils de débogage [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257)ici:. Lorsque vous installez les outils de débogage, des raccourcis courts et des éléments de menu ne sont pas créés. Après l’installation des outils de débogage, ouvrez l’Explorateur Windows, une fenêtre de ligne de commande ou Skype entreprise Server Management Shell, puis accédez au répertoire (emplacement par défaut) C:\Program Files\Skype entreprise Server 2015 \ débogage. Double-cliquez sur Snoop. exe ou tapez Snoop. exe, puis appuyez sur entrée si vous utilisez la ligne de commande ou Skype entreprise Server Management Shell.
  
> [!IMPORTANT]
> Cette rubrique n’a pas pour objectif de détailler et de discuter des techniques de résolution des problèmes. Le dépannage et les processus associés constituent un sujet complexe. Pour plus d’informations sur la résolution des problèmes de base liés à la résolution des problèmes liés à la résolution [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003)des problèmes de charge de travail, voir le kit de ressources Microsoft Lync Server 2010 Les processus et procédures s’appliquent toujours à Skype entreprise Server 2015. 
  
### <a name="to-open-a-log-file-in-snooper"></a>Pour ouvrir un fichier journal dans Snooper

1. Pour utiliser Snooper pour ouvrir des fichiers journaux, vous devez disposer de l’accès en lecture à ces fichiers. Pour utiliser Snooper et accéder aux fichiers journaux, vous devez être membre du groupe de sécurité RBAC CsAdministrator ou CsServerAdministrator, ou d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes. 
    
2. Après l’installation des outils de débogage (LyncDebugTools.msi), définissez le répertoire sur l’emplacement de Snooper.exe à l’aide de l’Explorateur Windows ou à partir de la ligne de commande. Par défaut, les outils de débogage se trouvent dans les outils de débogage C:\Program Files\Skype entreprise Server 2015. Double-cliquez ou exécutez Snooper.exe.
    
3. Après avoir ouvert Snooper, cliquez avec le bouton droit sur **Fichier**, cliquez sur **Ouvrir un fichier**, recherchez vos fichiers journaux, sélectionnez un fichier dans la boîte de dialogue **Ouvrir**, puis cliquez sur **Ouvrir**.
    
4. Les messages de **suivi** du fichier journal sont affichés sous l’onglet **suivi** . cliquez sur l’onglet **messages** pour afficher le contenu des traces collectées.
    
### <a name="to-display-a-call-flow-diagram"></a>Pour afficher un diagramme de flux des appels

1. Pour utiliser Snooper pour ouvrir des fichiers journaux, vous devez disposer de l’accès en lecture à ces fichiers. Pour utiliser Snooper et accéder aux fichiers journaux, vous devez être membre du groupe de sécurité RBAC CsAdministrator ou CsServerAdministrator, ou d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes.
    
2. Ouvrez un fichier journal, cliquez sur l’onglet **Messages**, puis sélectionnez une conversation dans la vue des messages ou un composant de suivi dans l’onglet **Suivi**.
    
3. Cliquez sur **Flux des appels**.
    
> [!NOTE]
> Si vous cliquez sur un message ou une trace qui ne fait pas partie d’un flux d’appels, le diagramme ne s’affichera pas et un message de statut s’affichera en bas de Snooping indiquant «ce message n’est pas éligible pour callfow». Choisissez un autre message ou une trace et le flux d’appels s’affichera si le message ou la trace fait partie d’un flux d’appels. 
  
4. Parcourez les messages ou lignes de trace et vérifiez si le diagramme de flux des appels est mis à jour ou modifié pour afficher un nouveau diagramme.
    
5. Placez le curseur sur les éléments pour obtenir des informations sur les messages d’appel, les points de terminaison et les autres composants.
