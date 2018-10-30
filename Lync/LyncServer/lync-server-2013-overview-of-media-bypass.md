---
title: 'Lync Server 2013 : Vue d’ensemble de la déviation du trafic multimédia'
TOCTitle: Vue d’ensemble de la déviation du trafic multimédia
ms:assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412740(v=OCS.15)
ms:contentKeyID: 49298338
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue d’ensemble de la déviation du trafic multimédia dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-21_

La déviation du trafic multimédia est utile lorsque vous voulez réduire le nombre de serveurs de médiation déployés. Un pool de serveurs de médiation est généralement déployé sur un site central et contrôle des passerelles sur des sites de succursale. L’activation de la déviation du trafic multimédia permet aux médias de passer des appels RTC (réseau téléphonique commuté) depuis des clients situés sur les sites de succursale directement par les passerelles de ces sites. L’acheminement des appels sortants Lync Server 2013 et les stratégies Voix Entreprise doivent être configurés correctement pour que les appels RTC passés depuis les clients sur un site de succursale soient acheminés vers la passerelle appropriée.

Les réseaux Wi-Fi subissent généralement plus de pertes de paquets que les réseaux câblés. La récupération de cette perte de paquets n’est habituellement pas très bien supportée par les passerelles. C’est pourquoi nous vous conseillons d’évaluer la qualité d’un réseau Wi-Fi avant de déterminer si le contournement doit être activé pour un sous-réseau sans fil. Il convient également de tenir compte d’un compromis entre diminution de la latence et récupération de perte de paquets. RTAudio, un codec disponible pour les appels qui ne contournent pas le serveur de médiation, convient davantage à la gestion de la perte de paquets.

Une fois la structure Voix Entreprise en place, la planification de la déviation du trafic multimédia est simple.

  - Si vous avez une topologie centralisée sans liaison de réseau distant vers les sites de succursale, vous pouvez activer la déviation du trafic multimédia car il n’est pas nécessaire d’affiner le contrôle.

  - Si votre topologie distribuée est constituée d’une ou plusieurs régions réseau et de leurs sites de succursale affiliés, déterminez les éléments suivants :
    
      - Si vos homologues de serveur de médiation sont en mesure de prendre en charge les fonctionnalités requises pour la déviation du trafic multimédia.
    
      - Quels sont les sites bien connectés dans chaque région réseau.
    
      - Quelle combinaison de déviation du trafic multimédia et de contrôle d’admission des appels est appropriée pour votre réseau.

Lorsque vous activez la déviation du trafic multimédia, un ID unique de contournement est généré automatiquement pour une région réseau et pour tous les sites réseau sans restrictions de bande passante au sein de cette région. Les sites avec restrictions de bande passante dans la région et les sites connectés à la région sur les liaisons du réseau étendu se voient attribués à chacun un ID de contournement unique.

Lorsqu’un utilisateur passe un appel vers le réseau téléphonique commuté, le serveur de médiation compare l’ID de contournement du sous-réseau du client avec celui du sous-réseau de la passerelle. Si les deux ID de contournement concordent, la déviation du trafic multimédia est utilisée pour l’appel. Si les ID ne coïncident pas, le média de l’appel doit transiter par le serveur de médiation.

Lorsqu’un utilisateur reçoit un appel depuis le réseau téléphonique commuté, le client de l’utilisateur compare son ID de contournement à celui de la passerelle RTC. Si les deux ID concordent, le média passe directement de la passerelle au client, en contournant le serveur de médiation.

Seuls les clients et les périphériques Lync 2010 ou version ultérieure prennent en charge les interactions de la déviation du trafic multimédia à l’aide d’un serveur de médiation.

> [!IMPORTANT]  
> En plus d’autoriser la déviation du trafic multimédia global, vous devez autoriser la déviation du trafic multimédia individuellement sur chaque jonction RTC. Si le contournement est autorisé globalement mais ne l’est pas pour une jonction RTC donnée, la déviation du trafic multimédia ne sera appelée pour aucun appel impliquant cette jonction RTC. En outre, lorsque la déviation du trafic multimédia est définie sur <strong>Utiliser les informations de site et de région</strong> , vous devez associer tous les sous-réseaux routables aux sites sur lesquels ils se situent. Si un site compte des sous-réseaux routables pour lesquels le contournement n’est pas souhaité, ces sous-réseaux devront être regroupés dans un nouveau site avant d’autoriser la déviation du trafic multimédia. Vous êtes ainsi assuré que les sous-réseaux non routables recevront un ID de contournement distinct.

## Voir aussi

#### Concepts

[Modes de déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-media-bypass-modes.md)  
[Déviation du trafic multimédia et contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)  
[Configuration technique requise pour la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)

