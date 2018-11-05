---
title: Associer des sous-réseaux à des sites réseau pour le contournement de média
TOCTitle: Associer des sous-réseaux à des sites réseau pour le contournement de média
ms:assetid: 5bc632b7-1446-470f-b332-48ea0ca4d1fd
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398401(v=OCS.15)
ms:contentKeyID: 49297295
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Associer des sous-réseaux à des sites réseau pour le contournement de média

 

_**Dernière rubrique modifiée :** 2012-09-12_

> [!NOTE]  
> Dans cette rubrique, nous partons du principe que vous avez déjà configuré les paramètres globaux de contournement de média, mais aussi la région et les sites de réseau pour le contournement de média.

Chaque sous-réseau de votre réseau doit être associé à un site réseau spécifique. Ceci est dû au fait que les informations de sous-réseau permettent de déterminer le site réseau sur lequel se trouve un système d’extrémité. Lorsque les emplacements des deux parties sont connus dans une session, le contournement de média peut déterminer où le média doit être envoyé pour traitement.

Le contournement de média ne doit respecter aucune condition particulière pour associer les sous-réseaux aux sites réseau. Pour créer une association entre des sous-réseaux et des sites réseau dans votre topologie, suivez les procédures décrites dans [Association d’un sous-réseau à un site réseau dans Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

## Étapes suivantes : Créer des profils de stratégie de bande passante

Une fois que vous avez associé les sous-réseaux à des sites réseau pour le contournement de média, vous devez créer un ou plusieurs profils de stratégie de bande passante qui partitionneront les sous-réseaux en éléments de bonne connectivité et éléments sans connectivité à des fins de contournement de média. Tous les sous-réseaux d’une région réseau comportant des sites réseau qui ne sont soumis à aucune limitation de bande passante disposent d’une bonne connectivité. Ces sous-réseaux peuvent donc utiliser le contournement de média.

Pour obtenir les procédures de configuration des profils de stratégie de bande passante, voir [Créer des profils de stratégie de bande passante dans Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).

