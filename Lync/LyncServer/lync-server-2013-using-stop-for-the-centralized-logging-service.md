---
title: Utilisation de la commande Stop pour le service de journalisation centralisée
TOCTitle: Utilisation de la commande Stop pour le service de journalisation centralisée
ms:assetid: 09ac093e-8f30-4874-84b4-12548ac8c898
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ687964(v=OCS.15)
ms:contentKeyID: 49891225
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Utilisation de la commande Stop pour le service de journalisation centralisée

 

_**Dernière rubrique modifiée :** 2012-11-01_

Vous pouvez arrêter une session de journalisation en cours avec l’applet de commande Stop-CsClsLogging. En général, vous rencontrerez peu de situations vous obligeant à arrêter une session de journalisation. Par exemple, vous pouvez faire des recherches dans les journaux et modifier des configurations sans devoir arrêter d’abord la journalisation. Si deux scénarios sont en cours d’exécution, par exemple AlwaysOn et UserReplicator, alors que vous devez recueillir des informations relatives à l’authentification, vous devez arrêter un de ces deux scénarios (au niveau global, du site, du pool ou de l’ordinateur) avant de pouvoir lancer l’exécution du scénario d’authentification. Pour plus d’informations, voir [Stop-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Stop-CsClsLogging).

> [!NOTE]  
> Lorsque vous souhaitez déterminer les scénarios que vous pouvez exécuter sur un déploiement, un pool ou un ordinateur donné, gardez à l’esprit que vous ne pouvez exécuter que deux scénarios <strong>par ordinateur</strong>. Si vous procédez à la journalisation de l’activité d’un pool, vous devez traiter ce pool globalement. Dans la plupart des cas, il n’est pas judicieux d’exécuter différents scénarios sur chaque ordinateur dans un pool. Il n’est pas non plus logique d’examiner le problème pour lequel vous recherchez des données et vous demander alors quel scénario convient le mieux pour un ordinateur donné dans le déploiement entier. Par exemple, si vous envisagez d’utiliser le scénario UserReplicator, exécuter UserReplicator sur un serveur Edge ou un pool de serveurs Edge ne sert pas à grand chose.<br />
Une fois que vous avez compris l’origine du problème et avez déterminé son impact, vous devez choisir soigneusement les scénarios à exécuter sur quels ordinateurs et pools. Bien qu’il soit judicieux d’exécuter le scénario AlwaysOn pour une application large, car il recueille des informations sur une grande variété de fournisseurs, certains scénarios ne sont utiles que sur certains ordinateurs ou pools. De plus, lorsque vous lancez une session de journalisation vous devez choisir au préalable le scénario offrant les meilleurs résultats. Si vous utilisez un scénario inapproprié, ou si vous utilisez un scénario qui est approprié pour la tâche mais pas adapté au niveau d’application envisagé (global, site, pool ou ordinateur), vous risquez d’obtenir des données inutiles, comme si vous n’aviez pas exécuté de scénario du tout.

Pour contrôler les fonctions du service de journalisation centralisée à l’aide de Lync Server Management Shell, vous devez être membre de l’un des groupes de sécurité RBAC (Contrôle d’accès basé sur un rôle), CsAdministrator et CsServerAdministrator, ou d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes. Pour obtenir une liste de tous les rôles RBAC auxquels cette applet de commande a été affectée (notamment des rôles RBAC personnalisés que vous avez créés), exécutez la commande suivante à partir de l’invite de Lync Server Management Shell ou de Windows PowerShell :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Par exemple :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

## Pour arrêter une session du service de journalisation centralisée en cours

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Demandez au service de journalisation centralisée de détecter quels scénarios sont exécutés en tapant ce qui suit :
    
        Show-CsClsLogging
    
    ![Console Windows PowerShell après appel de Show-CsCl](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Console Windows PowerShell après appel de Show-CsCl")
    
    Le résultat de Show-CsClsLogging est un résumé des scénarios en cours d’exécution et de leur étendue d’application. Pour plus d’informations, voir [Show-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Show-CsClsLogging).

3.  Pour arrêter une session de journalisation en cours avec un scénario spécifique, tapez :
    
        Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
    
    Par exemple :
    
        Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
    
    Cette commande arrête la journalisation avec le scénario UserReplicatior sur pool01.contoso.net.
    
    > [!NOTE]  
    > Les journaux créés au cours de cette session de journalisation avec le scénario UserReplicator ne sont pas supprimés. Vous pouvez continuer à effectuer des recherches avec la journalisation au lieu d’utiliser la commande Search-CsClsLogging. Pour plus d’informations, voir <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</a>.

Faisant pendant à l’applet de commande Start-CsClsLogging, l’applet de commande Stop-CsClsLogging arrête la session de journalisation, définie par des scénarios, et conserve les journaux créés par celle-ci. Vous pouvez exécuter deux scénarios sur un ordinateur donné à tout moment. La méthode d’arrêt d’un scénario pour recueillir des informations à l’aide d’un autre scénario est une tâche courante que vous pouvez effectuer au cours du dépannage de la plupart des charges de travail.

## Voir aussi

#### Tâches

[Utilisation de la commande Start pour la capture des journaux par le service de journalisation centralisée](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)  

#### Concepts

[Présentation du service de journalisation centralisée](lync-server-2013-overview-of-the-centralized-logging-service.md)  

#### Autres ressources

[Show-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Show-CsClsLogging)  
[Start-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Start-CsClsLogging)  
[Stop-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Stop-CsClsLogging)

