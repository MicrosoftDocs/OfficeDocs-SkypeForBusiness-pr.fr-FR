---
title: Configuration des fournisseurs pour le service de journalisation centralisée dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: 'Résumé : Apprenez à configurer des fournisseurs de scénario pour le Service de journalisation centralisée dans Skype pour Business Server 2015.'
ms.openlocfilehash: a609d7406f59702aeb906a21132eff5f861ce037
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a>Configuration des fournisseurs pour le service de journalisation centralisée dans Skype Entreprise Server 2015
 
**Résumé :** Apprenez à configurer des fournisseurs de scénario pour le Service de journalisation centralisée dans Skype pour Business Server 2015.
  
Les concepts et la configuration des fournisseurs de Service de journalisation centralisée est un des plus importants à comprendre. Theproviders sont directement mappés sur Skype pour composants de rôle de serveur de Business Server dans le Skype pour modèle suivi de serveur d’entreprise. Le fournisseur définit les composants d’un Skype pour Business Server 2015 qui vont être tracées, le type de messages (par exemple, fatal, erreur ou avertissement) pour collecter et les indicateurs (par exemple, TF_Connection ou TF_Diag). Les fournisseurs sont les composants traçables dans chaque Skype pour le rôle de serveur de serveur d’entreprise. À l’aide de fournisseurs, vous définissez le niveau et le type de suivi sur les composants (par exemple, S4, SIPStack, Messagerie instantanée et Présence). Le fournisseur défini est utilisé dans un scénario pour regrouper tous les fournisseurs d’une collection logique donnée qui répondent à une condition de problème spécifique.
  
Pour exécuter les fonctions du Service de journalisation centralisée à l’aide de la Skype pour Business Server Management Shell, vous devez être un membre de la CsAdministrator ou les groupes de sécurité de CsServerAdministrator accès basé sur les rôles (RBAC) de contrôle, soit un rôle RBAC personnalisé qui contient une ou l’autre de ces deux groupes. Pour retourner une liste de tous les rôles de contrôle (RBAC) d’accès basé sur le rôle de cette applet de commande a été affectée (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de la Skype pour Business Server Management Shell ou le Windows PowerShell invite de commandes :
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Exemple :
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

Le reste de cette rubrique met l’accent sur la définition des fournisseurs, la modification d’un fournisseur et la spécification du contenu d’un fournisseur afin d’optimiser votre dépannage. Il existe deux façons d’émettre des commandes de Service de journalisation centralisée. Vous pouvez utiliser le fichier CLSController.exe qui se trouve, par défaut, dans le répertoire C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent. Ou bien, vous pouvez utiliser le Skype pour Business Server Management Shell pour émettre des commandes de Windows PowerShell. À l’aide de Windows PowerShell, vous pouvez définir de nouveaux fournisseurs à utiliser dans vos sessions d’enregistrement et avoir un contrôle total sur leur création, qu’ils perçoivent, et à quel niveau ils collectent des données.
  
> [!IMPORTANT]
> Comme nous l’avons précédemment mentionné, les fournisseurs sont très puissants. Cependant, les scénarios le sont davantage, et ce du fait qu’ils contiennent toutes les informations nécessaires pour définir et exécuter le suivi sur les composants que les fournisseurs représentent. Les scénarios étant une collection de fournisseurs, une certaine analogie peut être établie entre, d’une part, l’exécution d’un fichier de commandes qui contient des centaines de commandes destinées à collecter une grande quantité d’informations et, d’autre part, l’émission de centaines de commandes, une à la fois, à la ligne de commande. 
  
Au lieu de vous obliger à fouiller profondément dans les détails des fournisseurs, le Service de journalisation centralisée fournit un certain nombre de scénarios qui sont déjà définies pour vous. Les scénarios fournis couvrent la grande majorité des problèmes que vous êtes susceptible de rencontrer. Dans de rares cas, vous devrez créer et définir des fournisseurs et les affecter à des scénarios. Nous vous recommandons fortement de vous familiariser avec chacun des scénarios fournis avant d’étudier la nécessité de créer de nouveaux scénarios et de nouveaux fournisseurs. Bien que des informations sur la création de fournisseurs sont données ici pour vous familiariser avec la façon dont les scénarios utilisent les éléments des fournisseurs pour collecter des informations de suivi, aucun détail sur les fournisseurs eux-mêmes n’est fourni pour le moment. 
  
Les éléments clés de la définition d’un fournisseur dans un scénario introduit dans un [Service centralisé d’enregistrement dans Skype pour entreprise 2015](centralized-logging-service.md), sont :
  
- **Fournisseurs** Si vous êtes familiarisé avec les OCSLogger, les fournisseurs sont les composants que vous choisissez pour indiquer OCSLogger à ce que le moteur de suivi doit collecter des journaux à partir de. Les fournisseurs sont les mêmes composants et, dans de nombreux cas, ont le même nom que les composants dans OCSLogger. Si vous n’êtes pas familiarisé avec les OCSLogger, les fournisseurs sont rôle serveur de composants spécifiques que le Service de journalisation centralisée peut collecter des journaux à partir de. En ce qui concerne le Service de journalisation centralisée, le CLSAgent est la partie d’architecture centralisée journalisation du Service de qui effectue le suivi des composants que vous avez définis dans la configuration des fournisseurs.
    
- **Niveaux d’enregistrement** OCSLogger offraient la possibilité de choisir un nombre de niveaux de détail pour les données collectées. Cette fonctionnalité fait partie intégrante du Service de journalisation centralisée et des scénarios et est définie par le paramètre de **Type** . Vous avez le choix entre les valeurs suivantes :
    
  - **Tous les** Collecte trace des messages de type erreur fatale, erreur, avertissement, des commentaires et des informations de débogage dans le journal pour le fournisseur défini.
    
  - **Erreur fatale** Collecte uniquement les messages de trace définis comme « Erreur irrécupérable ».
    
  - **Erreur** Collecte uniquement les messages de trace définis comme « Erreur » ou « Erreur irrécupérable ».
    
  - **Avertissement** Collecte uniquement les messages de trace du type « Warning », « Erreur » et « Erreurs Fatal ».
    
  - **Info** Collecte uniquement les messages de trace qui indiquent des messages d’avertissement, d’erreur et un message d’information pour le fournisseur défini, plus irrécupérable.
    
  - **Commentaires** Collecte tous les messages de trace d’erreur irrécupérable, type, d’avertissement et commentaires pour le fournisseur défini.
    
  - **Déboguer** c’est essentiellement l’équivalent de « Tous » - collecte des traces de type Fatal, erreur, avertissement, informations, de commentaires et de débogage pour le fournisseur défini.
    
- **Indicateurs** OCSLogger offraient la possibilité de choisir des indicateurs pour chaque fournisseur qui a défini le type d’informations que vous pouvez récupérer à partir des fichiers de trace. Vous pouvez choisir les indicateurs suivants selon le fournisseur :
    
  - **TF_Connection** Fournit des entrées des journaux liées à la connexion. Ces journaux incluent des informations sur les connexions établies depuis et vers un composant particulier. Ils peuvent également comprendre des informations importantes au niveau du réseau (c’est-à-dire, pour les composants sans le concept d’une connexion).
    
  - **TF_Security** Fournit toutes les entrées de journal des événements liées à la sécurité. Par exemple, pour SipStack, il s’agit d’événements de sécurité tels que les échecs de validation de domaine et les échecs d’authentification ou d’autorisation du client.
    
  - **TF_Diag** Fournit des événements de diagnostic que vous pouvez utiliser pour diagnostiquer ou résoudre les problèmes de composant. Par exemple, pour SipStack, il s’agit d’échecs de certificat ou d’avertissements/erreurs DNS.
    
  - **TF_Protocol** Fournit des messages de protocole de messages SIP et le Pack de Codec de communauté combinées.
    
  - **TF_Component** Active la journalisation sur les composants spécifiés dans le cadre des fournisseurs.
    
  - **Tous les** Définit tous les indicateurs disponibles disponibles pour le fournisseur.
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>Pour obtenir des informations sur les fournisseurs existants de scénario de Service de journalisation centralisée

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Pour examiner la configuration de fournisseurs existants, tapez ce qui suit :
    
  ```
  Get-CsClsScenario -Identity <scope and scenario name>
  ```

    Par exemple, pour examiner des informations sur l’Intendant Conférence global, tapez :
    
  ```
  Get-CsClsScenario -Identity "global/CAA"
  ```

    La commande affiche une liste de fournisseurs avec les indicateurs, paramètres et composants associés. Si les informations affichées ne sont pas suffisamment ou si la liste est trop longue pour le format de liste par défaut de Windows PowerShell, vous pouvez afficher des informations supplémentaires en définissant une méthode de sortie différent. Pour cela, tapez :
    
  ```
  Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
  ```

    La sortie de cette commande affiche chaque fournisseur sur cinq lignes avec le nom du fournisseur, le type de journalisation, le niveau d’enregistrement, les indicateurs, le GUID et le rôle sur une ligne distincte. 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>Pour définir un nouveau fournisseur de scénario de Service de journalisation centralisée

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Un fournisseur de scénario se compose d’un composant à suivre, d’indicateurs à utiliser et d’un niveau de détail à collecter. Pour cela, tapez :
    
  ```
  $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
  ```

    Par exemple, une définition de fournisseur de suivi qui définit ce qu’il faut collecter à partir du fournisseur Lyss et à quel niveau de détail ressemble à ceci :
    
  ```
  $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
  ```

-Collecte de niveau grave, erreur, avertissement et informations messages. Les indicateurs utilisés sont tous ceux qui sont définis pour le fournisseur de Lyss et incluent TF_Connection, TF_Diag et TF_Protocol.After à la variable $LyssProvider est définie, vous pouvez l’utiliser avec l’applet de commande **New-CsClsScenario** pour collecter des traces à partir du fournisseur de Lyss. Pour terminer la création du fournisseur et son affectation à un nouveau scénario, tapez :

```
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

Où $LyssProvider est la variable qui contient le scénario défini créé avec **New-CsClsProvider**.
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>Pour modifier un fournisseur de scénario de Service de journalisation centralisée existant

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Pour mettre à jour ou modifier la configuration d’un fournisseur existant, tapez :
    
  ```
  $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
  ```

    Vous pouvez ensuite mettre à jour le scénario pour affecter le fournisseur en tapant ce qui suit :
    
  ```
  Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
  ```

À l’issue de l’exécution de la commande, des indicateurs et un niveau mis à jour pour le fournisseur sont affectés au scénario site:Redmond/RedmondLyssInfo. Vous pouvez examiner le nouveau scénario en utilisant Get-CsClsScenario. Pour plus d’informations, consultez [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).
> [!CAUTION]
> **Nouveau-ClsCsProvider** ne vérifie pas afin de déterminer si les indicateurs sont valides. Assurez-vous que les indicateurs (par exemple, TF_DIAG ou TF_CONNECTION) sont correctement épelés. Si ce n’est pas le cas, le fournisseur ne peut pas retourner les informations du journal attendues.
  
Si vous souhaitez ajouter des fournisseurs supplémentaires à ce scénario, tapez ce qui suit :

```
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

Dans le cas où chaque fournisseur défini avec la directive d’ajouter a déjà définie à l’aide de la procédure **New-CsClsProvider** .
### <a name="to-remove-a-scenario-provider"></a>Pour supprimer un fournisseur de scénario

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Les applets de commande fournies vous permettent de mettre à jour des fournisseurs existants et de créer de nouveaux fournisseurs. Pour supprimer un fournisseur, vous devez utiliser la directive de remplacement du paramètre de fournisseur de **Set-CsClsScenario**. La seule façon de supprimer complètement un fournisseur est de le remplacer par un fournisseur redéfini du même nom et d’utiliser la directive Update. Par exemple, le fournisseur LyssProvider est défini comme suit : WPP comme type de journal, Debug comme niveau, et TF_CONNECTION et TF_DIAG comme indicateurs. Vous devez modifier les indicateurs à « Tout ». Pour modifier le fournisseur, tapez ce qui suit :
    
  ```
  $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
  ```

  ```
  Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
  ```

3. Si vous souhaitez supprimer complètement un scénario et les fournisseurs associés à celui-ci, tapez ce qui suit :
    
  ```
  Remove-CsClsScenario -Identity <scope and name of scenario>
  ```

    Exemple :
    
  ```
  Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
  ```

    > [!CAUTION]
    > L’applet de commande **Remove-CsClsScenario** ne vous demande pas de confirmation. Le scénario est supprimé, ainsi que les fournisseurs affectés à celui-ci. Vous pouvez recréer le scénario en réexécutant les commandes que vous avez utilisées pour le créer initialement. Il n’existe aucune procédure pour récupérer des scénarios ou des fournisseurs supprimés.
  
Lorsque vous supprimez un scénario à l’aide de l’applet de commande **Remove-CsClsScenario** , vous supprimez complètement le scénario à partir de la portée. Pour utiliser les scénarios que vous avez créés et les fournisseurs qui faisaient partie du scénario, vous devez créer de nouveaux fournisseurs et les affecter à un nouveau scénario.
## <a name="see-also"></a>Voir aussi

#### 

[Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[Nouvelle-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[Supprimer-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[Ensemble-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[Nouvelle-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)

