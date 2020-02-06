---
title: Configuration des scénarios du service de journalisation centralisée dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: 'Résumé : Découvrez comment créer, modifier et supprimer des scénarios pour le service de journalisation centralisé dans Skype entreprise Server 2015.'
ms.openlocfilehash: b7cfcbc85df7d66374d2bf33d572b9e91b30edde
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816593"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Configuration des scénarios du service de journalisation centralisée dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment créer, modifier et supprimer des scénarios pour le service de journalisation centralisé dans Skype entreprise Server 2015.
  
Les scénarios définissent l’étendue (c’est-à-dire, le site, le pool ou l’ordinateur) et les fournisseurs à utiliser dans le service de journalisation centralisé. By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence). By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition. Si vous constatez qu’un scénario doit être modifié en fonction de vos besoins en matière de résolution des problèmes et de journalisation, les outils de débogage de Skype entreprise Server 2015 vous fournissent un module Windows PowerShell intitulé ClsScenarioEdit. psm1 qui contient une fonction namedEdit-CsClsScenario. The purpose of the module is to edit the properties of the named scenario. Examples of how this module works are provided in this topic. Téléchargez les [outils de débogage](https://go.microsoft.com/fwlink/p/?LinkId=285257) de Skype entreprise Server 2015 avant d’aller plus loin.
  
> [!IMPORTANT]
> Pour une étendue donnée (globale, site, pool ou ordinateur), deux scénarios au maximum peuvent être exécutés en même temps. Pour déterminer les scénarios actuellement en cours d’exécution, utilisez Windows PowerShell et [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps). L’utilisation de Windows PowerShell et [de Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)vous permet de changer dynamiquement les scénarios qui s’exécutent. Cette opération peut s’avérer utile lors d’une session de journalisation pour ajuster ou affiner les données que vous collectez et les fournisseurs d’où ces données sont issues. 
  
Pour exécuter les fonctions de service de journalisation centralisées à l’aide de Skype entreprise Server Management Shell, vous devez être membre des groupes de sécurité CsAdministrator ou CsServerAdministrator de contrôle d’accès basé sur les rôles (RBAC), ou un rôle RBAC personnalisé qui contient l’un de ces deux groupes. Pour renvoyer la liste de tous les rôles RBAC attribués à cette applet de commande, y compris les rôles RBAC personnalisés que vous avez créés vous-même, exécutez la commande suivante à partir de Skype entreprise Server Management Shell ou de l’invite Windows PowerShell :
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Exemple :
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

Le reste de cette rubrique porte sur la façon de définir, de modifier, de supprimer un scénario, de récupérer des scénarios en cours dʼexécution et de spécifier les éléments dʼun scénario afin dʼoptimiser la résolution de problèmes. Vous pouvez utiliser Skype entreprise Server Management Shell pour exécuter les commandes Windows PowerShell. Lorsque vous utilisez Windows PowerShell, vous pouvez définir de nouveaux scénarios à utiliser dans vos sessions de journalisation.
  
Comme nous l’avons introduit dans le [service de journalisation centralisée de Skype entreprise 2015](centralized-logging-service.md), les éléments d’un scénario sont les suivants :
  
- **Fournisseurs** Si vous avez l’habitude d’utiliser OCSLogger, les fournisseurs sont les composants que vous choisissez pour indiquer à OCSLogger ce sur quoi le moteur de suivi doit collecter les journaux. Les fournisseurs sont les mêmes composants et, dans de nombreux cas, ont le même nom que les composants dans OCSLogger. Si vous n’êtes pas familiarisé avec OCSLogger, les fournisseurs sont des composants spécifiques du rôle serveur, que le service de journalisation centralisé peut collecter dans les journaux. Pour plus d’informations sur la configuration des fournisseurs, voir [configurer des fournisseurs pour le service de journalisation centralisé dans Skype entreprise Server 2015](configure-providers.md).
    
- **Identité** Le paramètre-Identity définit l’étendue et le nom du scénario. Par exemple, vous pouvez définir une étendue de « global » et identifier le scénario avec « LyssServiceScenario ». Lorsque vous combinez les deux, vous définissez l’identité (par exemple, « Global/LyssServiceScenario »).
    
    Vous pouvez également utiliser les paramètres-nom et parent. Le paramètre Name permet d’identifier le scénario de manière unique. Si vous utilisez Name, vous devez également utiliser Parent pour ajouter le scénario à global ou site. 
    
    > [!IMPORTANT]
    > Si vous utilisez les paramètres nom et parent, vous ne pouvez pas utiliser le paramètre **-Identity** .
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>Pour créer un scénario avec l’applet de commande New-CsClsScenario

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
2. Pour créer un nouveau scénario pour une session de journalisation, utilisez [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) et définissez le nom du scénario (cʼest-à-dire comment il va être identifié de manière unique). Choisissez un type de format de journalisation dans WPP (cʼest-à-dire le préprocesseur de suivi Windows défini par défaut), EventLog (format de journal des événements Windows) ou IISLog (fichier au format ASCII basé sur le format de fichier journal IIS). Ensuite, définissez Level (voir la définition sous Niveaux de journalisation de cette rubrique) et Flags (voir la définition sous Indicateurs dans cette rubrique).
    
    Dans cet exemple de scénario, nous utilisons LyssProvider comme exemple de variable de fournisseur.
    
    Pour créer un scénario en utilisant les options définies, tapez :
    
   ```PowerShell
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    Exemple :
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    Le format alternatif utilise-Name et-parent :
    
   ```PowerShell
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>Pour créer un scénario avec plusieurs fournisseurs à l’aide de l’applet de commande New-CsClsScenario

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
2. Vous êtes limité à deux scénarios par étendue. Cependant, le nombre de fournisseurs n’est pas limité. Dans cet exemple, supposons que vous avez créé trois fournisseurs et que vous souhaitez les affecter tous les trois au scénario que vous définissez. Les noms des variables de fournisseur sont LyssProvider, ABServerProvider et SIPStackProvider. Pour définir et affecter plusieurs fournisseurs à un scénario, tapez ce qui suit dans une invite de commandes Skype entreprise Server Management Shell ou Windows PowerShell :
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > Comme il est connu dans Windows PowerShell, la Convention de création d’une table de hachage de `@{<variable>=<value1>, <value2>, <value>…}` valeurs à l’aide de assplatting est connue. Pour plus d’informations sur la projection dans Windows PowerShell, [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760)reportez-vous à la rubrique. 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>Pour modifier un scénario existant avec l’applet de commande Set-CsClsScenario

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
2. Vous êtes limité à deux scénarios par étendue. Vous pouvez modifier les scénarios qui s’ exécutent à tout moment, même lorsqu’une session de capture de journalisation est en cours. Si vous redéfinissez les scénarios en cours d’exécution, la session de journalisation actuelle cesse d’utiliser le scénario qui a été supprimé et utilise ensuite le nouveau scénario. Toutefois, les informations de journalisation qui ont été capturées avec le scénario supprimé sont conservées dans les journaux capturés. Pour définir un nouveau scénario, procédez comme suit (en partant du principe que l’ajout d’un fournisseur déjà défini appelé « S4Provider ») :
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    Par exemple :
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    Si vous souhaitez remplacer des fournisseurs, définissez un fournisseur unique ou une liste séparée par des virgules des fournisseurs pour remplacer l’ensemble actuel. Si vous souhaitez seulement remplacer l’un des fournisseurs, ajoutez les fournisseurs actuels aux nouveaux fournisseurs pour créer un nouvel ensemble de fournisseurs contenant les nouveaux fournisseurs et les fournisseurs existants. Pour remplacer tous les fournisseurs par un nouvel ensemble, tapez ce qui suit :
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    Par exemple, pour remplacer l’ensemble actuel comprenant $LyssProvider, $ABServerProvider et $SIPStackProvider par $LyssServiceProvider :
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    Pour remplacer seulement le fournisseur $LyssProvider de l’ensemble actuel comprenant $LyssProvider, $ABServerProvider et $SIPStackProvider par $LyssServiceProvider, tapez ce qui suit :
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>Pour supprimer un scénario existant avec l’applet de commande Remove-CsClsScenario

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
2. Si vous souhaitez supprimer un scénario précédemment défini, tapez ce qui suit :
    
   ```PowerShell
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    Par exemple, pour supprimer le scénario défini site:Redmond/LyssServiceScenario :
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

L’applet de commande **Remove-CsClsScenario** supprime le scénario spécifié, mais vous pouvez toujours accéder aux suivis capturés dans les journaux et lancer des recherches dans ceux-ci.
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a>Pour charger et décharger l’applet de commande Edit-CsClsScenario à l’aide du module ClsScenarioEdit.psm1

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
    > [!IMPORTANT]
    > Le module ClsScenarioEdit.psm1 est fourni sous forme d’un téléchargement web distinct. Le module fait partie des outils de débogage de Skype entreprise Server 2015. Par défaut, les outils de débogage sont installés dans le répertoire C:\Program Files\Skype for Business Server 2015\Debugging Tools. 
  
2. Dans Windows PowerShell, tapez :
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > Le chargement réussi du module vous renvoie à l’invite de commandes Windows PowerShell. Pour vérifier que le module est chargé et que Edit-CsClsScenario est disponible, tapez `Get-Help Edit-CsClsScenario`. Le résumé de base de la syntaxe pour EditCsClsScenario doit apparaître. 
  
3. Pour décharger les modules, tapez :
    
   ```PowerShell
   Remove-Module ClsController
   ```

    > [!TIP]
    > Le déchargement réussi du module revient à l’invite de commandes Windows PowerShell. Pour vérifier que le module est déchargé, tapez `Get-Help Edit-CsClsScenario`. Windows PowerShell tente de Rechercher l’aide de l’applet de cmdlet et échoue. 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>Pour supprimer un fournisseur existant d’un scénario avec le module Edit-ClsController

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
2. Dans Windows PowerShell, tapez :
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > Le chargement réussi du module vous renvoie à l’invite de commandes Windows PowerShell. Pour vérifier que le module est chargé et que Edit-CsClsScenario est disponible, tapez `Get-Help Edit-CsClsScenario`. Le résumé de base de la syntaxe pour EditCsClsScenario doit apparaître. 
  
3. Pour supprimer un fournisseur du scénario AlwaysOn, tapez :
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   Par exemple :
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   Les paramètres ScenarioName et ProviderName sont positionnels (c’est-à-dire qu’ils doivent être définis dans la position attendue dans la ligne de commande). Il n’est pas nécessaire de définir explicitement le nom du paramètre si le nom du scénario est en position deux et que le fournisseur est en position trois par rapport au nom de l’applet de commande (en position un). Compte tenu de ces informations, la commande précédente ressemble alors à ceci :
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   La mise en place de valeurs de paramètres ne s’applique qu’aux fournisseurs. Tous les autres paramètres doivent être définis explicitement.
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>Pour ajouter un fournisseur à un scénario avec le module Edit-ClsController

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
2. Pour ajouter un fournisseur au scénario AlwaysOn, tapez :
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    Par exemple :
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    -Loglevel peut être du type Fatal, Error, Warning, Info, Verbose, Debug ou All. -Les indicateurs peuvent être tout indicateur pris en charge par le fournisseur (par exemple, TF_COMPONENT TF_DIAG. -LES indicateurs peuvent également être de valeurs
    
   Il est aussi possible de taper l’exemple précédent à l’aide de la fonctionnalité positionnelle de l’applet de commande. Par exemple, pour ajouter le fournisseur ChatServer au scénario AlwaysOn, tapez :
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```
