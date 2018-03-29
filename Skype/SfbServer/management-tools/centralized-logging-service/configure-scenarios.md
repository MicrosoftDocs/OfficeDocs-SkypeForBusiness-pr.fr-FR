---
title: Configuration des scénarios du service de journalisation centralisée dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: 'Résumé : Apprenez à créer, modifier et supprimer des scénarios pour le Service centralisé de journalisation dans Skype pour Business Server 2015.'
ms.openlocfilehash: e8b9575ed949e1769e867113be301deede981018
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Configuration des scénarios du service de journalisation centralisée dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment créer, modifier et supprimer des scénarios pour le Service centralisé de journalisation dans Skype pour Business Server 2015.
  
Scénarios de définissant la portée (c'est-à-dire, global, site, pool ou ordinateur) et les fournisseurs à utiliser dans le Service de journalisation centralisée. À l’aide de scénarios, pour activer ou désactiver le suivi sur les fournisseurs (par exemple, S4, SIPStack, messagerie instantanée et présence). Configuration d’un scénario, vous pouvez regrouper tous les fournisseurs pour une collection logique donnée cette adresse un problème spécifique. Si vous trouvez qu’un scénario doit être modifié pour répondre à la résolution des problèmes et la journalisation des besoins, le Skype pour les outils de débogage de 2015 Business Server fournit un module Windows PowerShell nommé ClsScenarioEdit.psm1 qui contient une fonction namedEdit-CsClsScenario. L’objectif du module est pour modifier les propriétés du scénario nommé. Exemples de fonctionne de ce module sont fournis dans cette rubrique. Avant d’aller plus loin, télécharger le Skype pour Business Server 2015, [Outils de débogage](https://go.microsoft.com/fwlink/p/?LinkId=285257) .
  
> [!IMPORTANT]
> Pour une étendue donnée (globale, site, pool ou ordinateur), deux scénarios au maximum peuvent être exécutés en même temps. Pour déterminer les scénarios qui sont en cours d’exécution, utilisez Windows PowerShell et [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps). À l’aide de Windows PowerShell et [Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps), vous pouvez modifier de façon dynamique les scénarios qui sont en cours d’exécution. Cette opération peut s’avérer utile lors d’une session de journalisation pour ajuster ou affiner les données que vous collectez et les fournisseurs d’où ces données sont issues. 
  
Pour exécuter les fonctions du Service de journalisation centralisée à l’aide de la Skype pour Business Server Management Shell, vous devez être un membre de la CsAdministrator ou les groupes de sécurité de CsServerAdministrator accès basé sur les rôles (RBAC) de contrôle, soit un rôle RBAC personnalisé qui contient une ou l’autre de ces deux groupes. Pour retourner une liste de tous la RBAC rôles que cette applet de commande a été affectée, y compris les rôles RBAC personnalisés que vous avez créés vous-même, exécutent la commande suivante à partir de la Skype Business Server Management Shell ou de l’invite de Windows PowerShell :
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Exemple :
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

Le reste de cette rubrique porte sur la façon de définir, de modifier, de supprimer un scénario, de récupérer des scénarios en cours dʼexécution et de spécifier les éléments dʼun scénario afin dʼoptimiser la résolution de problèmes. Vous pouvez utiliser le Skype pour Business Server Management Shell pour émettre des commandes de Windows PowerShell. Lors de l’utilisation de Windows PowerShell, vous pouvez définir de nouveaux scénarios pour l’utilisation dans vos sessions d’enregistrement.
  
Lors de l’introduction dans un [Service centralisé d’enregistrement dans Skype pour entreprise 2015](centralized-logging-service.md), les éléments d’un scénario sont les suivantes :
  
- **Fournisseurs** Si vous êtes familiarisé avec les OCSLogger, les fournisseurs sont les composants que vous choisissez pour indiquer OCSLogger à ce que le moteur de suivi doit collecter des journaux à partir de. Les fournisseurs sont les mêmes composants et, dans de nombreux cas, ont le même nom que les composants dans OCSLogger. Si vous n’êtes pas familiarisé avec les OCSLogger, les fournisseurs sont des composants spécifiques de rôle de serveur que le Service de journalisation centralisée peut collecter des journaux à partir de. Pour plus d’informations sur la configuration des fournisseurs, voir [configurer les fournisseurs de Service centralisé de journalisation dans Skype pour Business Server 2015](configure-providers.md).
    
- **Identité** Le paramètre-Identity définit la portée et le nom du scénario. Par exemple, vous pouvez définir une étendue de « global » et identifier le scénario avec « LyssServiceScenario ». Lorsque vous combinez les deux, vous définissez l’identité (par exemple, « global/LyssServiceScenario »).
    
    Si vous le souhaitez, vous pouvez utiliser les paramètres - nom et - Parent. Le paramètre Name permet d’identifier le scénario de manière unique. Si vous utilisez Name, vous devez également utiliser Parent pour ajouter le scénario à global ou site. 
    
    > [!IMPORTANT]
    > Si vous utilisez les paramètres de nom et Parent, vous ne pouvez pas utiliser le **-identité** paramètre.
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>Pour créer un scénario avec l’applet de commande New-CsClsScenario

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Pour créer un nouveau scénario pour une session de journalisation, utilisez [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) et définir le nom du scénario (en d’autres termes, comment il identifie). Choisissez un type de format de journalisation dans WPP (cʼest-à-dire le préprocesseur de suivi Windows défini par défaut), EventLog (format de journal des événements Windows) ou IISLog (fichier au format ASCII basé sur le format de fichier journal IIS). Ensuite, définissez Level (voir la définition sous Niveaux de journalisation de cette rubrique) et Flags (voir la définition sous Indicateurs dans cette rubrique).
    
    Dans cet exemple de scénario, nous utilisons LyssProvider comme exemple de variable de fournisseur.
    
    Pour créer un scénario en utilisant les options définies, tapez :
    
  ```
  New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
  ```

    Exemple :
    
  ```
  New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
  ```

    L’autre format en utilisant - Name et - Parent :
    
  ```
  New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
  ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>Pour créer un scénario avec plusieurs fournisseurs à l’aide de l’applet de commande New-CsClsScenario

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Vous êtes limité à deux scénarios par étendue. Cependant, le nombre de fournisseurs n’est pas limité. Dans cet exemple, supposons que vous avez créé trois fournisseurs et que vous souhaitez les affecter tous les trois au scénario que vous définissez. Les noms des variables de fournisseur sont LyssProvider, ABServerProvider et SIPStackProvider. Pour définir et affecter plusieurs fournisseurs pour un scénario, tapez ce qui suit à une Skype pour l’invite de commande Business Server Management Shell ou de Windows PowerShell :
    
  ```
  New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
  ```

    > [!NOTE]
    > Telle qu’elle est connue dans Windows PowerShell, la convention pour la création d’une table de hachage des valeurs à l’aide de `@{<variable>=<value1>, <value2>, <value>…}` est appelée assplatting. Pour plus d’informations sur splatting dans Windows PowerShell, voir [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760). 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>Pour modifier un scénario existant avec l’applet de commande Set-CsClsScenario

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Vous êtes limité à deux scénarios par étendue. Vous pouvez modifier les scénarios qui s’ exécutent à tout moment, même lorsqu’une session de capture de journalisation est en cours. Si vous redéfinissez les scénarios en cours d’exécution, la session de journalisation actuelle cesse d’utiliser le scénario qui a été supprimé et utilise ensuite le nouveau scénario. Toutefois, les informations de journalisation qui ont été capturées avec le scénario supprimé sont conservées dans les journaux capturés. Pour définir un nouveau scénario, effectuez l’opération suivante (qui est, à condition que l’ajout d’un fournisseur déjà défini nommé « S4Provider ») :
    
  ```
  Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
  ```

    Exemple :
    
  ```
  Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
  ```

    Si vous souhaitez remplacer des fournisseurs, définissez un fournisseur unique ou une liste séparée par des virgules des fournisseurs pour remplacer l’ensemble actuel. Si vous souhaitez seulement remplacer l’un des fournisseurs, ajoutez les fournisseurs actuels aux nouveaux fournisseurs pour créer un nouvel ensemble de fournisseurs contenant les nouveaux fournisseurs et les fournisseurs existants. Pour remplacer tous les fournisseurs par un nouvel ensemble, tapez ce qui suit :
    
  ```
  Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
  ```

    Par exemple, pour remplacer l’ensemble actuel comprenant $LyssProvider, $ABServerProvider et $SIPStackProvider par $LyssServiceProvider :
    
  ```
  Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
  ```

    Pour remplacer seulement le fournisseur $LyssProvider de l’ensemble actuel comprenant $LyssProvider, $ABServerProvider et $SIPStackProvider par $LyssServiceProvider, tapez ce qui suit :
    
  ```
  Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
  ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>Pour supprimer un scénario existant avec l’applet de commande Remove-CsClsScenario

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Si vous souhaitez supprimer un scénario précédemment défini, tapez ce qui suit :
    
  ```
  Remove-CsClsScenario -Identity <name of scope and scenario>
  ```

    Par exemple, pour supprimer le scénario défini site:Redmond/LyssServiceScenario :
    
  ```
  Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
  ```

L’applet de commande **Remove-CsClsScenario** supprime le scénario spécifié, mais les traces qui ont été capturées sont toujours disponibles dans les journaux pour effectuer une recherche sur.
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a>Pour charger et décharger l’applet de commande Edit-CsClsScenario à l’aide du module ClsScenarioEdit.psm1

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
    > [!IMPORTANT]
    > Le module ClsScenarioEdit.psm1 est fourni sous forme d’un téléchargement web distinct. Le module fait partie de la Skype pour les outils de débogage de Business Server 2015. Par défaut, les outils de débogage sont installés dans le répertoire C:\Program Files\Skype for Business Server 2015\Debugging Tools. 
  
2. À partir du Windows PowerShell, tapez :
    
  ```
  Import-Module "CDBurn\OCO\amd64\Support"
  ```

    > [!TIP]
    > Succès du chargement du module vous renvoie à l’invite de commande Windows PowerShell. Pour confirmer que le module est chargé et que CsClsScenario-Edition est disponible, tapez `Get-Help Edit-CsClsScenario`. Le résumé de base de la syntaxe pour EditCsClsScenario doit apparaître. 
  
3. Pour décharger les modules, tapez :
    
  ```
  Remove-Module ClsController
  ```

    > [!TIP]
    > Réussite déchargement du module renvoie vous à l’invite de commande Windows PowerShell. Pour confirmer que le module est déchargé, tapez `Get-Help Edit-CsClsScenario`. Windows PowerShell va tenter de localiser l’aide de l’applet de commande et l’échec. 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>Pour supprimer un fournisseur existant d’un scénario avec le module Edit-ClsController

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. À partir du Windows PowerShell, tapez :
    
  ```
  Import-Module "CDBurn\OCO\amd64\Support"
  ```

    > [!TIP]
    > Succès du chargement du module vous renvoie à l’invite de commande Windows PowerShell. Pour confirmer que le module est chargé et que CsClsScenario-Edition est disponible, tapez `Get-Help Edit-CsClsScenario`. Le résumé de base de la syntaxe pour EditCsClsScenario doit apparaître. 
  
3. Pour supprimer un fournisseur du scénario AlwaysOn, tapez :
    
  ```
  Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
  ```

  Par exemple :
    
  ```
  Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
  ```

   Les paramètres ScenarioName et ProviderName sont positionnels (c’est-à-dire qu’ils doivent être définis dans la position attendue dans la ligne de commande). Il n’est pas nécessaire de définir explicitement le nom du paramètre si le nom du scénario est en position deux et que le fournisseur est en position trois par rapport au nom de l’applet de commande (en position un). Compte tenu de ces informations, la commande précédente ressemble alors à ceci :
    
  ```
  Edit-CsClsScenario AlwaysOn ChatServer -Remove
  ```

  La position mise des valeurs de paramètre s’applique uniquement à - scénario et - fournisseur. Tous les autres paramètres doivent être définis explicitement.
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>Pour ajouter un fournisseur à un scénario avec le module Edit-ClsController

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Pour ajouter un fournisseur au scénario AlwaysOn, tapez :
    
  ```
  Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
  ```

    Par exemple :
    
  ```
  Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
  ```

    -Loglevel peut être du type Fatal, Error, Warning, Info, Verbose, Debug ou All. -Indicateurs peuvent être un des indicateurs qui prend en charge le fournisseur, telles que TF_COMPONENT, TF_DIAG. -Indicateurs peuvent également être de valeur toutes
    
  Il est aussi possible de taper l’exemple précédent à l’aide de la fonctionnalité positionnelle de l’applet de commande. Par exemple, pour ajouter le fournisseur ChatServer au scénario AlwaysOn, tapez :
    
  ```
  Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
  ```


