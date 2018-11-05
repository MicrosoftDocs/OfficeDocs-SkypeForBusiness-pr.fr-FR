---
title: Affectation d’une stratégie de voix par utilisateur
TOCTitle: Affectation d’une stratégie de voix par utilisateur
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49891468
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Affectation d’une stratégie de voix par utilisateur

 

_**Dernière rubrique modifiée :** 2013-02-22_

Les stratégies de voix au niveau global ou au niveau du site sont automatiquement assignées à tous les comptes d’utilisateurs Lync Server 2013 activés pour Voix Enterprise. Vous pouvez également assigner des stratégies de voix à des utilisateurs spécifiques à l’aide du Panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell. Appliquez les procédures de cette rubrique pour assigner de manière explicite des stratégies par utilisateur à des utilisateurs Lync Server.

## Pour assigner une stratégie de voix spécifique à l’utilisateur à l’aide du Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.

4.  Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier l’utilisateur Lync Server** sous **Stratégie de voix**, sélectionnez la stratégie d’utilisateur à appliquer.
    
    > [!NOTE]  
    > Les paramètres <strong>&lt;Automatique&gt;</strong> appliquent les paramètres de stratégie globale ou du serveur par défaut.

## Pour assigner une stratégie de voix spécifique à l’utilisateur à l’aide de Lync Server Management Shell

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Pour assigner une stratégie de voix utilisateur existante à un utilisateur, exécutez la commande suivante à l’invite :
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    Par exemple :
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    Dans cet exemple, l’utilisateur dont le nom complet est Bob Kelly a reçu la stratégie de voix portant le nom **VoicePolicyJapan**.

Pour plus d’informations sur l’assignation d’une stratégie de voix spécifique à l’utilisateur ou sur l’exécution de l’applet de commande **Grant-CsVoicePolicy**, voir la documentation de [Lync Server Management Shell](lync-server-2013-lync-server-management-shell.md).

## Assignation d’une stratégie de voix par utilisateur à l’aide d’applets de commande Windows PowerShell

Les stratégies de voix par utilisateur peuvent également être assignées à l’aide de Windows PowerShell et de l’applet de commande **Grant-CsVoicePolicy**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Assignation d’une stratégie de voix par utilisateur à un utilisateur unique

  - La commande suivante assigne la stratégie de voix par utilisateur RedmondVoicePolicy à l’utilisateur Ken Myer.
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## Assignation d’une stratégie de voix par utilisateur à plusieurs utilisateurs

  - Cette commande assigne la stratégie de voix par utilisateur FinanceVoicePolicy à tous les utilisateurs qui ont des comptes dans l’unité d’organisation Finance dans Active Directory. Pour plus d’informations sur le paramètre OU utilisé dans cette commande, voir la documentation de l’applet de commande [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser).
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## Annulation de l’assignation d’une stratégie de voix par utilisateur

  - La commande suivante annule l’assignation d’une stratégie de voix par utilisateur précédemment affectée à Ken Myer. Lorsque cette stratégie par utilisateur n’est plus affectée à Ken Myer, celui-ci est automatiquement géré par la stratégie globale ou, le cas échéant, par la stratégie de site locale associée. La stratégie de site est prioritaire sur la stratégie globale.
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Grant-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsVoicePolicy).

## Voir aussi

#### Tâches

[Désactivation d’un utilisateur pour Voix Entreprise](lync-server-2013-disable-a-user-for-enterprise-voice.md)  

#### Autres ressources

[Lync Server Management Shell](lync-server-2013-lync-server-management-shell.md)

