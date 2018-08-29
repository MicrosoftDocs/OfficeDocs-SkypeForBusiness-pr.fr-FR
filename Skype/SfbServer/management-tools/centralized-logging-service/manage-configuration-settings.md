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
ms.openlocfilehash: 163ac9607e3b690aac2f069c38e967692721d819
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23253117"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>Gestion des paramètres de configuration du service de journalisation centralisée dans Skype Entreprise Server 2015

**Résumé :** Découvrez comment récupérer, mettre à jour et créer des paramètres de configuration pour le Service de journalisation centralisée dans Skype pour Business Server 2015.

Le Service de journalisation centralisée est contrôlé et configuré par les paramètres et les paramètres qui sont créés et utilisés par le Centralized Logging Service contrôleur (CLSController) pour envoyer des commandes à Agent du Service de journalisation centralisée (l’ordinateur individuel Et CLSAgent). Lʼagent traite les commandes qui lui sont envoyées et (dans le cas dʼune commande de démarrage) utilise la configuration des scénarios, fournisseurs, durée des suivis et indicateurs pour lancer la collecte des journaux de suivi en fonction des informations de configuration fournies.

> [!IMPORTANT]
>  Pas toutes les applets de commande Windows PowerShell indiqués pour le Service de journalisation centralisée sont conçus pour une utilisation avec Skype pour les déploiements sur site Business Server 2015. Bien qu’ils semblent fonctionner correctement, les cmdlets suivantes ne sont pas conçus pour fonctionner avec Skype pour les déploiements sur site Business Server 2015 :

-  **Cmdlets CsClsRegion :** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)et [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).
-  **Cmdlets CsClsSearchTerm :** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) et [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).
-  **Cmdlets CsClsSecurityGroup :** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps), [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)et [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).

Les paramètres définis dans ces applets de commande ne seront pas entraver ou entraîner un comportement indésirable, mais ils sont conçus pour une utilisation avec Microsoft Office 365 et produisent pas les résultats attendus dans les déploiements sur site. Cela ne signifie ne pas que n’est pas pour ces applets de commande dans les déploiements sur site, mais leur utilisation est une rubrique plus avancée qui n’est pas abordée dans cette documentation.

Le Service de journalisation centralisée peut être exécuté dans une étendue qui inclut un ordinateur unique ou un pool d’ordinateurs, à une étendue de site (autrement dit, un site défini tel que le site de Redmond qui constituée une collection d’ordinateur et les pools de votre déploiement) ou une étendue globale (c'est-à-dire tous les ordinateurs et pools de votre déploiement).

Pour configurer l’étendue du Service de journalisation centralisée à l’aide de la Skype pour Business Server Management Shell, vous devez être un membre de la CsAdministrator ou les groupes de sécurité CsServerAdministrator accès basé sur un rôle RBAC (contrôle) ou un rôle RBAC personnalisé qui contient une de ces deux groupes. Pour retourner une liste de tous les rôles RBAC que cette applet de commande a été assigné à (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de la Skype Business Server Management Shell ou de l’invite de Windows PowerShell :

```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

Par exemple :

```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Il existe des différences fondamentales entre les commandes de ligne de commande que vous pouvez exécuter Windows PowerShell ou CLSController. Windows PowerShell fournit une méthode riche pour configurer et définir des scénarios et réutiliser les scénarios de manière explicite pour vos scénarios de dépannage. CLSController fournit un moyen rapide et efficace d’émettre des commandes et d’obtenir des résultats, l’ensemble de commandes pour CLSController est limité à un nombre fini de commandes disponibles à partir de la ligne de commande. Contrairement aux applets de commande Windows PowerShell, CLSController ne peut pas définir de nouveaux scénarios, gérer étendue à un site ou au niveau global et plusieurs autres limitations d’un ensemble limité de commande ne pouvant être configurés de façon dynamique. Alors que CLSController fournit un moyen pour une exécution rapide, Windows PowerShell fournit un moyen d’étendre les fonctionnalités du Service de journalisation centralisée au-delà de ce qui est possible avec CLSController.

Une étendue d’ordinateur unique peut être définie lors de l’exécution de [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) et [- CsClsLogging mise à jour](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) à l’aide de la commande-paramètre Computers. -Ordinateurs paramètre accepte une liste séparée par des virgules des noms de domaine complet (FQDN) pour l’ordinateur cible.

> [!TIP]
> Vous pouvez également définir - Pools et une liste séparée par des virgules des pools que vous souhaitez exécuter les commandes de journalisation sur.

Site et Global étendues sont définies dans les applets de commande **New -**, **Set -** et **Remove -** Centralized Logging Service. Les exemples suivants montrent comment définir une étendue globale ou de site.

> [!IMPORTANT]
> Les commandes indiquées peuvent contenir des paramètres et des concepts décrits dans d’autres sections. Les exemples de commandes visent à illustrer l’utilisation de la **-Identity** paramètre pour définir l’étendue et les autres paramètres figurent par souci d’intégralité et spécifier l’étendue. Pour plus d’informations sur les applets de commande **Set-CsClsConfiguration** , voir [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) dans la documentation des opérations.

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>Pour récupérer la configuration actuelle du Service de journalisation centralisée

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.

2. Tapez ce qui suit à l’invite de ligne de commande :

  ```
  Get-CsClsConfiguration
  ```

Utilisez les applets de commande **New-CsClsConfiguration** et **Set-CsClsConfiguration** pour créer une nouvelle configuration ou mettre à jour une configuration existante. Lorsque vous exécutez **Get-CsClsConfiguration**, il affiche des informations similaires à l’écran suivant, où le déploiement a actuellement la configuration globale par défaut, mais aucune configuration de site :

![Exemple de sortie de Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>Pour récupérer la configuration du Service de journalisation centralisée actuelle à partir du magasin de l’ordinateur local

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.

2. Tapez ce qui suit à l’invite de ligne de commande :

  ```
  Get-CsClsConfiguration -LocalStore
  ```

Lorsque vous utilisez le premier exemple où **Get-CsClsConfiguration** ne spécifie pas tous les paramètres, les références de commande du magasin Central de gestion des données. Si vous spécifiez le paramètre - LocalStore, la commande fait référence à l’ordinateur LocalStore au lieu du magasin Central de gestion.
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
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>Pour créer une nouvelle configuration de Service de journalisation centralisée

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.

2. Tapez ce qui suit à l’invite de ligne de commande :

  ```
  New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
  ```

    > [!NOTE]
    > New-CsClsConfiguration permet dʼaccéder à un grand nombre de paramètres de configuration facultatifs. Pour plus d’informations sur les options de configuration, voir [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) et [Présentation centralisée Logging Service de paramètres de Configuration](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).

Par exemple, pour créer une configuration qui définit un dossier réseau pour les fichiers en cache, la période de substitution pour les fichiers journaux et la taille de la substitution pour les fichiers journaux, tapez :

  ```
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

Vous devez planifier avec soin la création de nouvelles configurations et comment définir de nouvelles propriétés pour le Service de journalisation centralisée. Faites attention lorsque vous apportez des modifications et assurez-vous de bien comprendre l’impact sur la journalisation des scénarios. Apportez des modifications à la configuration pour améliorer la résolution des problèmes en permettant une meilleure gestion des tailles de journaux et de la période de substitution.
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>Pour supprimer une configuration existante de Service de journalisation centralisée

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.

2. Tapez ce qui suit à l’invite de ligne de commande :

  ```
  Remove-CsClsConfiguration -Identity <scope and name>
  ```

Par exemple, pour supprimer une configuration de Service de journalisation centralisée que vous avez créé pour augmenter le temps de substitution du fichier journal, augmentez la taille du fichier journal survol et définissez l’emplacement du cache du fichier journal sur un partage réseau comme suit :

  ```
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> Il s’agit de la nouvelle configuration a été créée dans la procédure « pour créer une nouvelle configuration de Service de journalisation centralisée ».

Si vous choisissez de supprimer une configuration au niveau du site, le site utilisera les paramètres globaux.
## <a name="see-also"></a>Voir aussi

[Configuration des fournisseurs pour le service de journalisation centralisée dans Skype Entreprise Server 2015](configure-providers.md)

[Configuration des scénarios du service de journalisation centralisée dans Skype Entreprise Server 2015](configure-scenarios.md)

[Service de journalisation centralisée pour Skype Entreprise 2015](centralized-logging-service.md)

[Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[New-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[Remove-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)