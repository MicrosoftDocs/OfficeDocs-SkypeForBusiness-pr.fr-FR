---
title: Paramètres de configuration de version du client
TOCTitle: Paramètres de configuration de version du client
ms:assetid: c72df4e6-a889-4cb6-86f7-8334d7774c6e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ923062(v=OCS.15)
ms:contentKeyID: 53095523
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Paramètres de configuration de version du client

 

_**Dernière rubrique modifiée :** 2013-02-23_

Les paramètres de configuration de version du client servent à activer ou désactiver le contrôle de version du client. La configuration globale de version du client est installée avec Lync Server 2013 et permet d’activer ou de désactiver le contrôle de version du client pour l’ensemble du déploiement de serveur. Lorsque la configuration globale est activée, toutes les stratégies de version du client qui sont en place prendront effet lorsque les utilisateurs tenteront de se connecter. Vous pouvez afficher les paramètres de configuration de version du client à partir du Panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell.

> [!NOTE]  
> N’étant associés à aucun utilisateur, site ou service spécifique, les utilisateurs anonymes sont affectés uniquement par les stratégies globales.

## Pour afficher les paramètres de configuration de version du client à l’aide du Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur le bouton de navigation **Configuration de la version du client**.

4.  Double-cliquez sur la configuration de version du client à afficher.

## Affichage des paramètres de configuration de version du client à l’aide d’applets de commande Windows PowerShell

Vous pouvez afficher les paramètres de configuration de version du client à l’aide de l’applet de commande **Get-CsClientVersionConfiguration**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour afficher les informations de configuration de version du client

  - Pour afficher des informations sur tous vos paramètres de configuration de version du client, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur Entrée :
    
        Get-CsClientVersionConfiguration
    
    Cette commande renvoie des informations semblables à celles-ci :
    
        Identity      : Global
        DefaultAction : Allow
        DefaultURL    :
        Enabled       : True

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Get-CsClientVersionConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClientVersionConfiguration).

