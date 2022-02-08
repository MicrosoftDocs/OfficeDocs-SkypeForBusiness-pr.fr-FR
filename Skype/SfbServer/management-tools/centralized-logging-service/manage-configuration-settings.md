---
title: Gérer les paramètres de configuration du service de journalisation centralisée Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: 'Résumé : Découvrez comment récupérer, mettre à jour et créer des paramètres de configuration pour le service de journalisation centralisée dans Skype Entreprise Server 2015.'
ms.openlocfilehash: 655c5a18d64ae17000f975680f0b9b9a6a42323f
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385554"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>Gérer les paramètres de configuration du service de journalisation centralisée Skype Entreprise Server 2015

**Résumé :** Découvrez comment récupérer, mettre à jour et créer des paramètres de configuration pour le service de journalisation centralisée Skype Entreprise Server 2015.

Le service de journalisation centralisée est contrôlé et configuré par des paramètres et des paramètres créés et utilisés par le contrôleur de service de journalisation centralisée (CLSController) pour envoyer des commandes à l’agent CLSAgent (Centralized Logging Service Agent) de l’ordinateur individuel. L’agent traite les commandes qui lui sont envoyées et (dans le cas d’une commande De démarrage) utilise la configuration des scénarios, des fournisseurs, de la durée du suivi et des indicateurs pour commencer à collecter les journaux de suivi en fonction des informations de configuration fournies.

> [!IMPORTANT]
>  Les cmdlets Windows PowerShell répertoriées pour le service de journalisation centralisée ne sont pas toutes destinées à être Skype Entreprise Server déploiements locaux en 2015. Bien qu’elles semblent fonctionner, les cmdlets suivantes ne sont pas conçues pour fonctionner avec les déploiements locaux Skype Entreprise Server 2015 :

-  **Cmdlets CsClsRegion** [: Get-CsClsRegion](/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](/powershell/module/skype/new-csclsregion?view=skype-ps) et [Remove-CsClsRegion](/powershell/module/skype/remove-csclsregion?view=skype-ps).
-  **Cmdlets CsClsSearchTerm** : [Get-CsClsSearchTerm](/powershell/module/skype/get-csclssearchterm?view=skype-ps) et [Set-CsClsSearchTerm](/powershell/module/skype/set-csclssearchterm?view=skype-ps).
-  **Cmdlets CsClsSecurityGroup** : [Get-CsClsSecurityGroup](/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](/powershell/module/skype/set-csclssecuritygroup?view=skype-ps),  [New-CsClsSecurityGroup](/powershell/module/skype/new-csclssecuritygroup?view=skype-ps) et [Remove-CsClsSecurityGroup](/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).

Les paramètres définis dans ces cmdlets n’empêchent pas ou ne provoquent aucun comportement indésirable, mais ils sont conçus pour être utilisés avec Microsoft 365 ou Office 365 et ne donnent pas les résultats attendus dans les déploiements locaux. Cela ne veut pas dire qu’il n’est pas nécessaire d’utiliser ces cmdlets dans les déploiements locaux, mais leur utilisation est un sujet plus avancé qui n’est pas abordé dans cette documentation.

Le service de journalisation centralisée peut être exécuté dans une étendue comprenant un seul ordinateur ou un pool d’ordinateurs, au niveau d’un site (autrement dit, un site défini tel que le site Redmond qui contient une collection d’ordinateurs et de pools dans votre déploiement) ou au niveau global (c’est-à-dire, tous les ordinateurs et pools de votre déploiement).

Pour configurer l’étendue du service de journalisation centralisée à l’aide de l’environnement de ligne de commande Skype Entreprise Server Management Shell, vous devez être membre des groupes de sécurité RBAC CsAdministrator ou CsServerAdministrator, ou d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes. Pour retourner la liste de tous les rôles RBAC attribués à cette cmdlet (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de l’invite Skype Entreprise Server Management Shell ou Windows PowerShell suivante :

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

Par exemple :

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Il existe des différences fondamentales entre les commandes de ligne de commande que vous pouvez exécuter dans Windows PowerShell ou CLSController. Windows PowerShell fournit une méthode enrichie pour configurer et définir des scénarios, et pour réutiliser ces scénarios de manière significative pour vos scénarios de dépannage. CLSController fournit un moyen rapide et efficace d’émettre des commandes et d’obtenir des résultats, l’ensemble de commandes pour CLSController est limité à un nombre fini de commandes disponibles à partir de la ligne de commande. Contrairement aux cmdlets Windows PowerShell, CLSController ne peut pas définir de nouveaux scénarios, gérer l’étendue au niveau global ou d’un site, ni de nombreuses autres limitations d’un jeu de commandes fini qui ne peut pas être configuré dynamiquement. Bien que CLSController offre un moyen d’une exécution rapide, Windows PowerShell permet d’étendre la fonctionnalité du service de journalisation centralisée au-delà de ce qui est possible avec CLSController.

Une étendue d’ordinateur unique peut être définie lors de l’exécution d’une commande [Search-CsClsLogging](/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](/powershell/module/skype/sync-csclslogging?view=skype-ps) et [Update-CsClsLogging](/powershell/module/skype/update-csclslogging?view=skype-ps) à l’aide du paramètre -Computers. Le paramètre -Computers accepte une liste séparée par des virgules de noms de domaine complets (FQDN) pour l’ordinateur cible.

> [!TIP]
> Vous pouvez également définir -Pools et une liste séparée par des virgules des pools sur qui vous souhaitez exécuter les commandes de journalisation.

Les étendues site et globale sont définies dans les cmdlets **New-**, **Set-**, and **Remove-** Centralized Logging Service. Les exemples suivants montrent comment définir une étendue globale ou de site.

> [!IMPORTANT]
> Les commandes indiquées peuvent contenir des paramètres et des concepts décrits dans d’autres sections. Les exemples de commandes sont destinés à démontrer l’utilisation du paramètre **-Identity** pour définir l’étendue, et les autres paramètres sont inclus pour l’intégralité et pour spécifier l’étendue. Pour plus d’informations sur les applets de commande **Set-CsClsConfiguration**, voir [Set-CsClsConfiguration](/powershell/module/skype/set-csclsconfiguration?view=skype-ps) dans la documentation des opérations.

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>Pour récupérer la configuration actuelle du service de journalisation centralisée

1. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer, sur** Tous les **programmes, sur** **Skype Entreprise 2015**, puis sur Skype Entreprise Server **Management Shell**.

2. Tapez ce qui suit à l’invite de ligne de commande :

   ```PowerShell
   Get-CsClsConfiguration
   ```

Utilisez les cmdlets **New-CsClsConfiguration** et **Set-CsClsConfiguration** pour créer une configuration ou mettre à jour une configuration existante. Lorsque vous exécutez **Get-CsClsConfiguration**, elle affiche des informations similaires à la capture d’écran suivante, où le déploiement possède actuellement la configuration globale par défaut, mais aucune configuration de site définie :

![Exemple de sortie de Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>Pour récupérer la configuration actuelle du service de journalisation centralisée à partir du magasin local de l’ordinateur

1. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer, sur** Tous les **programmes, sur** **Skype Entreprise 2015**, puis sur Skype Entreprise Server **Management Shell**.

2. Tapez ce qui suit à l’invite de ligne de commande :

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

Lorsque vous utilisez le premier exemple où **Get-CsClsConfiguration** ne spécifie aucun paramètre, la commande fait référence au magasin central de gestion pour les données. Si vous spécifiez le paramètre -LocalStore, la commande fait référence à l’ordinateur LocalStore au lieu du magasin central de gestion.
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>Pour récupérer une liste des scénarios actuellement définis

1. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer, sur** Tous les **programmes, sur** **Skype Entreprise 2015**, puis sur Skype Entreprise Server **Management Shell**.

2. Tapez ce qui suit à l’invite de ligne de commande :

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    Pour exemple, pour récupérer les scénarios définis au niveau global :

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

L’cmdlet **Get-CsClsConfiguration** affiche toujours les scénarios qui font partie de la configuration d’une étendue donnée. Dans la plupart des cas, tous les scénarios ne sont pas affichés, et sont tronqués. La commande utilisée ici répertorie tous les scénarios et des informations partielles sur les fournisseurs, les paramètres et les indicateurs utilisés.
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Pour mettre à jour une étendue globale pour le service de journalisation centralisée à l’aide Windows PowerShell

1. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer, sur** Tous les **programmes, sur** **Skype Entreprise 2015**, puis sur Skype Entreprise Server **Management Shell**.

2. Tapez ce qui suit à l’invite de ligne de commande :

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   Par exemple :

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

La commande indique au CLSAgent de chaque ordinateur et pool du déploiement de définir la valeur de substitution dans le fichier de suivi à 40 mégaoctets. Les ordinateurs et les pools de tous les sites sont affectés par cette commande, et définiront la valeur de substitution du journal de suivi configuré à 40 mégaoctets.
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Pour mettre à jour une étendue de site pour le service de journalisation centralisée à l’aide de Windows PowerShell

1. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer, sur** Tous les **programmes, sur** **Skype Entreprise 2015**, puis sur Skype Entreprise Server **Management Shell**.

2. Tapez ce qui suit à l’invite de ligne de commande :

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   Par exemple :

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> Comme indiqué dans l’exemple, l’emplacement par défaut des fichiers journaux est %TEMP%\Tracing. Cependant, dans la mesure où CLSAgent écrit dans le fichier et qu’il s’exécute en tant que service réseau, la variable %TEMP% devient %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.

Cette commande indique au CLSAgent de chaque ordinateur et pool du site Redmond de définir la taille de la valeur de substitution du fichier de suivi à 40 mégaoctets. Les ordinateurs et les pools des autres sites ne sont pas affectés par cette commande, et continueront d’utiliser la valeur de substitution du journal de suivi configurée actuellement et définie par défaut (20 mégaoctets) ou lors du démarrage de la session de journalisation.
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>Pour créer une configuration du service de journalisation centralisée

1. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer, sur** Tous les **programmes, sur** **Skype Entreprise 2015**, puis sur Skype Entreprise Server **Management Shell**.

2. Tapez ce qui suit à l’invite de ligne de commande :

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > New-CsClsConfiguration fournit un accès à de nombreux paramètres de configuration supplémentaires. Pour plus d’informations sur les options de configuration, voir [Get-CsClsConfiguration](/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Paramètres](/previous-versions/office/lync-server-2013/lync-server-2013-understanding-centralized-logging-service-configuration-settings).

Par exemple, pour créer une configuration qui définit un dossier réseau pour les fichiers en cache, la période de substitution pour les fichiers journaux et la taille de la substitution pour les fichiers journaux, tapez :

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

Vous devez soigneusement planifier la création de nouvelles configurations et la façon dont vous définissez de nouvelles propriétés pour le service de journalisation centralisée. Faites attention lorsque vous apportez des modifications et assurez-vous de bien comprendre l’impact sur la journalisation des scénarios. Apportez des modifications à la configuration pour améliorer la résolution des problèmes en permettant une meilleure gestion des tailles de journaux et de la période de substitution.
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>Pour supprimer une configuration existante du service de journalisation centralisée

1. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer, sur** Tous les **programmes, sur** **Skype Entreprise 2015**, puis sur Skype Entreprise Server **Management Shell**.

2. Tapez ce qui suit à l’invite de ligne de commande :

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

Par exemple, pour supprimer une configuration du service de journalisation centralisée que vous avez créée pour augmenter le temps de déploiement des fichiers journaux, augmentez la taille du fichier journal de rollover et définissez l’emplacement du cache des fichiers journaux sur un partage réseau comme suit :

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> Il s’agit de la nouvelle configuration qui a été créée dans la procédure « Pour créer une nouvelle configuration du service de journalisation centralisée ».

Si vous choisissez de supprimer une configuration au niveau du site, le site utilisera les paramètres globaux.
## <a name="see-also"></a>Voir aussi

[Configurer des fournisseurs pour le service de journalisation centralisée dans Skype Entreprise Server 2015](configure-providers.md)

[Configurer des scénarios pour le service de journalisation centralisée dans Skype Entreprise Server 2015](configure-scenarios.md)

[Service de journalisation centralisée Skype Entreprise 2015](centralized-logging-service.md)

[Set-CsClsConfiguration](/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[Get-CsClsConfiguration](/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[New-CsClsConfiguration](/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[Remove-CsClsConfiguration](/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)