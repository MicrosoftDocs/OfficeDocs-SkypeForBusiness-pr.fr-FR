---
title: Recherche dans les journaux de capture créés par le service de journalisation centralisée dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: 'Résumé : Découvrez comment rechercher et lire des journaux de Service de journalisation centralisée dans Skype pour Business Server 2015.'
ms.openlocfilehash: 463daf41d0e1e1e7c5a718adcd48bdb3f227feff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33914911"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Recherche dans les journaux de capture créés par le service de journalisation centralisée dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment rechercher et lire des journaux de Service de journalisation centralisée dans Skype pour Business Server 2015.
  
Les fonctionnalités de recherche dans le Service de journalisation centralisée sont utiles et puissantes pour les raisons suivantes : 
  
- Vos recherches et les résultats sont exécutés sur un seul ordinateur, un pool, un site ou une étendue globale, en fonction des critères que vous définissez.
    
- Vos recherches peuvent être larges à l’origine, puis s’affiner sur des critères plus ciblés, tels que l’heure, le composant ou l’ordinateur. Vous effectuer une recherche sur les mêmes journaux et que vous n’avez pas besoin exécuter à nouveau une session de journalisation lorsque les critères de recherche est modifié.
    
- Les résultats de votre recherche sont issus de tous les ordinateurs et pools de l’étendue, collectés et regroupés en un seul fichier de sortie qui représente tous les résultats des critères de recherche (limités aux scénarios qui ont été exécutés et aux données capturées par les scénarios). Vous utilisez des outils familiers, tels que **Snooper** ou **Notepad**, pour lire le fichier de sortie et les messages de suivi de tout votre déploiement.
    
Le CLSAgent sur chaque ordinateur individuel crée les journaux en fonction du ou des scénarios (deux scénarios par ordinateur peuvent s’exécuter en même temps). Les journaux, ainsi que leurs fichiers d’index et de cache associés, sont gérés par le CLSAgent. Lorsque vous définissez et exécutez une recherche, la commande de recherche indique au CLSAgent quelles informations extraire. Le CLSAgent exécute la requête sur les fichiers journaux, les fichiers de cache et les fichiers d’index et renvoie les résultats de la recherche au CLSController. Le CLSController reçoit les résultats de la recherche en provenance de tous les ordinateurs et pools dans l’étendue de la recherche. Le CLSController regroupe ensuite (combine) les journaux et les classe en fonction de l’écart de temps : l’entrée la plus ancienne en premier et l’entrée la plus récente en dernier.
  
Après chaque recherche, l’applet de commande **Sync-CsClsLogging** est exécutée et vide le cache utilisé par les recherches (à ne pas confondre avec les fichiers cache gérés par CLSAgent). Le fait de vider le cache permet de garantir que la prochaine opération de recherche bénéficie d’une mémoire tampon nette de capture du fichier journal et du fichier de suivi sur le CLSController.
  
Pour tirer le meilleur parti du service de journalisation centralisée, vous avez besoin d’une bonne compréhension de la façon de configurer la recherche pour retourner uniquement les messages de suivi à partir des journaux d’ordinateur et le pool qui sont pertinents pour le problème que vous effectuez une recherche. problèmes
  
Pour exécuter les fonctions de recherche du Service de journalisation centralisée à l’aide de la Skype pour Business Server Management Shell, vous devez être un membre de la CsAdministrator ou les groupes de sécurité CsServerAdministrator accès basé sur un rôle RBAC (contrôle) ou un rôle RBAC personnalisé qui contient une de ces deux groupes. Pour retourner une liste de tous les rôles RBAC cette applet de commande a été assigné à (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de la Skype Business Server Management Shell ou de l’invite de Windows PowerShell :
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Par exemple :
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

Le reste de cette rubrique se concentre sur la définition d’une recherche en vue d’optimiser la résolution des problèmes.
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>Pour exécuter une recherche de base en utilisant le Service de journalisation centralisée

1. Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.
    
2. Assurez-vous que le scénario AlwaysOn s’exécute dans votre déploiement au niveau de l’étendue globale, puis tapez ce qui suit dans une invite de commandes :
    
   ```
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> Par défaut, Search-CsClsLogging envoie les résultats de la recherche à la console. Si vous souhaitez enregistrer les résultats de recherche dans un fichier, utilisez - OutputFilePath _ \<chemin d’accès complet chaîne\>_. Pour définir le paramètre - OutputFilePath, indiquez un chemin d’accès et un nom de fichier dans le cadre du paramètre dans un format de chaîne entouré guillemets (par exemple, C:\LogFiles\SearchOutput.txt). Dans cet exemple, vous devez vous assurer que le répertoire C:\LogFiles existe et que vous disposez des autorisations en lecture et en écriture (autorisation NTSF Modifier) sur le dossier. Les résultats sont ajoutés et ne sont pas remplacés. Si vous avez besoin de fichiers séparés, définissez un nom de fichier différent pour chaque recherche. 
  
Par exemple :
    
  ```
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>Pour exécuter une recherche de base sur un ordinateur ou un pool en utilisant le Service de journalisation centralisée

1. Pour limiter la recherche à un ordinateur ou un pool spécifique, utilisez-paramètre ordinateurs avec l’ordinateur défini par un nom complet de l’ordinateur, placé entre guillemets et séparés par une virgule, comme suit :
    
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

3. Si vous avez besoin rechercher un pool entier au lieu d’un seul ordinateur, modifiez l’ordinateurs paramètre - à - Pools, supprimer le nom d’ordinateur et remplacer avec le pool ou les pools de guillemets séparées par des virgules.
    
    Par exemple :
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. Lorsque vous utilisez les commandes de recherche, les pools peuvent être n’importe quel pool dans votre déploiement, telles que les pools frontaux, pools de serveurs Edge, les pools de serveurs de conversation permanente ou d’autres personnes qui sont définis comme un pool de votre déploiement.
    
    Par exemple :
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a>Pour exécuter une recherche à l’aide des paramètres d’heure

1. Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.
    
2. Par défaut, l’heure de début pour les paramètres temporels d’une recherche est définie sur 25 minutes avant les cinq minutes après l’heure où vous lancez la recherche. En d’autres mots, si nous effectuons une recherche à 16 h 00 00, la recherche s’étendra alors de 15 h 35 00 à 16 h 05 00. Si vous avez besoin rechercher les 60 minutes ou 3 heures avant l’heure actuelle, utilisez le paramètre - StartTime et définir la chaîne de date et heure pour indiquer l’heure à que laquelle démarrer la recherche. 
    
    Par exemple, à l’aide de - StartTime et EndTime - pour définir une plage de date et heure, vous pouvez définir une recherche de 8 à 9 h 00 sur 20/11/2012 sur votre pool. Vous pouvez configurer le chemin d’accès de sortie de manière à écrire les résultats dans un fichier nommé c:\logfile.txt comme suit :
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> La date et l’heure que vous définissez peut s’appeler « date heure » ou « heure date ». « La commande analyser la chaîne et utiliser les valeurs appropriées pour la date et heure et vos paramètres régionaux et de la culture sur l’ordinateur que vous exécutez la cmdlet à partir de. 
  
3. Si vous souhaitez récupérer les journaux commençant à 11:00:00 AM sur 20/11/2012, vous définissez l’heure de début. La plage de temps par défaut pour la recherche est de 30 minutes, sauf si vous définissez une heure de fin - spécifique. La recherche obtenue renverra les journaux des ordinateurs ou pools définis entre 11 h 00 00 et 11 h 30 00.
    
Par exemple :
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. Pour effectuer une recherche de journaux au sein d’une période spécifique, définissez une heure de début - et - EndTime. Les journaux entre 13 h 00 et 14 h 45 doivent être présents sur l’ordinateur edge01.contoso.net. 
    
Par exemple :
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>Pour exécuter une recherche avancée à l’aide d’autres critères et options de correspondance

1. Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.
    
2. Pour exécuter une commande visant à collecter les suivis pour des composants en particulier, tapez ce qui suit :
    
   ```
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

Exemple :
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

La recherche obtenue renvoie toutes les entrées de journaux qui possèdent des composants de suivi pour SIPStack, S4 et UserServices sur tous les ordinateurs et pools de votre déploiement au cours des 30 dernières minutes.
    
3. Pour limiter la recherche avec les mêmes composants à seulement votre pool frontal nommé pool01.contoso.net, tapez :
    
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

Vous réalisez l’avantage réel du Service de journalisation centralisée après exécution de la recherche et que vous disposez d’un fichier que vous pouvez utiliser pour localiser un problème. Il existe plusieurs méthodes que vous pouvez lire le fichier. Le fichier de sortie est au format texte standard et vous pouvez utiliser Notepad.exe ou autres programmes qui vous permettra d’ouvrir et de lire un fichier texte. Pour les fichiers de grande taille et problèmes plus complexes, vous pouvez utiliser un outil tel que Snooper.exe est conçu pour lire et analyser la sortie d’enregistrement à partir du Service de journalisation centralisée. Snooper est inclus dans les outils de débogage qui sont disponibles en tant que téléchargement séparé. Vous pouvez télécharger les outils de débogage ici : [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257). Lorsque vous installez les outils de débogage, les raccourcis et les éléments de menu ne sont pas créés. Après avoir installé les outils de débogage, ouvrez l’Explorateur Windows, une fenêtre de ligne de commande ou Skype pour Business Server Management Shell et accédez au répertoire (emplacement par défaut) C:\Program Files\Skype pour Business Server 2015\Debugging Tools. Double-cliquez sur Snooper.exe ou tapez Snooper.exe, puis appuyez sur entrée si vous utilisez la ligne de commande ou Skype pour Business Server Management Shell.
  
> [!IMPORTANT]
> Cette rubrique n’a pas pour objectif de détailler et de discuter des techniques de résolution des problèmes. Le dépannage et les processus associés constituent un sujet complexe. Pour plus d’informations sur les notions élémentaires de dépannage et de résolution des problèmes de charges de travail spécifiques, consultez le Kit de ressources de Microsoft Lync Server 2010 à [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003). Les processus et procédures toujours s’appliquent à Skype for Business Server 2015. 
  
### <a name="to-open-a-log-file-in-snooper"></a>Pour ouvrir un fichier journal dans Snooper

1. Pour utiliser Snooper pour ouvrir des fichiers journaux, vous devez disposer de l’accès en lecture à ces fichiers. Pour utiliser Snooper et accéder aux fichiers journaux, vous devez être membre du groupe de sécurité RBAC CsAdministrator ou CsServerAdministrator, ou d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes. 
    
2. Après l’installation des outils de débogage (LyncDebugTools.msi), définissez le répertoire sur l’emplacement de Snooper.exe à l’aide de l’Explorateur Windows ou à partir de la ligne de commande. Par défaut, les outils de débogage sont situés dans C:\Program Files\Skype pour Business Server 2015\Debugging Tools. Double-cliquez ou exécutez Snooper.exe.
    
3. Après avoir ouvert Snooper, cliquez avec le bouton droit sur **Fichier**, cliquez sur **Ouvrir un fichier**, recherchez vos fichiers journaux, sélectionnez un fichier dans la boîte de dialogue **Ouvrir**, puis cliquez sur **Ouvrir**.
    
4. Messages de **suivi** du fichier journal sont affichés dans le **suivi** de l' onglet, cliquez sur l’onglet **Messages** pour afficher le contenu du message des traces collectés.
    
### <a name="to-display-a-call-flow-diagram"></a>Pour afficher un diagramme de flux des appels

1. Pour utiliser Snooper pour ouvrir des fichiers journaux, vous devez disposer de l’accès en lecture à ces fichiers. Pour utiliser Snooper et accéder aux fichiers journaux, vous devez être membre du groupe de sécurité RBAC CsAdministrator ou CsServerAdministrator, ou d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes.
    
2. Ouvrez un fichier journal, cliquez sur l’onglet **Messages**, puis sélectionnez une conversation dans la vue des messages ou un composant de suivi dans l’onglet **Suivi**.
    
3. Cliquez sur **Flux des appels**.
    
> [!NOTE]
> Si vous cliquez sur un message ou de suivi qui ne fait pas partie d’un flux d’appel, le diagramme n’apparaît pas et un message d’état apparaît en bas de Snooper indiquant « ce message n’est pas éligible pour callfow ». Choisissez un autre message ou suivi et le flux d’appels s’affiche si le message ou le suivi fait partie d’un flux d’appels. 
  
4. Parcourez les messages ou lignes de trace et vérifiez si le diagramme de flux des appels est mis à jour ou modifié pour afficher un nouveau diagramme.
    
5. Placez le curseur sur les éléments pour obtenir des informations sur les messages d’appel, les points de terminaison et les autres composants.
