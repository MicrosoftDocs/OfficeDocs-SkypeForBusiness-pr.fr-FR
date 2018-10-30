---
title: Configuration des scénarios pour le service de journalisation centralisée
TOCTitle: Configuration des scénarios pour le service de journalisation centralisée
ms:assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688085(v=OCS.15)
ms:contentKeyID: 49891383
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des scénarios pour le service de journalisation centralisée

 

_**Dernière rubrique modifiée :** 2016-12-08_

Les scénarios définissent l’étendue (globale, site, pool ou ordinateur) et les fournisseurs à utiliser dans le service de journalisation centralisée. À l’aide de scénarios, vous activez ou désactivez le suivi des fournisseurs (par exemple, S4, SIPStack, messagerie instantanée et présence). En configurant un scénario, vous pouvez regrouper tous les fournisseurs d’une collection logique donnée qui répondent à une condition de problème spécifique. Si vous constatez qu’un scénario doit être modifié pour répondre à vos besoins en termes de dépannage et de journalisation, Lync Server 2013 Debug Tools fournit un module Windows PowerShell nommé *ClsController.psm1* qui contient une fonction intitulée *Edit-CsClsScenario*. Grâce à ce module, vous pouvez modifier les propriétés du scénario nommé. Des exemples d’utilisation de ce module sont fournis dans cette rubrique. Vous pouvez télécharger Lync Server 2013 Debug Tools à l'adresse suivante : [http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)

> [!IMPORTANT]  
> Pour une étendue donnée (globale, site, pool ou ordinateur), deux scénarios au maximum peuvent être exécutés en même temps. Pour déterminer les scénarios en cours d’exécution, utilisez Windows PowerShell et <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsScenario">Get-CsClsScenario</a>. Avec Windows PowerShell et <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsScenario">Set-CsClsScenario</a>, vous pouvez modifier dynamiquement les scénarios en cours d’exécution. Cette opération peut s’avérer utile lors d’une session de journalisation pour ajuster ou affiner les données que vous collectez et les fournisseurs d’où ces données sont issues.

Pour exécuter les fonctions du service de journalisation centralisée à l’aide de Lync Server Management Shell, vous devez être membre soit du groupe de sécurité de contrôle d’accès en fonction du rôle (RBAC) CsAdministrator ou CsServerAdministrator, soit d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes. Pour retourner une liste de tous les rôles RBAC auxquels cette applet de commande a été affectée, y compris tout rôle RBAC personnalisé que vous avez créé vous-même, exécutez la commande suivante à partir du Lync Server Management Shell ou de l’invite Windows PowerShell :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Par exemple :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

Le reste de cette rubrique met l’accent sur la définition d’un scénario, la modification d’un scénario, la récupération des scénarios en cours d’exécution, la suppression d’un scénario et la spécification du contenu d’un scénario afin d’optimiser votre dépannage. Deux méthodes s’offrent à vous pour émettre des commandes du service de journalisation centralisée. Vous pouvez utiliser le fichier CLSController.exe qui se trouve, par défaut, dans le répertoire C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent. Vous pouvez aussi utiliser Lync Server Management Shell pour émettre des commandes Windows PowerShell. Il est important de noter que lorsque vous utilisez CLSController.exe à la ligne de commande, la sélection de scénarios disponibles est limitée. Lorsque vous utilisez Windows PowerShell, vous pouvez définir de nouveaux scénarios à utiliser dans vos sessions de journalisation.

Comme indiqué dans [Présentation du service de journalisation centralisée](lync-server-2013-overview-of-the-centralized-logging-service.md), les éléments d’un scénario sont les suivants :

  - **Fournisseurs**   Si vous avez déjà utilisé OCSLogger, les fournisseurs sont les composants que vous choisissez pour indiquer à OCSLogger la nature des journaux que le moteur de suivi doit collecter. Les fournisseurs sont les mêmes composants et, dans de nombreux cas, ont le même nom que les composants dans OCSLogger. Si vous ne connaissez pas OCSLogger, les fournisseurs sont des composants spécifiques à un rôle serveur à partir desquels le service de journalisation centralisée peut collecter des journaux. Pour plus d’informations sur la configuration des fournisseurs, voir [Configuration des fournisseurs pour le service de journalisation centralisée](lync-server-2013-configuring-providers-for-centralized-logging-service.md).

  - **Identité**   Le paramètre –Identity définit l’étendue et le nom du scénario. Par exemple, vous pouvez définir une étendue « global » et nommer le scénario « LyssServiceScenario ». Lorsque vous combinez les deux, vous définissez l’identité (par exemple, « global/LyssServiceScenario »).
    
    Vous pouvez éventuellement utiliser les paramètres –Name et –Parent. Le paramètre Name permet d’identifier le scénario de manière unique. Si vous utilisez Name, vous devez également utiliser Parent pour ajouter le scénario à global ou site.
    
    > [!IMPORTANT]  
    > Si vous utilisez les paramètres Name et Parent, vous ne pouvez pas utiliser le paramètre <strong>–Identity</strong>.

## Pour créer un scénario avec l’applet de commande New-CsClsScenario

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Pour créer un scénario pour une session de journalisation, utilisez [New-CsClsProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsProvider) et définissez le nom du scénario (c’est-à-dire comment il va être identifié de manière unique). Choisissez un type de format de journalisation : vous avez le choix entre WPP (préprocesseur de suivi de logiciel Windows ; la valeur par défaut), EventLog (format de journal des événements Windows) et IISLog (fichier au format ASCII basé sur le format du fichier journal IIS). Ensuite, définissez Level (voir la définition sous Niveaux de journalisation dans cette rubrique) et Flags (voir la définition sous Indicateurs dans cette rubrique).
    
    Dans cet exemple de scénario, nous utilisons LyssProvider comme exemple de variable de fournisseur.
    
    Pour créer un scénario en utilisant les options définies, tapez :
    
        New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
    
    Par exemple :
    
        New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
    
    Autre format utilisant –Name et –Parent :
    
        New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider

## Pour créer un scénario avec plusieurs fournisseurs à l’aide de l’applet de commande New-CsClsScenario

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Vous êtes limité à deux scénarios par étendue. Cependant, le nombre de fournisseurs n’est pas limité. Dans cet exemple, supposons que vous avez créé trois fournisseurs et que vous souhaitez les affecter tous les trois au scénario que vous définissez. Les noms des variables de fournisseur sont LyssProvider, ABServerProvider et SIPStackProvider. Pour définir plusieurs fournisseurs et les affecter à un scénario, tapez la commande suivante à une invite de commandes Lync Server Management Shell ou Windows PowerShell :
    
        New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
    
    > [!NOTE]  
    > Au même titre que dans Windows PowerShell, la convention pour la création d’une table de hachage de valeurs à l’aide de <code>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</code> est connue sous le terme de <em>projection</em>. Pour plus d’informations sur la projection dans Windows PowerShell, voir <a href="http://go.microsoft.com/fwlink/?linkid=267760%26clcid=0x40c">http://go.microsoft.com/fwlink/?linkid=267760&amp;clcid=0x40C</a>.

## Pour modifier un scénario existant avec l’applet de commande Set-CsClsScenario

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Vous êtes limité à deux scénarios par étendue. Vous pouvez modifier les scénarios qui s’ exécutent à tout moment, même lorsqu’une session de capture de journalisation est en cours. Si vous redéfinissez les scénarios en cours d’exécution, la session de journalisation actuelle cesse d’utiliser le scénario qui a été supprimé et utilise ensuite le nouveau scénario. Toutefois, les informations de journalisation qui ont été capturées avec le scénario supprimé sont conservées dans les journaux capturés. Pour définir un nouveau scénario, procédez comme suit (pour cela, nous partons du principe qu’un fournisseur déjà défini nommé « S4Provider » a été ajouté) :
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
    
    Par exemple :
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
    
    Si vous souhaitez remplacer des fournisseurs, définissez un fournisseur unique ou une liste séparée par des virgules des fournisseurs pour remplacer l’ensemble actuel. Si vous souhaitez seulement remplacer l’un des fournisseurs, ajoutez les fournisseurs actuels aux nouveaux fournisseurs pour créer un nouvel ensemble de fournisseurs contenant les nouveaux fournisseurs et les fournisseurs existants. Pour remplacer tous les fournisseurs par un nouvel ensemble, tapez ce qui suit :
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
    
    Par exemple, pour remplacer l’ensemble actuel comprenant $LyssProvider, $ABServerProvider et $SIPStackProvider par $LyssServiceProvider :
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
    
    Pour remplacer seulement le fournisseur $LyssProvider de l’ensemble actuel comprenant $LyssProvider, $ABServerProvider et $SIPStackProvider par $LyssServiceProvider, tapez ce qui suit :
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}

## Pour supprimer un scénario existant avec l’applet de commande Remove-CsClsScenario

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Si vous souhaitez supprimer un scénario précédemment défini, tapez ce qui suit :
    
        Remove-CsClsScenario -Identity <name of scope and scenario>
    
    Par exemple, pour supprimer le scénario défini site:Redmond/LyssServiceScenario :
    
        Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"

L’applet de commande **Remove-CsClsScenario** supprime le scénario spécifié, mais vous pouvez toujours accéder aux suivis capturés dans les journaux et lancer des recherches dans ceux-ci.

## Pour charger et décharger l’applet de commande Edit-CsClsScenario à l’aide du module ClsController.psm1

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.
    
    > [!IMPORTANT]  
    > Le module ClsController.psm1 est fourni sous forme d’un téléchargement web distinct. Le module fait partie des outils de débogage Lync Server 2013. Par défaut, les outils de débogage sont installés dans le répertoire C:\Program Files\Lync Server 2013\Debugging Tools.

2.  Dans Windows PowerShell, tapez :
    
        Import-Module "C:\Program Files\Lync Server 2013\Debugging Tools\ClsController.psm1"
    
    > [!TIP]  
    > Au terme du chargement du module, vous revenez à l’invite de commandes Windows PowerShell. Pour vérifier que le module est chargé et que Edit-CsClsScenario est disponible, tapez <code>Get-Help Edit-CsClsScenario</code>. Le résumé de base de la syntaxe pour EditCsClsScenario doit apparaître.

3.  Pour décharger les modules, tapez :
    
        Remove-Module ClsController
    
    > [!TIP]  
    > Au terme du déchargement du module, vous revenez à l’invite de commandes Windows PowerShell. Pour vérifier que le module est déchargé, tapez <code>Get-Help Edit-CsClsScenario</code>. Windows PowerShell tente ensuite de localiser l’aide de l’applet de commande et échoue.

## Pour supprimer un fournisseur existant d’un scénario avec le module Edit-ClsController

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Pour supprimer un fournisseur du scénario AlwaysOn, tapez :
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
    
    Par exemple :
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
    
    Les paramètres ScenarioName et ProviderName sont positionnels (c’est-à-dire qu’ils doivent être définis dans la position attendue dans la ligne de commande). Il n’est pas nécessaire de définir explicitement le nom du paramètre si le nom du scénario est en position deux et que le fournisseur est en position trois par rapport au nom de l’applet de commande (en position un). Compte tenu de ces informations, la commande précédente ressemble alors à ceci :
    
        Edit-CsClsScenario AlwaysOn ChatServer -Remove
    
    Le placement positionnel des valeurs de paramètre s’applique uniquement à –Scenario et à –Provider. Tous les autres paramètres doivent être définis explicitement.

## Pour ajouter un fournisseur à un scénario avec le module Edit-ClsController

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Pour ajouter un fournisseur au scénario AlwaysOn, tapez :
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
    
    Par exemple :
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
    
    \-Loglevel peut être du type Fatal, Error, Warning, Info, Verbose, Debug ou All. –Flags peut avoir pour valeur n’importe quel indicateur pris en charge par le fournisseur, comme TF\_COMPONENT, TF\_DIAG. –Flags peut également avoir la valeur ALL.
    
    Il est aussi possible de taper l’exemple précédent à l’aide de la fonctionnalité positionnelle de l’applet de commande. Par exemple, pour ajouter le fournisseur ChatServer au scénario AlwaysOn, tapez :
    
        Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL

