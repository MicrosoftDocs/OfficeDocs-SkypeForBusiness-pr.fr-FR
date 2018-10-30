---
title: Exigences relatives à l'infrastructure réseau pour Lync Server 2013
TOCTitle: Exigences relatives à l'infrastructure réseau pour Lync Server 2013
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425841(v=OCS.15)
ms:contentKeyID: 49296842
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exigences relatives à l'infrastructure réseau pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-08-28_

La carte réseau de chaque serveur de la topologie Lync Server 2013 doit prendre en charge au moins 1 gigabit par seconde (Gbits/s). En général, vous devez connecter tous les rôles serveur de la topologie Lync Server à l’aide d’un réseau local (LAN) à bande passante élevée et à faible latence. La taille du réseau local est fonction de la taille de la topologie :

  - Dans les topologies Standard Edition, les serveurs doivent résider dans un réseau prenant en charge 1 Gbits/s Ethernet ou équivalent.

  - Dans les topologies de pool de serveurs frontaux, la majorité des serveurs doit résider dans un réseau prenant en charge plus de 1 Gbits/s, en particulier pour la prise en charge des fonctionnalités de conférence A/V et du partage d’application.

Dans le cas de l’intégration au réseau téléphonique commuté (RTC ou, en anglais, PSTN pour Public Switched Telephone Network), vous pouvez utiliser les lignes T1/E1 ou les jonctions SIP.

## Conditions de réseau requises pour les fonctionnalités audio/vidéo

Pour utiliser les fonctionnalités audio/vidéo (A/V) dans un déploiement Lync Server, le réseau doit être configuré comme suit :

  - Si vous déployez un serveur Edge unique ou un pool de serveurs Edge utilisant l’équilibrage de la charge DNS, vous pouvez configurer le pare-feu externe en tant que NAT. Vous ne pouvez pas configurer le pare-feu interne en tant que NAT. Pour plus d’informations sur ces conditions requises, voir [Définition de la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) dans la documentation de planification.
    
    > [!IMPORTANT]  
    > Si vous disposer d’un pool de serveurs Edge et que vous utilisez un équilibreur de la charge matérielle, vous devez utiliser des adresses IP publiques sur chacun des serveurs Edge et vous ne pouvez pas utiliser NAT pour les serveurs ou le pool au niveau de votre périphérique NAT (par exemple, le pare-feu ou tout autre périphérique d’infrastructure qui appliquerait NAT au trafic entrant ou sortant). Pour plus d’informations, voir <a href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Résumé des ports - Serveur Edge consolidé mis à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013</a> dans la documentation de planification pour l’accès des utilisateurs externes.

  - Si votre organisation utilise une infrastructure de qualité de service (QoS), le sous-système multimédia est compatible avec cette infrastructure.

  - Si vous utilisez le protocole IPSec, nous vous recommandons de le désactiver sur les plages de ports utilisées pour le trafic A/V. Pour plus d’informations, voir [Exceptions Ipsec dans Lync Server 2013](lync-server-2013-ipsec-exceptions.md) dans la documentation de planification.

Pour bénéficier d’une qualité optimale lors de l’utilisation des fonctionnalités multimédias, procédez comme suit :

  - Configurez les liaisons réseau pour qu’elles prennent en charge un débit de 65 kilobits par seconde (Kbits/s) par flux audio et 500 Kbits/s par flux vidéo, le cas échéant, pendant les pics d’utilisation. Une session audio ou vidéo bidirectionnelle comprend deux flux.

  - Pour gérer les pics imprévus dépassant ces estimations et l’utilisation croissante des fonctionnalités audio/vidéo pouvant se produire au fil du temps, les points de terminaison multimédias Lync Server sont évolutifs. Ils peuvent s’adapter aux conditions fluctuantes du réseau et prendre en charge des charges trois fois supérieures au débit standard (voir le paragraphe précédent) pour les données audio et vidéo, tout en continuant à offrir une qualité acceptable. Cependant, cette capacité d’adaptation ne peut en aucun cas compenser les lacunes d’un réseau présentant une configuration insuffisante. Au contraire, une telle configuration réduit la capacité des points de terminaison multimédias Lync Server à gérer dynamiquement des conditions fluctuantes occasionnant, par exemple, un taux de perte de paquets très élevé.

  - Pour les liaisons réseau dont la mise en service s’avère à la fois coûteuse et difficile, vous serez peut-être contraint à prendre en charge un trafic moins important. Si tel est le cas, laissez l’élasticité des points de terminaison multimédias Lync Server absorber la différence entre ce volume de trafic et les pics, au prix d’une baisse de la qualité vocale. En outre, on constate une réduction de la capacité de traitement supplémentaire pouvant normalement absorber les soudaines augmentations de trafic.

  - Dans le cas des liaisons ne pouvant pas bénéficier d’un débit optimal à court terme, par exemple dans un réseau étendu doté de liaisons de qualité médiocre, vous devez envisager de désactiver les fonctionnalités vidéo pour certains utilisateurs.

  - Configurez votre réseau de manière à assurer un retard maximal (temps de réponse) de 150 millisecondes (ms) de bout en bout en cas de pic de charge. Les temps de réponse sont les seuls désavantages liés au réseau que les composants multimédias de Lync Server ne peuvent pas compenser ; c’est pourquoi il est impératif de trouver et éliminer les points faibles.

  - Pour les serveurs exécutant un logiciel antivirus, incluez tous les serveurs exécutant Lync Server dans la liste d’exceptions du pare-feu de sorte à bénéficier d’une qualité audio et de performances optimales.

## Conditions de réseau requises pour les fonctionnalités de conférence web

La bande passante utilisée pour le téléchargement du contenu de conférence à partir du serveur des services Internet (IIS) dépend du volume du contenu à télécharger.

