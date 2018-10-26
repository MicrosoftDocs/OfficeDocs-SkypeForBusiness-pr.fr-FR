---
title: Création ou modification de sous-réseaux
TOCTitle: Création ou modification de sous-réseaux
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg520957(v=OCS.15)
ms:contentKeyID: 49296429
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création ou modification de sous-réseaux

 

_**Dernière rubrique modifiée :** 2013-02-21_

Un sous-réseau de réseau doit être associé à un site réseau afin de déterminer l’emplacement géographique de l’hôte appartenant à ce sous-réseau. Vous pouvez utiliser le Panneau de configuration Lync Server pour configurer les sous-réseaux. Le Panneau de configuration Lync Server vous permet de créer, de modifier ou de supprimer un sous-réseau de réseau. Pour plus d’informations sur la suppression d’un sous-réseau de réseau, voir [Suppression des sous-réseaux](lync-server-2013-deleting-network-subnets.md)

La plupart des déploiements de Microsoft Lync Server 2013 qui implémentent le contrôle d’admission des appels (CAC) comptent généralement un nombre important de sous-réseaux. Pour cette raison, il est souvent préférable de configurer les sous-réseaux depuis Lync Server Management Shell, ce qui vous permet d’appeler l’applet de commande**New-CsNetworkSubnet** conjointement avec l’applet de commande Windows PowerShell**Import-CSV**. En utilisant conjointement ces applets de commande, vous pouvez lire les paramètres de sous-réseau dans un fichier de valeurs séparées par des virgules (.csv) et créer simultanément plusieurs sous-réseaux. Pour voir des exemples de création de sous-réseaux à partir d’un fichier .csv, voir [New-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSubnet).

## Pour créer un sous-réseau de réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Sous-réseau**.

4.  Dans la page **Sous-réseau**, cliquez sur **Nouveau**.

5.  Dans **Nouveau sous-réseau**, entrez une valeur dans le champ **ID de sous-réseau**. Il doit s’agir d’une adresse IP (par exemple, 174.11.12.0), qui doit être la première adresse dans la plage d’adresses IP définie par le sous-réseau.

6.  Dans le champ **Masque**, entrez une valeur numérique comprise entre 1 et 32.
    
    > [!NOTE]  
    > Cette valeur est le masque de bits à appliquer au sous-réseau en cours de création.

7.  Dans le champ **ID de site réseau**, sélectionnez le site auquel ce sous-réseau appartient.

8.  (Facultatif) Tapez une valeur dans le champ **Description** pour fournir plus d’informations sur ce sous-réseau, car son nom ne suffit pas à le décrire.

9.  Cliquez sur **Valider**.

## Pour modifier un sous-réseau de réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Sous-réseau**.

4.  Dans la page **Sous-réseau**, cliquez sur le sous-réseau que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier le sous-réseau**, vous pouvez modifier le masque de bits, le site réseau associé ou la description du sous-réseau. Si vous modifiez le masque de bits, n’oubliez pas que l’ID du sous-réseau doit toujours être la première adresse dans la plage d’adresses IP définie par le sous-réseau.

7.  Cliquez sur **Valider**.

## Voir aussi

#### Tâches

[Suppression des sous-réseaux](lync-server-2013-deleting-network-subnets.md)  

#### Concepts

[À propos des régions réseau, des sites réseau et des sous-réseaux dans Lync Server 2013](lync-server-2013-about-network-regions-sites-and-subnets.md)  

#### Autres ressources

[New-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSubnet)  
[Set-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkSubnet)  
[Remove-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkSubnet)  
[Get-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkSubnet)

