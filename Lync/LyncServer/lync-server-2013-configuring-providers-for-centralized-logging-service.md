---
title: Configuration des fournisseurs pour le service de journalisation centralisée
TOCTitle: Configuration des fournisseurs pour le service de journalisation centralisée
ms:assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688082(v=OCS.15)
ms:contentKeyID: 49891381
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des fournisseurs pour le service de journalisation centralisée

 

_**Dernière rubrique modifiée :** 2014-03-19_

La maîtrise des concepts et de la configuration des *fournisseurs* dans le service de journalisation centralisée est des plus essentielles. Les *fournisseurs* sont directement mappés aux composants du rôle serveur Lync Server dans le modèle de suivi Lync Server. Le fournisseur définit les composants d’un serveur Lync Server 2013 qui feront l’objet d’un suivi, le type de message à collecter (par exemple, Fatal, Error ou Warning) et les indicateurs (par exemple, TF\_Connection ou TF\_Diag). Les fournisseurs sont les composants pouvant faire l’objet d’un suivi dans chaque rôle serveur Lync Server. À l’aide de fournisseurs, vous définissez le niveau et le type de suivi sur les composants (par exemple, S4, SIPStack, Messagerie instantanée et Présence). Le fournisseur défini est utilisé dans un scénario pour regrouper tous les fournisseurs d’une collection logique donnée qui répondent à une condition de problème spécifique.

Pour exécuter les fonctions du service de journalisation centralisée à l’aide de Lync Server Management Shell, vous devez être membre soit des groupes de sécurité de contrôle d’accès en fonction du rôle (RBAC) CsAdministrator ou CsServerAdministrator, soit d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes. Pour retourner une liste de tous les rôles RBAC auxquels cette applet de commande a été affectée (y compris tout rôle RBAC personnalisé que vous avez créé vous-même), exécutez la commande suivante à partir du Lync Server Management Shell ou de l’invite Windows PowerShell :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Par exemple :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

Le reste de cette rubrique porte sur la définition des fournisseurs, la modification d’un fournisseur et ce que contient une définition de fournisseur afin d’optimiser le dépannage. Deux méthodes s’offrent à vous pour émettre des commandes du service de journalisation centralisée. Vous pouvez utiliser le fichier CLSController.exe qui se trouve, par défaut, dans le répertoire C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent. Vous pouvez aussi utiliser Lync Server Management Shell pour émettre des commandes Windows PowerShell. Il est important de noter que lorsque vous utilisez CLSController.exe à la ligne de commande, la sélection de scénarios disponibles dans lesquels les fournisseurs sont déjà définis est limitée et non modifiable ; toutefois, vous pouvez définir le niveau de journalisation. En utilisant Windows PowerShell, vous pouvez définir de nouveaux fournisseurs à utiliser dans vos sessions de journalisation et disposer d’un contrôle complet sur leur création, ce qu’ils collectent et à quel niveau ils collectent des données.

> [!IMPORTANT]  
> Comme nous l’avons précédemment mentionné, les fournisseurs sont très puissants. Cependant, les scénarios le sont davantage, et ce du fait qu’ils contiennent toutes les informations nécessaires pour définir et exécuter le suivi sur les composants que les fournisseurs représentent. Les scénarios étant une collection de fournisseurs, une certaine analogie peut être établie entre, d’une part, l’exécution d’un fichier de commandes qui contient des centaines de commandes destinées à collecter une grande quantité d’informations et, d’autre part, l’émission de centaines de commandes, une à la fois, à la ligne de commande.<br />
Au lieu de vous demander d’étudier en profondeur les détails des fournisseurs, le service de journalisation centralisée fournit un certain nombre de scénarios qui sont déjà définis pour vous. Les scénarios fournis couvrent la grande majorité des problèmes que vous êtes susceptible de rencontrer. Dans de rares cas, vous devrez créer et définir des fournisseurs et les affecter à des scénarios. Nous vous recommandons fortement de vous familiariser avec chacun des scénarios fournis avant d’étudier la nécessité de créer de nouveaux scénarios et de nouveaux fournisseurs. Bien que des informations sur la création de fournisseurs sont données ici pour vous familiariser avec la façon dont les scénarios utilisent les éléments des fournisseurs pour collecter des informations de suivi, aucun détail sur les fournisseurs eux-mêmes n’est fourni pour le moment.

Introduits dans [Présentation du service de journalisation centralisée](lync-server-2013-overview-of-the-centralized-logging-service.md), les éléments clés de la définition d’un fournisseur à utiliser dans un scénario sont les suivants :

  - **Fournisseurs**   Si vous avez déjà utilisé OCSLogger, les fournisseurs sont les composants que vous choisissez pour indiquer à OCSLogger la nature des journaux que le moteur de suivi doit collecter. Les fournisseurs sont les mêmes composants et, dans de nombreux cas, ont le même nom que les composants dans OCSLogger. Si vous ne connaissez pas OCSLogger, les fournisseurs sont des composants spécifiques à un rôle serveur à partir desquels le service de journalisation centralisée peut collecter des journaux. Dans le cas du service de journalisation centralisée, le CLSAgent est la partie architecturale du service de journalisation centralisée qui fait le suivi des composants que vous définissez dans la configuration de fournisseurs.

  - **Niveaux de journalisation** OCSLogger permettait de choisir différents niveaux de détail pour les données collectées. Cette fonctionnalité, qui fait partie intégrante du service de journalisation centralisée et des scénarios, est définie par le paramètre **Type**. Vous avez le choix entre les valeurs suivantes :
    
      - **All**   Collecte des messages de suivi de type Fatal, Error, Warning et Info dans le journal du fournisseur défini.
    
      - **Fatal**   Collecte uniquement les messages de suivi qui indiquent un échec pour le fournisseur défini.
    
      - **Error**   Collecte uniquement les messages de suivi qui indiquent une erreur pour le fournisseur défini, ainsi que les messages de type Fatal.
    
      - **Warning**   Collecte uniquement les messages de suivi qui indiquent un avertissement pour le fournisseur défini, ainsi que les messages de type Fatal et Error.
    
      - **Info**   Collecte uniquement les messages de suivi qui indiquent un message d’information pour le fournisseur défini, ainsi que les messages de type Fatal, Error et Warning.
    
      - **Verbose**   Collecte tous les messages de suivi de type Fatal, Error, Warning et Info pour le fournisseur défini.

  - **Indicateurs**   OCSLogger offrait la possibilité de choisir des indicateurs pour chaque fournisseur afin de définir le type d’information à récupérer à partir des fichiers de suivi. Vous pouvez choisir les indicateurs suivants selon le fournisseur :
    
      - **TF\_Connection**   Fournit des entrées de journal relatives à la connexion. Ces journaux incluent des informations sur les connexions établies depuis et vers un composant particulier. Ils peuvent également comprendre des informations importantes au niveau du réseau (c’est-à-dire, pour les composants sans le concept d’une connexion).
    
      - **TF\_Security**   Fournit l’ensemble des événements/entrées de journal en rapport avec la sécurité. Par exemple, pour SipStack, il s’agit d’événements de sécurité tels que les échecs de validation de domaine et les échecs d’authentification ou d’autorisation du client.
    
      - **TF\_Diag**   Fournit des événements de diagnostic que vous pouvez utiliser pour diagnostiquer ou dépanner le composant. Par exemple, pour SipStack, il s’agit d’échecs de certificat ou d’avertissements/erreurs DNS.
    
      - **TF\_Protocol**   Fournit des messages de protocole tels que les messages SIP et CCCP.
    
      - **TF\_Component**   Permet la journalisation sur les composants spécifiés dans le cadre des fournisseurs.
    
      - **All**   Définit tous les indicateurs disponibles pour le fournisseur.

## Pour examiner des informations sur les fournisseurs de scénario existants du service de journalisation centralisée

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Pour examiner la configuration de fournisseurs existants, tapez ce qui suit :
    
        Get-CsClsScenario -Identity <scope and scenario name>
    
    Par exemple, pour examiner des informations sur l’Intendant Conférence global, tapez :
    
        Get-CsClsScenario -Identity "global/CAA"
    
    La commande affiche une liste de fournisseurs avec les indicateurs, paramètres et composants associés. Si les informations affichées ne sont pas suffisantes ou si la liste est trop longue pour le format de liste Windows PowerShell par défaut, vous pouvez afficher des informations supplémentaires en définissant une méthode de sortie différente. Pour cela, tapez :
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    La sortie de cette commande affiche chaque fournisseur sur cinq lignes avec le nom du fournisseur, le type de journalisation, le niveau d’enregistrement, les indicateurs, le GUID et le rôle sur une ligne distincte.

## Pour définir un nouveau fournisseur de scénario du service de journalisation centralisée

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Un fournisseur de scénario se compose d’un composant à suivre, d’indicateurs à utiliser et d’un niveau de détail à collecter. Pour cela, tapez :
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    Par exemple, une définition de fournisseur de suivi qui définit ce qu’il faut collecter à partir du fournisseur Lyss et à quel niveau de détail ressemble à ceci :
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

–Level collecte les messages Fatal, Error, Warning et Info. Les indicateurs utilisés sont tous ceux définis pour le fournisseur Lyss, à savoir TF\_Connection, TF\_Diag et TF\_Protocol.

Après avoir défini la variable $LyssProvider, vous pouvez l’utiliser avec la nouvelle applet de commande **New-CsClsScenario** pour collecter des suivis à partir du fournisseur Lyss. Pour terminer la création du fournisseur et son affectation à un nouveau scénario, tapez :

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

Où $LyssProvider est la variable qui contient le scénario défini créé avec **New-CsClsProvider**.

## Pour modifier un fournisseur de scénario existant du service de journalisation centralisée

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Pour mettre à jour ou modifier la configuration d’un fournisseur existant, tapez :
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    Vous pouvez ensuite mettre à jour le scénario pour affecter le fournisseur en tapant ce qui suit :
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

À l’issue de l’exécution de la commande, des indicateurs et un niveau mis à jour pour le fournisseur sont affectés au scénario site:Redmond/RedmondLyssInfo. Vous pouvez examiner le nouveau scénario en utilisant Get-CsClsScenario. Pour plus d’informations, voir [Get-CsClsScenario](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsScenario).

> [!WARNING]  
> <strong>New-ClsCsProvider</strong> ne vérifie pas si les indicateurs sont valides. Assurez-vous que les indicateurs (par exemple, TF_DIAG ou TF_CONNECTION) sont correctement épelés. Si ce n’est pas le cas, le fournisseur ne peut pas retourner les informations du journal attendues.

Si vous souhaitez ajouter des fournisseurs supplémentaires à ce scénario, tapez ce qui suit :

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

Où chaque fournisseur défini avec la directive Add a déjà été défini à l’aide du processus **New-CsClsProvider**.

## Pour supprimer un fournisseur de scénario

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Les applets de commande fournies vous permettent de mettre à jour des fournisseurs existants et de créer de nouveaux fournisseurs. Pour supprimer un fournisseur, vous devez utiliser la directive Replace pour le paramètre Provider pour **Set-CsClsScenario**. La seule façon de supprimer complètement un fournisseur est de le remplacer par un fournisseur redéfini du même nom et d’utiliser la directive Update. Par exemple, le fournisseur LyssProvider est défini comme suit : WPP comme type de journal, Debug comme niveau, et TF\_CONNECTION et TF\_DIAG comme indicateurs. Vous devez affecter aux indicateurs la valeur « All ». Pour modifier le fournisseur, tapez ce qui suit :
    
    ```
    $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
    ```
    ```
    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
    ```

3.  Si vous souhaitez supprimer complètement un scénario et les fournisseurs associés à celui-ci, tapez ce qui suit :
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    Par exemple :
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    > [!WARNING]  
    > L’applet de commande <strong>Remove-CsClsScenario</strong> ne vous demande pas confirmation. Le scénario est supprimé, ainsi que les fournisseurs affectés à celui-ci. Vous pouvez recréer le scénario en réexécutant les commandes que vous avez utilisées pour le créer initialement. Il n’existe aucune procédure pour récupérer des scénarios ou des fournisseurs supprimés.

Lorsque vous supprimez un scénario à l’aide de l’applet de commande **Remove-CsClsScenario**, vous supprimez complètement le scénario de l’étendue. Pour utiliser les scénarios que vous avez créés et les fournisseurs qui faisaient partie du scénario, vous devez créer de nouveaux fournisseurs et les affecter à un nouveau scénario.

## Voir aussi

#### Autres ressources

[Get-CsClsScenario](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsScenario)  
[New-CsClsScenario](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsScenario)  
[Remove-CsClsScenario](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClsScenario)  
[Set-CsClsScenario](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsScenario)  
[New-CsClsProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsProvider)

