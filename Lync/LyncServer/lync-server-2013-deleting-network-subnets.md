---
title: Suppression des sous-réseaux
TOCTitle: Suppression des sous-réseaux
ms:assetid: c1850f38-40a3-48c9-b6f1-f181c5e63b6b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721873(v=OCS.15)
ms:contentKeyID: 49891522
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression des sous-réseaux

 

_**Dernière rubrique modifiée :** 2013-02-21_

La procédure suivante vous permet de supprimer un sous-réseau. À partir du Panneau de configuration Lync Server, vous pouvez créer, modifier ou supprimer un sous-réseau. Pour plus d’informations, voir [Création ou modification de sous-réseaux](lync-server-2013-create-or-modify-network-subnets.md)

La plupart des déploiements de Microsoft Lync Server 2013 qui implémentent le contrôle d’admission des appels (CAC) comptent généralement un nombre important de sous-réseaux. Pour cette raison, il est souvent préférable de configurer les sous-réseaux depuis Lync Server Management Shell, ce qui vous permet d’appeler l’applet de commande **New-CsNetworkSubnet** conjointement avec l’applet de commande Windows PowerShell**Import-CSV**. En utilisant conjointement ces applets de commande, vous pouvez lire les paramètres de sous-réseau dans un fichier de valeurs séparées par des virgules (.csv) et créer simultanément plusieurs sous-réseaux. Pour obtenir des exemples de création de sous-réseaux à partir d’un fichier .csv, voir [New-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSubnet).

## Pour supprimer un sous-réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Sous-réseau**.

4.  Dans la page **Sous-réseau**, cliquez sur le sous-réseau à supprimer.
    
    > [!NOTE]  
    > Vous pouvez supprimer plusieurs sous-réseaux à la fois. Pour cela, appuyez sur Ctrl et tout en maintenant cette touche enfoncée, sélectionnez les différents sous-réseaux à supprimer. Pour sélectionner la totalité des sous-réseaux, cliquez sur <strong>Sélectionner tout</strong> dans le menu <strong>Edition</strong>.

5.  Dans le menu **Edition**, cliquez sur **Supprimer**.

6.  Cliquez sur **OK**.

## Voir aussi

#### Tâches

[Création ou modification de sous-réseaux](lync-server-2013-create-or-modify-network-subnets.md)

