---
title: Afficher les règles de stratégie de version du client
TOCTitle: Afficher les règles de stratégie de version du client
ms:assetid: f3a0215f-f72f-4e9b-a07b-25858dc4203a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ923060(v=OCS.15)
ms:contentKeyID: 53095567
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Afficher les règles de stratégie de version du client

 

_**Dernière rubrique modifiée :** 2013-02-23_

Une stratégie de version du client est composée d’un ensemble de règles de stratégie de version du client. Ces règles définissent les actions qui doivent être entreprises lorsque les utilisateurs tentent de se connecter avec des clients et des versions de client spécifiques. Vous pouvez afficher les règles de stratégie de version client à partir du Panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell.

## Pour afficher les règles de stratégie de version client à l’aide du Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur le bouton de navigation **Stratégie de version du client**.

4.  Dans la page **Stratégie de version du client**, double-cliquez sur une stratégie de version du client que vous voulez afficher.

5.  Les règles s’affichent dans la page **Modifier la stratégie de version du client**. Pour afficher les détails d’une règle, sélectionnez-la, puis cliquez sur **Afficher les détails**.

## Affichage des règles de stratégie de version du client à l’aide des applets de commande Windows PowerShell

Vous pouvez afficher les règles de stratégie de version du client à l’aide de Lync Server Management Shell et de l’applet de commande **Get-CsClientVersionPolicyRule**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une sessions à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour afficher les règles de stratégie de version du client

  - Pour afficher les règles de stratégie de version du client, tapez la commande suivante dans Lync Server Management Shell et appuyez sur Entrée:
    
        Get-CsClientVersionPolicyRule
    
    Des informations ressemblant à celles-ci sont retournées pour chaque règle configurée :
    
        Identity          : Global/2336c611-a243-4c5d-994b-eea8a524d0e4
        Priority          : 0
        RuleId            : 2336c611-a243-4c5d-994b-eea8a524d0e4
        Description       :
        Action            : Block
        ActionUrl         :
        MajorVersion      : 1
        MinorVersion      : 3
        BuildNumber       :
        QfeNumber         :
        UserAgent         : RTC
        UserAgentFullName :
        Enabled           : True
        CompareOp         : LEQ

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Get-CsClientVersionPolicyRule](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClientVersionPolicyRule).

