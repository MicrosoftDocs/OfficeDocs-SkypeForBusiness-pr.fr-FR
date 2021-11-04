---
title: Rechercher les journaux de capture créés par le service de journalisation centralisée Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: 'Résumé : Découvrez comment rechercher et lire les journaux de capture du service de journalisation centralisée Skype Entreprise Server 2015.'
ms.openlocfilehash: e5a1935b5c2bfcfccd0001adab53d04f6d8a1307
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766332"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Rechercher les journaux de capture créés par le service de journalisation centralisée Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment rechercher et lire les journaux de capture du service de journalisation centralisée Skype Entreprise Server 2015.
  
Les fonctionnalités de recherche dans le service de journalisation centralisée sont utiles et puissantes pour les raisons suivantes : 
  
- Vos recherches et les résultats sont exécutés sur un seul ordinateur, un pool, un site ou une étendue globale, en fonction des critères que vous définissez.
    
- Vos recherches peuvent être larges à l’origine, puis s’affiner sur des critères plus ciblés, tels que l’heure, le composant ou l’ordinateur. Vous recherchez dans les mêmes journaux et n’avez pas besoin d’exécuter à nouveau une session de journalisation lorsque les critères de recherche changent.
    
- Les résultats de votre recherche sont recueillis sur tous les ordinateurs et pools de l’étendue, collectés et regroupés dans un seul fichier de sortie qui représente tous les résultats des critères de recherche (limités aux scénarios qui ont été exécutés et aux données capturées par les scénarios). Vous utilisez des outils familiers, tels que **Snooper** ou le **Bloc-notes** pour lire le fichier de sortie et les messages de suivi de tout votre déploiement.
    
Le CLSAgent sur chaque ordinateur individuel crée les journaux en fonction du ou des scénarios (deux scénarios par ordinateur peuvent s’exécuter en même temps). Les journaux, ainsi que leurs fichiers d’index et de cache associés, sont gérés par le CLSAgent. Lorsque vous définissez et exécutez une recherche, la commande de recherche indique au CLSAgent quelles informations extraire. Le CLSAgent exécute la requête sur les fichiers journaux, les fichiers de cache et les fichiers d’index et renvoie les résultats de la recherche au CLSController. Le CLSController reçoit les résultats de la recherche en provenance de tous les ordinateurs et pools dans l’étendue de la recherche. Le CLSController regroupe ensuite (combine) les journaux et les classe en fonction de l’écart de temps : l’entrée la plus ancienne en premier et l’entrée la plus récente en dernier.
  
Au terme de chaque recherche, l’applet de commande **Sync-CsClsLogging** est exécutée et vide le cache utilisé par les recherches (à ne pas confondre avec les fichiers de cache gérés par le CLSAgent). Le fait de vider le cache permet de s’assurer que la prochaine opération de recherche bénéficie d’une mémoire tampon nette de capture du fichier journal et du fichier de suivi sur le CLSController.
  
Pour tirer le meilleur parti du service de journalisation centralisée, vous devez bien comprendre comment configurer la recherche pour renvoyer uniquement les messages de suivi provenant de l’ordinateur et des journaux du pool qui sont pertinents pour le problème que vous recherchez. problèmes
  
Pour exécuter les fonctions de recherche du service de journalisation centralisée à l’aide de l’environnement de ligne de commande Skype Entreprise Server Management Shell, vous devez être membre des groupes de sécurité RBAC CsAdministrator ou CsServerAdministrator, ou d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes. Pour retourner la liste de tous les rôles RBAC qui ont été affectés à cette cmdlet (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de l’invite Skype Entreprise Server Management Shell ou Windows PowerShell suivante :
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Par exemple :
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

Le reste de cette rubrique se concentre sur la définition d’une recherche en vue d’optimiser la résolution des problèmes.
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>Pour exécuter une recherche de base à l’aide du service de journalisation centralisée

1. Démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
2. Assurez-vous que le scénario AlwaysOn s’exécute dans votre déploiement au niveau de l’étendue globale, puis tapez ce qui suit dans une invite de commandes :
    
   ```PowerShell
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> Par défaut, Search-CsClsLogging envoie les résultats de la recherche à la console. Si vous souhaitez enregistrer les résultats de la recherche dans un fichier, utilisez -OutputFilePath  _\<string fully qualified file path\>_ . Pour définir le paramètre -OutputFilePath, fournissez un chemin d’accès et un nom de fichier dans le cadre du paramètre dans un format de chaîne entre guillemets (par exemple, C:\LogFiles\SearchOutput.txt). Dans cet exemple, vous devez vous assurer que le répertoire C:\LogFiles existe et que vous disposez des autorisations en lecture et en écriture (autorisation NTFS Modifier) sur le dossier. Les résultats sont ajoutés et ne sont pas remplacés. Si vous souhaitez des fichiers séparés, définissez un nom de fichier distinct pour chaque recherche. 
  
Par exemple :
    
  ```PowerShell
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>Pour exécuter une recherche de base sur un pool ou un ordinateur à l’aide du service de journalisation centralisée

1. Pour limiter la recherche à un pool ou un ordinateur spécifique, utilisez le paramètre -Computers avec l’ordinateur défini par un nom complet d’ordinateur, entre guillemets et séparé par une virgule comme suit :
    
   ```PowerShell
   Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
   ```

Par exemple :
    
  ```PowerShell
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. Pour rechercher plusieurs ordinateurs, tapez le nom de plusieurs ordinateurs en les entourant de guillemets et en les séparant par une virgule, comme suit :
    
   ```PowerShell
   Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
   ```

3. Si vous devez effectuer une recherche dans un pool entier au lieu d’un seul ordinateur, remplacez le paramètre -Computers par -Pools, supprimez le nom de l’ordinateur et remplacez-le par le ou les pools entre guillemets séparés par des virgules.
    
    Par exemple :
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. Lorsque vous utilisez les commandes de recherche, les pools peuvent être n’importe quel pool de votre déploiement, comme les pools frontaux, les pools de serveurs Edge, les pools de serveurs de conversation permanente ou d’autres pools définis en tant que pool dans votre déploiement.
    
    Par exemple :
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a>Pour exécuter une recherche à l’aide des paramètres d’heure

1. Démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
2. Par défaut, l’heure de début des paramètres spécifiques au temps d’une recherche est de 25 minutes avant cinq minutes après le début de la recherche. En d’autres termes, si nous faisons une recherche à 16:00:00, l’heure de début de la recherche s’affiche de 15:35:00 à 16:05:00. Si vous devez effectuer une recherche 60 minutes ou 3 heures avant l’heure actuelle, utilisez le paramètre -StartTime et définissez la date et l’heure pour indiquer l’heure de début de la recherche. 
    
    Par exemple, en utilisant -StartTime et -EndTime pour définir une heure et une plage de dates, vous pouvez définir une recherche entre 8 h 00 et 9 h 00 le 20/11/2012 sur votre pool. Vous pouvez configurer le chemin d’accès de sortie de manière à écrire les résultats dans un fichier nommé c:\logfile.txt comme suit :
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> La chaîne d’heure et de date que vous spécifiez peut être « date time » ou « time date ». « La commande va parquer la chaîne et utiliser les valeurs appropriées pour la date et l’heure, ainsi que vos paramètres régionaux et de culture sur l’ordinateur à partir de laquelle vous exécutez la cmdlet. 
  
3. Si vous souhaitez récupérer les journaux à partir de 11:00:00 le 20/11/2012, définissez -StartTime. La période par défaut de la recherche est de 30 minutes, sauf si vous définissez un paramètre -EndTime spécifique. La recherche obtenue renverra les journaux des ordinateurs ou pools définis entre 11 h 00 00 et 11 h 30 00.
    
Par exemple :
    
  ```PowerShell
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. Pour effectuer une recherche de journaux dans un laps de temps spécifique, définissez un -StartTime et un -EndTime. Les journaux entre 13 h 00 et 14 h 45 doivent être présents sur l’ordinateur edge01.contoso.net. 
    
Par exemple :
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>Pour exécuter une recherche avancée à l’aide d’autres critères et options de correspondance

1. Démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
2. Pour exécuter une commande visant à collecter les suivis pour des composants en particulier, tapez ce qui suit :
    
   ```PowerShell
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

Par exemple :
    
  ```PowerShell
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

La recherche obtenue renvoie toutes les entrées de journaux qui possèdent des composants de suivi pour SIPStack, S4 et UserServices sur tous les ordinateurs et pools de votre déploiement au cours des 30 dernières minutes.
    
3. Pour limiter la recherche avec les mêmes composants à votre pool frontal nommé pool01.contoso.net, tapez :
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. La logique de recherche par défaut pour les commandes comprenant plusieurs paramètres utilise l’opérateur logique OR avec chacun des paramètres définis. Vous pouvez modifier ce comportement en spécifiant le **paramètre -MatchAll.** Pour ce faire, tapez ce qui suit :
    
   ```PowerShell
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. Si vos scénarios sont définis de manière à s’exécuter constamment (par exemple AlwaysOn) ou si vous avez défini un scénario à long terme, les journaux peuvent s’étendre de l’ordinateur local au partage de fichiers. Pour définir le partage de fichiers, utilisez le paramètre CacheFileNetworkFolder à l’aide de New-CsClsConfiguration pour créer une nouvelle configuration ou modifiez une configuration existante avec Set-CsClsConfiguration. Si vous ne souhaitez pas que la recherche englobe le partage de fichiers dans la collection des journaux à parcourir, utilisez le paramètre SkipNetworkLogs comme suit :
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a>Lire les journaux de capture à partir du service de journalisation centralisée

Vous réalisez les avantages réels du service de journalisation centralisée après avoir exécuté la recherche et vous avez un fichier que vous pouvez utiliser pour suivre un problème signalé. Il existe plusieurs façons de lire le fichier. Le fichier de sortie est au format texte standard et vous pouvez utiliser Notepad.exe ou tout autre programme qui vous permettra d’ouvrir et de lire un fichier texte. Pour les fichiers plus volumineux et les problèmes plus complexes, vous pouvez utiliser un outil tel que Snooper.exe qui est conçu pour lire et consulter la sortie de journalisation à partir du service de journalisation centralisée. Snooper est inclus dans les outils de débogage disponibles en téléchargement séparé. Vous pouvez télécharger les outils de débogage ici [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257) : Lorsque vous installez les outils de débogage, les raccourcis et les éléments de menu ne sont pas créés. Après avoir installé les outils de débogage, ouvrez Windows Explorer, une fenêtre de ligne de commande ou Skype Entreprise Server Management Shell et allez dans le répertoire (emplacement par défaut) C:\Program Files\Skype Entreprise Server 2015\Debugging Tools. Double-cliquez sur Snooper.exe ou tapez Snooper.exe, puis appuyez sur Entrée si vous utilisez la ligne de commande ou Skype Entreprise Server Management Shell.
  
> [!IMPORTANT]
> L’objectif de cette rubrique n’est pas de détailler et de discuter des techniques de dépannage. La résolution des problèmes et les processus qui l’entourent sont un sujet complexe. Pour plus d’informations sur la résolution des problèmes de base et la résolution des problèmes de charges de travail spécifiques, consultez le manuel du Kit de ressources Microsoft Lync Server 2010 à l’emplacement . [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003) Les processus et procédures s’appliquent toujours Skype Entreprise Server 2015. 
  
### <a name="to-open-a-log-file-in-snooper"></a>Pour ouvrir un fichier journal dans Snooper

1. Pour utiliser Snooper et ouvrir des fichiers journaux, vous devez accéder en lecture aux fichiers journaux. Pour utiliser Snooper et accéder aux fichiers journaux, vous devez être membre des groupes de sécurité RBAC (Contrôle d’accès basé sur un rôle) CsAdministrator ou CsServerAdministrator, ou d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes. 
    
2. Après l’installation des outils de débogage (LyncDebugTools.msi), modifiez le répertoire à l’emplacement de Snooper.exe à l’aide de Windows Explorer ou à partir de la ligne de commande. Par défaut, les outils de débogage se trouvent dans C:\Program Files\Skype Entreprise Server 2015\Debugging Tools. Double-cliquez ou exécutez Snooper.exe.
    
3. Une fois Snooper ouvert, cliquez avec le bouton droit sur **Fichier,** cliquez  sur **OuvrirFichier,** recherchez vos fichiers journaux, sélectionnez un fichier dans la boîte de dialogue Ouvrir, puis cliquez sur **Ouvrir.**
    
4. Les **messages** de suivi du fichier journal sont affichés sous **l’onglet** Suivi. Cliquez sur **l’onglet** Messages pour afficher le contenu du message des suivis collectés.
    
### <a name="to-display-a-call-flow-diagram"></a>Pour afficher un diagramme de flux d’appels

1. Pour utiliser Snooper et ouvrir des fichiers journaux, vous devez accéder en lecture aux fichiers journaux. Pour utiliser Snooper et accéder aux fichiers journaux, vous devez être membre des groupes de sécurité RBAC (Contrôle d’accès basé sur un rôle) CsAdministrator ou CsServerAdministrator, ou d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes.
    
2. Ouvrez un fichier journal et cliquez sur **l’onglet Messages,** sélectionnez une conversation dans l’affichage des messages ou sélectionnez un composant de suivi sous **l’onglet** Suivi.
    
3. Cliquez **sur Appeler Flow**.
    
> [!NOTE]
> Si vous cliquez sur un message ou un suivi qui ne fait pas partie d’un flux d’appels, le diagramme n’apparaît pas et un message d’état apparaît en bas de Snooper indiquant « Ce message n’est pas éligible pour callfow ». Choisissez un autre message ou suivi et le flux d’appels s’affiche si le message ou le suivi fait partie d’un flux d’appels. 
  
4. Déplacez-vous dans les messages ou les lignes de suivi et notez si le diagramme de flux d’appels est mis à jour ou change pour afficher un nouveau diagramme.
    
5. Pointez sur les éléments pour obtenir des informations sur les messages d’appel, les points de terminaison et d’autres composants.
