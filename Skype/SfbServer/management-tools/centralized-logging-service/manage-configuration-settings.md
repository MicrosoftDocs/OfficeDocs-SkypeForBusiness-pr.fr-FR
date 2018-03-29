---
title: Gestion des paramètres de configuration du service de journalisation centralisée dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: 'Résumé : Découvrez comment récupérer, mettre à jour et créer des paramètres de configuration pour le Service de journalisation centralisée dans Skype pour Business Server 2015.'
ms.openlocfilehash: 0c4d03119a61fccd062e650c38815bee069852f5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>Gestion des paramètres de configuration du service de journalisation centralisée dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment récupérer, mettre à jour et créer des paramètres de configuration pour le Service de journalisation centralisée dans Skype pour Business Server 2015.
  
Le Service de journalisation centralisée est contrôlé et configuré par des paramètres et des paramètres qui sont créés et utilisés par le centralisée journalisation contrôleur de Service (CLSController) pour envoyer des commandes à centralisée Service l’Agent d’enregistrement (l’ordinateur individuel CLSAgent). Lʼagent traite les commandes qui lui sont envoyées et (dans le cas dʼune commande de démarrage) utilise la configuration des scénarios, fournisseurs, durée des suivis et indicateurs pour lancer la collecte des journaux de suivi en fonction des informations de configuration fournies.
  
> [!IMPORTANT]
>  Pas toutes les applets de commande Windows PowerShell pour le Service de journalisation centralisée sont conçus pour une utilisation avec les Skype pour les déploiements sur site de Business Server 2015. Bien qu’ils semblent fonctionner correctement, les applets de commande suivantes ne sont pas conçus pour fonctionner avec Skype pour les déploiements sur site de Business Server 2015 :

-  **CsClsRegion applets de commande :** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [Nouvelle-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)et [CsClsRegion à la suppression](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps). 
-  **CsClsSearchTerm applets de commande :** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) et [CsClsSearchTerm de l’ensemble](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).  
-  **CsClsSecurityGroup applets de commande :** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps), [Nouvelle-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)et [CsClsSecurityGroup à la suppression](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps). 

Les paramètres définis dans ces applets de commande ne seront pas entraver ou provoquer un comportement indésirable, mais ils sont conçus pour une utilisation avec Microsoft Office 365 et ne produira pas les résultats attendus dans les déploiements sur site. Cela ne signifie ne pas qu’il n’y a pas d’utilisation de ces applets de commande dans les déploiements sur site, mais leur utilisation est un sujet plus complexe qui n’est pas traitée dans cette documentation.
  
Le Service de journalisation centralisée peut être exécuté à une portée qui inclut un ordinateur unique ou un groupe d’ordinateurs, à une étendue de site (autrement dit, un site défini tel que le site de Redmond qui constituée une collection d’ordinateur et les pools dans votre déploiement) ou à une portée globale (ce qui est tous les ordinateurs et les pools dans votre déploiement).
  
Pour configurer l’étendue du Service de journalisation centralisée à l’aide de la Skype pour Business Server Management Shell, vous devez être un membre de la CsAdministrator ou les groupes de sécurité de CsServerAdministrator accès basé sur les rôles (RBAC) de contrôle, soit un rôle RBAC personnalisé qui contient une ou l’autre de ces deux groupes. Pour retourner une liste de tous les rôles RBAC que cette applet de commande a été attribué à (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de la Skype Business Server Management Shell ou de l’invite de Windows PowerShell :
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

Par exemple :
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Il existe des différences fondamentales entre les commandes de ligne de commande que vous pouvez exécuter dans Windows PowerShell ou CLSController. Windows PowerShell fournit une méthode riche à configurer et à définir des scénarios et de réutiliser les scénarios de manière explicite pour vos scénarios de résolution des problèmes. CLSController fournit un moyen rapide et efficace d’émettre des commandes et d’obtenir des résultats, l’ensemble de commandes pour CLSController est limité à un nombre fini de commandes disponibles à partir de la ligne de commande. À la différence des applets de commande Windows PowerShell, CLSController ne peut pas définir de nouveaux scénarios, gérer la portée au site ou au niveau global et de nombreuses autres limitations d’un jeu de commandes limité qui ne peut pas être configuré dynamiquement. CLSController fournit un moyen pour une exécution rapide, Windows PowerShell permet d’étendre les fonctionnalités du Service de journalisation centralisée au-delà de ce qui est possible avec CLSController. 
  
Une étendue d’ordinateur unique peut être définie lors de l’exécution d’une [Recherche-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Afficher-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Début-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) et de [CsClsLogging de la mise à jour](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) à l’aide de la commande-paramètre d’ordinateurs. -Ordinateurs paramètre accepte une liste séparée par des virgules de noms de domaine pleinement qualifié (FQDN) pour l’ordinateur cible.
  
> [!TIP]
> Vous pouvez également définir - Pools et une liste séparée par des virgules des pools que vous souhaitez exécuter les commandes de journalisation sur. 
  
Les étendues globales et de site sont définies dans les applets de commande **New -**, **Set**et **Remove -** centralisée Service d’enregistrement. Les exemples suivants montrent comment définir une étendue globale ou de site.
  
> [!IMPORTANT]
> Les commandes indiquées peuvent contenir des paramètres et des concepts décrits dans d’autres sections. Les commandes de l’exemple sont destinés à montrer l’utilisation de la **-identité** paramètre pour définir la portée et les autres paramètres sont inclus par souci d’exhaustivité et spécifier l’étendue. Pour plus d’informations sur les applets de commande **Set-CsClsConfiguration** , voir [CsClsConfiguration de l’ensemble](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) de la documentation sur les opérations.
  
### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>Pour récupérer la configuration du Service de journalisation centralisée en cours

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Tapez ce qui suit à l’invite de ligne de commande :
    
  ```
  Get-CsClsConfiguration
  ```

Utiliser les applets de commande **New-CsClsConfiguration** et **CsClsConfiguration de l’ensemble** pour créer une nouvelle configuration ou mettre à jour une configuration existante. Lorsque vous exécutez **Get-CsClsConfiguration**, il affiche des informations similaires à l’écran suivant, où le déploiement a actuellement la configuration globale par défaut, mais aucune des configurations de site défini par :
  
![Exemple de sortie de Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>Pour récupérer la configuration de Service centralisé d’enregistrement en cours dans le magasin de l’ordinateur local

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Tapez ce qui suit à l’invite de ligne de commande :
    
  ```
  Get-CsClsConfiguration -LocalStore
  ```

Lorsque vous utilisez le premier exemple où **Get-CsClsConfiguration** ne spécifie pas de paramètres, les références de commande du magasin Central de gestion des données. Si vous spécifiez le paramètre - LocalStore, la commande est relié à l’ordinateur LocalStore au lieu du magasin Central de gestion.
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>Pour récupérer une liste des scénarios actuellement définis

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Tapez ce qui suit à l’invite de ligne de commande :
    
  ```
  Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
  ```

    Par exemple, pour récupérer les scénarios définis au niveau global :
    
  ```
  Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
  ```

L’applet de commande **Get-CsClsConfiguration** affiche toujours les scénarios qui font partie de la configuration d’une étendue donnée. Dans la plupart des cas, tous les scénarios ne sont pas affichés et sont tronqués. La commande utilisée ici répertorie tous les scénarios et des informations partielles concernant les fournisseurs, les paramètres et les indicateurs utilisés.
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Pour mettre à jour une étendue globale pour le Service de journalisation centralisée à l’aide de Windows PowerShell

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Tapez ce qui suit à l’invite de ligne de commande :
    
  ```
  Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
  ```

  Exemple :
    
  ```
  Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
  ```

La commande indique au CLSAgent de chaque ordinateur et pool du déploiement de définir la valeur de substitution dans le fichier de suivi à 40 mégaoctets. Les ordinateurs et les pools de tous les sites sont affectés par cette commande, et définiront la valeur de substitution du journal de suivi configuré à 40 mégaoctets.
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Pour mettre à jour une étendue de site pour le Service de journalisation centralisée à l’aide de Windows PowerShell

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Tapez ce qui suit à l’invite de ligne de commande :
    
  ```
  Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
  ```

  Exemple :
    
  ```
  Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40  
  ```

> [!NOTE]
> Comme indiqué dans l’exemple, l’emplacement par défaut des fichiers journaux est %TEMP%\Tracing. Cependant, dans la mesure où CLSAgent écrit dans le fichier et qu’il s’exécute en tant que service réseau, la variable %TEMP% devient %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. 
  
Cette commande indique au CLSAgent de chaque ordinateur et pool du site Redmond de définir la taille de la valeur de substitution du fichier de suivi à 40 mégaoctets. Les ordinateurs et les pools des autres sites ne sont pas affectés par cette commande, et continueront d’utiliser la valeur de substitution du journal de suivi configurée actuellement et définie par défaut (20 mégaoctets) ou lors du démarrage de la session de journalisation.
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>Pour créer une nouvelle configuration du Service de journalisation centralisée

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Tapez ce qui suit à l’invite de ligne de commande :
    
  ```
  New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
  ```

    > [!NOTE]
    > New-CsClsConfiguration permet dʼaccéder à un grand nombre de paramètres de configuration facultatifs. Pour plus d’informations sur les options de configuration, consultez [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) et la [Compréhension centralisée Service Configuration paramètres de journalisation](http://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx). 
  
Par exemple, pour créer une configuration qui définit un dossier réseau pour les fichiers en cache, la période de substitution pour les fichiers journaux et la taille de la substitution pour les fichiers journaux, tapez :
    
  ```
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

Vous devez planifier soigneusement la création de nouvelles configurations et comment définir de nouvelles propriétés pour le Service de journalisation centralisée. Faites attention lorsque vous apportez des modifications et assurez-vous de bien comprendre l’impact sur la journalisation des scénarios. Apportez des modifications à la configuration pour améliorer la résolution des problèmes en permettant une meilleure gestion des tailles de journaux et de la période de substitution.
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>Pour supprimer une configuration de Service de journalisation centralisée existante

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Tapez ce qui suit à l’invite de ligne de commande :
    
  ```
  Remove-CsClsConfiguration -Identity <scope and name>
  ```

Par exemple, pour supprimer une configuration de Service centralisé d’enregistrement que vous avez créé pour augmenter le délai de substitution de fichier journal, augmentez la taille du fichier journal survol et définir l’emplacement du cache de fichier journal sur un partage réseau, comme suit :
    
  ```
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> Il s’agit de la nouvelle configuration qui a été créée dans la procédure « pour créer une nouvelle configuration du Service de journalisation centralisée ». 
  
Si vous choisissez de supprimer une configuration au niveau du site, le site utilisera les paramètres globaux.
## <a name="see-also"></a>Voir aussi

#### 

[Configurer les fournisseurs de service de journalisation centralisée dans Skype pour Business Server 2015](configure-providers.md)
  
[Configurer des scénarios pour le Service centralisé de journalisation dans Skype pour Business Server 2015](configure-scenarios.md)
#### 

[Service de journalisation centralisée dans Skype pour entreprise 2015](centralized-logging-service.md)
#### 

[Ensemble-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)
  
[Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)
  
[Nouvelle-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)
  
[Supprimer-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)

