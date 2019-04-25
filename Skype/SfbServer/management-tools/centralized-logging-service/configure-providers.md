---
title: Configuration des fournisseurs pour le service de journalisation centralisée dans Skype Entreprise Server 2015
ms.reviewer: ''
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
description: 'Résumé : Découvrez comment configurer des fournisseurs de scénario pour le Service de journalisation centralisée Skype pour Business Server 2015.'
ms.openlocfilehash: 36eb16eb1aea584e1ca28670ea75bd3a262ceb1a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217501"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a>Configuration des fournisseurs pour le service de journalisation centralisée dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment configurer des fournisseurs de scénario pour le Service de journalisation centralisée Skype pour Business Server 2015.
  
Les concepts et la configuration de fournisseurs de Service de journalisation centralisée est un des plus importants à comprendre. Theproviders correspondent directement aux Skype pour les composants de rôle de serveur Business Server dans le Skype pour le modèle de suivi du serveur d’entreprise. Le fournisseur définit les composants d’un Skype pour Business Server 2015 qui vont être tracées, le type de messages (par exemple, irrécupérable, erreur ou avertissement) pour collecter et les indicateurs (par exemple, TF_Connection ou TF_Diag). Fournisseurs sont les composants reconstituer dans chaque Skype pour le rôle de serveur Business Server. À l’aide de fournisseurs, vous définissez le niveau et le type de suivi sur les composants (par exemple, S4, SIPStack, Messagerie instantanée et Présence). Le fournisseur défini est utilisé dans un scénario pour regrouper tous les fournisseurs d’une collection logique donnée qui répondent à une condition de problème spécifique.
  
Pour exécuter les fonctions de Service de journalisation centralisée à l’aide de la Skype pour Business Server Management Shell, vous devez être un membre de la CsAdministrator ou les groupes de sécurité CsServerAdministrator accès basé sur un rôle RBAC (contrôle) ou un rôle RBAC personnalisé qui contient une de ces deux groupes. Pour retourner une liste de tous les rôles RBAC (contrôle) d’accès basé sur le rôle de cette applet de commande a été assigné (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de la Skype pour Business Server Management Shell ou de Windows PowerShell invite de commandes :
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Exemple :
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

Le reste de cette rubrique met l’accent sur la définition des fournisseurs, la modification d’un fournisseur et la spécification du contenu d’un fournisseur afin d’optimiser votre dépannage. Il existe deux façons d’émettre des commandes de Service de journalisation centralisée. Vous pouvez utiliser le fichier CLSController.exe qui se trouve, par défaut, dans le répertoire C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent. Ou bien, vous pouvez utiliser la Skype pour Business Server Management Shell pour exécuter des commandes de Windows PowerShell. À l’aide de Windows PowerShell, vous pouvez définir des nouveaux fournisseurs à utiliser dans vos sessions de journalisation et contrôler leur création, qu’ils collectent, et à quel niveau collecter des données.
  
> [!IMPORTANT]
> Comme nous l’avons précédemment mentionné, les fournisseurs sont très puissants. Cependant, les scénarios le sont davantage, et ce du fait qu’ils contiennent toutes les informations nécessaires pour définir et exécuter le suivi sur les composants que les fournisseurs représentent. Les scénarios étant une collection de fournisseurs, une certaine analogie peut être établie entre, d’une part, l’exécution d’un fichier de commandes qui contient des centaines de commandes destinées à collecter une grande quantité d’informations et, d’autre part, l’émission de centaines de commandes, une à la fois, à la ligne de commande. 
  
Au lieu de devoir approfondir profondément les détails des fournisseurs, le Service de journalisation centralisée fournit un certain nombre de scénarios qui sont déjà définies pour vous. Les scénarios fournis couvrent la grande majorité des problèmes que vous êtes susceptible de rencontrer. Dans de rares cas, vous devrez créer et définir des fournisseurs et les affecter à des scénarios. Nous vous recommandons fortement de vous familiariser avec chacun des scénarios fournis avant d’étudier la nécessité de créer de nouveaux scénarios et de nouveaux fournisseurs. Bien que des informations sur la création de fournisseurs sont données ici pour vous familiariser avec la façon dont les scénarios utilisent les éléments des fournisseurs pour collecter des informations de suivi, aucun détail sur les fournisseurs eux-mêmes n’est fourni pour le moment. 
  
Introduite dans [Centralized Logging Service dans Skype pour Business 2015](centralized-logging-service.md), les éléments clés de la définition d’un fournisseur à utiliser dans un scénario sont les suivants :
  
- **Fournisseurs** Si vous êtes familiarisé avec OCSLogger, fournisseurs sont les composants que vous choisissez pour indiquer OCSLogger quel le moteur de suivi doit collecter des journaux. Les fournisseurs sont les mêmes composants et, dans de nombreux cas, ont le même nom que les composants dans OCSLogger. Si vous n’êtes pas familiarisé avec OCSLogger, les fournisseurs sont server-role certains composants qui le Service de journalisation centralisée peut collecter les journaux de. Dans le cas du Service de journalisation centralisée, et le CLSAgent est la partie architecturale de the Centralized Logging Service qui effectue le suivi des composants que vous définissez dans la configuration des fournisseurs.
    
- **Niveaux d’enregistrement** OCSLogger fourni l’option pour choisir un nombre de niveaux de détail des données collectées. Cette fonctionnalité fait partie intégrante du Service de journalisation centralisée et des scénarios et est définie par le paramètre de **Type** . Vous avez le choix entre les valeurs suivantes :
    
  - **Tous les** Collecte de messages de type fatal, erreur, avertissement, commentaires et les informations de débogage dans le journal de suivi pour le fournisseur défini.
    
  - **Irrécupérable** Collecte uniquement les messages de suivi définies en tant que « Fatal ».
    
  - **Erreur** Collecte uniquement les messages de suivi définis comme « Erreur » ou « Fatal ».
    
  - **Avertissement** Collecte uniquement les messages de suivi de type « Warning », « Erreur » et « Irrécupérable ».
    
  - **Info** Collecte uniquement les messages de suivi qui indiquent un message d’information pour le fournisseur défini, ainsi qu’irrécupérable, erreur et messages d’avertissement.
    
  - **Verbose** Collecte tous les messages de suivi de l’erreur irrécupérable, type, d’avertissement et verbose pour le fournisseur défini.
    
  - **Débogage** c’est essentiellement l’équivalent de « Tous » - traces de collecte de type Fatal, erreur, avertissement, informations, commentaires et débogage pour le fournisseur défini.
    
- **Indicateurs** OCSLogger fourni l’option pour choisir les indicateurs pour chaque fournisseur défini le type d’informations que vous pouvez récupérer à partir des fichiers de suivi. Vous pouvez choisir les indicateurs suivants selon le fournisseur :
    
  - **TF_Connection** Fournit des entrées du journal liées à la connexion. Ces journaux incluent des informations sur les connexions établies depuis et vers un composant particulier. Ils peuvent également comprendre des informations importantes au niveau du réseau (c’est-à-dire, pour les composants sans le concept d’une connexion).
    
  - **TF_Security** Fournit toutes les entrées du journal des événements liées à la sécurité. Par exemple, pour SipStack, il s’agit d’événements de sécurité tels que les échecs de validation de domaine et les échecs d’authentification ou d’autorisation du client.
    
  - **TF_Diag** Fournit des événements de diagnostic que vous pouvez utiliser pour diagnostiquer ou de résoudre le composant. Par exemple, pour SipStack, il s’agit d’échecs de certificat ou d’avertissements/erreurs DNS.
    
  - **TF_Protocol** Fournit des messages de protocole tels que les messages SIP et combinés Communauté Codec Pack.
    
  - **TF_Component** Active la journalisation sur les composants spécifiés dans le cadre des fournisseurs.
    
  - **Tous les** Définit tous les indicateurs disponibles pour le fournisseur.
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>Pour passer en revue les informations sur les fournisseurs de scénario de Service de journalisation centralisée existants

1. Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.
    
2. Pour examiner la configuration de fournisseurs existants, tapez ce qui suit :
    
   ```
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    Par exemple, pour examiner des informations sur l’Intendant Conférence global, tapez :
    
   ```
   Get-CsClsScenario -Identity "global/CAA"
   ```

    La commande affiche une liste de fournisseurs avec les indicateurs, paramètres et composants associés. Si les informations affichées ne sont pas suffisamment ou la liste est trop longue pour le format par défaut de Windows PowerShell, vous pouvez afficher des informations supplémentaires en définissant une méthode de sortie différent. Pour cela, tapez :
    
   ```
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    La sortie de cette commande affiche chaque fournisseur sur cinq lignes avec le nom du fournisseur, le type de journalisation, le niveau d’enregistrement, les indicateurs, le GUID et le rôle sur une ligne distincte. 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>Pour définir un nouveau fournisseur de scénario de Service de journalisation centralisée

1. Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.
    
2. Un fournisseur de scénario se compose d’un composant à suivre, d’indicateurs à utiliser et d’un niveau de détail à collecter. Pour cela, tapez :
    
   ```
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    Par exemple, une définition de fournisseur de suivi qui définit ce qu’il faut collecter à partir du fournisseur Lyss et à quel niveau de détail ressemble à ceci :
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

-Collectées par niveau irrécupérable, erreur, avertissement et informations les messages. Les indicateurs utilisés sont tous les paramètres définis pour le fournisseur Lyss et incluent TF_Connection, TF_Diag et TF_Protocol.After la variable $LyssProvider est définie, vous pouvez l’utiliser avec l’applet de commande **New-CsClsScenario** à collecter les suivis à partir du fournisseur Lyss. Pour terminer la création du fournisseur et son affectation à un nouveau scénario, tapez :

```
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

Où $LyssProvider est la variable qui contient le scénario défini créé avec **New-CsClsProvider**.
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>Pour modifier un fournisseur de scénario de Service de journalisation centralisée existant

1. Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.
    
2. Pour mettre à jour ou modifier la configuration d’un fournisseur existant, tapez :
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    Vous pouvez ensuite mettre à jour le scénario pour affecter le fournisseur en tapant ce qui suit :
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

À l’issue de l’exécution de la commande, des indicateurs et un niveau mis à jour pour le fournisseur sont affectés au scénario site:Redmond/RedmondLyssInfo. Vous pouvez examiner le nouveau scénario en utilisant Get-CsClsScenario. Pour plus d’informations, voir [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).
> [!CAUTION]
> **New-ClsCsProvider** ne vérifie pas si les indicateurs sont valides. Assurez-vous que les indicateurs (par exemple, TF_DIAG ou TF_CONNECTION) sont correctement épelés. Si ce n’est pas le cas, le fournisseur ne peut pas retourner les informations du journal attendues.
  
Si vous souhaitez ajouter des fournisseurs supplémentaires à ce scénario, tapez ce qui suit :

```
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

Où chaque fournisseur défini avec la directive Add a déjà été défini à l’aide du processus **New-CsClsProvider**.
### <a name="to-remove-a-scenario-provider"></a>Pour supprimer un fournisseur de scénario

1. Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.
    
2. Les applets de commande fournies vous permettent de mettre à jour des fournisseurs existants et de créer de nouveaux fournisseurs. Pour supprimer un fournisseur, vous devez utiliser la directive Replace pour le paramètre Provider pour **Set-CsClsScenario**. La seule façon de supprimer complètement un fournisseur est de le remplacer par un fournisseur redéfini du même nom et d’utiliser la directive Update. Par exemple, le fournisseur LyssProvider est défini comme suit : WPP comme type de journal, Debug comme niveau, et TF_CONNECTION et TF_DIAG comme indicateurs. Vous devez modifier les indicateurs à « Toutes ». Pour modifier le fournisseur, tapez ce qui suit :
    
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
    > L’applet de commande **Remove-CsClsScenario** ne vous demande pas confirmation. Le scénario est supprimé, ainsi que les fournisseurs affectés à celui-ci. Vous pouvez recréer le scénario en réexécutant les commandes que vous avez utilisées pour le créer initialement. Il n’existe aucune procédure pour récupérer des scénarios ou des fournisseurs supprimés.
  
Lorsque vous supprimez un scénario à l’aide de l’applet de commande **Remove-CsClsScenario**, vous supprimez complètement le scénario de l’étendue. Pour utiliser les scénarios que vous avez créés et les fournisseurs qui faisaient partie du scénario, vous devez créer de nouveaux fournisseurs et les affecter à un nouveau scénario.
## <a name="see-also"></a>Voir aussi

[Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[New-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[Remove-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)
