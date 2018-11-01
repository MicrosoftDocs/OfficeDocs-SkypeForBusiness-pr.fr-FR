---
title: Afficher les stratégies de version du client
TOCTitle: Afficher les stratégies de version du client
ms:assetid: 6cd9a897-c694-4d6a-8259-2d3c01fce275
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ898479(v=OCS.15)
ms:contentKeyID: 53095446
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Afficher les stratégies de version du client

 

_**Dernière rubrique modifiée :** 2013-02-23_

Les stratégies de version du client servent à appliquer un ensemble de règles de contrôle de version du client de manière globale ou sur un site, pool ou groupe d’utilisateurs spécifique. Vous pouvez afficher les stratégies de version du client qui ont été configurées dans votre environnement Lync Server 2013 à partir du Panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell.

## Pour afficher les stratégies de version du client à l’aide du Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur le bouton de navigation **Stratégie de version du client**.

4.  Si vous souhaitez afficher les règles d’une stratégie de version du client, dans la page **Stratégie de version du client**, double-cliquez sur la stratégie à afficher.

## Affichage de stratégies de version du client à l’aide d’applets de commande Windows PowerShell

Vous pouvez afficher les stratégies de version du client à l’aide de l’applet de commande **Get-CsClientVersionPolicy**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour afficher les stratégies de version du client

  - Pour afficher des informations sur toutes vos stratégies de version du client, tapez la commande suivante dans Lync Server Management Shell et appuyez sur Entrée :
    
        Get-CsClientVersionPolicy
    
    Vous obtiendrez des indications semblables à ceci :
    
        Identity    : Global
        Rules       : {RuleId=2336c611-a243-4c5d-994b-eea8a524d0e4;
                      Description=;Action=Block;ActionUrl=;MajorVersion=1;
                      MinorVersion=3;BuildNumber=;QfeNumber=;
                      UserAgent=RTC;UserAgentFullName=;Enabled=True;
                      CompareOp=LEQ, RuleId=342c9b90-4cef-483a-a73a-
                      4fe75c88711d;Description=;Action=Block;ActionUrl=;
                      MajorVersion=5;MinorVersion=;BuildNumber=;QfeNumber=;
                      UserAgent=WM;UserAgentFullName=;Enabled=True;
                      CompareOp=LEQ,RuleId=ea03af61-9db5-4bf9-af3f-042
                      ab8dd9994;Description=;Action=Block;ActionUrl=;
                      MajorVersion=3;MinorVersion=5;BuildNumber=6907;
                      QfeNumber=83;UserAgent=OC;UserAgentFullName=;
                      Enabled=True;CompareOp=LEQ, RuleId=831edb68-
                      e482-4431-a10e-add365ba8099;Description=;
                      Action=Block;ActionUrl=;MajorVersion=2;MinorVersion=0;
                      BuildNumber=5999;QfeNumber=;UserAgent=UCCP;
                      UserAgentFullName=;Enabled=True;CompareOp=LEQ...}
        Description :

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Get-CsClientVersionPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClientVersionPolicy).

