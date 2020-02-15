---
title: 'Lync Server 2013 : configuration des fournisseurs pour le service de journalisation centralisée'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring providers for Centralized Logging Service
ms:assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688082(v=OCS.15)
ms:contentKeyID: 49733678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51dbb8c1a2e24290e4ab2805bed191e5f2dc86bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a>Configuration des fournisseurs pour le service de journalisation centralisée dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-03-19_

Les concepts et la configuration des *fournisseurs* dans le service de journalisation centralisée sont les plus importants à comprendre. Les *fournisseurs* mappent directement vers les composants de rôle serveur Lync Server dans le modèle de suivi Lync Server. Le fournisseur définit les composants d’un Lync Server 2013 qui seront suivis, le type de messages (par exemple, fatal, erreur ou avertissement) à collecter, ainsi que les indicateurs (par exemple, TF\_Connection ou TF\_diag). Les fournisseurs sont les composants traçables dans chaque rôle serveur Lync Server. À l’aide de fournisseurs, vous définissez le niveau et le type de suivi sur les composants (par exemple, S4, SIPStack, Messagerie instantanée et Présence). Le fournisseur défini est utilisé dans un scénario pour regrouper tous les fournisseurs d’une collection logique donnée qui répondent à une condition de problème spécifique.

Pour exécuter les fonctions du service de journalisation centralisée à l’aide de Lync Server Management Shell, vous devez être membre des groupes de sécurité CsAdministrator ou RBAC (contrôle d’accès basé sur un rôle) CsServerAdministrator, ou d’un rôle RBAC personnalisé qui contient l’une des ces deux groupes. Pour renvoyer la liste de tous les rôles RBAC (contrôle d’accès basé sur un rôle) auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de Lync Server Management Shell ou de l’invite Windows PowerShell :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Par exemple :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

Le reste de cette rubrique porte sur la définition des fournisseurs, la modification d’un fournisseur et ce que contient une définition de fournisseur afin d’optimiser le dépannage. Il existe deux façons d’émettre des commandes de service de journalisation centralisée. Vous pouvez utiliser le CLSController. exe qui se trouve, par défaut, dans le répertoire C :\\Program Files\\Common files\\Microsoft Lync Server 2013\\CLSAgent. Vous pouvez utiliser Lync Server Management Shell pour émettre des commandes Windows PowerShell. Il est important de noter que lorsque vous utilisez CLSController.exe à la ligne de commande, la sélection de scénarios disponibles dans lesquels les fournisseurs sont déjà définis est limitée et non modifiable ; toutefois, vous pouvez définir le niveau de journalisation. À l’aide de Windows PowerShell, vous pouvez définir de nouveaux fournisseurs à utiliser dans vos sessions de journalisation et disposer d’un contrôle total sur leur création, leur collecte et leur niveau de collecte des données.

<div class="">


> [!IMPORTANT]  
> Comme nous l’avons précédemment mentionné, les fournisseurs sont très puissants. Cependant, les scénarios le sont davantage, et ce du fait qu’ils contiennent toutes les informations nécessaires pour définir et exécuter le suivi sur les composants que les fournisseurs représentent. Les scénarios étant une collection de fournisseurs, une certaine analogie peut être établie entre, d’une part, l’exécution d’un fichier de commandes qui contient des centaines de commandes destinées à collecter une grande quantité d’informations et, d’autre part, l’émission de centaines de commandes, une à la fois, à la ligne de commande.<BR>Au lieu de vous demander d’approfondir les détails des fournisseurs, le service de journalisation centralisée fournit un certain nombre de scénarios qui sont déjà définis pour vous. Les scénarios fournis couvrent la grande majorité des problèmes que vous êtes susceptible de rencontrer. Dans de rares cas, vous devrez créer et définir des fournisseurs et les affecter à des scénarios. Nous vous recommandons fortement de vous familiariser avec chacun des scénarios fournis avant d’étudier la nécessité de créer de nouveaux scénarios et de nouveaux fournisseurs. Bien que des informations sur la création de fournisseurs sont données ici pour vous familiariser avec la façon dont les scénarios utilisent les éléments des fournisseurs pour collecter des informations de suivi, aucun détail sur les fournisseurs eux-mêmes n’est fourni pour le moment.



</div>

Introduits dans [Overview of the Centralized Logging Service in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), les éléments clés de la définition d’un fournisseur à utiliser dans un scénario sont les suivants :

  - **Fournisseurs**   si vous êtes familiarisé avec OCSLogger, les fournisseurs sont les composants que vous choisissez pour indiquer à OCSLogger ce que le moteur de suivi doit collecter dans les journaux. Les fournisseurs sont les mêmes composants et, dans de nombreux cas, ont le même nom que les composants dans OCSLogger. Si vous n’êtes pas familiarisé avec OCSLogger, les fournisseurs sont des composants spécifiques au rôle serveur, dont le service de journalisation centralisée peut collecter des journaux. Dans le cas du service de journalisation centralisée, le CLSAgent est la partie architecturale du service de journalisation centralisée qui effectue le suivi des composants que vous définissez dans la configuration des fournisseurs.

  - **Niveaux de journalisation**   OCSLogger offre la possibilité de choisir un certain nombre de niveaux de détail pour les données collectées. Cette fonctionnalité fait partie intégrante du service de journalisation centralisée et des scénarios, et est définie par le paramètre **type** . Vous pouvez choisir l'une des options suivantes :
    
      - **All collecte les**   messages de suivi de type fatal, Error, Warning et info dans le journal pour le fournisseur défini.
    
      - **Fatal**   collecte uniquement les messages de suivi qui indiquent un échec pour le fournisseur défini.
    
      - **Error**   collecte uniquement les messages de suivi qui indiquent une erreur pour le fournisseur défini, ainsi que les messages irrécupérables.
    
      - **Warning**   collecte uniquement les messages de suivi qui indiquent un avertissement pour le fournisseur défini, ainsi que les messages d’erreur et fatale.
    
      - **Info**   collecte uniquement les messages de suivi qui indiquent un message d’information pour le fournisseur défini, ainsi que les messages d’erreur fatale, d’erreur et d’avertissement.
    
      - **Verbose**   collecte tous les messages de suivi de type fatal, Error, Warning et info pour le fournisseur défini.

  - **Indicateurs**   OCSLogger offre la possibilité de choisir des indicateurs pour chaque fournisseur définissant le type d’informations que vous pouvez récupérer dans les fichiers de suivi. Vous pouvez choisir les indicateurs suivants selon le fournisseur :
    
      - **TF\_Connection**   fournit des entrées de journal liées à la connexion. Ces journaux incluent des informations sur les connexions établies depuis et vers un composant particulier. Ils peuvent également comprendre des informations importantes au niveau du réseau (c’est-à-dire, pour les composants sans le concept d’une connexion).
    
      - **TF\_Security**   fournit tous les événements/entrées de journal liés à la sécurité. Par exemple, pour SipStack, il s’agit d’événements de sécurité tels que les échecs de validation de domaine et les échecs d’authentification ou d’autorisation du client.
    
      - **TF\_diag**   fournit des événements de diagnostic que vous pouvez utiliser pour diagnostiquer ou dépanner le composant. Par exemple, pour SipStack, il s’agit d’échecs de certificat ou d’avertissements/erreurs DNS.
    
      - **Le\_protocole**   TF fournit des messages de protocole, tels que SIP et les messages du Pack de codecs communautaires combinés.
    
      - **Le\_composant**   TF active la journalisation sur les composants spécifiés dans le cadre des fournisseurs.
    
      - **All**   définit tous les indicateurs disponibles pour le fournisseur.

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>Pour consulter les informations sur les fournisseurs de scénarios de service de journalisation centralisée existants

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Pour examiner la configuration de fournisseurs existants, tapez ce qui suit :
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    Par exemple, pour examiner des informations sur l’Intendant Conférence global, tapez :
    
        Get-CsClsScenario -Identity "global/CAA"
    
    La commande affiche une liste de fournisseurs avec les indicateurs, paramètres et composants associés. Si les informations affichées ne sont pas suffisantes ou si la liste est trop longue pour le format de liste Windows PowerShell par défaut, vous pouvez afficher des informations supplémentaires en définissant une autre méthode de sortie. Pour cela, tapez :
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    La sortie de cette commande affiche chaque fournisseur sur cinq lignes avec le nom du fournisseur, le type de journalisation, le niveau d’enregistrement, les indicateurs, le GUID et le rôle sur une ligne distincte.

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>Pour définir un nouveau fournisseur de scénario de service de journalisation centralisée

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Un fournisseur de scénario se compose d’un composant à suivre, d’indicateurs à utiliser et d’un niveau de détail à collecter. Pour cela, tapez :
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    Par exemple, une définition de fournisseur de suivi qui définit ce qu’il faut collecter à partir du fournisseur Lyss et à quel niveau de détail ressemble à ceci :
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

–Level collecte les messages Fatal, Error, Warning et Info. Les indicateurs utilisés sont tous ceux définis pour le fournisseur Lyss, et incluent la connexion\_TF, TF\_diag et TF\_Protocol.

Après avoir défini la variable $LyssProvider, vous pouvez l’utiliser avec la nouvelle applet de commande **New-CsClsScenario** pour collecter des suivis à partir du fournisseur Lyss. Pour terminer la création du fournisseur et son affectation à un nouveau scénario, tapez :

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

Où $LyssProvider est la variable qui contient le scénario défini créé avec **New-CsClsProvider**.

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>Pour modifier un fournisseur de scénario de service de journalisation centralisé existant

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Pour mettre à jour ou modifier la configuration d’un fournisseur existant, tapez :
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    Vous pouvez ensuite mettre à jour le scénario pour affecter le fournisseur en tapant ce qui suit :
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

À l’issue de l’exécution de la commande, des indicateurs et un niveau mis à jour pour le fournisseur sont affectés au scénario site:Redmond/RedmondLyssInfo. Vous pouvez examiner le nouveau scénario en utilisant Get-CsClsScenario. Pour plus d’informations, voir [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).

<div class="">


> [!WARNING]  
> <STRONG>New-ClsCsProvider</STRONG> ne vérifie pas si les indicateurs sont valides. Assurez-vous que les indicateurs (par exemple, TF_DIAG ou TF_CONNECTION) sont correctement épelés. Si ce n’est pas le cas, le fournisseur ne peut pas retourner les informations du journal attendues.



</div>

Si vous souhaitez ajouter des fournisseurs supplémentaires à ce scénario, tapez ce qui suit :

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

Où chaque fournisseur défini avec la directive Add a déjà été défini à l’aide du processus **New-CsClsProvider**.

</div>

<div>

## <a name="to-remove-a-scenario-provider"></a>Pour supprimer un fournisseur de scénario

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Les applets de commande fournies vous permettent de mettre à jour des fournisseurs existants et de créer de nouveaux fournisseurs. Pour supprimer un fournisseur, vous devez utiliser la directive Replace pour le paramètre Provider pour **Set-CsClsScenario**. La seule façon de supprimer complètement un fournisseur est de le remplacer par un fournisseur redéfini du même nom et d’utiliser la directive Update. Par exemple, notre fournisseur LyssProvider est défini avec WPP comme type de journal, niveau défini sur déboguer et ensemble d’indicateurs\_sont connexion TF\_et TF diag. Vous devez affecter aux indicateurs la valeur « All ». Pour modifier le fournisseur, tapez ce qui suit :
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

     &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  Si vous souhaitez supprimer complètement un scénario et les fournisseurs associés à celui-ci, tapez ce qui suit :
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    Par exemple :
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    <div class="">
    

    > [!WARNING]  
    > L’applet de commande <STRONG>Remove-CsClsScenario</STRONG> ne vous demande pas confirmation. Le scénario est supprimé, ainsi que les fournisseurs affectés à celui-ci. Vous pouvez recréer le scénario en réexécutant les commandes que vous avez utilisées pour le créer initialement. Il n’existe aucune procédure pour récupérer des scénarios ou des fournisseurs supprimés.

    
    </div>

Lorsque vous supprimez un scénario à l’aide de l’applet de commande **Remove-CsClsScenario**, vous supprimez complètement le scénario de l’étendue. Pour utiliser les scénarios que vous avez créés et les fournisseurs qui faisaient partie du scénario, vous devez créer de nouveaux fournisseurs et les affecter à un nouveau scénario.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)  
[New-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/New-CsClsScenario)  
[Remove-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Remove-CsClsScenario)  
[Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario)  
[New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

