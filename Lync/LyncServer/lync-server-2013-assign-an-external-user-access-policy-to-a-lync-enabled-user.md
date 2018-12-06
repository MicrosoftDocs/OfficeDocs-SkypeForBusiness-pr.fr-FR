---
title: "Lync Server 2013 : Attri. strat. d’accès des util. ext. à util. activé pr Lync"
TOCTitle: Attribution d’une stratégie d’accès des utilisateurs externes à un utilisateur activé pour Lync
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398551(v=OCS.15)
ms:contentKeyID: 49297723
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Attribution d’une stratégie d’accès des utilisateurs externes à un utilisateur activé pour Lync dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-22_

Si Lync Server a été activé pour un utilisateur, vous pouvez configurer la fédération SIP, la fédération XMPP, l’accès des utilisateurs distants et la connectivité PIC (Public IM Connectivity) dans le Panneau de configuration Lync Server en appliquant les stratégies appropriées aux utilisateurs spécifiques. Par exemple, si vous avez créé une stratégie de prise en charge de l’accès des utilisateurs distants, vous devez l’appliquer à l’utilisateur avant qu’il puisse se connecter à Lync Server depuis un emplacement distant d’où il pourra collaborer avec les utilisateurs internes.

> [!NOTE]  
> Pour prendre en charge l’accès des utilisateurs externes, vous devez activer la prise en charge pour chaque type d’accès d’utilisateur externe à prendre en charge, puis configurer les stratégies appropriées et d’autres options afin de contrôler son utilisation. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuration de la prise en charge de l’accès des utilisateurs externes dans Lync Server 2013</a> dans la documentation de déploiement ou <a href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">Gestion de la fédération et de l’accès externe à Lync Server 2013</a> dans la documentation des opérations.

La procédure de cette rubrique vous permet d’appliquer une stratégie d’accès des utilisateurs externes créée précédemment à un ou plusieurs comptes d’utilisateurs.

## Pour appliquer une stratégie d’utilisateur externe à un compte d’utilisateur

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs** , puis recherchez le compte d’utilisateur que vous souhaitez configurer.

4.  Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier** , puis sur **Afficher les détails** .

5.  Dans **Modifier l’utilisateur Lync Server** sous **Stratégie d’accès externe** , sélectionnez la stratégie d’utilisateur à appliquer.
    
    > [!NOTE]  
    > Les paramètres <strong>&lt;Automatique&gt;</strong> appliquent les paramètres de stratégie globale ou du serveur par défaut.

## Affectatiion e stratégies d’accès externe utilisateur via les appplets de commande Windows PowerShell

Il est possible d’affecter des stratégies d’accès externe utilisateur à l’aide de Windows PowerShell et de l’applet de commande Grant-CsExternalAccessPolicy (exécutable depuis le Lync Server 2013 Management Shell ou une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)..

## Affecter une stratégie d’accès externe utilisateur à un seul utilisateur

  - Cette commande permet d’affecter la stratégie d’accès externe par utilisateur RedmondExternalAccessPolicy à l’utilisateur Ken Myer.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

## Affecter une stratégie d’accès externe utilisateur à plusieurs utilisateurs

  - Cette commande permet d’affecter la stratégie d’accès externe par utilisateur USAExternalAccessPolicy à tous les utilisateurs qui possèdent des comptes dans l’unité d’organisation (OU) UnitedStates dans Active Directory. Pour plus d’informations sur le paramètre OU utilisé dans cette commande, reportez-vous à la documentation de l’applet de commande [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser).
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

## Désaffecter une stratégie d’accès externe utilisateur

  - Cette commande annule l’affectation d’une stratégie d’accès externe par utilisateur précédemment affectée à Ken Myer. Lorsque cette stratégie par utilisateur n’est plus affectée à Ken Myer, celui-ci est automatiquement géré par la stratégie globale ou, le cas échéant, par la stratégie de site locale associée. La stratégie de site est prioritaire sur la stratégie globale.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

Pour plus d’informations, reportez-vous à la rubrique d’aide sur l’applet de commande [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy).

