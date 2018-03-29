---
title: Recherche dans les journaux de capture créés par le service de journalisation centralisée dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: 'Résumé : Découvrez comment rechercher et lire des journaux de Service de journalisation centralisée dans Skype pour Business Server 2015.'
ms.openlocfilehash: ccf9827848d190179b5f942646a74947047c02c5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Recherche dans les journaux de capture créés par le service de journalisation centralisée dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment rechercher et lire des journaux de Service de journalisation centralisée dans Skype pour Business Server 2015.
  
Les fonctionnalités de recherche dans le Service de journalisation centralisée sont utile et puissante pour les raisons suivantes : 
  
- Vos recherches et les résultats sont exécutés sur un seul ordinateur, un pool, un site ou une étendue globale, en fonction des critères que vous définissez.
    
- Vos recherches peuvent être larges à l’origine, puis s’affiner sur des critères plus ciblés, tels que l’heure, le composant ou l’ordinateur. Vous effectuer une recherche sur les mêmes journaux et n’avez pas besoin d’exécuter à nouveau une session de journalisation lorsque les critères de recherche est modifié.
    
- Les résultats de votre recherche sont issus de tous les ordinateurs et pools de l’étendue, collectés et regroupés en un seul fichier de sortie qui représente tous les résultats des critères de recherche (limités aux scénarios qui ont été exécutés et aux données capturées par les scénarios). Vous utilisez des outils familiers, tels que **Snooper** ou **Notepad**, pour lire le fichier de sortie et les messages de suivi de tout votre déploiement.
    
Le CLSAgent sur chaque ordinateur individuel crée les journaux en fonction du ou des scénarios (deux scénarios par ordinateur peuvent s’exécuter en même temps). Les journaux, ainsi que leurs fichiers d’index et de cache associés, sont gérés par le CLSAgent. Lorsque vous définissez et exécutez une recherche, la commande de recherche indique au CLSAgent quelles informations extraire. Le CLSAgent exécute la requête sur les fichiers journaux, les fichiers de cache et les fichiers d’index et renvoie les résultats de la recherche au CLSController. Le CLSController reçoit les résultats de la recherche en provenance de tous les ordinateurs et pools dans l’étendue de la recherche. Le CLSController regroupe ensuite (combine) les journaux et les classe en fonction de l’écart de temps : l’entrée la plus ancienne en premier et l’entrée la plus récente en dernier.
  
Après chaque recherche, l’exécution de l’applet de commande **Sync-CsClsLogging** , et elle vide le cache utilisé par la recherche (à ne pas pour confondre avec les fichiers du cache gérés par le CLSAgent). Le fait de vider le cache permet de garantir que la prochaine opération de recherche bénéficie d’une mémoire tampon nette de capture du fichier journal et du fichier de suivi sur le CLSController.
  
Pour tirer le meilleur parti du service de journalisation centralisée, vous devez bien comprendre comment configurer la recherche pour retourner uniquement les messages de trace à partir des journaux d’ordinateur et le pool qui concernent le problème que vous effectuez une recherche. problèmes
  
Pour exécuter les fonctions de recherche du Service de journalisation centralisée à l’aide de la Skype pour Business Server Management Shell, vous devez être un membre de la CsAdministrator ou les groupes de sécurité de CsServerAdministrator accès basé sur les rôles (RBAC) de contrôle, soit un rôle RBAC personnalisé qui contient une ou l’autre de ces deux groupes. Pour retourner une liste de tous les rôles RBAC cette applet de commande a été attribué à (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de la Skype Business Server Management Shell ou de l’invite de Windows PowerShell :
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Exemple :
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

Le reste de cette rubrique se concentre sur la définition d’une recherche en vue d’optimiser la résolution des problèmes.
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>Pour exécuter une recherche de base en utilisant le Service de journalisation centralisée

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Assurez-vous que le scénario AlwaysOn s’exécute dans votre déploiement au niveau de l’étendue globale, puis tapez ce qui suit dans une invite de commandes :
    
  ```
  Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
  ```

> [!NOTE]
> Par défaut, Search-CsClsLogging envoie les résultats de la recherche à la console. Si vous souhaitez enregistrer des résultats de la recherche dans un fichier, utilisez - OutputFilePath _ \<chemin d’accès de fichier complet de chaîne\>_. Pour définir le paramètre - OutputFilePath, fournissez un chemin d’accès et un nom de fichier comme partie du paramètre sous forme de chaîne entouré guillemets (par exemple ; C:\LogFiles\SearchOutput.txt). Dans cet exemple, vous devez vous assurer que le répertoire C:\LogFiles existe et que vous disposez des autorisations en lecture et en écriture (autorisation NTSF Modifier) sur le dossier. Les résultats sont ajoutés et ne sont pas remplacés. Si vous avez besoin de fichiers séparés, définissez un nom de fichier différent pour chaque recherche. 
  
Exemple :
    
  ```
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>Pour exécuter une recherche simple sur un pool ou d’un ordinateur en utilisant le Service de journalisation centralisée

1. Pour limiter la recherche à un ordinateur ou un pool spécifique, utilisez-paramètre d’ordinateurs avec l’ordinateur défini par un nom qualifié complet de l’ordinateur, placé entre guillemets et séparés par des virgules, comme suit :
    
  ```
  Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
  ```

Exemple :
    
  ```
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. Pour rechercher plusieurs ordinateurs, tapez le nom de plusieurs ordinateurs en les entourant de guillemets et en les séparant par une virgule, comme suit :
    
  ```
  Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

3. Si vous devez rechercher un pool entier au lieu d’un seul ordinateur, modifier paramètre - ordinateurs à - Pools, supprimer le nom de l’ordinateur et remplacer avec le pool ou les pools de guillemets doubles séparés par des virgules.
    
    Par exemple :
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. Lorsque vous utilisez les commandes de recherche, les pools peuvent être n’importe quel pool dans votre déploiement, comme les pools de Front-End, pools de bord, pools de serveur de conversation persistant ou ceux qui sont définis comme un pool de ressources dans votre déploiement.
    
    Exemple :
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-a-search-by-using-time-parameters"></a>Pour exécuter une recherche à l’aide des paramètres d’heure

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Par défaut, l’heure de début pour les paramètres temporels d’une recherche est définie sur 25 minutes avant les cinq minutes après l’heure où vous lancez la recherche. En d’autres mots, si nous effectuons une recherche à 16 h 00 00, la recherche s’étendra alors de 15 h 35 00 à 16 h 05 00. Si vous devez rechercher les 60 minutes ou trois heures avant l’heure actuelle, utilisez le paramètre - StartTime et définissez la chaîne de date et d’heure pour indiquer l’heure à que laquelle démarrer la recherche. 
    
    Par exemple, aide - StartTime et EndTime - pour définir une plage de date et d’heure, vous pouvez définir une recherche entre 8 heures et 9 heures sur 20/11/2012 sur votre pool. Vous pouvez configurer le chemin d’accès de sortie de manière à écrire les résultats dans un fichier nommé c:\logfile.txt comme suit :
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

> [!NOTE]
> La date et l’heure que vous définissez peut s’appeler « date heure » ou « heure date ». « La commande analyser la chaîne et utiliser les valeurs appropriées pour les date et heure et vos paramètres régionaux et la culture sur la machine où que vous exécutez à partir d’applet de commande. 
  
3. Si vous souhaitez récupérer les journaux commençant à 11:00:00 AM sur 20/11/2012, vous définissez l’heure de début de. La plage de temps pour la recherche par défaut est de 30 minutes, sauf si vous définissez une heure de fin - spécifique. La recherche obtenue renverra les journaux des ordinateurs ou pools définis entre 11 h 00 00 et 11 h 30 00.
    
Exemple :
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. Pour effectuer une recherche de journaux dans un délai spécifique, définissez une heure de début de- et d’une heure de fin. Les journaux entre 13 h 00 et 14 h 45 doivent être présents sur l’ordinateur edge01.contoso.net. 
    
Exemple :
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>Pour exécuter une recherche avancée à l’aide d’autres critères et options de correspondance

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Pour exécuter une commande visant à collecter les suivis pour des composants en particulier, tapez ce qui suit :
    
  ```
  Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
  ```

Exemple :
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

La recherche obtenue renvoie toutes les entrées de journaux qui possèdent des composants de suivi pour SIPStack, S4 et UserServices sur tous les ordinateurs et pools de votre déploiement au cours des 30 dernières minutes.
    
3. Pour limiter la recherche avec les mêmes composants à tout votre pool frontal nommé pool01.contoso.net, tapez :
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. La logique de recherche par défaut pour les commandes comprenant plusieurs paramètres utilise l’opérateur logique OR avec chacun des paramètres définis. Vous pouvez modifier ce comportement en spécifiant le paramètre **- MatchAll** . Pour ce faire, tapez ce qui suit :
    
  ```
  Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

5. Si vos scénarios sont définis de manière à s’exécuter constamment (par exemple AlwaysOn) ou si vous avez défini un scénario à long terme, les journaux peuvent s’étendre de l’ordinateur local au partage de fichiers. Pour définir le partage de fichiers, utilisez le paramètre CacheFileNetworkFolder à l’aide de New-CsClsConfiguration pour créer une nouvelle configuration ou modifiez une configuration existante avec Set-CsClsConfiguration. Si vous ne souhaitez pas que la recherche englobe le partage de fichiers dans la collection des journaux à parcourir, utilisez le paramètre SkipNetworkLogs comme suit :
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

  ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a>Lire les journaux de capture à partir du Service de journalisation centralisée

Vous vous rendez compte de l’avantage réel du Service de journalisation centralisée après l’exécution de la recherche et que vous disposez d’un fichier que vous pouvez utiliser pour identifier un problème signalé. Il existe un certain nombre de méthodes que vous pouvez lire le fichier. Le fichier de sortie est au format texte standard et vous pouvez utiliser Notepad.exe ou tout autre programme qui vous permettra d’ouvrir et de lire un fichier texte. Pour les fichiers plus volumineux et les problèmes plus complexes, vous pouvez utiliser un outil tel que Snooper.exe conçu pour lire et analyser la sortie d’enregistrement à partir du Service de journalisation centralisée. Détecte est inclus dans les outils de débogage qui sont disponibles en tant que téléchargement séparé. Vous pouvez télécharger les outils de débogage ici : [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257). Lorsque vous installez les outils de débogage, les raccourcis et les éléments de menu ne sont pas créés. Après avoir installé les outils de débogage, ouvrez l’Explorateur Windows, une fenêtre de ligne de commande ou Skype pour Business Server Management Shell et accédez au répertoire (emplacement par défaut), Files\Skype C:\Program pour Business Server 2015\Debugging Tools. Double-cliquez sur Snooper.exe ou tapez Snooper.exe et appuyez sur entrée si vous utilisez la ligne de commande ou Skype pour Business Server Management Shell.
  
> [!IMPORTANT]
> Cette rubrique n’a pas pour objectif de détailler et de discuter des techniques de résolution des problèmes. Le dépannage et les processus associés constituent un sujet complexe. Pour plus d’informations sur les notions de base de résolution des problèmes et le dépannage des charges de travail spécifiques, consultez le Kit de ressources techniques de Microsoft Lync Server 2010 à [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003). Les processus et procédures s’appliquent toujours à Skype pour Business Server 2015. 
  
### <a name="to-open-a-log-file-in-snooper"></a>Pour ouvrir un fichier journal dans Snooper

1. Pour utiliser Snooper pour ouvrir des fichiers journaux, vous devez disposer de l’accès en lecture à ces fichiers. Pour utiliser Snooper et accéder aux fichiers journaux, vous devez être membre du groupe de sécurité RBAC CsAdministrator ou CsServerAdministrator, ou d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes. 
    
2. Après l’installation des outils de débogage (LyncDebugTools.msi), définissez le répertoire sur l’emplacement de Snooper.exe à l’aide de l’Explorateur Windows ou à partir de la ligne de commande. Par défaut, les outils de débogage se trouvent dans C:\Program des Files\Skype pour les outils Business Server 2015\Debugging. Double-cliquez ou exécutez Snooper.exe.
    
3. Après avoir ouvert Snooper, cliquez avec le bouton droit sur **Fichier**, cliquez sur **Ouvrir un fichier**, recherchez vos fichiers journaux, sélectionnez un fichier dans la boîte de dialogue **Ouvrir**, puis cliquez sur **Ouvrir**.
    
4. Les messages de **Trace** du fichier journal sont affichées dans la **Trace** de l' onglet, cliquez sur l’onglet **Messages** pour afficher le contenu du message des traces collectées.
    
### <a name="to-display-a-call-flow-diagram"></a>Pour afficher un diagramme de flux des appels

1. Pour utiliser Snooper pour ouvrir des fichiers journaux, vous devez disposer de l’accès en lecture à ces fichiers. Pour utiliser Snooper et accéder aux fichiers journaux, vous devez être membre du groupe de sécurité RBAC CsAdministrator ou CsServerAdministrator, ou d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes.
    
2. Ouvrez un fichier journal, cliquez sur l’onglet **Messages**, puis sélectionnez une conversation dans la vue des messages ou un composant de suivi dans l’onglet **Suivi**.
    
3. Cliquez sur **Flux des appels**.
    
> [!NOTE]
> Si vous cliquez sur un message ou une trace qui ne fait pas partie d’un flux d’appel, le diagramme ne s’affiche pas et un message d’état s’affiche en bas de détecte indiquant « ce message n’est pas éligible pour callfow ». Choisir un autre message trace et le flux des appels s’affiche si le suivi du message ou fait partie d’un flux d’appels. 
  
4. Parcourez les messages ou lignes de trace et vérifiez si le diagramme de flux des appels est mis à jour ou modifié pour afficher un nouveau diagramme.
    
5. Placez le curseur sur les éléments pour obtenir des informations sur les messages d’appel, les points de terminaison et les autres composants.