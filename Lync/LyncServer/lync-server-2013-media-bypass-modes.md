---
title: 'Lync Server 2013 : Modes de déviation du trafic multimédia'
TOCTitle: Modes de déviation du trafic multimédia
ms:assetid: 38c06c81-7e45-4423-9e00-7fbfa4befe46
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425862(v=OCS.15)
ms:contentKeyID: 49296889
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modes de déviation du trafic multimédia dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-05_

Vous devez configurer la déviation du trafic multimédia à la fois au niveau global et au niveau de chaque jonction RTC. Lorsque vous activez la déviation du trafic multimédia au niveau global, vous avez le choix entre deux options : **Toujours ignorer** et **Utiliser la configuration des sites et des régions** .

L’option **Toujours ignorer** engendre une tentative de contournement pour tous les appels RTC. Elle est utiilisée pour les déploiements où il n’est pas nécessaire d’activer le contrôle d’admission d’appel ou d’indiquer des informations de configuration détaillées concernant la période de tentative de déviation du trafic multimédia. En outre, cette option est appliquée lorsque la connectivité entre les clients et les passerelles RTC est satisfaisante. Dans cette configuration, les sous-réseaux sont mappés à un seul ID de contournement, calculé par le système.

L’option **Utiliser la configuration des sites et des régions** associe l’ID de contournement à la configuration de site ou de région chargée de prendre la décision relative au contournement. Cette configuration présente l’avantage d’apporter la flexibilité de configurer le contournement pour la plupart des topologies courantes. Elle permet de contrôler de manière précise quand le contournement doit se produire et prend en charge les interactions avec le contrôle d’admission des appels (CAC). Le système tente de vous faciliter la tâche en affectant automatiquement des ID de contournement comme indiqué ci-dessous.

  - Le système affecte automatiquement un ID de contournement unique à chaque région.

  - Tout site connecté à une région via une liaison de réseau étendu (WAN) non soumise à des contraintes de bande passante hérite du même ID de contournement que la région.

  - Un site connecté à une région via une liaison de réseau étendu à bande passante restreinte se voit affecter un ID de contournement différent de celui de la région.

  - Les sous-réseaux associés à chaque site héritent de l’ID de contournement de ce site.

## Voir aussi

#### Concepts

[Vue d’ensemble de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-overview-of-media-bypass.md)  
[Déviation du trafic multimédia et contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)  
[Configuration technique requise pour la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)

