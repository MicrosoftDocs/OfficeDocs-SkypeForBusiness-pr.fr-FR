---
title: Affichage des informations d’une région réseau
TOCTitle: Affichage des informations d’une région réseau
ms:assetid: 665740d0-a3ed-460f-8337-5ed945f90589
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688076(v=OCS.15)
ms:contentKeyID: 49891373
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Affichage des informations d’une région réseau

 

_**Dernière rubrique modifiée :** 2013-02-23_

Une région réseau interconnecte diverses parties d’un réseau sur plusieurs zones géographiques. Chaque région réseau doit être associée à un site central. Le site central est le site du centre de données dans lequel le service de stratégie de bande passante du service Contrôle d’admission des appels est exécuté. Vous pouvez utiliser le Panneau de configuration Lync Server pour afficher les régions réseau. Les régions réseau incluent des paramètres qui déterminent si d’autres chemins via Internet peuvent être empruntés pour les connexions audio et vidéo. Utilisez cette rubrique pour afficher des régions réseau existantes. Pour plus d’informations sur la création ou la modification de régions réseau existantes, voir [Création ou modification de régions réseau](lync-server-2013-creating-or-modifying-network-regions.md).

## Pour afficher des informations sur une région réseau avec Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Région**.

4.  Dans la page **Région**, cliquez sur la région que vous souhaitez afficher.
    
    > [!NOTE]  
    > Vous ne pouvez afficher qu’une région à la fois.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

## Affichage d’informations sur une région réseau à l’aide d’applets de commande Windows PowerShell

Vous pouvez également afficher des informations sur une région réseau à l’aide de Windows PowerShell et de l’applet de commande **Get-CsNetworkRegion**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour afficher les informations sur une région réseau

  - Pour afficher des informations sur toutes vos régions réseau, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur Entrée :
    
        Get-CsNetworkRegion
    
    Les informations retournées se présentent ainsi :
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Get-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkRegionLink).

## Voir aussi

#### Tâches

[Création ou modification de régions réseau](lync-server-2013-creating-or-modifying-network-regions.md)  
[Suppression de régions réseau existantes](lync-server-2013-deleting-existing-network-regions.md)

