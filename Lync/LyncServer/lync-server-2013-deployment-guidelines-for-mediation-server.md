---
title: 'Lync Server 2013 : Instructions de déploiement du serveur de médiation'
TOCTitle: Instructions de déploiement du serveur de médiation
ms:assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398622(v=OCS.15)
ms:contentKeyID: 49297844
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Instructions de déploiement du serveur de médiation dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Cette rubrique décrit des directives de planification pour le déploiement du serveur de médiation. Après les avoir passées en revue, nous vous conseillons d’utiliser l’outil de planification pour créer et afficher d’autres topologies possibles qui peuvent servir de modèles pour visualiser à quoi pourrait ressembler la topologie finale sur mesure que vous décidez de déployer.

## serveur de médiation colocalisé ou autonome ?

Le serveur de médiation est colocalisé par défaut sur le serveur Standard Edition ou le serveur frontal dans un pool de serveurs frontaux sur les sites centraux. Le nombre d’appels RTC (réseau téléphonique commuté) pouvant être gérés et le nombre d’ordinateurs requis dans le pool dépendront des éléments suivants :

  - du nombre d’homologues de passerelle que le pool de serveurs de médiation contrôle ;

  - des périodes de trafic aux heures de pointe via ces passerelles ;

  - du pourcentage d’appels qui contournent le serveur de médiation.

Lors de la planification, n’oubliez de tenir compte de la configuration de traitement multimédia pour les appels RTC et les conférences A/V qui ne sont pas configurés pour le contournement du média, ainsi que du traitement nécessaire pour gérer les interactions de signalisation des nombreux appels devant être pris en charge aux heures de pointe. Si la puissance du processeur n’est pas suffisante, vous devrez alors déployer un pool de serveurs de médiation autonome. Les passerelles RTC, les IP-PBX et contrôleurs de frontière de session (SBC) devront être scindés en sous-ensembles contrôlés par les serveurs de médiation colocalisés dans un pool et les serveurs de médiation autonomes dans un ou plusieurs pools autonomes.

Si vous avez déployé des passerelles RTC, des systèmes IP-PBX ou des contrôleurs de frontière de session (SBC) dont les fonctionnalités ne permettent pas d’interagir avec un pool de serveurs de médiation, notamment dans le cadre des opérations énoncées ci-après, vous devrez alors les associer à un pool autonome constitué d’un serveur de médiation unique :

  - Exécutez l’équilibrage de charge DNS de la couche réseau sur les serveurs de médiation au sein d’un pool (ou bien acheminez de manière uniforme le trafic sur tous les serveurs de médiation de ce dernier)

  - Acceptez le trafic de n’importe quel serveur de médiation dans un pool

Vous pouvez utiliser l’outil de planification Microsoft Lync Server 2013 pour évaluer si le pool frontal dans lequel vous souhaitez colocaliser le serveur de médiation peut gérer la charge. Si votre environnement ne remplit pas les conditions requises, vous devez alors déployer un pool de serveurs de médiation autonome.

## Considérations relatives au site central et aux sites de succursale

Les serveurs de médiation sur le site central peuvent être utilisés pour acheminer les appels sur les sites de succursale pour les passerelles RTC ou les IP-PBX. Si vous déployez des jonctions SIP, cependant, vous devez déployer un serveur de médiation sur le site où s’arrête chaque jonction. La disponibilité d’un serveur de médiation sur le site central qui achemine les appels sur un site de succursale pour un IP/PBX ou une passerelle RTC ne requiert pas l’utilisation de la déviation du trafic multimédia. Cependant, si vous pouvez l’activer, vous pourrez réduire la latence du chemin d’accès des médias et par conséquent, obtenir une qualité des médias améliorée du fait que le chemin d’accès des médias n’est plus nécessaire pour suivre le chemin de signalisation. La déviation du trafic multimédia réduira également la charge de traitement sur le pool.

> [!NOTE]  
> La déviation du trafic multimédia ne fonctionnera pas avec chaque passerelle RTC, système IP-PBX et SBC. Microsoft a testé plusieurs passerelles RTC et systèmes SBC en collaboration avec des partenaires agréés et a réalisé plusieurs tests avec les systèmes IP-PBX de Cisco. La déviation du trafic multimédia n’est prise en charge qu’avec les produits et versions répertoriés dans « Infrastructure qualifiée pour Microsoft Lync » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</a>.

Si la résistance de site de succursale est requise, un Survivable Branch Appliance ou une combinaison d’un serveur frontal, d’un serveur de médiation et d’une passerelle doit être déployé sur le site de succursale. (L’hypothèse avec la résistance de site de succursale est que la présence et la conférence ne sont pas résilientes sur le site.) Pour des instructions de planification de site de succursale pour la voix, reportez-vous à [Planification de la résistance vocale d’un site de succursale dans Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

Pour les interactions avec un IP-PBX, si ce dernier ne prend pas correctement en charge les interactions des médias préliminaires avec celles de plusieurs boîtes de dialogue préliminaires et les interactions RFC 3960, une coupure peut se produire sur le message d’accueil pour les appels entrants de l’IP-PBX vers les points de terminaison Lync. Ce comportement peut s’aggraver si un serveur de médiation sur le site central achemine les appels pour un IP-PBX là où s’arrête l’itinéraire sur un site de succursale, car la signalisation a besoin de plus de temps pour se terminer. Si vous rencontrez ce problème, le seul moyen de réduire la coupure sur le message d’accueil consiste à déployer un serveur de médiation sur le site de succursale.

Pour finir, si votre site central comporte un TDM PBX ou que votre IP-PBX ne supprime pas le besoin d’une passerelle RTC, vous devez alors déployer une passerelle sur l’itinéraire d’appel qui se connecte au serveur de médiation et au PBX.

> [!NOTE]  
> Pour améliorer les performances multimédias d’un serveur de médiation autonome, activez RSS (receive-side scaling) sur les cartes réseau de ces serveurs. RSS permet la gestion en parallèle des paquets entrants par plusieurs processeurs sur le serveur. Pour plus d’informations, reportez-vous à « Améliorations RSS dans Windows Server 2008 » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</a>. Pour plus d’informations sur l’activation de RSS, reportez-vous à la documentation de votre carte réseau.
