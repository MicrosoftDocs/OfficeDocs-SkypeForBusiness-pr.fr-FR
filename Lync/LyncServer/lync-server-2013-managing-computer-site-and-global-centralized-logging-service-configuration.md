---
title: Gestion de la configuration de l’ordinateur, du site et du service de journalisation centralisée
description: La gestion de la configuration de l’ordinateur, du site et du service de journalisation centralisée.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing computer, site and global Centralized Logging Service configuration
ms:assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688138(v=OCS.15)
ms:contentKeyID: 49733738
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37dee125d69e17664fddd0c32feb3048ffcf91b5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570380"
---
# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a>Gestion de la configuration de l’ordinateur, du site et du service de journalisation centralisée dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-04_

Le service de journalisation centralisée peut être exécuté au niveau d’un ordinateur, d’un pool d’ordinateurs, d’un site (un site défini tel que Redmond qui contient un ensemble d’ordinateurs et de pools dans votre déploiement), ou globalement (c’est-à-dire tous les ordinateurs et pools de votre déploiement).

Pour configurer l’étendue du service de journalisation centralisée à l’aide de Lync Server Management Shell, vous devez être membre des groupes de sécurité CsAdministrator ou RBAC (contrôle d’accès basé sur un rôle CsServerAdministrator), ou d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes. Pour renvoyer la liste de tous les rôles RBAC auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de Lync Server Management Shell ou de l’invite Windows PowerShell :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

Par exemple :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> Windows PowerShell fournit des options supplémentaires et des options de configuration supplémentaires qui ne sont pas disponibles à l’aide de CLSController.exe. CLSController offre une méthode rapide et concise pour exécuter des commandes, mais l’ensemble de commandes disponibles pour CLSController est limité. Windows PowerShell n’est pas limité à la seule commande disponible pour le processeur de commandes du CLSController, et fournit un ensemble plus large de commandes et un ensemble d’options plus riche. Par exemple, CLSController.exe fournit des options d’étendue pour les ordinateurs et les pools. Avec Windows PowerShell, vous pouvez indiquer des ordinateurs ou des pools dans la plupart des commandes, et lorsque vous définissez de nouveaux scénarios (CLSController dispose d’un nombre limité de scénarios qui ne peuvent pas être modifiés par l’utilisateur), vous pouvez définir un site ou une étendue globale. Cette fonctionnalité puissante de Windows PowerShell vous permet de définir un scénario de site ou une étendue globale, mais de limiter la journalisation réelle à un ordinateur ou un pool.<BR>Il existe des différences fondamentales entre les commandes de ligne de commande que vous pouvez exécuter dans Windows PowerShell ou CLSController. Windows PowerShell fournit une méthode riche pour configurer et définir des scénarios, et pour réutiliser ces scénarios de manière significative pour les scénarios de dépannage. CLSController fournit un moyen rapide et efficace d’émettre des commandes et d’obtenir des résultats, l’ensemble de commandes pour CLSController est limité à un nombre fini de commandes disponibles à partir de la ligne de commande. Contrairement aux applets de commande Windows PowerShell, CLSController ne peut pas définir de nouveaux scénarios, gérer l’étendue au niveau d’un site ou d’un niveau global et de nombreuses autres limitations d’un jeu de commandes finies qui ne peuvent pas être configurés dynamiquement. Bien que CLSController offre un moyen pour une exécution rapide, Windows PowerShell permet d’étendre la fonctionnalité du service de journalisation centralisée au-delà de ce qui est possible avec CLSController.



</div>

Une seule étendue d’ordinateur peut être définie lors de l’exécution d’une commande [Search-CsClsLogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15)), [Show-CsClsLogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15)), [Start-CsClsLogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15)), [Stop-CsClsLogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15)), [Sync-CsClsLogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15)) et [Update-CsClsLogging](https://technet.microsoft.com/library/JJ619170(v=OCS.15)) à l’aide du paramètre – Computers. Le paramètre –Computers accepte une liste de noms de domaine complets séparée par des virgules pour l’ordinateur cible.

<div>


> [!TIP]
> Vous pouvez également définir –Pools et une liste de pools séparée par des virgules sur laquelle exécuter les commandes de journalisation.



</div>

Les étendues de site et global sont définies dans les cmdlets **New-**, **Set-** et **Remove-** Centralized Logging Service. Les exemples suivants montrent comment définir une étendue globale ou de site.

<div>


> [!IMPORTANT]
> Les commandes indiquées peuvent contenir des paramètres et des concepts décrits dans d’autres sections. Les exemples de commandes sont conçus pour décrire l’utilisation du paramètre <STRONG>–Identity</STRONG> pour définir l’étendue, et les autres paramètres sont inclus pour être exhaustif et pour spécifier l’étendue. Pour plus d’informations sur les applets de commande <STRONG>Set-CsClsConfiguration</STRONG>, voir <A href="https://technet.microsoft.com/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A> dans la documentation des opérations.



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>Pour récupérer la configuration actuelle du service de journalisation centralisée

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Tapez ce qui suit à l’invite de ligne de commande :
    
        Get-CsClsConfiguration

Utilisez les applets de commande **New-CsClsConfiguration** et **Set-CsClsConfiguration** pour créer une nouvelle configuration ou pour mettre à jour une configuration existante.

Lorsque vous exécutez **Get-CsClsConfiguration**, il affiche des informations similaires à la capture d’écran suivante, dans laquelle le déploiement dispose actuellement de la configuration globale par défaut, mais aucune configuration de site n’est définie :

![Exemple de sortie de Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Exemple de sortie de Get-CsClsConfiguration.")

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>Pour récupérer la configuration actuelle du service de journalisation centralisée dans le magasin local de l’ordinateur

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Tapez ce qui suit à l’invite de ligne de commande :
    
        Get-CsClsConfiguration -LocalStore

Lorsque vous utilisez le premier exemple où **Get-CsClsConfiguration** ne spécifie aucun paramètre, la commande fait référence au magasin central de gestion pour les données. Si vous spécifiez le paramètre – LocalStore, la commande fait référence à l’ordinateur LocalStore à la place du magasin central de gestion.

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>Pour récupérer une liste des scénarios actuellement définis

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Tapez ce qui suit à l’invite de ligne de commande :
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    Pour exemple, pour récupérer les scénarios définis au niveau global :
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

L’applet de commande **Get-CsClsConfiguration** affiche toujours les scénarios qui font partie d’une configuration donnée. Dans la plupart des cas, tous les scénarios ne sont pas affichés, et sont tronqués. La commande utilisée ici répertorie tous les scénarios et des informations partielles sur les fournisseurs, les paramètres et les indicateurs utilisés.

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Pour mettre à jour une étendue globale pour le service de journalisation centralisée à l’aide de Windows PowerShell

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Tapez ce qui suit à l’invite de ligne de commande :
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    Par exemple :
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

La commande indique au CLSAgent de chaque ordinateur et pool du déploiement de définir la valeur de substitution dans le fichier de suivi à 40 mégaoctets. Les ordinateurs et les pools de tous les sites sont affectés par cette commande, et définiront la valeur de substitution du journal de suivi configuré à 40 mégaoctets.

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Pour mettre à jour une étendue de site pour le service de journalisation centralisée à l’aide de Windows PowerShell

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Tapez ce qui suit à l’invite de ligne de commande :
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    Par exemple :
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > Comme indiqué dans l’exemple, l’emplacement par défaut des fichiers journaux est %TEMP%\Tracing. Cependant, dans la mesure où CLSAgent écrit dans le fichier et qu’il s’exécute en tant que service réseau, la variable %TEMP% devient %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.

    
    </div>

Cette commande indique au CLSAgent de chaque ordinateur et pool du site Redmond de définir la taille de la valeur de substitution du fichier de suivi à 40 mégaoctets. Les ordinateurs et les pools des autres sites ne sont pas affectés par cette commande, et continueront d’utiliser la valeur de substitution du journal de suivi configurée actuellement et définie par défaut (20 mégaoctets) ou lors du démarrage de la session de journalisation.

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a>Pour créer une nouvelle configuration de service de journalisation centralisée

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Tapez ce qui suit à l’invite de ligne de commande :
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > New-CsClsConfiguration fournit un accès à de nombreux paramètres de configuration supplémentaires. Pour plus d’informations sur les options de configuration, voir <A href="https://technet.microsoft.com/library/JJ619179(v=OCS.15)">Get-CsClsConfiguration</A> et <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Présentation des paramètres de configuration du service de journalisation centralisée dans Lync Server 2013</A>.

    
    </div>
    
    Par exemple, pour créer une configuration qui définit un dossier réseau pour les fichiers en cache, la période de substitution pour les fichiers journaux et la taille de la substitution pour les fichiers journaux, tapez :
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

Vous devez planifier avec soin la création de nouvelles configurations et la définition de nouvelles propriétés pour le service de journalisation centralisée. Faites attention lorsque vous apportez des modifications et assurez-vous de bien comprendre l’impact sur la journalisation des scénarios. Apportez des modifications à la configuration pour améliorer la résolution des problèmes en permettant une meilleure gestion des tailles de journaux et de la période de substitution.

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>Pour supprimer une configuration de service de journalisation centralisée existante

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Tapez ce qui suit à l’invite de ligne de commande :
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    Par exemple, pour supprimer une configuration de service de journalisation centralisée que vous avez créée pour augmenter le temps de substitution du fichier journal, augmentez la taille du fichier journal de survol et définissez l’emplacement du cache du fichier journal sur un partage réseau comme suit :
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > Il s’agit de la nouvelle configuration qui a été créée dans la procédure « pour créer une nouvelle configuration de service de journalisation centralisée ».

    
    </div>

Si vous choisissez de supprimer une configuration au niveau du site, le site utilisera les paramètres globaux.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Vue d’ensemble du service de journalisation centralisée dans Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Gestion des paramètres de configuration du service de journalisation centralisée dans Lync Server 2013](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))  
[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))  
[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))  
[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

