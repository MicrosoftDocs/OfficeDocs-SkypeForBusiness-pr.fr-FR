---
title: Configurer des fournisseurs pour le service de journalisation centralisée dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: 'Résumé : Découvrez comment configurer des fournisseurs de scénarios pour le service de journalisation centralisée Skype Entreprise Server 2015.'
ms.openlocfilehash: a0c15061f209da9389018412322ea705f93b614f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60751663"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a>Configurer des fournisseurs pour le service de journalisation centralisée dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment configurer des fournisseurs de scénarios pour le service de journalisation centralisée Skype Entreprise Server 2015.
  
Les concepts et la configuration des fournisseurs dans le service de journalisation centralisée sont l’un des concepts les plus importants à comprendre. Lesprovideurs mappent directement aux Skype Entreprise Server de rôle serveur dans le modèle Skype Entreprise Server suivi. Le fournisseur définit les composants d’un Skype Entreprise Server 2015 qui seront suivis, le type de messages (par exemple, fatal, erreur ou avertissement) à collecter et les indicateurs (par exemple, TF_Connection ou TF_Diag). Les fournisseurs sont les composants de suivi dans chaque rôle Skype Entreprise Server serveur. À l’aide de fournisseurs, vous définissez le niveau et le type de suivi sur les composants (par exemple, S4, SIPStack, Messagerie instantanée et Présence). Le fournisseur défini est utilisé dans un scénario pour regrouper tous les fournisseurs d’une collection logique donnée qui répondent à une condition de problème spécifique.
  
Pour exécuter les fonctions du service de journalisation centralisée à l’aide de l’environnement de ligne de commande Skype Entreprise Server Management Shell, vous devez être membre des groupes de sécurité RBAC CsAdministrator ou CsServerAdministrator, ou d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes. Pour retourner la liste de tous les rôles RBAC (Contrôle d’accès basé sur un rôle) attribués à cette cmdlet (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de l’invite Skype Entreprise Server Management Shell ou Windows PowerShell :
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Par exemple :
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

Le reste de cette rubrique porte sur la définition des fournisseurs, la modification d’un fournisseur et ce que contient une définition de fournisseur afin d’optimiser le dépannage. Il existe deux façons d’émettre des commandes du service de journalisation centralisée. Vous pouvez utiliser la CLSController.exe qui se trouve, par défaut, dans le répertoire C:\Program Files\Common Files\Skype Entreprise Server 2015\CLSAgent. Vous pouvez également utiliser l’environnement de Skype Entreprise Server Management Shell pour émettre Windows PowerShell commandes. À l’aide de Windows PowerShell, vous pouvez définir de nouveaux fournisseurs à utiliser dans vos sessions de journalisation et avoir un contrôle total sur leur création, ce qu’ils collectent et à quel niveau ils collectent des données.
  
> [!IMPORTANT]
> Comme nous l’avons précédemment mentionné, les fournisseurs sont très puissants. Cependant, les scénarios le sont davantage, et ce du fait qu’ils contiennent toutes les informations nécessaires pour définir et exécuter le suivi sur les composants que les fournisseurs représentent. Les scénarios étant une collection de fournisseurs, une certaine analogie peut être établie entre, d’une part, l’exécution d’un fichier de commandes qui contient des centaines de commandes destinées à collecter une grande quantité d’informations et, d’autre part, l’émission de centaines de commandes, une à la fois, à la ligne de commande. 
  
Au lieu de vous demander d’en détailler les détails des fournisseurs, le service de journalisation centralisée fournit un certain nombre de scénarios qui sont déjà définis pour vous. Les scénarios fournis couvrent la grande majorité des problèmes que vous êtes susceptible de rencontrer. Dans de rares cas, vous devrez créer et définir des fournisseurs et les affecter à des scénarios. Nous vous recommandons fortement de vous familiariser avec chacun des scénarios fournis avant d’étudier la nécessité de créer de nouveaux scénarios et de nouveaux fournisseurs. Bien que des informations sur la création de fournisseurs sont données ici pour vous familiariser avec la façon dont les scénarios utilisent les éléments des fournisseurs pour collecter des informations de suivi, aucun détail sur les fournisseurs eux-mêmes n’est fourni pour le moment. 
  
Introduits dans le service de journalisation centralisée dans [Skype Entreprise 2015,](centralized-logging-service.md)les éléments clés de la définition d’un fournisseur à utiliser dans un scénario sont les suivants :
  
- **Fournisseurs** Si vous êtes familiarisé avec OCSLogger, les fournisseurs sont les composants que vous choisissez d’indiquer à OCSLogger à partir de quoi le moteur de suivi doit collecter les journaux. Les fournisseurs sont les mêmes composants et, dans de nombreux cas, ont le même nom que les composants dans OCSLogger. Si vous n’êtes pas familiarisé avec OCSLogger, les fournisseurs sont des composants spécifiques au rôle de serveur à partir desse que le service de journalisation centralisée peut collecter des journaux. Dans le cas du service de journalisation centralisée, le CLSAgent est la partie architecturale du service de journalisation centralisée qui fait le suivi des composants que vous définissez dans la configuration des fournisseurs.
    
- **Niveaux de journalisation** OCSLogger a fourni la possibilité de choisir un certain nombre de niveaux de détails pour les données collectées. Cette fonctionnalité fait partie intégrante du service de journalisation centralisée et des scénarios et est définie par le **paramètre Type.** Vous pouvez choisir l'une des options suivantes :
    
  - **Tout** Collecte les messages de suivi de type Fatal, Error, Warning, Verbose et Debug info dans le journal du fournisseur défini.
    
  - **Fatal** Collecte uniquement les messages de suivi définis comme « Fatal ».
    
  - **Erreur** Collecte uniquement les messages de suivi définis comme « Erreur » ou « Fatal ».
    
  - **Avertissement** Collecte uniquement les messages de suivi de type « Avertissement », « Erreur » et « Fatal ».
    
  - **Informations** Collecte uniquement les messages de suivi qui indiquent un message d’information pour le fournisseur défini, ainsi que les messages fatals, d’erreur et d’avertissement.
    
  - **Verbose** Collecte tous les messages de suivi de type Fatal, Error, Warning et Verbose pour le fournisseur défini.
    
  - **Le débogage** est essentiellement l’équivalent de « All » : collecte des traces de type Fatal, Error, Warning, Info, Verbose et Debug pour le fournisseur défini.
    
- **Indicateurs** OCSLogger fournissait la possibilité de choisir des indicateurs pour chaque fournisseur qui définissaient le type d’informations que vous pouviez récupérer à partir des fichiers de suivi. Vous pouvez choisir les indicateurs suivants selon le fournisseur :
    
  - **TF_Connection** Fournit des entrées de journal liées à la connexion. Ces journaux incluent des informations sur les connexions établies depuis et vers un composant particulier. Ils peuvent également comprendre des informations importantes au niveau du réseau (c’est-à-dire, pour les composants sans le concept d’une connexion).
    
  - **TF_Security** Fournit toutes les entrées d’événements/journaux liées à la sécurité. Par exemple, pour SipStack, il s’agit d’événements de sécurité tels que les échecs de validation de domaine et les échecs d’authentification ou d’autorisation du client.
    
  - **TF_Diag** Fournit des événements de diagnostic que vous pouvez utiliser pour diagnostiquer ou dépanner le composant. Par exemple, pour SipStack, il s’agit d’échecs de certificat ou d’avertissements/erreurs DNS.
    
  - **TF_Protocol** Fournit des messages de protocole tels que les messages SIP et Combined Community Codec Pack.
    
  - **TF_Component** Active la journalisation sur les composants spécifiés dans le cadre des fournisseurs.
    
  - **Tout** Définit tous les indicateurs disponibles pour le fournisseur.
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>Pour passer en revue les informations sur les fournisseurs de scénarios du service de journalisation centralisée existants

1. Démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
2. Pour examiner la configuration de fournisseurs existants, tapez ce qui suit :
    
   ```PowerShell
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    Par exemple, pour examiner des informations sur l’Intendant Conférence global, tapez :
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA"
   ```

    La commande affiche une liste de fournisseurs avec les indicateurs, paramètres et composants associés. Si les informations affichées ne sont pas suffisantes ou si la liste est trop longue pour le format de liste Windows PowerShell par défaut, vous pouvez afficher des informations supplémentaires en définissant une méthode de sortie différente. Pour cela, tapez :
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    La sortie de cette commande affiche chaque fournisseur sur cinq lignes avec le nom du fournisseur, le type de journalisation, le niveau d’enregistrement, les indicateurs, le GUID et le rôle sur une ligne distincte. 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>Pour définir un nouveau fournisseur de scénarios de service de journalisation centralisée

1. Démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
2. Un fournisseur de scénario se compose d’un composant à suivre, d’indicateurs à utiliser et d’un niveau de détail à collecter. Pour cela, tapez :
    
   ```PowerShell
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    Par exemple, une définition de fournisseur de suivi qui définit ce qu’il faut collecter à partir du fournisseur Lyss et à quel niveau de détail ressemble à ceci :
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

Le niveau collecte les messages fatals, d’erreur, d’avertissement et d’informations. Les indicateurs utilisés sont tous ceux définis pour le fournisseur Lyss et incluent TF_Connection, TF_Diag et TF_Protocol.Une fois la $LyssProvider variable définie, vous pouvez l’utiliser avec l';cmdlet **New-CsClsScenario** pour collecter les suivis à partir du fournisseur Lyss. Pour terminer la création du fournisseur et son affectation à un nouveau scénario, tapez :

```PowerShell
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

Où $LyssProvider est la variable qui contient le scénario défini créé avec **New-CsClsProvider**.
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>Pour modifier un fournisseur de scénarios de service de journalisation centralisée existant

1. Démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
2. Pour mettre à jour ou modifier la configuration d’un fournisseur existant, tapez :
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    Vous pouvez ensuite mettre à jour le scénario pour affecter le fournisseur en tapant ce qui suit :
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

À l’issue de l’exécution de la commande, des indicateurs et un niveau mis à jour pour le fournisseur sont affectés au scénario site:Redmond/RedmondLyssInfo. Vous pouvez examiner le nouveau scénario en utilisant Get-CsClsScenario. Pour plus d’informations, voir [Get-CsClsScenario](/powershell/module/skype/get-csclsscenario?view=skype-ps).
> [!CAUTION]
> **New-ClsCsProvider** ne vérifie pas si les indicateurs sont valides. Assurez-vous que les indicateurs (par exemple, TF_DIAG ou TF_CONNECTION) sont correctement épelés. Si ce n’est pas le cas, le fournisseur ne peut pas retourner les informations du journal attendues.
  
Si vous souhaitez ajouter des fournisseurs supplémentaires à ce scénario, tapez ce qui suit :

```PowerShell
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

Où chaque fournisseur défini avec la directive Add a déjà été défini à l’aide du processus **New-CsClsProvider**.
### <a name="to-remove-a-scenario-provider"></a>Pour supprimer un fournisseur de scénario

1. Démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
2. Les applets de commande fournies vous permettent de mettre à jour des fournisseurs existants et de créer de nouveaux fournisseurs. Pour supprimer un fournisseur, vous devez utiliser la directive Replace pour le paramètre Provider pour **Set-CsClsScenario**. La seule façon de supprimer complètement un fournisseur est de le remplacer par un fournisseur redéfini du même nom et d’utiliser la directive Update. Par exemple, le fournisseur LyssProvider est défini comme suit : WPP comme type de journal, Debug comme niveau, et TF_CONNECTION et TF_DIAG comme indicateurs. Vous devez modifier les indicateurs en « Tous ». Pour modifier le fournisseur, tapez ce qui suit :
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
   ```

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
   ```

3. Si vous souhaitez supprimer complètement un scénario et les fournisseurs associés à celui-ci, tapez ce qui suit :
    
   ```PowerShell
   Remove-CsClsScenario -Identity <scope and name of scenario>
   ```

    Par exemple :
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
   ```

    > [!CAUTION]
    > L’applet de commande **Remove-CsClsScenario** ne vous demande pas confirmation. Le scénario est supprimé, ainsi que les fournisseurs affectés à celui-ci. Vous pouvez recréer le scénario en réexécutant les commandes que vous avez utilisées pour le créer initialement. Il n’existe aucune procédure pour récupérer des scénarios ou des fournisseurs supprimés.
  
Lorsque vous supprimez un scénario à l’aide de l’applet de commande **Remove-CsClsScenario**, vous supprimez complètement le scénario de l’étendue. Pour utiliser les scénarios que vous avez créés et les fournisseurs qui faisaient partie du scénario, vous devez créer de nouveaux fournisseurs et les affecter à un nouveau scénario.
## <a name="see-also"></a>Voir aussi

[Get-CsClsScenario](/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[New-CsClsScenario](/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[Remove-CsClsScenario](/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[Set-CsClsScenario](/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[New-CsClsProvider](/powershell/module/skype/new-csclsprovider?view=skype-ps)