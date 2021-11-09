---
title: Configurer des scénarios pour le service de journalisation centralisée dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: 'Résumé : Découvrez comment créer, modifier et supprimer des scénarios pour le service de journalisation centralisée Skype Entreprise Server 2015.'
ms.openlocfilehash: 10225be172d91aba18db29a1a6669cfbe8656fa6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855441"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Configurer des scénarios pour le service de journalisation centralisée dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment créer, modifier et supprimer des scénarios pour le service de journalisation centralisée dans Skype Entreprise Server 2015.
  
Les scénarios définissent l’étendue (globale, de site, de pool ou d’ordinateur) et les fournisseurs à utiliser dans le service de journalisation centralisée. À l’aide de scénarios, vous activez ou désactivez le suivi des fournisseurs (par exemple, S4, SIPStack, messagerie instantanée et présence). En configurant un scénario, vous pouvez regrouper tous les fournisseurs d’une collection logique donnée qui répondent à une condition de problème spécifique. Si vous trouvez qu’un scénario doit être modifié pour répondre à vos besoins de dépannage et de journalisation, les outils de débogage Skype Entreprise Server 2015 vous fournissent un module Windows PowerShell nommé ClsScenarioEdit.psm1 qui contient une fonction nomméeEdit-CsClsScenario. Grâce à ce module, vous pouvez modifier les propriétés du scénario nommé. Des exemples d’utilisation de ce module sont fournis dans cette rubrique. Téléchargez Skype Entreprise Server outils [de](https://go.microsoft.com/fwlink/p/?LinkId=285257) débogage 2015 avant d’aller plus loin.
  
> [!IMPORTANT]
> Pour une étendue donnée (globale, site, pool ou ordinateur), deux scénarios au maximum peuvent être exécutés en même temps. Pour déterminer les scénarios en cours d’exécution, utilisez Windows PowerShell et [Get-CsClsScenario](/powershell/module/skype/get-csclsscenario?view=skype-ps). En utilisant Windows PowerShell [et Set-CsClsScenario,](/powershell/module/skype/set-csclsscenario?view=skype-ps)vous pouvez modifier dynamiquement les scénarios en cours d’exécution. Cette opération peut s’avérer utile lors d’une session de journalisation pour ajuster ou affiner les données que vous collectez et les fournisseurs d’où ces données sont issues. 
  
Pour exécuter les fonctions du service de journalisation centralisée à l’aide de l’environnement de ligne de commande Skype Entreprise Server Management Shell, vous devez être membre des groupes de sécurité RBAC CsAdministrator ou CsServerAdministrator, ou d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes. Pour retourner la liste de tous les rôles RBAC attribués à cette cmdlet, y compris les rôles RBAC personnalisés que vous avez créés vous-même, exécutez la commande suivante à partir de l’invite Skype Entreprise Server Management Shell ou Windows PowerShell :
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Par exemple :
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

Le reste de cette rubrique met l’accent sur la définition d’un scénario, la modification d’un scénario, la récupération des scénarios en cours d’exécution, la suppression d’un scénario et la spécification du contenu d’un scénario afin d’optimiser votre dépannage. Vous pouvez utiliser l’environnement Skype Entreprise Server Management Shell pour émettre Windows PowerShell commandes. Lorsque vous utilisez Windows PowerShell, vous pouvez définir de nouveaux scénarios à utiliser dans vos sessions de journalisation.
  
Comme introduit dans le service de journalisation centralisée [Skype Entreprise 2015,](centralized-logging-service.md)les éléments d’un scénario sont les suivants :
  
- **Fournisseurs** Si vous êtes familiarisé avec OCSLogger, les fournisseurs sont les composants que vous choisissez d’indiquer à OCSLogger à partir de quoi le moteur de suivi doit collecter les journaux. Les fournisseurs sont les mêmes composants et, dans de nombreux cas, ont le même nom que les composants dans OCSLogger. Si vous n’êtes pas familiarisé avec OCSLogger, les fournisseurs sont des composants spécifiques au rôle de serveur à partir desse que le service de journalisation centralisée peut collecter des journaux. Pour plus d’informations sur la configuration des fournisseurs, voir [Configure providers for Centralized Logging Service in Skype Entreprise Server 2015](configure-providers.md).
    
- **Identité** Le paramètre -Identity définit l’étendue et le nom du scénario. Par exemple, vous pouvez définir une étendue « globale » et identifier le scénario avec « LyssServiceScenario ». Lorsque vous combinez les deux, vous définissez l’identité (par exemple, « global/LyssServiceScenario »).
    
    Si vous le souhaitez, vous pouvez utiliser les paramètres -Name et -Parent. Le paramètre Name permet d’identifier le scénario de manière unique. Si vous utilisez Name, vous devez également utiliser Parent pour ajouter le scénario à global ou site. 
    
    > [!IMPORTANT]
    > Si vous utilisez les paramètres Name et Parent, vous ne pouvez pas utiliser le **paramètre -Identity.**
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>Pour créer un scénario avec l’applet de commande New-CsClsScenario

1. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
2. Pour créer un scénario pour une session de journalisation, utilisez [New-CsClsProvider](/powershell/module/skype/new-csclsprovider?view=skype-ps) et définissez le nom du scénario (c’est-à-dire comment il va être identifié de manière unique). Choisissez un type de format de journalisation : vous avez le choix entre WPP (préprocesseur de suivi de logiciel Windows ; la valeur par défaut), EventLog (format de journal des événements Windows) et IISLog (fichier au format ASCII basé sur le format du fichier journal IIS). Ensuite, définissez Level (voir la définition sous Niveaux de journalisation dans cette rubrique) et Flags (voir la définition sous Indicateurs dans cette rubrique).
    
    Dans cet exemple de scénario, nous utilisons LyssProvider comme exemple de variable de fournisseur.
    
    Pour créer un scénario en utilisant les options définies, tapez :
    
   ```PowerShell
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    Par exemple :
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    Autre format utilisant -Name et -Parent :
    
   ```PowerShell
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>Pour créer un scénario avec plusieurs fournisseurs à l’aide de l’applet de commande New-CsClsScenario

1. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
2. Vous êtes limité à deux scénarios par étendue. Cependant, le nombre de fournisseurs n’est pas limité. Dans cet exemple, supposons que vous avez créé trois fournisseurs et que vous souhaitez les affecter tous les trois au scénario que vous définissez. Les noms des variables de fournisseur sont LyssProvider, ABServerProvider et SIPStackProvider. Pour définir et affecter plusieurs fournisseurs à un scénario, tapez ce qui suit à une invite de commandes Skype Entreprise Server Management Shell ou Windows PowerShell commande suivante :
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > Comme il est connu dans Windows PowerShell, la convention de création d’une table de hachage de valeurs à l’aide est appelée `@{<variable>=<value1>, <value2>, <value>…}` « platting ». Pour plus d’informations sur la splatting dans Windows PowerShell, voir [https://go.microsoft.com/fwlink/p/?LinkId=267760](/previous-versions/technet-magazine/gg675931(v=msdn.10)) . 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>Pour modifier un scénario existant avec l’applet de commande Set-CsClsScenario

1. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
2. Vous êtes limité à deux scénarios par étendue. Vous pouvez modifier les scénarios qui s’ exécutent à tout moment, même lorsqu’une session de capture de journalisation est en cours. Si vous redéfinissez les scénarios en cours d’exécution, la session de journalisation actuelle cesse d’utiliser le scénario qui a été supprimé et utilise ensuite le nouveau scénario. Toutefois, les informations de journalisation qui ont été capturées avec le scénario supprimé sont conservées dans les journaux capturés. Pour définir un nouveau scénario, faites ce qui suit (autrement dit, en supposant l’ajout d’un fournisseur déjà défini nommé « S4Provider » ) :
    
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

1. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
2. Si vous souhaitez supprimer un scénario précédemment défini, tapez ce qui suit :
    
   ```PowerShell
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    Par exemple, pour supprimer le scénario défini site:Redmond/LyssServiceScenario :
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

L’applet de commande **Remove-CsClsScenario** supprime le scénario spécifié, mais vous pouvez toujours accéder aux suivis capturés dans les journaux et lancer des recherches dans ceux-ci.
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a>Pour charger et décharger lEdit-CsClsScenario cmdlet à l’aide du module ClsScenarioEdit.psm1

1. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
    > [!IMPORTANT]
    > Le module ClsScenarioEdit.psm1 est fourni en tant que téléchargement Web distinct. Le module fait partie des outils de débogage Skype Entreprise Server 2015. Par défaut, les outils de débogage sont installés dans le répertoire C:\Program Files\Skype Entreprise Server 2015\Debugging Tools. 
  
2. Dans la Windows PowerShell, tapez :
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > Le chargement réussi du module vous renvoie à l’invite Windows PowerShell commande. Pour confirmer que le module est chargé et que Edit-CsClsScenario est disponible, tapez  `Get-Help Edit-CsClsScenario` . Le résumé de base de la syntaxe pour EditCsClsScenario doit apparaître. 
  
3. Pour décharger les modules, tapez :
    
   ```PowerShell
   Remove-Module ClsController
   ```

    > [!TIP]
    > Le déchargement réussi du module vous renvoie à l’invite Windows PowerShell commande. Pour confirmer que le module est déchargé, tapez  `Get-Help Edit-CsClsScenario` . Windows PowerShell tente de localiser l’aide de la cmdlet et échoue. 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>Pour supprimer un fournisseur existant d’un scénario avec le module Edit-ClsController

1. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
2. Dans la Windows PowerShell, tapez :
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > Le chargement réussi du module vous renvoie à l’invite Windows PowerShell commande. Pour confirmer que le module est chargé et que Edit-CsClsScenario est disponible, tapez  `Get-Help Edit-CsClsScenario` . Le résumé de base de la syntaxe pour EditCsClsScenario doit apparaître. 
  
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

   Le placement positionnel des valeurs de paramètre s’applique uniquement à -Scenario et -Provider. Tous les autres paramètres doivent être définis explicitement.
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>Pour ajouter un fournisseur à un scénario avec le module Edit-ClsController

1. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
2. Pour ajouter un fournisseur au scénario AlwaysOn, tapez :
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    Par exemple :
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    -Loglevel peut être du type Fatal, Error, Warning, Info, Verbose, Debug ou All. -Flags peut être l’un des indicateurs que le fournisseur prend en charge, tels que TF_COMPONENT, TF_DIAG. -Flags peut également être de valeur ALL
    
   Il est aussi possible de taper l’exemple précédent à l’aide de la fonctionnalité positionnelle de l’applet de commande. Par exemple, pour ajouter le fournisseur ChatServer au scénario AlwaysOn, tapez :
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```