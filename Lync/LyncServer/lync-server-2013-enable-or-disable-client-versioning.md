---
title: Activer ou désactiver la gestion des versions du client
TOCTitle: Activer ou désactiver la gestion des versions du client
ms:assetid: 33a98cb9-a979-4bb6-afb2-512f601d7ac5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ898475(v=OCS.15)
ms:contentKeyID: 53095391
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activer ou désactiver la gestion des versions du client

 

_**Dernière rubrique modifiée :** 2013-02-23_

Les paramètres de configuration de version du client sont utilisés pour activer ou désactiver le contrôle de version du client, soit globalement, soit pour des sites spécifiques. La configuration globale de version du client est installée avec Lync Server 2013 et permet d’activer ou de désactiver le contrôle de version du client pour le déploiement complet du serveur. Lorsque la configuration globale est activée, toutes les stratégies de version du client qui sont en place prendront effet quand les utilisateurs tenteront de se connecter. Vous pouvez désactiver la configuration globale de version du client si vous ne voulez qu’aucun contrôle de la version du client ne se produise. Vous pouvez activer ou désactiver la gestion de la version du client depuis le Panneau de configuration Lync Server 2013 ou Lync Server 2013 Management Shell.

> [!NOTE]  
> Comme ils ne sont pas associés à un utilisateur, un site ou un service spécifiques, les utilisateurs anonymes sont uniquement affectés par les stratégies globales.

## Pour activer ou désactiver la gestion de la version du client à l’aide du Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur le bouton de navigation **Configuration de la version du client**.

4.  Procédez comme suit :
    
      - Pour activer ou désactiver globalement la gestion de la version du client, double-cliquez sur la configuration **Global**, puis modifiez les paramètres.
    
      - Pour activer ou désactiver la gestion de la version du client pour un site spécifique, cliquez sur **Nouveau**, sélectionnez le site, cliquez sur **OK**, puis modifiez les paramètres du site.

## Activation ou désactivation de la gestion de la version du client à l’aide d’applets de commande Windows PowerShell

Vous pouvez activer ou désactiver la gestion de la version du client à l’aide de l’applet de commande **Set-CsClientVersionConfiguration**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour activer la gestion de la version du client

  - Vous pouvez activer la gestion de la version du client en définissant la propriété **Enabled** sur True ($True).
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

## Pour désactiver la gestion de la version du client

  - Vous pouvez désactiver la gestion de la version du client en définissant la propriété **Enabled** sur False ($False).
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Set-CsClientVersionConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientVersionConfiguration).

