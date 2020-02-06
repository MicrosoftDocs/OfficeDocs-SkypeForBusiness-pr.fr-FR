---
title: Configuration des fournisseurs pour le service de journalisation centralisée dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: 'Résumé : Découvrez comment configurer des fournisseurs de scénarios pour le service de journalisation centralisé dans Skype entreprise Server 2015.'
ms.openlocfilehash: e2c633dabf30ffbc42fa90066bf469e10dc25fb6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816603"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a>Configuration des fournisseurs pour le service de journalisation centralisée dans Skype Entreprise Server 2015
 
**Résumé :** Apprenez à configurer les fournisseurs de scénarios pour le service de journalisation centralisé dans Skype entreprise Server 2015.
  
Les concepts et la configuration des fournisseurs dans le service de journalisation centralisé sont les plus importants à comprendre. Theproviders mappez directement aux composants du rôle serveur Skype entreprise Server dans le modèle de suivi de Skype entreprise Server. Le fournisseur définit les composants d’une 2015 Skype entreprise Server qui sera tracée, le type de messages (par exemple, irrécupérable, erreur ou avertissement) à collecter et les indicateurs (par exemple, TF_Connection ou TF_Diag). Les fournisseurs sont les composants traçables de chaque rôle serveur Skype entreprise Server. À l’aide de fournisseurs, vous définissez le niveau et le type de suivi sur les composants (par exemple, S4, SIPStack, Messagerie instantanée et Présence). Le fournisseur défini est utilisé dans un scénario pour regrouper tous les fournisseurs d’une collection logique donnée qui répondent à une condition de problème spécifique.
  
Pour exécuter les fonctions de service de journalisation centralisées à l’aide de Skype entreprise Server Management Shell, vous devez être membre des groupes de sécurité CsAdministrator ou CsServerAdministrator de contrôle d’accès basé sur les rôles (RBAC), ou un rôle RBAC personnalisé qui contient l’un de ces deux groupes. Pour renvoyer la liste de tous les rôles de contrôle d’accès basés sur des rôles (RBAC) affectés à cette applet de commande (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de Skype entreprise Server Management Shell ou Windows PowerShell demandant
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Exemple :
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

Le reste de cette rubrique met l’accent sur la définition des fournisseurs, la modification d’un fournisseur et la spécification du contenu d’un fournisseur afin d’optimiser votre dépannage. Il existe deux façons d’envoyer des commandes de service de journalisation centralisées. Vous pouvez utiliser le fichier CLSController.exe qui se trouve, par défaut, dans le répertoire C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent. Vous pouvez utiliser Skype entreprise Server Management Shell pour exécuter les commandes Windows PowerShell. À l’aide de Windows PowerShell, vous pouvez définir de nouveaux fournisseurs à utiliser dans vos sessions de journalisation et disposer d’un contrôle total sur la création, la collecte et le niveau de collecte des données.
  
> [!IMPORTANT]
> Comme nous l’avons précédemment mentionné, les fournisseurs sont très puissants. Cependant, les scénarios le sont davantage, et ce du fait qu’ils contiennent toutes les informations nécessaires pour définir et exécuter le suivi sur les composants que les fournisseurs représentent. Les scénarios étant une collection de fournisseurs, une certaine analogie peut être établie entre, d’une part, l’exécution d’un fichier de commandes qui contient des centaines de commandes destinées à collecter une grande quantité d’informations et, d’autre part, l’émission de centaines de commandes, une à la fois, à la ligne de commande. 
  
Au lieu de vous demander de vous plonger dans les détails des fournisseurs, le service de journalisation centralisé fournit un certain nombre de scénarios déjà définis pour vous. Les scénarios fournis couvrent la grande majorité des problèmes que vous êtes susceptible de rencontrer. Dans de rares cas, vous devrez créer et définir des fournisseurs et les affecter à des scénarios. Nous vous recommandons fortement de vous familiariser avec chacun des scénarios fournis avant d’étudier la nécessité de créer de nouveaux scénarios et de nouveaux fournisseurs. Bien que des informations sur la création de fournisseurs sont données ici pour vous familiariser avec la façon dont les scénarios utilisent les éléments des fournisseurs pour collecter des informations de suivi, aucun détail sur les fournisseurs eux-mêmes n’est fourni pour le moment. 
  
Introduction dans le [service de journalisation centralisée de Skype entreprise 2015](centralized-logging-service.md), les principaux éléments de la définition d’un fournisseur pour une utilisation dans un scénario sont les suivants :
  
- **Fournisseurs** Si vous avez l’habitude d’utiliser OCSLogger, les fournisseurs sont les composants que vous choisissez pour indiquer à OCSLogger ce sur quoi le moteur de suivi doit collecter les journaux. Les fournisseurs sont les mêmes composants et, dans de nombreux cas, ont le même nom que les composants dans OCSLogger. Si vous n’êtes pas familiarisé avec l’utilisation de OCSLogger, les fournisseurs sont des composants spécifiques au rôle serveur pour lesquels le service de journalisation centralisé peut collecter des journaux. Dans le cas d’un service de journalisation centralisé, le CLSAgent est la partie architecturale du service de journalisation centralisé qui effectue le suivi des composants que vous définissez dans la configuration des fournisseurs.
    
- **Niveaux de journalisation** OCSLogger vous a permis de choisir un certain nombre de niveaux de détail pour les données collectées. Cette fonctionnalité fait partie intégrante du service de journalisation centralisé et des scénarios, et est définie par le paramètre de **type** . Vous avez le choix entre les valeurs suivantes :
    
  - **All (tous** ) Collecte les messages de suivi de type irrécupérable, erreur, avertissement, commentaires et informations de débogage du journal du fournisseur défini.
    
  - **Erreur irrécupérable** Recueille uniquement les messages de suivi définis comme « irrécupérables ».
    
  - **Erreur** Recueille uniquement les messages de suivi définis comme « erreur » ou « irrécupérable ».
    
  - **Avertissement** Recueille uniquement les messages de suivi de type « avertissement », « erreur » et « irrécupérable ».
    
  - **Infos** Recueille uniquement les messages de suivi qui indiquent un message d’information pour le fournisseur défini, ainsi que les messages d’avertissement ou d’erreur irrécupérable.
    
  - **Commentaires** Recueille tous les messages de suivi de type irrécupérable, erreur, avertissement et détaillé pour le fournisseur défini.
    
  - Le **débogage** est essentiellement un équivalent de « All », qui rassemble les traces de type irrécupérable, erreur, avertissement, informations, détaillé et débogage du fournisseur défini.
    
- **Indicateurs** OCSLogger a fourni l’option de sélection d’indicateurs pour chaque fournisseur définissant le type d’informations que vous pouvez récupérer dans les fichiers de suivi. Vous pouvez choisir les indicateurs suivants selon le fournisseur :
    
  - **TF_Connection** Fournit des entrées de journal liées à la connexion. Ces journaux incluent des informations sur les connexions établies depuis et vers un composant particulier. Ils peuvent également comprendre des informations importantes au niveau du réseau (c’est-à-dire, pour les composants sans le concept d’une connexion).
    
  - **TF_Security** Fournit les entrées d’événements/de journal relatives à la sécurité. Par exemple, pour SipStack, il s’agit d’événements de sécurité tels que les échecs de validation de domaine et les échecs d’authentification ou d’autorisation du client.
    
  - **TF_Diag** Fournit des événements de diagnostics que vous pouvez utiliser pour diagnostiquer ou résoudre les problèmes liés au composant. Par exemple, pour SipStack, il s’agit d’échecs de certificat ou d’avertissements/erreurs DNS.
    
  - **TF_Protocol** Fournit des messages de protocole tels que SIP et les messages du Pack de codecs de la Communauté combinée.
    
  - **TF_Component** Permet de se connecter aux composants spécifiés dans le cadre des fournisseurs.
    
  - **All (tous** ) Définit tous les indicateurs disponibles disponibles pour le fournisseur.
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>Pour consulter des informations sur les fournisseurs de scénarios de service de journalisation centralisée existants

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
2. Pour examiner la configuration de fournisseurs existants, tapez ce qui suit :
    
   ```PowerShell
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    Par exemple, pour examiner des informations sur l’Intendant Conférence global, tapez :
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA"
   ```

    La commande affiche une liste de fournisseurs avec les indicateurs, paramètres et composants associés. Si les informations affichées ne sont pas suffisantes ou si la liste est trop longue pour le format de liste Windows PowerShell par défaut, vous pouvez afficher des informations supplémentaires en définissant une autre méthode de sortie. Pour cela, tapez :
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    La sortie de cette commande affiche chaque fournisseur sur cinq lignes avec le nom du fournisseur, le type de journalisation, le niveau d’enregistrement, les indicateurs, le GUID et le rôle sur une ligne distincte. 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>Pour définir un nouveau fournisseur de scénarios de service de journalisation centralisée

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
2. Un fournisseur de scénario se compose d’un composant à suivre, d’indicateurs à utiliser et d’un niveau de détail à collecter. Pour cela, tapez :
    
   ```PowerShell
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    Par exemple, une définition de fournisseur de suivi qui définit ce qu’il faut collecter à partir du fournisseur Lyss et à quel niveau de détail ressemble à ceci :
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

Le niveau de données collecte les messages d’erreur, d’avertissement et d’erreur irrécupérable. Les indicateurs utilisés sont tous ceux définis pour le fournisseur Lyss et incluent TF_Connection, TF_Diag et TF_Protocol. une fois la variable $LyssProvider définie, vous pouvez l’utiliser avec l’applet **de nouvelle cmdlet New-CsClsScenario** pour collecter des traces du fournisseur de Lyss. Pour terminer la création du fournisseur et son affectation à un nouveau scénario, tapez :

```PowerShell
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

Où $LyssProvider est la variable qui contient le scénario défini créé avec **New-CsClsProvider**.
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>Pour modifier un fournisseur de scénarios de service de journalisation centralisé existant

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
2. Pour mettre à jour ou modifier la configuration d’un fournisseur existant, tapez :
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    Vous pouvez ensuite mettre à jour le scénario pour affecter le fournisseur en tapant ce qui suit :
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

À l’issue de l’exécution de la commande, des indicateurs et un niveau mis à jour pour le fournisseur sont affectés au scénario site:Redmond/RedmondLyssInfo. Vous pouvez examiner le nouveau scénario en utilisant Get-CsClsScenario. Pour plus d’informations, voir [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).
> [!CAUTION]
> **New-ClsCsProvider** ne vérifie pas si les indicateurs sont valides. Assurez-vous que les indicateurs (par exemple, TF_DIAG ou TF_CONNECTION) sont correctement épelés. Si ce n’est pas le cas, le fournisseur ne peut pas retourner les informations du journal attendues.
  
Si vous souhaitez ajouter des fournisseurs supplémentaires à ce scénario, tapez ce qui suit :

```PowerShell
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

Où chaque fournisseur défini avec la directive Add a déjà été défini à l’aide du processus **New-CsClsProvider**.
### <a name="to-remove-a-scenario-provider"></a>Pour supprimer un fournisseur de scénario

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
2. Les applets de commande fournies vous permettent de mettre à jour des fournisseurs existants et de créer de nouveaux fournisseurs. Pour supprimer un fournisseur, vous devez utiliser la directive Replace pour le paramètre Provider pour **Set-CsClsScenario**. La seule façon de supprimer complètement un fournisseur est de le remplacer par un fournisseur redéfini du même nom et d’utiliser la directive Update. Par exemple, le fournisseur LyssProvider est défini comme suit : WPP comme type de journal, Debug comme niveau, et TF_CONNECTION et TF_DIAG comme indicateurs. Vous devez remplacer les indicateurs par « All ». Pour modifier le fournisseur, tapez ce qui suit :
    
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

    Exemple :
    
   ```PowerShell
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
