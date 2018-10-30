---
title: Création ou modification de régions réseau
TOCTitle: Création ou modification de régions réseau
ms:assetid: bd08bb66-5976-4ece-b45c-7de19569f814
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182579(v=OCS.15)
ms:contentKeyID: 49298667
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création ou modification de régions réseau

 

_**Dernière rubrique modifiée :** 2012-11-01_

Une région réseau interconnecte diverses parties d’un réseau sur plusieurs zones géographiques. Chaque région réseau doit être associée à un site central. Le site central est celui du centre de données dans lequel le service de stratégie de bande passante du contrôle d’admission des appels (CAC) s’exécute. Le Panneau de configuration Lync Server vous permet de configurer les régions réseau. Celles-ci incluent des paramètres qui déterminent si d’autres chemins peuvent être empruntés sur Internet pour les connexions audio et vidéo. À partir du Panneau de configuration Lync Server, vous pouvez créer, modifier ou supprimer une région réseau. Consultez la rubrique pour créer et modifier des régions réseau. Pour plus d’informations sur la suppression de régions réseau, voir [Suppression de régions réseau existantes](lync-server-2013-deleting-existing-network-regions.md).

## Pour créer une région réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Région**.

4.  Dans la page **Région**, cliquez sur **Nouveau**.

5.  Tapez une valeur dans le champ **Nom** de la page **Nouvelle région**. Cette valeur doit être unique dans votre déploiement Microsoft Lync Server 2013.

6.  Dans la liste déroulante **Site central**, sélectionnez le site central pour cette région réseau.

7.  La case à cocher **Activer un autre chemin d’accès à l’audio** est activée par défaut. Ce champ détermine si les appels audio seront acheminés via un autre chemin si la bande passante adéquate n’existe pas dans le chemin principal. Désactivez cette case à cocher uniquement si vous avez besoin de désactiver le déchargement vers Internet. Si vous prévoyez de passer des appels Internet, cette case à cocher doit être activée, indépendamment des paramètres de bande passante.

8.  La case à cocher **Activer un autre chemin d’accès à la vidéo** est activée par défaut. Ce champ détermine si les appels vidéo seront acheminés via un autre chemin si la bande passante adéquate n’existe pas dans le chemin principal. Désactivez cette case à cocher uniquement si vous avez besoin de désactiver le déchargement vers Internet. Si vous prévoyez de passer des appels Internet, cette case à cocher doit être activée, indépendamment des paramètres de bande passante.

9.  (Facultatif) Tapez une valeur dans le champ **Description** pour fournir plus d’informations sur cette région, car son nom seul ne suffit pas à la décrire.

10. Cliquez sur **Valider**.

Le tableau **Sites associés** n’est pas utilisé pour la création d’une région réseau. Vous associez un site à une région lorsque vous créez ou modifiez le site. Pour plus d’informations, voir [Création ou modification des sites réseau](lync-server-2013-creating-or-modifying-network-sites.md).

## Pour modifier une région réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Région**.

4.  Dans la page **Région**, cliquez sur la région que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier la région**, vous pouvez modifier les paramètres permettant d’activer et de désactiver les chemins audio et vidéo alternatifs et modifier également la description (pour plus d’informations, voir la section « Pour créer une région réseau » plus haut dans cette rubrique).

7.  Cliquez sur **Valider**.

Vous ne pouvez pas modifier les **sites associés** sur cette page. La liste des sites associés est fournie à titre de référence pour vous informer des sites qui seront affectés par la modification des paramètres de région.

## Voir aussi

#### Tâches

[Suppression de régions réseau existantes](lync-server-2013-deleting-existing-network-regions.md)  
[Configurer les régions de réseau pour le contrôle d’admission des appels (CAC)](lync-server-2013-configure-network-regions-for-cac.md)  

#### Autres ressources

[New-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkRegion)  
[Set-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkRegion)  
[Remove-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkRegion)  
[Get-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkRegionLink)

