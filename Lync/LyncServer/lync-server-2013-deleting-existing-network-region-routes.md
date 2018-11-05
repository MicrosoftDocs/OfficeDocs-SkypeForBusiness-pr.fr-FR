---
title: Suppression des itinéraires de zones réseau existants
TOCTitle: Suppression des itinéraires de zones réseau existants
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49891371
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression des itinéraires de zones réseau existants

 

_**Dernière rubrique modifiée :** 2012-11-01_

Chaque région au sein d’une configuration de contrôle d’admission des appels doit disposer d’un moyen lui permettant d’accéder à toutes les autres régions. Alors que les liens de région définissent des restrictions de bande passante sur les connexions entre les régions et qu’ils représentent également des liens physiques, un itinéraire détermine le chemin lié que la connexion traverse d’une région à une autre. Vous pouvez utiliser le Panneau de configuration Lync Server pour configurer les itinéraires de région réseau. Le Panneau de configuration Lync Server vous permet de créer, de modifier ou de supprimer un itinéraire de région réseau. Utilisez cette rubrique pour supprimer des itinéraires de région réseau existants. Pour plus d’informations sur la création ou la modification d’itinéraires de région réseau, voir [Création ou modification des itinéraires de région réseau](lync-server-2013-creating-or-modifying-network-region-routes.md).

## Pour supprimer un itinéraire de région réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Itinéraire de région**.

4.  Dans la page **Itinéraire de région**, cliquez sur l’itinéraire de région à supprimer.
    
    > [!NOTE]  
    > Vous pouvez supprimer plusieurs itinéraires de région à la fois. Pour cela, appuyez sur Ctrl et tout en maintenant cette touche enfoncée, sélectionnez plusieurs itinéraires de région. Ou, pour sélectionner tous les itinéraires de région, cliquez sur <strong>Sélectionner tout</strong> dans le menu <strong>Edition</strong>.

5.  Dans le menu **Edition**, cliquez sur **Supprimer**.

6.  Cliquez sur **OK**.

## Voir aussi

#### Tâches

[Création ou modification des itinéraires de région réseau](lync-server-2013-creating-or-modifying-network-region-routes.md)  

#### Concepts

[Configurer un itinéraire de région réseau](https://technet.microsoft.com/fr-fr/library/gg133706\(v=ocs.15\))  

#### Autres ressources

[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterRegionRoute)

