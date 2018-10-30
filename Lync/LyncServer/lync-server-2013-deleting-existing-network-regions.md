---
title: Suppression de régions réseau existantes
TOCTitle: Suppression de régions réseau existantes
ms:assetid: c7293a2f-2b49-4c4a-903f-f7edcea2bc5f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721882(v=OCS.15)
ms:contentKeyID: 49891536
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression de régions réseau existantes

 

_**Dernière rubrique modifiée :** 2013-02-21_

Une région réseau interconnecte diverses parties d’un réseau sur plusieurs zones géographiques. Chaque région réseau doit être associée à un site central. Le site central est celui du centre de données dans lequel le service de stratégie de bande passante du contrôle d’admission des appels (CAC) s’exécute. Le Panneau de configuration Lync Server vous permet de configurer les régions réseau. Celles-ci incluent des paramètres qui déterminent si d’autres chemins peuvent être empruntés sur Internet pour les connexions audio et vidéo. À partir du Panneau de configuration Lync Server, vous pouvez créer, modifier ou supprimer une région réseau. Consultez la rubrique pour supprimer des régions réseau. Pour plus d’informations sur la création et la modification de régions réseau, voir [Création ou modification de régions réseau](lync-server-2013-creating-or-modifying-network-regions.md).

## Pour supprimer une région réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Région**.

4.  Dans la page **Région**, cliquez sur la région à supprimer.
    
    > [!NOTE]  
    > Vous pouvez supprimer plusieurs régions à la fois. Pour cela, appuyez sur la touche Ctrl et, tout en la maintenant enfoncée, sélectionnez plusieurs régions. Pour sélectionner toutes les régions, cliquez sur <strong>Sélectionner tout</strong> dans le menu <strong>Edition</strong>.

5.  Dans le menu **Edition**, cliquez sur **Supprimer**.

6.  Cliquez sur **OK**.
    
    > [!WARNING]  
    > Vous ne pouvez pas supprimer une région réseau si elle est associée à un site réseau. Si vous essayez, un message d’erreur s’affiche. Pour savoir si une région est associée à des sites, sélectionnez-la, puis cliquez sur <strong>Afficher les détails</strong> dans le menu <strong>Edition</strong>.

## Voir aussi

#### Tâches

[Création ou modification de régions réseau](lync-server-2013-creating-or-modifying-network-regions.md)

