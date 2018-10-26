---
title: Affichage des informations des itinéraires de région réseau
TOCTitle: Affichage des informations des itinéraires de région réseau
ms:assetid: 34dd9fa3-e695-4680-b244-3019298b5009
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688021(v=OCS.15)
ms:contentKeyID: 49891304
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Affichage des informations des itinéraires de région réseau

 

_**Dernière rubrique modifiée :** 2013-02-23_

Chaque région au sein d’un contrôle d’admission des appels doit disposer d’un moyen lui permettant d’accéder à toutes les autres régions. Alors que les liens de région définissent des restrictions de bande passante sur les connexions entre les régions et qu’ils représentent également des liens physiques, un itinéraire détermine le chemin lié que la connexion traverse d’une région à une autre. Appliquez les procédures suivantes pour afficher les itinéraires de région réseau existants dans le Panneau de configuration Lync Server 2013 ou Lync Server 2013 Management Shell. Pour plus d’informations sur la création ou la modification des itinéraires de région réseau, voir [Création ou modification des itinéraires de région réseau](lync-server-2013-creating-or-modifying-network-region-routes.md).

## Pour afficher les informations d’un itinéraire de région réseau dans le Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Itinéraire de région**.

4.  Dans la page **Itinéraire de région**, cliquez sur l’itinéraire de région que vous souhaitez modifier.
    
    > [!NOTE]  
    > Vous ne pouvez afficher qu’un itinéraire de région à la fois.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

## Affichage des informations d’itinéraire de région réseau à l’aide des applets de commande Lync Server PowerShell

Les informations d’itinéraire de région réseau peuvent aussi être affichées à l’aide de Lync Server PowerShell et de l’applet de commande Get-CsNetworkInterRegionRoute. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Affichage des informations d’itinéraire de région réseau

  - Pour afficher des informations sur tous vos itinéraires de région réseau, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur Entrée :
    
        Get-CsNetworkInterRegionRoute
    
    Les informations retournées se présentent ainsi :
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterRegionRoute).

## Voir aussi

#### Tâches

[Création ou modification des itinéraires de région réseau](lync-server-2013-creating-or-modifying-network-region-routes.md)  
[Suppression des itinéraires de zones réseau existants](lync-server-2013-deleting-existing-network-region-routes.md)

