---
title: Affichage des informations d’un site réseau
TOCTitle: Affichage des informations d’un site réseau
ms:assetid: 24a97d98-b168-4016-81bf-c2c478092b87
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ687996(v=OCS.15)
ms:contentKeyID: 49891267
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Affichage des informations d’un site réseau

 

_**Dernière rubrique modifiée :** 2013-02-23_

Les sites réseau sont les bureaux ou emplacements configurés au sein de chaque région d’un contrôle d’admission des appels (Call Admission Control ou CAC) ou encore d’un déploiement Enhanced 9-1-1. Vous pouvez afficher des informations sur les sites réseau dans Panneau de configuration Lync Server 2013 ou Lync Server Management Shell. Pour plus d’informations sur la création ou la modification de sites réseau, voir [Création ou modification des sites réseau](lync-server-2013-creating-or-modifying-network-sites.md).

## Pour afficher des informations sur les sites réseau dans Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Site**.

4.  Dans la page **Site**, cliquez sur le site que vous souhaitez afficher.
    
    > [!NOTE]  
    > Vous ne pouvez afficher les informations que d’un site à la fois.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

## Pour afficher des informations sur les sites réseau à l’aide des applets de commande Lync Server Management Shell

Vous pouvez afficher des informations sur les sites réseau à l’aide de l’applet de commande Get-CsNetworkSite. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour afficher des informations sur les sites réseau

  - Pour afficher des informations sur tous vos sites réseau, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur Entrée :
    
        Get-CsNetworkSite
    
    Les informations retournées se présentent ainsi :
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Get-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkSite).

## Voir aussi

#### Tâches

[Création ou modification des sites réseau](lync-server-2013-creating-or-modifying-network-sites.md)  
[Suppression d’un site réseau existant](lync-server-2013-deleting-an-existing-network-site.md)

