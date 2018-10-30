---
title: Désactivation du contournement de média réseau
TOCTitle: Désactivation du contournement de média réseau
ms:assetid: 936d2678-d712-4589-b172-b5793013652f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688141(v=OCS.15)
ms:contentKeyID: 49891448
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Désactivation du contournement de média réseau

 

_**Dernière rubrique modifiée :** 2012-10-15_

Les paramètres de contournement de média sont appliqués globalement dans un déploiement Microsoft Lync Server 2013. Le contournement de média autorise les appels à contourner le serveur de médiation. Pour plus d’informations sur l’utilisation du contournement de média, voir [Planification de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) dans la section Planification. Vous pouvez désactiver le contournement de média à partir du Panneau de configuration Lync Server. Pour des informations sur l’activation et la configuration du contournement de média, voir [Activation du contournement de média réseau](lync-server-2013-enabling-network-media-bypass.md)

## Pour désactiver le contournement de média

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Globale**.

4.  Dans la page **Globale**, cliquez sur la configuration **Globale**. Il n’existe toujours qu’une seule configuration, qui se nomme toujours Globale.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier la configuration globale**, décochez la case **Activer le contournement de média**.

7.  Cliquez sur **OK** pour enregistrer vos modifications.

## Voir aussi

#### Tâches

[Activation du contournement de média réseau](lync-server-2013-enabling-network-media-bypass.md)

