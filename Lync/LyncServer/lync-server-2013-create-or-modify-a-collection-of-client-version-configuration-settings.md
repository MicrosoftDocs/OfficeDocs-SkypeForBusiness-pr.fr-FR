---
title: "Créer ou mod. une collection de par. de conf. de la version du client"
TOCtitle: "Créer ou mod. une collection de par. de conf. de la version du client"
ms:assetid: 4e6faffd-a36f-40f1-8734-78d84b7df921
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ898477(v=OCS.15)
ms:contentKeyID: 53095418
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Créer ou modifier une collection de paramètres de configuration de la version du client

 

_**Dernière rubrique modifiée :** 2013-02-23_

Les paramètres de configuration de version du client sont utilisés pour activer ou désactiver le contrôle de version du client. La configuration globale de version du client est installée avec Lync Server et permet d’activer ou de désactiver le contrôle de version du client pour le déploiement complet du serveur. Vous pouvez également configurer les paramètres de configuration de version du client pour des sites spécifiques. Vous pouvez créer ou modifier des paramètres de configuration de version du client à partir du Panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell.

> [!NOTE]  
> Comme ils ne sont pas associés à un utilisateur, un site ou un service spécifiques, les utilisateurs anonymes sont uniquement affectés par les stratégies globales.

## Pour créer ou modifier des paramètres de configuration de version du client à l’aide du Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur le bouton de navigation **Configuration de la version du client**.

4.  Dans la page **Configuration de la version du client**, procédez comme suit :
    
      - Pour créer une configuration, cliquez sur **Nouveau**, sélectionnez un site, cliquez sur **OK**, puis mettez à jour les paramètres.
    
      - Pour modifier une configuration, sélectionnez celle-ci, cliquez sur **Modifier**, cliquez sur **Afficher les détails**, puis apportez les modifications de votre choix aux paramètres.

## Création ou modification de paramètres de configuration de version du client à l’aide d’applets de commande Windows PowerShell

Vous pouvez créer des paramètres de configuration de version du client à l’aide de l’applet de commande **New-CsClientVersionConfiguration**, et les modifier à l’aide de l’applet de commande **Set-CsClientVersionConfiguration**. Ces applets de commande peuvent être exécutées à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour créer une collection de paramètres de configuration de version du client

  - La commande suivante crée une collection de paramètres de configuration de version du client appliquée au site Redmond. Dans cet exemple, la gestion des versions du client est désactivée pour le site Redmond.
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

## Pour activer la gestion des versions du client pour un site

  - Cette commande active la gestion des versions du client pour le site Redmond.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

## Pour désactiver la gestion des versions du client dans l’ensemble de l’organisation

  - Dans cet exemple, la gestion des versions du client est désactivée pour tous les paramètres de configuration de version du client utilisés dans l’organisation.
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

Pour plus d’informations, voir les rubriques d’aide relatives aux applets de commande [New-CsClientVersionConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientVersionConfiguration) et [Set-CsClientVersionConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientVersionConfiguration).

