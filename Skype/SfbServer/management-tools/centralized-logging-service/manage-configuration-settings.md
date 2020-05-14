---
title: Gérer les paramètres de configuration du service de journalisation centralisée dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: 'Résumé : Découvrez comment récupérer, mettre à jour et créer des paramètres de configuration pour le service de journalisation centralisée dans Skype entreprise Server 2015.'
ms.openlocfilehash: ed75aab211f2d2abbf0a2007fd83e5be8bb70404
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221174"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>Gérer les paramètres de configuration du service de journalisation centralisée dans Skype entreprise Server 2015

**Résumé :** Découvrez comment récupérer, mettre à jour et créer des paramètres de configuration pour le service de journalisation centralisée dans Skype entreprise Server 2015.

Le service de journalisation centralisée est contrôlé et configuré par les paramètres et les paramètres créés et utilisés par le contrôleur de service de journalisation centralisée (CLSController) pour envoyer des commandes à l’agent de service de journalisation centralisée de l’ordinateur individuel (CLSAgent). L’agent traite les commandes qui lui sont envoyées et (dans le cas d’une commande Démarrer) utilise la configuration des scénarios, des fournisseurs, de la durée du suivi et des indicateurs pour commencer à collecter des journaux de suivi en fonction des informations de configuration fournies.

> [!IMPORTANT]
>  Toutes les applets de commande Windows PowerShell répertoriées pour le service de journalisation centralisée ne sont pas conçues pour être utilisées avec des déploiements locaux de Skype entreprise Server 2015. Bien qu’ils semblent fonctionner, les cmdlets suivantes ne sont pas conçues pour fonctionner avec des déploiements locaux de Skype entreprise Server 2015 :

-  **Applets de commande CsClsRegion :** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)et [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).
-  **Applets de commande CsClsSearchTerm :** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) et [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).
-  **Applets de commande CsClsSecurityGroup :** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps), [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)et [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).

Les paramètres définis dans ces cmdlets n’entravent pas ou ne provoquent pas de comportement indésirable, mais ils sont conçus pour être utilisés avec Microsoft 365 ou Office 365 et ne produisent pas les résultats attendus dans les déploiements locaux. Cela ne signifie pas qu’il n’est pas utilisé pour ces applets de commande dans des déploiements locaux, mais leur utilisation est une rubrique plus avancée qui n’est pas abordée dans cette documentation.

Le service de journalisation centralisée peut être exécuté au niveau d’un ordinateur unique ou d’un pool d’ordinateurs, au niveau d’un site (un site défini tel que Redmond qui contient un ensemble d’ordinateurs et de pools dans votre déploiement), ou globalement (tous les ordinateurs et pools de votre déploiement).

Pour configurer l’étendue du service de journalisation centralisée à l’aide de Skype entreprise Server Management Shell, vous devez être membre des groupes de sécurité CsAdministrator ou RBAC (contrôle d’accès basé sur le rôle CsServerAdministrator), ou un rôle RBAC personnalisé qui contient l’un de ces deux groupes. Pour renvoyer la liste de tous les rôles RBAC auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de Skype for Business Server Management Shell ou de l’invite Windows PowerShell :

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

Par exemple :

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Il existe des différences fondamentales entre les commandes de ligne de commande que vous pouvez exécuter dans Windows PowerShell ou CLSController. Windows PowerShell fournit une méthode riche pour configurer et définir des scénarios, et pour réutiliser ces scénarios de manière significative pour les scénarios de dépannage. CLSController fournit un moyen rapide et efficace d’émettre des commandes et d’obtenir des résultats, l’ensemble de commandes pour CLSController est limité à un nombre fini de commandes disponibles à partir de la ligne de commande. Contrairement aux applets de commande Windows PowerShell, CLSController ne peut pas définir de nouveaux scénarios, gérer l’étendue au niveau d’un site ou d’un niveau global et de nombreuses autres limitations d’un jeu de commandes finies qui ne peuvent pas être configurés dynamiquement. Bien que CLSController offre un moyen pour une exécution rapide, Windows PowerShell permet d’étendre la fonctionnalité du service de journalisation centralisée au-delà de ce qui est possible avec CLSController.

Une seule étendue d’ordinateur peut être définie lors de l’exécution d’une commande [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) et [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) à l’aide du paramètre-Computers. Le paramètre-Computers accepte une liste de noms de domaine complets (FQDN) séparés par des virgules pour l’ordinateur cible.

> [!TIP]
> Vous pouvez également définir des pools et une liste séparée par des virgules des pools dans lesquels vous souhaitez exécuter les commandes de journalisation.

Les étendues de site et global sont définies dans les cmdlets **New-**, **Set-** et **Remove-** Centralized Logging Service. Les exemples suivants montrent comment définir une étendue globale ou de site.

> [!IMPORTANT]
> Les commandes indiquées peuvent contenir des paramètres et des concepts décrits dans d’autres sections. Les exemples de commandes sont destinés à illustrer l’utilisation du paramètre **-Identity** pour définir l’étendue, et les autres paramètres sont inclus pour des précisions et pour spécifier l’étendue. Pour plus d’informations sur les applets de commande **Set-CsClsConfiguration**, voir [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) dans la documentation des opérations.

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>Pour récupérer la configuration actuelle du service de journalisation centralisée

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise 2015**, puis sur **Skype entreprise Server Management Shell**.

2. Tapez ce qui suit à l’invite de ligne de commande :

   ```PowerShell
   Get-CsClsConfiguration
   ```

Utilisez les applets de commande **New-CsClsConfiguration** et **Set-CsClsConfiguration** pour créer une nouvelle configuration ou pour mettre à jour une configuration existante. Lorsque vous exécutez **Get-CsClsConfiguration**, il affiche des informations similaires à la capture d’écran suivante, dans laquelle le déploiement dispose actuellement de la configuration globale par défaut, mais aucune configuration de site n’est définie :

![Exemple de sortie de Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>Pour récupérer la configuration actuelle du service de journalisation centralisée dans le magasin local de l’ordinateur

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise 2015**, puis sur **Skype entreprise Server Management Shell**.

2. Tapez ce qui suit à l’invite de ligne de commande :

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

Lorsque vous utilisez le premier exemple où **Get-CsClsConfiguration** ne spécifie aucun paramètre, la commande fait référence au magasin central de gestion pour les données. Si vous spécifiez le paramètre-LocalStore, la commande fait référence à l’ordinateur LocalStore à la place du magasin central de gestion.
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>Pour récupérer une liste des scénarios actuellement définis

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise 2015**, puis sur **Skype entreprise Server Management Shell**.

2. Tapez ce qui suit à l’invite de ligne de commande :

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    Pour exemple, pour récupérer les scénarios définis au niveau global :

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

L’applet de commande **Get-CsClsConfiguration** affiche toujours les scénarios qui font partie de la configuration d’une étendue donnée. Dans la plupart des cas, tous les scénarios ne sont pas affichés, et sont tronqués. La commande utilisée ici répertorie tous les scénarios et des informations partielles sur les fournisseurs, les paramètres et les indicateurs utilisés.
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Pour mettre à jour une étendue globale pour le service de journalisation centralisée à l’aide de Windows PowerShell

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise 2015**, puis sur **Skype entreprise Server Management Shell**.

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

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise 2015**, puis sur **Skype entreprise Server Management Shell**.

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
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>Pour créer une nouvelle configuration de service de journalisation centralisée

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise 2015**, puis sur **Skype entreprise Server Management Shell**.

2. Tapez ce qui suit à l’invite de ligne de commande :

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > New-CsClsConfiguration fournit un accès à de nombreux paramètres de configuration supplémentaires. Pour plus d’informations sur les options de configuration, voir [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) et [Understanding Centralized Logging Service Configuration Settings](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).

Par exemple, pour créer une configuration qui définit un dossier réseau pour les fichiers en cache, la période de substitution pour les fichiers journaux et la taille de la substitution pour les fichiers journaux, tapez :

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

Vous devez planifier avec soin la création de nouvelles configurations et la définition de nouvelles propriétés pour le service de journalisation centralisée. Faites attention lorsque vous apportez des modifications et assurez-vous de bien comprendre l’impact sur la journalisation des scénarios. Apportez des modifications à la configuration pour améliorer la résolution des problèmes en permettant une meilleure gestion des tailles de journaux et de la période de substitution.
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>Pour supprimer une configuration de service de journalisation centralisée existante

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise 2015**, puis sur **Skype entreprise Server Management Shell**.

2. Tapez ce qui suit à l’invite de ligne de commande :

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

Par exemple, pour supprimer une configuration de service de journalisation centralisée que vous avez créée pour augmenter le temps de substitution du fichier journal, augmentez la taille du fichier journal de survol et définissez l’emplacement du cache du fichier journal sur un partage réseau comme suit :

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> Il s’agit de la nouvelle configuration qui a été créée dans la procédure « pour créer une nouvelle configuration de service de journalisation centralisée ».

Si vous choisissez de supprimer une configuration au niveau du site, le site utilisera les paramètres globaux.
## <a name="see-also"></a>Voir aussi

[Configurer des fournisseurs pour le service de journalisation centralisée dans Skype entreprise Server 2015](configure-providers.md)

[Configuration des scénarios pour le service de journalisation centralisée dans Skype entreprise Server 2015](configure-scenarios.md)

[Service de journalisation centralisée dans Skype entreprise 2015](centralized-logging-service.md)

[Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[New-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[Remove-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
