---
title: Affichage des informations d’un sous-réseau
TOCTitle: Affichage des informations d’un sous-réseau
ms:assetid: 46f165f2-efe3-4cc1-9fee-a78b7f2ed41e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688044(v=OCS.15)
ms:contentKeyID: 49891330
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Affichage des informations d’un sous-réseau

 

_**Dernière rubrique modifiée :** 2013-02-23_

Vous pouvez utiliser la procédure suivante pour afficher un sous-réseau. Dans le Panneau de configuration Lync Server, vous pouvez créer, modifier ou supprimer un sous-réseau. Pour plus d’informations sur la création ou la modification de sous-réseaux, voir [Création ou modification de sous-réseaux](lync-server-2013-create-or-modify-network-subnets.md).

## Pour afficher un sous-réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Sous-réseau**.

4.  Dans la page **Sous-réseau**, cliquez sur le sous-réseau que vous souhaitez afficher.
    
    > [!NOTE]  
    > Vous ne pouvez afficher qu’un seul sous-réseau à la fois.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

## Affichage des informations de configuration du sous-réseau à l’aide des applets de commande Lync Server PowerShell

Vous pouvez également afficher les informations relatives au sous-réseau à l’aide de Lync Server PowerShell et de l’applet de commande Get-CsNetworkSubnet. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Affichage des informations relatives au sous-réseau

  - Pour afficher des informations sur l’ensemble de vos sous-réseaux, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur Entrée :
    
        Get-CsNetworkSubnet
    
    Les informations retournées se présentent ainsi :
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Get-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkSubnet).

## Voir aussi

#### Tâches

[Création ou modification de sous-réseaux](lync-server-2013-create-or-modify-network-subnets.md)  
[Suppression des sous-réseaux](lync-server-2013-deleting-network-subnets.md)

