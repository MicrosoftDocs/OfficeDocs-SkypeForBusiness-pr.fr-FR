---
title: "Gest. conf. du serv. de journ. Centr. au niv. d’un ordi., site ou au niv. gl."
TOCtitle: "Gest. conf. du serv. de journ. Centr. au niv. d’un ordi., site ou au niv. gl."
ms:assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688138(v=OCS.15)
ms:contentKeyID: 49891449
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Gestion de la configuration du service de journalisation centralisée au niveau d’un ordinateur, d’un site ou au niveau global

 

_**Dernière rubrique modifiée :** 2014-02-04_

Le service de journalisation centralisée peut être exécuté au niveau d’un ordinateur, d’un pool d’ordinateurs, d’un site (un site défini tel que Redmond qui contient un ensemble d’ordinateurs et de pools dans votre déploiement), ou globalement (tous les ordinateurs et pools de votre déploiement).

Pour configurer l’étendue du service de journalisation centralisée en utilisant Lync Server Management Shell, vous devez être membre des groupes de sécurité de rôle de contrôle d’accès en fonction du rôle (RBAC) CsAdministrator ou CsServerAdministrator ou d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes. Pour retourner une liste de tous les rôles RBAC auxquels cette applet de commande a été assignée (y compris les rôles RBAC personnalisés que vous avez créés), exécutez la commande suivante à l’invite Lync Server Management Shell ou Windows PowerShell :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

Par exemple :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

> [!NOTE]  
> Windows PowerShell fournit davantage d’options et d’options de configuration qui ne sont pas disponibles en utilisant CLSController.exe. CLSController offre une méthode rapide et concise pour exécuter des commandes, mais l’ensemble de commandes disponibles pour CLSController est limité. Windows PowerShell n’est pas limité aux commandes disponibles au processeur de commandes de CLSController, et fournit un large éventail de commandes et des options supplémentaires. Par exemple, CLSController.exe fournit des options d’étendue pour les ordinateurs et les pools. Avec Windows PowerShell, vous pouvez indiquer les ordinateurs et les pools dans la plupart des commandes, et quand vous définissez de nouveaux scénarios (CLSController dispose d’un nombre fini de scénarios qui ne sont pas modifiables par l’utilisateur) vous pouvez définir une étendue de site ou globale. Cette fonctionnalité puissante de Windows PowerShell vous permet de définir un scénario au niveau global ou du site, mais limite la journalisation réelle à un ordinateur ou un pool.<br />
Il existe des différences fondamentales entre les commandes en ligne de commande que vous exécutez dans Windows PowerShell ou CLSController. Windows PowerShell permet de configurer et de définir des scénarios avec plus d’options, et de réutiliser ces scénarios pour le dépannage. CLSController fournit un moyen rapide et efficace d’émettre des commandes et d’obtenir des résultats, l’ensemble de commandes pour CLSController est limité à un nombre fini de commandes disponibles à partir de la ligne de commande. À la différence des applets de commande Windows PowerShell, CLSController ne peut pas définir de nouveaux scénarios ou gérer l’étendue au niveau global ou d’un site et son ensemble de commandes fini ne peut pas être configuré dynamiquement. Bien que CLSController permette une exécution rapide, Windows PowerShell permet d’étendre la fonctionnalité du service de journalisation centralisée bien au-delà de ce qu’il est possible de faire avec CLSController.

Une étendue d’ordinateur peut être définie lors de l’exécution d’une commande [Search-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Search-CsClsLogging), [Show-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Show-CsClsLogging), [Start-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Start-CsClsLogging), [Stop-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Stop-CsClsLogging), [Sync-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Sync-CsClsLogging) et [Update-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Update-CsClsLogging) avec le paramètre –Computers. Le paramètre –Computers accepte une liste de noms de domaine complets séparés par des virgules pour l’ordinateur cible.

> [!TIP]  
> Vous pouvez également définir –Pools et une liste de pools séparée par des virgules sur laquelle exécuter les commandes de journalisation.

Les étendues globale et de site sont définies dans les applets de commande **New-**, **Set-** et **Remove-**service de journalisation centralisée. Les exemples suivants montrent comment définir une étendue globale ou de site.

> [!IMPORTANT]  
> Les commandes indiquées peuvent contenir des paramètres et des concepts décrits dans d’autres sections. Les exemples de commandes sont conçus pour décrire l’utilisation du paramètre <strong>–Identity</strong> pour définir l’étendue, et les autres paramètres sont inclus pour être exhaustif et pour spécifier l’étendue. Pour plus d’informations sur les applets de commande <strong>Set-CsClsConfiguration</strong>, voir <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsConfiguration">Set-CsClsConfiguration</a> dans la documentation des opérations.

## Pour récupérer la configuration du service de journalisation centralisée actuelle

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Tapez ce qui suit à l’invite de ligne de commande :
    
        Get-CsClsConfiguration

Utilisez les applets de commande **New-CsClsConfiguration** et **Set-CsClsConfiguration** pour créer une nouvelle configuration ou pour mettre à jour une configuration existante.

Quand vous exécutez **Get-CsClsConfiguration**, elle affiche des informations identiques à celles présentées dans la capture suivante, quand le déploiement utilise la configuration globale par défaut, sans configuration de site :

![Exemple de sortie de Get-CsClsConfiguration.](images/JJ688138.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Exemple de sortie de Get-CsClsConfiguration.")

## Pour récupérer la configuration du service de journalisation centralisée actuelle du magasin local de l’ordinateur

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Tapez ce qui suit à l’invite de ligne de commande :
    
        Get-CsClsConfiguration -LocalStore

Quand vous utilisez le premier exemple dans lequel **Get-CsClsConfiguration** ne spécifie aucun paramètre, la commande référence le magasin central de gestion pour les données. Si vous spécifiez le paramètre –LocalStore, la commande référence l’ordinateur LocalStore à la place du magasin central de gestion.

## Pour récupérer une liste des scénarios actuellement définis

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Tapez ce qui suit à l’invite de ligne de commande :
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    Pour exemple, pour récupérer les scénarios définis au niveau global :
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

L’applet de commande **Get-CsClsConfiguration** affiche toujours les scénarios qui font partie d’une configuration donnée. Dans la plupart des cas, tous les scénarios ne sont pas affichés, et sont tronqués. La commande utilisée ici répertorie tous les scénarios et des informations partielles sur les fournisseurs, les paramètres et les indicateurs utilisés.

## Pour mettre à jour une étendue globale pour le service de journalisation centralisée en utilisant Windows PowerShell

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Tapez ce qui suit à l’invite de ligne de commande :
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    Par exemple :
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

La commande indique au CLSAgent de chaque ordinateur et pool du déploiement de définir la valeur de substitution dans le fichier de suivi à 40 mégaoctets. Les ordinateurs et les pools de tous les sites sont affectés par cette commande, et définiront la valeur de substitution du journal de suivi configuré à 40 mégaoctets.

## Pour mettre à jour une étendue de site pour le service de journalisation centralisée en utilisant Windows PowerShell

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Tapez ce qui suit à l’invite de ligne de commande :
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    Par exemple :
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    > [!NOTE]  
    > Comme indiqué dans l’exemple, l’emplacement par défaut des fichiers journaux est %TEMP%\Tracing. Cependant, dans la mesure où CLSAgent écrit dans le fichier et qu’il s’exécute en tant que service réseau, la variable %TEMP% devient %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.

Cette commande indique au CLSAgent de chaque ordinateur et pool du site Redmond de définir la taille de la valeur de substitution du fichier de suivi à 40 mégaoctets. Les ordinateurs et les pools des autres sites ne sont pas affectés par cette commande, et continueront d’utiliser la valeur de substitution du journal de suivi configurée actuellement et définie par défaut (20 mégaoctets) ou lors du démarrage de la session de journalisation.

## Pour créer une nouvelle configuration du service de journalisation centralisée

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Tapez ce qui suit à l’invite de ligne de commande :
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    > [!NOTE]  
    > New-CsClsConfiguration fournit un accès à de nombreux paramètres de configuration supplémentaires. Pour plus d’informations sur les options de configuration, voir <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsConfiguration">Get-CsClsConfiguration</a> et <a href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Présentation des paramètres de configuration du service de journalisation centralisée</a>.    
    
    
    Par exemple, pour créer une configuration qui définit un dossier réseau pour les fichiers en cache, la période de substitution pour les fichiers journaux et la taille de la substitution pour les fichiers journaux, tapez :
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

Préparez soigneusement la création de configurations et la définition des nouvelles propriétés pour le service de journalisation centralisée. Faites attention lorsque vous apportez des modifications et assurez-vous de bien comprendre l’impact sur la journalisation des scénarios. Apportez des modifications à la configuration pour améliorer la résolution des problèmes en permettant une meilleure gestion des tailles de journaux et de la période de substitution.

## Pour supprimer une configuration du service de journalisation centralisée existante

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Tapez ce qui suit à l’invite de ligne de commande :
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    Par exemple, pour supprimer une configuration du service de journalisation centralisée que vous avez créée afin d’améliorer le temps de substitution du fichier journal, augmentez la taille du fichier journal de substitution, et définissez l’emplacement de mise en cache du fichier journal sur un partage réseau comme suit :
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    > [!NOTE]  
    > Il s’agit de la nouvelle créée dans la procédure « Pour créer une nouvelle configuration du service de journalisation centralisée ».

Si vous choisissez de supprimer une configuration au niveau du site, le site utilisera les paramètres globaux.

## Voir aussi

#### Concepts

[Présentation du service de journalisation centralisée](lync-server-2013-overview-of-the-centralized-logging-service.md)  

#### Autres ressources

[Gestion des paramètres de configuration du service de journalisation centralisée à l’aide de PowerShell](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
[Set-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsConfiguration)  
[Get-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsConfiguration)  
[New-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsConfiguration)  
[Remove-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClsConfiguration)

