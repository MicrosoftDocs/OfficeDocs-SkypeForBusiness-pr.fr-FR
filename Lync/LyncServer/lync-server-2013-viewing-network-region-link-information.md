---
title: Affichage des informations des liens de région réseau
TOCTitle: Affichage des informations des liens de région réseau
ms:assetid: 7b6b2ea2-83d8-4376-afb2-70e5d2cf6444
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688102(v=OCS.15)
ms:contentKeyID: 49891405
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Affichage des informations des liens de région réseau

 

_**Dernière rubrique modifiée :** 2013-02-23_

Vous pouvez afficher les liens entre deux régions réseau dans le cadre du service Contrôle d’admission des appels (CAC). Au sein d’un réseau, les régions sont liées par une connectivité physique au réseau étendu (WAN). Vous pouvez utiliser le Panneau de configuration Lync Server pour afficher un lien existant entre deux régions réseau. Pour plus d’informations sur la création ou la modification d’un lien de région réseau, voir [Configuration des liens de région réseau](lync-server-2013-configuring-network-region-links.md).

## Pour afficher un lien de région réseau dans le Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Lien de région**.

4.  Dans la page **Lien de région**, cliquez sur le lien de région que vous souhaitez afficher.
    
    > [!NOTE]  
    > Vous ne pouvez afficher des informations que sur un lien de région à la fois.

5.  Dans le menu **Edition**, sélectionnez **Afficher les détails**.

## Affichage des informations de lien de région réseau avec les applets de commande Lync Server Management Shell

Vous pouvez également afficher des liens de région réseau avec Lync Server Management Shell et l’applet de commande **Get-CsNetworkRegionLink**. Vous pouvez utiliser cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour afficher les informations d’un lien de région réseau

  - Pour afficher les informations relatives à tous les liens de région réseau, tapez la commande suivante dans Lync Server Management Shell et appuyez sur Entrée :
    
        Get-CsNetworkRegionLink
    
    Cette commande renvoie le type d’informations suivantes :
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

Pour plus d’informations, voir [Get-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkRegionLink).

## Voir aussi

#### Tâches

[Configuration des liens du site réseau](lync-server-2013-configuring-network-site-links.md)

