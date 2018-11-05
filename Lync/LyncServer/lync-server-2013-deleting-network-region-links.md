---
title: Suppression des liens de région réseau
TOCTitle: Suppression des liens de région réseau
ms:assetid: 839273cd-d23f-4b38-84e6-d2dc972f49cd
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688114(v=OCS.15)
ms:contentKeyID: 49891420
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression des liens de région réseau

 

_**Dernière rubrique modifiée :** 2012-11-01_

Vous pouvez configurer les liens entre deux régions réseau dans le cadre du service Contrôle d’admission des appels (CAC). Au sein d’un réseau, les régions sont liées par une connectivité physique au réseau étendu (WAN). Vous pouvez utiliser le Panneau de configuration Lync Server pour supprimer un lien existant entre deux régions réseau. Pour plus d’informations sur la création ou la modification d’un lien de région réseau, voir [Configuration des liens de région réseau](lync-server-2013-configuring-network-region-links.md).

## Pour supprimer un lien de région réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Lien de région**.

4.  Dans la page **Lien de région**, cliquez sur le lien de région que vous souhaitez supprimer.
    
    > [!NOTE]  
    > Vous pouvez supprimer plusieurs liens de région à la fois. Pour cela, appuyez sur Ctrl et tout en maintenant cette touche enfoncée, sélectionnez plusieurs liens de région. Ou, pour sélectionner tous les liens de région, cliquez sur <strong>Sélectionner tout</strong> dans le menu <strong>Edition</strong>.

5.  Dans le menu **Edition**, sélectionnez **Supprimer**.

6.  Cliquez sur **OK**.

## Voir aussi

#### Tâches

[Configuration des liens de région réseau](lync-server-2013-configuring-network-region-links.md)

