---
title: Attribution d’une stratégie de plan de numérotation par utilisateur
TOCTitle: Attribution d’une stratégie de plan de numérotation par utilisateur
ms:assetid: 9fea861f-7770-4cae-9b1f-2a960595bfc9
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688156(v=OCS.15)
ms:contentKeyID: 49891466
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Attribution d’une stratégie de plan de numérotation par utilisateur

 

_**Dernière rubrique modifiée :** 2013-02-22_

Pour terminer la configuration des comptes d’utilisateurs des utilisateurs de Voix Entreprise ou de conférence rendez-vous, il convient de leur assigner un plan de numérotation. Les comptes d’utilisateurs utilisent automatiquement le plan de numérotation global ou, s’il en existe un, le plan de numérotation au niveau du site si vous n’assignez pas de manière explicite un plan de numérotation utilisateur existant. Si vous voulez utiliser le plan de numérotation global ou de site pour tous les utilisateurs activés pour Voix Entreprise, vous pouvez ignorer cette section.

## Pour assigner un plan de numérotation à l’aide du Panneau de configuration Lync Server 2013

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez activer, puis cliquez sur **Rechercher**.

5.  Dans le tableau, cliquez sur le compte d’utilisateur auquel vous voulez assigner un plan de numérotation.

6.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

7.  Dans la page **Modifier l’utilisateur Lync Server**, sous **Téléphonie**, cliquez sur **Voix Entreprise**.

8.  Cliquez sur **Stratégie de plan de numérotation**, puis choisissez le plan de numérotation souhaité.

9.  Cliquez sur **Valider**.

Pour plus d’informations sur la configuration des plans de numérotation, voir la rubrique [Configuration des plans de numérotation dans Lync Server 2013](lync-server-2013-configuring-dial-plans.md).

## Pour assigner un plan de numérotation à l’aide de Lync Server 2013 Management Shell

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Pour assigner un plan de numérotation spécifique à un utilisateur, exécutez la commande suivante à l’invite :
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    Par exemple :
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    Dans cet exemple, l’utilisateur dont le nom complet est Bob Kelly s’est vu assigner le plan de numérotation utilisateur intitulé **DialPlanJapan**.

Pour plus d’informations sur l’assignation d’un plan de numérotation utilisateur ou sur l’exécution de l’applet de commande **Grant-CsDialPlan**, voir la documentation de [Lync Server Management Shell](lync-server-2013-lync-server-management-shell.md).

## Assignation d’un plan de numérotation par utilisateur à l’aide d’applets de commande Windows PowerShell

Les plans de numérotation par utilisateur peuvent également être assignés à l’aide de Windows PowerShell et de l’applet de commande **Grant-CsdialPlan**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Assignation d’un plan de numérotation par utilisateur à un utilisateur unique

  - La commande suivante assigne le plan de numérotation par utilisateur RedmondDialPlan à l’utilisateur Ken Myer.
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## Assignation d’un plan de numérotation par utilisateur à plusieurs utilisateurs

  - Cette commande assigne le plan de numérotation par utilisateur RedmondDialPlan à tous les utilisateurs qui travaillent dans la ville de Redmond. Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, voir la documentation de l’applet de commande [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser).
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## Annulation de l’assignation d’un plan de numérotation par utilisateur

  - La commande suivante annule l’assignation d’un plan de numérotation par utilisateur précédemment assigné à Ken Myer. Une fois l’assignation du plan de numérotation par utilisateur annulée, Ken Myer sera géré automatiquement à l’aide du plan de numérotation global, de son plan de numérotation de site local (s’il en existe un) ou du plan de numérotation à l’échelle du service assigné à son serveur d’inscriptions ou à sa passerelle PSTN. Un plan de numérotation à l’échelle du service est prioritaire par rapport à tout plan de numérotation de site et un plan de numérotation de site est prioritaire par rapport au plan de numérotation global.
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Grant-CsDialPlan](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsDialPlan).

## Voir aussi

#### Autres ressources

[Configuration des plans de numérotation dans Lync Server 2013](lync-server-2013-configuring-dial-plans.md)  
[Comptes d’utilisateur activés pour Lync Server 2013](lync-server-2013-user-accounts-enabled-for-lync-server.md)

