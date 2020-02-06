---
title: Gestion des paramètres de configuration du service de journalisation centralisée dans Skype Entreprise Server 2015
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
description: 'Résumé : Découvrez comment récupérer, mettre à jour et créer des paramètres de configuration pour le service de journalisation centralisé dans Skype entreprise Server 2015.'
ms.openlocfilehash: 95aa05cfcd31acda8e78927d674f3a19dff7ef56
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816583"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>Gestion des paramètres de configuration du service de journalisation centralisée dans Skype Entreprise Server 2015

**Résumé :** Découvrez comment récupérer, mettre à jour et créer des paramètres de configuration pour le service de journalisation centralisé dans Skype entreprise Server 2015.

Le service de journalisation centralisé est contrôlé et configuré à l’aide de paramètres et de paramètres créés et utilisés par le contrôleur de service de journalisation centralisé (CLSController) pour envoyer des commandes à l’agent de service de journalisation centralisé de l’ordinateur ( CLSAgent). Lʼagent traite les commandes qui lui sont envoyées et (dans le cas dʼune commande de démarrage) utilise la configuration des scénarios, fournisseurs, durée des suivis et indicateurs pour lancer la collecte des journaux de suivi en fonction des informations de configuration fournies.

> [!IMPORTANT]
>  Les applets de connexion Windows PowerShell n’ayant pas été répertoriées pour le service de journalisation centralisée sont conçues pour une utilisation avec Skype entreprise Server 2015 de déploiement local. Même si cela semble fonctionner, les cmdlets suivantes ne sont pas conçues pour fonctionner avec les déploiements locaux de Skype entreprise Server 2015 :

-  **Cmdlets CsClsRegion :** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)et [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).
-  **Cmdlets CsClsSearchTerm :** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) et [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).
-  **Cmdlets CsClsSecurityGroup :** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps), [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)et [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).

Les paramètres définis dans ces cmdlets n’entravent pas ou risquent de provoquer un comportement indésirable, mais ils sont conçus pour une utilisation avec Microsoft Office 365 et ne produiront pas les résultats attendus dans les déploiements sur site. Ce n’est pas qu’il n’y a aucune utilisation pour ces applets de configuration dans les déploiements sur site, mais leur utilisation est un sujet plus avancé qui n’est pas abordé dans cette documentation.

Le service de journalisation centralisé peut être exécuté sur une étendue qui inclut un ordinateur unique ou un pool d’ordinateurs, à l’échelle d’un site (c’est-à-dire un site défini tel que le site Redmond contenant une collection d’ordinateurs et de pools dans votre déploiement), ou à une étendue globale (c’est-à-dire , tous les ordinateurs et pools de votre déploiement).

Pour configurer l’étendue du service de journalisation centralisé à l’aide de Skype entreprise Server Management Shell, vous devez être membre des groupes de sécurité CsAdministrator ou CsServerAdministrator de contrôle d’accès basé sur les rôles (RBAC), ou un rôle RBAC personnalisé qui contient l’un de ces deux groupes. Pour renvoyer la liste de tous les rôles RBAC attribués à cette applet de commande (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de Skype entreprise Server Management Shell ou de l’invite Windows PowerShell :

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

Par exemple :

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Il existe des différences fondamentales entre les commandes de ligne de commande que vous pouvez exécuter dans Windows PowerShell ou CLSController. Windows PowerShell fournit une méthode complète pour configurer et définir des scénarios, et pour réutiliser ces scénarios de manière significative pour vos scénarios de dépannage. CLSController fournit un moyen rapide et efficace d’émettre des commandes et d’obtenir des résultats, l’ensemble de commandes pour CLSController est limité à un nombre fini de commandes disponibles à partir de la ligne de commande. À la différence des applets de commande Windows PowerShell, CLSController ne peut pas définir de nouveaux scénarios, gérer l’étendue au niveau d’un site ou d’un niveau global et de nombreuses autres limitations d’un jeu de commandes finies qui ne peuvent pas être configurés dynamiquement. Même si CLSController fournit un moyen pour une exécution rapide, Windows PowerShell fournit un moyen d’étendre la fonctionnalité de service de journalisation centralisée en plus de ce qui est possible avec CLSController.

Il est possible de définir une étendue d’ordinateur unique lors de l’exécution d’une commande [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) et [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) à l’aide du paramètre-Computers. Le paramètre-machines accepte une liste séparée par des virgules des noms de domaine complets (FQDN) de l’ordinateur cible.

> [!TIP]
> Vous pouvez également définir des groupes et une liste séparée par des virgules des regroupements sur lesquels vous souhaitez exécuter les commandes de journalisation.

Les étendues de site et globales sont définies dans les applets de service de journalisation de **nouvelles**, de **jeu**et de **suppression** . Les exemples suivants montrent comment définir une étendue globale ou de site.

> [!IMPORTANT]
> Les commandes indiquées peuvent contenir des paramètres et des concepts décrits dans d’autres sections. Les commandes d’exemple sont conçues pour illustrer l’utilisation du paramètre **-Identity** pour définir Scope, et les autres paramètres sont inclus pour l’exhaustivité et pour spécifier l’étendue. Pour plus d’informations sur les applets de commande **Set-CsClsConfiguration**, voir  [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) dans la documentation des opérations.

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>Pour récupérer la configuration actuelle du service de journalisation centralisée

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.

2. Tapez ce qui suit à l’invite de ligne de commande :

   ```PowerShell
   Get-CsClsConfiguration
   ```

Utilisez les applets de **CsClsConfiguration** et **Set-CsClsConfiguration** pour créer une nouvelle configuration ou pour mettre à jour une configuration existante. Lorsque vous exécutez **Get-CsClsConfiguration**, il affiche des informations similaires à la capture d’écran suivante, où le déploiement dispose actuellement de la configuration globale par défaut, mais pas de configurations de site définies :

![Exemple de sortie de Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>Pour récupérer la configuration actuelle du service de journalisation centralisée dans l’emplacement local de l’ordinateur

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.

2. Tapez ce qui suit à l’invite de ligne de commande :

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

Lorsque vous utilisez le premier exemple où **Get-CsClsConfiguration** ne spécifie aucun paramètre, la commande fait référence au magasin de gestion central pour les données. Si vous spécifiez le paramètre-LocalStore, la commande fait référence au LocalStore de l’ordinateur au lieu du magasin central de gestion.
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>Pour récupérer une liste des scénarios actuellement définis

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.

2. Tapez ce qui suit à l’invite de ligne de commande :

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    Par exemple, pour récupérer les scénarios définis au niveau global :

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

Le cmdlet **Get-CsClsConfiguration** affiche toujours les scénarios qui font partie de la configuration d’une étendue donnée. Dans la plupart des cas, tous les scénarios ne sont pas affichés et sont tronqués. La commande utilisée ici répertorie tous les scénarios et des informations partielles concernant les fournisseurs, les paramètres et les indicateurs utilisés.
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Pour mettre à jour une étendue globale pour le service de journalisation centralisée à l’aide de Windows PowerShell

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.

2. Tapez ce qui suit à l’invite de ligne de commande :

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   Exemple :

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

La commande indique au CLSAgent de chaque ordinateur et pool du déploiement de définir la valeur de substitution dans le fichier de suivi à 40 mégaoctets. Les ordinateurs et les pools de tous les sites sont affectés par cette commande, et définiront la valeur de substitution du journal de suivi configuré à 40 mégaoctets.
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Pour mettre à jour l’étendue d’un site du service de journalisation centralisé à l’aide de Windows PowerShell

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.

2. Tapez ce qui suit à l’invite de ligne de commande :

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   Exemple :

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> Comme indiqué dans l’exemple, l’emplacement par défaut des fichiers journaux est %TEMP%\Tracing. Cependant, dans la mesure où CLSAgent écrit dans le fichier et qu’il s’exécute en tant que service réseau, la variable %TEMP% devient %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.

Cette commande indique au CLSAgent de chaque ordinateur et pool du site Redmond de définir la taille de la valeur de substitution du fichier de suivi à 40 mégaoctets. Les ordinateurs et les pools des autres sites ne sont pas affectés par cette commande, et continueront d’utiliser la valeur de substitution du journal de suivi configurée actuellement et définie par défaut (20 mégaoctets) ou lors du démarrage de la session de journalisation.
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>Pour créer une configuration de service de journalisation centralisée

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.

2. Tapez ce qui suit à l’invite de ligne de commande :

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > New-CsClsConfiguration permet dʼaccéder à un grand nombre de paramètres de configuration facultatifs. Pour plus d’informations sur les options de configuration, reportez-vous à la rubrique [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) et [Présentation des paramètres de configuration du service de journalisation centralisé](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).

Par exemple, pour créer une configuration qui définit un dossier réseau pour les fichiers en cache, la période de substitution pour les fichiers journaux et la taille de la substitution pour les fichiers journaux, tapez :

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

Vous devez planifier soigneusement la création de nouvelles configurations et la façon dont vous définissez de nouvelles propriétés pour le service de journalisation centralisé. Faites attention lorsque vous apportez des modifications et assurez-vous de bien comprendre l’impact sur la journalisation des scénarios. Apportez des modifications à la configuration pour améliorer la résolution des problèmes en permettant une meilleure gestion des tailles de journaux et de la période de substitution.
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>Pour supprimer une configuration de service de journalisation centralisée existante

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.

2. Tapez ce qui suit à l’invite de ligne de commande :

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

Par exemple, pour supprimer une configuration de service de journalisation centralisée que vous avez créée afin d’augmenter la durée de substitution du fichier journal, augmentez la taille du fichier journal de détournement et définissez l’emplacement du cache du fichier journal sur un partage réseau comme suit :

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> Il s’agit de la nouvelle configuration créée dans la procédure « pour créer une configuration de service de journalisation centralisée ».

Si vous choisissez de supprimer une configuration au niveau du site, le site utilisera les paramètres globaux.
## <a name="see-also"></a>Voir aussi

[Configuration des fournisseurs pour le service de journalisation centralisée dans Skype Entreprise Server 2015](configure-providers.md)

[Configuration des scénarios du service de journalisation centralisée dans Skype Entreprise Server 2015](configure-scenarios.md)

[Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md)

[Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[New-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[Remove-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
