---
title: Configuration des liens de région réseau
TOCTitle: Configuration des liens de région réseau
ms:assetid: 952bc93e-e6aa-4539-85c7-2b15f14eb382
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182551(v=OCS.15)
ms:contentKeyID: 49298114
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des liens de région réseau

 

_**Dernière rubrique modifiée :** 2012-11-01_

Vous pouvez configurer des liens entre deux régions réseau dans le cadre du contrôle d’admission des appels. Au sein d’un réseau, les régions sont liées par une connectivité physique au réseau étendu (WAN). Vous pouvez utiliser le Panneau de configuration Lync Server pour définir un lien entre deux régions réseau et configurer les limites de bande passante pour les connexions audio et vidéo entre ces régions. Pour plus d’informations sur la suppression de lien de région réseau existant, voir [Suppression des liens de région réseau](lync-server-2013-deleting-network-region-links.md).

## Pour créer un lien de région réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Lien de région**.

4.  Dans la page **Lien de région**, cliquez sur **Nouveau**.

5.  Dans **Nouveau lien de région**, tapez une valeur dans le champ **Nom**.
    
    > [!NOTE]  
    > Cette valeur doit être unique dans votre déploiement Lync Server 2013.

6.  Dans la liste déroulante **Région réseau n° 1**, sélectionnez l’une des deux régions à relier.

7.  Dans la liste déroulante **Région réseau n° 2**, sélectionnez l’autre région à relier. Cette région doit être différente de la région sélectionnée pour Région réseau n° 1.

8.  (Facultatif) Si vous souhaitez ajouter des limites de bande passante sur les appels audio ou vidéo entre ces régions, sélectionnez un profil de stratégie de bande passante dans la liste déroulante **Stratégie de bande passante**.

9.  Cliquez sur **Valider**.

## Pour modifier un lien de région réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Lien de région**.

4.  Dans la page **Lien de région**, cliquez sur le lien de région que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans **Modifier le lien de région**, vous pouvez modifier les régions liées ou le profil de stratégie de bande passante pour ce lien.

7.  Cliquez sur **Valider**.

## Voir aussi

#### Tâches

[Suppression des liens de région réseau](lync-server-2013-deleting-network-region-links.md)  

#### Autres ressources

[New-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkRegionLink)  
[Set-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkRegionLink)  
[Remove-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkRegionLink)  
[Get-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkRegionLink)

