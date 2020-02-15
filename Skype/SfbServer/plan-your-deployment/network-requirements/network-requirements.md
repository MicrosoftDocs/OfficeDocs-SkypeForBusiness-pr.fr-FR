---
title: Planification de la configuration réseau requise pour Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
description: 'Résumé : consultez les considérations relatives aux composants réseau ci-dessous avant d’implémenter Skype entreprise Server.'
ms.openlocfilehash: 709da2ddd60b5b6ee69c22264c159d5d94ab91e3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42025795"
---
# <a name="plan-network-requirements-for-skype-for-business"></a>Planification de la configuration réseau requise pour Skype entreprise

**Résumé :** Examinez les considérations relatives aux composants réseau ci-dessous avant d’implémenter Skype entreprise Server.

Les informations contenues dans ces rubriques sont également abordées dans le livre blanc [: planification réseau, surveillance et résolution des problèmes avec Lync Server](https://www.microsoft.com/download/details.aspx?id=39084) avec des détails et une profondeur supplémentaires. Bien que le contenu soit explicitement fait référence à Lync 2010 et Lync 2013, les considérations relatives à Skype entreprise Server restent inchangées.

De même, si votre réseau implique un accès Wi-Fi ainsi qu’un accès câblé, le livre blanc [livraison de communications en temps réel de Lync 2013 sur Wi-Fi](https://www.microsoft.com/download/details.aspx?id=36494) est une bonne référence et s’applique également à Skype entreprise Server.

<!-- Deprecated tools
Network performance and needs are directly linked to the traffic load placed on them. When planning your network and server implementations we recommend making use of the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md), the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md), and the [Skype for Business Server 2015 Stress and Performance Tool](../../management-tools/stress-and-performance-tool/stress-and-performance-tool.md).    -->

## <a name="server-hardware"></a>Matériel serveur
<a name="S_hard"> </a>

La carte réseau de chaque serveur de la topologie Skype entreprise Server doit prendre en charge au moins 1 Gigabit par seconde (Gbits/s). En général, vous devez connecter tous les rôles serveur au sein de la topologie Skype entreprise Server à l’aide d’un réseau local (LAN) à faible bande passante et à faible latence. La taille du réseau local dépend de la taille de la topologie :

- Dans les topologies Standard Edition, les serveurs doivent se trouver dans un réseau prenant en charge 1 Gbits/s ou équivalent.

- Dans les topologies Enterprise Edition, la plupart des serveurs doivent se trouver dans un réseau prenant en charge plus de 1 Gbits/s, en particulier lors de la prise en charge de la conférence audio/vidéo (A/V) et du partage d’applications.

Pour l’intégration d’un réseau téléphonique commuté (PSTN), vous pouvez intégrer à l’aide de lignes T1/E1 ou de jonctions SIP.

## <a name="audiovideo-network-requirements"></a>Configuration requise pour le réseau audio/vidéo
<a name="AV_req"> </a>

La configuration réseau requise pour l’audio/vidéo (A/V) dans un déploiement Skype entreprise Server inclut les éléments suivants :

- Si vous déployez un serveur Edge unique ou un pool de serveurs Edge à l’aide de l’équilibrage de charge DNS, vous pouvez configurer le pare-feu _externe_ pour qu’il procède à la traduction d’adresses réseau (NAT). Vous ne pouvez pas configurer le pare-feu _interne_ pour qu’il effectue la traduction d’adresses réseau. Pour plus d’informations, voir la [planification des ports et des pare-feu](../edge-server-deployments/edge-environmental-requirements.md#port-and-firewall-planning).

    > [!IMPORTANT]
    > Si vous disposez d’un pool de serveurs Edge et que vous utilisez un programme d’équilibrage de la charge matérielle, vous devez utiliser des adresses IP publiques sur les serveurs Edge et vous ne pouvez pas utiliser le protocole NAT pour les serveurs ou le pool sur votre appareil compatible NAT (par exemple, un appareil de pare-feu ou un commutateur LAN. Pour plus d’informations, consultez la rubrique [scénarios de serveur Edge dans Skype entreprise Server](../edge-server-deployments/scenarios.md).

- Si votre organisation utilise une infrastructure de qualité de service (QoS), le sous-système multimédia est compatible avec cette infrastructure.

- Si vous utilisez la sécurité du protocole Internet (IPsec), nous vous recommandons de désactiver IPsec sur les plages de ports utilisées pour le trafic A/V. Pour plus d’informations, consultez la rubrique [IPSec exceptions](#ipsec-exceptions).

Pour obtenir une qualité multimédia optimale, procédez comme suit :

- Configurez les liens réseau pour qu’ils prennent en charge un débit de 65 kilobits par seconde (Kbits/s) par flux audio et 500 Kbits/s par flux vidéo, s’ils sont activés, pendant les périodes d’utilisation maximale. Une session audio ou vidéo bidirectionnelle utilise deux flux, de sorte qu’une connexion audio/téléphone simple nécessite que 130Kbps traite chaque flux. La vidéo utilise également 1000 kbits/s pour transporter une connexion en amont et en aval.

- Pour faire face à des pics inattendus dans le trafic et une utilisation accrue au fil du temps, les points de terminaison des médias Skype entreprise Server peuvent s’adapter aux conditions de réseau variables et prendre en charge trois fois le débit pour l’audio et la vidéo tout en conservant une qualité acceptable. Ne partez pas du principe que cette adaptabilité masque le problème lorsqu’un réseau est sous-configuré. Dans un réseau sous-approvisionné, la capacité des points de terminaison de Skype entreprise Server à traiter dynamiquement les différentes conditions réseau (par exemple, une perte de paquets élevée temporaire) est réduite.

- Pour les liens réseau dans lesquels la mise en service est très coûteuse et difficile, vous devrez peut-être envisager la mise en service d’un volume de trafic inférieur. Dans ce scénario, l’élasticité des points de terminaison des médias Skype entreprise Server absorbe la différence entre le volume de trafic et le niveau de trafic maximal, au prix d’une réduction de la qualité de la voix. De plus, il y aura une diminution de la hauteur suffisante autrement disponible pour absorber les pics soudains dans le trafic.

- Pour les liens qui ne peuvent pas être configurés correctement à court terme (par exemple, un site qui utilise des liaisons de réseau étendu très médiocres), envisagez de désactiver la vidéo pour certains utilisateurs.

- Approvisionnez le réseau pour garantir un retard de bout en bout de 150 millisecondes (MS) au-dessous de la charge maximale. La latence est l’un des problèmes de réseau que les composants multimédias de Skype entreprise Server ne peuvent pas réduire, et il est important de trouver et d’éliminer les points faibles.

- Pour les serveurs qui exécutent un logiciel antivirus, incluez tous les serveurs qui exécutent Skype entreprise Server dans la liste des exceptions afin de fournir des performances et une qualité audio optimales.

## <a name="ipsec-exceptions"></a>Exceptions IPsec

Dans les réseaux d’entreprise où la sécurité du protocole Internet (IPsec, Internet Protocol security) a été déployée (voir les RFC 4301-4309 de l’IETF), IPsec doit être désactivée sur la plage de ports utilisée pour la transmission des données audio/vidéo et des panoramas vidéo. Cette recommandation s’explique par la nécessité d’éviter tout retard dans l’affectation des ports multimédias lors de la négociation IPsec.

Le tableau suivant présente les paramètres recommandés pour les exceptions IPsec.

**Exceptions recommandées pour IPsec**

|Nom de la règle |Adresse IP source |Adresse IP de destination |Protocole |Port source |Port de destination |Besoin d’authentification |
|:--- |:--- |:--- |:--- |:---|:---|:--- |
|Serveur Edge A/V, ports internes/entrants|N'importe lequel  |Serveur Edge A/V - interne|UDP et TCP|N'importe lequel |N'importe lequel |Ne pas authentifier|
|Serveur Edge A/V, ports externes/entrants|N'importe lequel  |Serveur Edge A/V - externe|UDP et TCP|N'importe lequel |N'importe lequel |Ne pas authentifier|
|Serveur Edge A/V, ports internes/sortants|Serveur Edge A/V - interne  |Serveur Edge A/V - externe |UDP et TCP|N'importe lequel |N'importe lequel |Ne pas authentifier|
|Serveur Edge A/V, ports externes/sortants|Serveur Edge A/V - externe |N'importe lequel |UDP et TCP|N'importe lequel |N'importe lequel |Ne pas authentifier|
|Serveur de médiation, ports entrants|N'importe lequel  |Serveur (s) de médiation |UDP et TCP|N'importe lequel |N'importe lequel |Ne pas authentifier|
|Serveur de médiation, ports sortants|Serveur (s) de médiation  |N'importe lequel|UDP et TCP|N'importe lequel |N'importe lequel |Ne pas authentifier|
|Intendant Conférence entrant|N'importe lequel  |Serveur frontal exécutant l’Intendant Conférence |UDP et TCP|N'importe lequel |N'importe lequel |Ne pas authentifier|
|Intendant Conférence sortant|Serveur frontal exécutant l’Intendant Conférence  |N'importe lequel|UDP et TCP|N'importe lequel |N'importe lequel |Ne pas authentifier|
|Serveur de conférence A/V, ports entrants|N'importe lequel|Serveurs frontaux|UDP et TCP|N'importe lequel |N'importe lequel |Ne pas authentifier|
|Conférence A/V, ports sortants|Serveurs frontaux|N'importe lequel|UDP et TCP|N'importe lequel |N'importe lequel |Ne pas authentifier|
|Exchange, ports entrants|N'importe lequel|Messagerie unifiée Exchange|UDP et TCP|N'importe lequel |N'importe lequel |Ne pas authentifier|
|Serveurs de partage d’application, ports entrants|N'importe lequel|Serveurs de partage d’application|UDP et TCP|N'importe lequel |N'importe lequel |Ne pas authentifier|
|Serveur de partage d’application, ports sortants|Serveurs de partage d’application| N'importe lequel |UDP et TCP|N'importe lequel |N'importe lequel |Ne pas authentifier|
|Exchange, ports sortants|Messagerie unifiée Exchange|N'importe lequel|UDP et TCP|N'importe lequel |N'importe lequel |Ne pas authentifier|
|Clients| N'importe lequel  |N'importe lequel|UDP et TCP|N'importe lequel |N'importe lequel |Ne pas authentifier|
|         |         |         |         |         |         |         |


## <a name="conferencing-network-requirements"></a>Configuration requise pour le réseau de conférence
<a name="Conf_req"> </a>

La bande passante utilisée pour télécharger du contenu de conférence à partir du serveur IIS (Internet Information Services) dépend de la taille du contenu. Vous pouvez choisir de surveiller l’utilisation réelle et ajuster la planification de la bande passante en conséquence.

## <a name="network-bandwidth-requirements-for-media-traffic"></a>Besoins en bande passante réseau pour le trafic multimédia
<a name="Conf_req"> </a>

Un élément important de la planification du réseau est de s’assurer que votre réseau peut gérer le trafic multimédia généré par Skype entreprise Server. Cette section vous aide à planifier le trafic multimédia.

### <a name="media-traffic-network-usage"></a>Utilisation du réseau de trafic multimédia
<a name="Net_req"> </a>

L’utilisation de la bande passante par le trafic multimédia peut être difficile à calculer en raison du nombre de variables différentes, comme l’utilisation du codec, la résolution et les niveaux d’activité. L’utilisation de la bande passante est une fonction du codec utilisé et de l’activité du flux, qui peut varier d’un scénario à l’autre. Le tableau suivant répertorie les codecs audio généralement utilisés dans les scénarios Skype entreprise Server.

**Bande passante du codec audio**

|**Audio codec**|**Scénario**|**Vitesse de transmission de la charge utile audio (KBITs/s)**|**Charge utile audio de la bande passante et en-tête IP uniquement (Kbits/s)**|**Charge utile audio de la bande passante, en-tête IP, UDP, RTP et SRTP (Kbits/s)**|**Charge utile audio de la bande passante, en-tête IP, UDP, RTP, SRTP et correction d’erreur de transfert (Kbits/s)**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Large bande RTAudio  <br/> |Pair à pair  <br/> |29,0  <br/> |45,0  <br/> |57,0  <br/> |86,0  <br/> |
|Bande étroite RTAudio  <br/> |P2P d’égal à égal  <br/> |11,8  <br/> |27,8  <br/> |39,8  <br/> |51,6  <br/> |
|G. 722  <br/> |Vidéoconférence  <br/> |64,0  <br/> |80,0  <br/> |95,6  <br/> |159,6  <br/> |
|Stéréo G.722  <br/> |Conférence P2P  <br/> |128,0  <br/> |144,0  <br/> |159,6  <br/> |223,6  <br/> |
|G. 711  <br/> |RTC, Conférence  <br/> |64,0  <br/> |80,0  <br/> |92,0  <br/> |156,0  <br/> |
|Siren  <br/> |Vidéoconférence  <br/> |16,0  <br/> |32,0  <br/> |47,6  <br/> |63,6  <br/> |
|Large bande de soie  <br/> |Pair à pair  <br/> |36,0  <br/> |52,0  <br/> |64,0  <br/> |100,0  <br/> |
|Large bande de soie  <br/> |Pair à pair  <br/> |26,0  <br/> |42,0  <br/> |54,0  <br/> |80,0  <br/> |
|Large bande de soie  <br/> |Pair à pair  <br/> |20,0  <br/> |36,0  <br/> |48,0  <br/> |68,0  <br/> |
|Large bande de soie/bande étroite  <br/> |Pair à pair  <br/> |13,0  <br/> |29,0  <br/> |41,0  <br/> |54,0  <br/> |

> [!NOTE]
> Les appels PSTN provenant du client Skype entreprise utilisent généralement le codec G. 711, qui nécessite une bande passante élevée. S’il n’y a pas suffisamment de bande passante disponible pour ce codec, les appels peuvent échouer avec une erreur ressemblant à ce qui suit dans les journaux multimédia : au **moins un codec doit être activé, hr : c0042004**. Les journaux multimédias (fichiers. blogs) sont chiffrés et ne peuvent être décodés que par le personnel du support technique Microsoft.

Les numéros de bande passante du tableau précédent sont basés sur le 20 ms packeting (50 paquets par seconde) et les codecs Siren et de G. 722 incluent la charge de travail SRTP (Secure Real-Time Transport Protocol) supplémentaire à partir de scénarios de conférence et supposent que le flux est 100% actif. La correction d’erreur de transfert (FEC) est utilisée dynamiquement en cas de perte de paquets sur le lien pour aider à maintenir la qualité du flux audio.

La version stéréo du codec G. 722 est utilisée par les systèmes basés sur Lync Room System, qui utilise un microphone stéréo unique ou une paire de micros mono pour permettre aux écouteurs de mieux distinguer plusieurs haut-parleurs dans la salle de réunion.

**Bande passante de la résolution vidéo**

|**Codec vidéo**|**Résolution et proportions**|**Vitesse de transmission de la charge utile vidéo maximale (Kbits/s)**|**Vitesse de transmission de la charge utile vidéo minimale (Kbits/s)**|
|:-----|:-----|:-----|:-----|
|H. 264  <br/> |320x180 (16:9)  <br/> 212x160 (4:3)  <br/> |250  <br/> |15   <br/> |
|H. 264/RTVideo  <br/> |424x240 (16:9)  <br/> 320x240 (4:3)  <br/> |350  <br/> |100  <br/> |
|H. 264  <br/> |480x270 (16:9)  <br/> 424x320 (4:3)  <br/> |450  <br/> |200  <br/> |
|H. 264/RTVideo  <br/> |640x360 (16:9)  <br/> 640x480 (4:3)  <br/> |800  <br/> |300  <br/> |
|H. 264  <br/> |848x480 (16:9)  <br/> |1500  <br/> |400  <br/> |
|H. 264  <br/> |960x540 (16:9)  <br/> |2000  <br/> |500  <br/> |
|H. 264/RTVideo  <br/> |1280x720 (16:9)  <br/> |2500  <br/> |700  <br/> |
|H. 264  <br/> |1920x1080 (16:9)  <br/> |4000  <br/> |1500  <br/> |
|H. 264/RTVideo  <br/> |960x144 (20:3)  <br/> |500  <br/> |15   <br/> |
|H. 264  <br/> |1280x192 (20:3)  <br/> |1000  <br/> |250  <br/> |
|H. 264  <br/> |1 920x288 (20:3)  <br/> |2000  <br/> |500  <br/> |

Le codec par défaut pour la vidéo est la norme H. 264/MPEG-4 part 10 Advanced Video Coding, ainsi que ses extensions de codage vidéo évolutives pour une évolutivité temporelle. Pour conserver l’interopérabilité avec les clients hérités, le codec RTVideo est toujours utilisé pour les appels P2P entre Skype entreprise Server et les clients hérités. Dans les sessions de conférence avec Skype entreprise Server et les clients hérités, le point de terminaison Skype entreprise Server peut coder la vidéo à l’aide de codecs vidéo et envoyer le flux de transmission H. 264 aux clients Skype entreprise Server et le flux de flux RTVideo à l’héritage clients.

La bande passante requise dépend de la résolution, de la qualité, de la fréquence d’images et de la quantité de mouvement ou des modifications apportées à l’image. Pour chaque résolution, il existe deux vitesses de transmission pertinentes :

- **Vitesse de transmission de la charge utile maximale** Il s’agit de la vitesse de transmission utilisée par un point de terminaison pour la résolution à la fréquence d’images maximale. Il s’agit de la valeur qui permet la qualité vidéo et audio la plus élevée.

- **Vitesse de transmission de la charge utile minimale** Il s’agit de la vitesse de transmission au-dessous de laquelle un point de terminaison Skype entreprise Server bascule vers la résolution inférieure suivante. Pour garantir une certaine résolution, la vitesse de transmission de la charge utile vidéo ne doit pas être inférieure à cette vitesse de transmission minimale pour cette résolution. Cette valeur vous aide à comprendre la valeur la plus faible possible si la vitesse de transmission maximale n’est pas disponible ou pratique. Pour certains utilisateurs, ce type de vidéo à faible vitesse de transmission peut fournir une expérience vidéo inacceptable, donc soyez prudent avec ces débits minimaux de charge vidéo vidéo. Notez que pour les scènes vidéo statiques immuables, la vitesse de transmission réelle peut tomber temporairement en dessous de la vitesse de transmission minimale.

Skype entreprise Server prend en charge de nombreuses résolutions. Cela permet à Skype entreprise Server de s’adapter à une bande passante réseau différente et de la réception des fonctionnalités client. Le format d’image par défaut de Skype entreprise Server est de 16:9. Les proportions 4:3 héritées sont toujours prises en charge pour les webcams qui ne permettent pas la capture dans les proportions 16:9.

La fonction FEC vidéo est toujours incluse dans la vitesse de transmission de la charge utile vidéo lorsqu’elle est utilisée de sorte qu’il n’y a pas de valeurs distinctes pour la vidéo FEC et sans FEC vidéo.

Les points de terminaison ne transmettent pas les paquets audio ou vidéo en continu. Selon le scénario, les niveaux d’activité de flux sont différents, ce qui indique à quelle fréquence les paquets sont envoyés pour un flux. L’activité d’un flux varie en fonction du support et du scénario et non pas du codec qui est utilisé. Dans un scénario poste à poste :

- Les points de terminaison envoient uniquement des flux audio lorsque les utilisateurs parlent.

- Les deux participants reçoivent des flux audio.

- Si la vidéo est utilisée, les deux points de terminaison envoient et reçoivent des flux vidéo pendant l’appel.

- Pour les scènes vidéo statiques, la vitesse de transmission réelle peut être temporairement très faible, car le codec vidéo ignorera les régions de codage de la vidéo sans modification depuis l’exemple précédent.

Dans un scénario de conférence :

- Les points de terminaison envoient des flux audio uniquement lorsque les utilisateurs parlent.

- Tous les participants reçoivent des flux audio.

- Si la vidéo est utilisée, tous les participants peuvent recevoir jusqu’à cinq flux vidéo entrants et un flux panoramique (par exemple, proportions 20:3). Par défaut, les cinq flux vidéo entrants sont basés sur l’historique du haut-parleur actif, mais les utilisateurs peuvent également manuellement sélectionner les participants desquels ils souhaitent recevoir un flux vidéo. Si la fonction Multividéo est activée, la résolution et la bande passante requise pour chacun des flux vidéo seront plus faibles.

- Chaque participant qui active le flux vidéo d’envoi de l’utilisateur enverra un ou plusieurs flux vidéo. Skype entreprise Server offre la possibilité d’envoyer jusqu’à cinq flux vidéo afin d’optimiser la qualité vidéo pour tous les clients de réception. Le nombre réel de flux vidéo envoyé est déterminé par l’émetteur en fonction de la capacité du processeur, de la bande passante montante disponible et du nombre de clients de réception qui demandent un flux vidéo spécifique. Dans le cas le plus courant, un flux vidéo H.264 et un flux vidéo RTVideo sont envoyés quand un client hérité participe à une conférence. Il se peut également que plusieurs flux vidéo H.264 (par exemple, avec différentes résolutions vidéo) soient envoyés pour différentes demandes.

Outre la bande passante requise pour le trafic RTP (Real-Time Transport Protocol) pour les supports audio et vidéo, le protocole RTCP (Real-Time Transport Control Protocol) a lui aussi besoin de bande passante. RTCP est utilisé pour le signalement des statistiques et le contrôle hors-bande du flux RTP. Pour la planification, utilisez les valeurs de bande passante contenues dans le tableau ci-dessous pour le trafic RTCP. Ces valeurs représentent la bande passante maximale utilisée pour le RTCP et diffèrent pour les flux audio et vidéo en raison de différences entre les données de contrôle.

**Bande passante RTCP**

|**Support**|**Bande passante maximale RTCP (Kbits/s)**|
|:-----|:-----|
|Audio  <br/> |5   <br/> |
|Vidéo (uniquement H.264 ou RTVideo envoyé/reçu)  <br/> |10   <br/> |
|Vidéo (H.264 et RTVideo envoyé/reçu)  <br/> |15   <br/> |

Pour la planification de la capacité, les deux statistiques suivantes sont intéressantes :

- **Bande passante maximale sans FEC** Bande passante maximale utilisée par un flux. Cela inclut l’activité type du flux et le codec standard utilisé dans le scénario sans FEC. Il s’agit de la bande passante lorsque l’activité du flux est maximale et qu’aucune perte de paquets ne vient déclencher l’utilisation de la correction d’erreur de transfert. Cela est utile pour calculer la bande passante qui doit être allouée pour permettre l’utilisation du codec dans un scénario donné. FEC n’est pas censé être une exigence sur un réseau géré.

- **Bande passante maximale avec FEC** Bande passante maximale utilisée par un flux. Cela inclut l’activité type du flux et le codec standard utilisé dans le scénario avec FEC. Il s’agit de la bande passante lorsque l’activité du flux est maximale et qu’une perte de paquets vient déclencher l’utilisation de la correction d’erreur de transfert pour améliorer la qualité. Cela est utile pour calculer la bande passante qui doit être allouée pour permettre l’utilisation du codec dans un scénario donné et permettre l’utilisation de la fonction FEC afin de préserver la qualité sous des conditions de perte de paquets.

Les tableaux ci-dessous répertorient également une valeur de bande passante supplémentaire, la **bande passante type**. Il s’agit de la bande passante moyenne utilisée par un flux. Cela inclut l’activité type du flux et le codec standard utilisé dans le scénario. Cette bande passante peut être utilisée pour évaluer approximativement la consommation de bande passante par le trafic multimédia à un moment donné, mais elle ne doit pas être utilisée pour la planification de la capacité, car les appels individuels dépassent cette valeur lorsque le niveau d’activité est supérieur à la moyenne. La bande passante de flux vidéo classique dans les tableaux ci-dessous est basée sur un mélange de différentes résolutions vidéo observées dans les données client mesurées, et les installations de petite taille sont susceptibles de contenir des chiffres réels qui diffèrent des données de la table. Par exemple, dans les sessions d’égal à égal, la plupart des utilisateurs utiliseront la fenêtre de rendu vidéo par défaut, tandis que le pourcentage d’utilisateurs augmenterait ou augmentaient l’application Skype entreprise Server pour offrir une meilleure résolution vidéo.

Les tableaux suivants fournissent des valeurs pour les différents scénarios.

**Planification de la capacité audio/vidéo pour des sessions poste à poste**

|**Support**|**Codec**|**Bande passante pour un flux type ( Kbits/s)**|**Bande passante maximale sans correction d’erreur de transfert**|**Bande passante maximale avec correction d’erreur de transfert**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |Large bande RTAudio  <br/> |39,8  <br/> |62  <br/> |91  <br/> |
|Audio  <br/> |Bande étroite RTAudio  <br/> |29,3  <br/> |44,8  <br/> |56,6  <br/> |
|Audio  <br/> |Large bande de soie  <br/> |44,3  <br/> |69  <br/> |105  <br/> |
|Vidéo principale lors de l’appel de points de terminaison Skype entreprise Server  <br/> |H. 264  <br/> |460  <br/> |4010 (pour une résolution maximale de 1920x1080)  <br/> |Déjà inclus  <br/> |
|Vidéo principale lors de l’appel de points de terminaison Lync 2010 ou Office Communicator 2007 R2  <br/> |RTVideo  <br/> |460  <br/> |2510 (pour une résolution maximale de 1280x720)  <br/> |Déjà inclus  <br/> |
|Vidéo panoramique lors de l’appel de points de terminaison Skype entreprise Server  <br/> |H. 264  <br/> |190  <br/> |2010 (pour une résolution maximale de 1920x288)  <br/> |Déjà inclus  <br/> |
|Vidéo panoramique lors de l’appel de points de terminaison Lync 2010  <br/> |RTVideo  <br/> |190  <br/> |510 (pour une résolution maximale de 960x144)  <br/> |Déjà inclus  <br/> |

**Planification de la capacité audio/vidéo pour les conférences**

|**Support**|**Codec type**|**Bande passante pour un flux type ( Kbits/s)**|**Bande passante maximale sans correction d’erreur de transfert**|**Bande passante maximale avec correction d’erreur de transfert**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G. 722  <br/> |46,1  <br/> |100,6  <br/> |164,6  <br/> |
|Audio  <br/> |Siren  <br/> |25,5  <br/> |52,6  <br/> |68,6  <br/> |
|Réception vidéo principale  <br/> |H. 264 et RTVideo ¹  <br/> |260  <br/> |8015  <br/> |Non applicable  <br/> |
|Envoi vidéo principal  <br/> |H. 264 et RTVideo  <br/> |270  <br/> |8015  <br/> |Non applicable  <br/> |
|Réception vidéo panoramique  <br/> |H. 264 et RTVideo  <br/> |190  <br/> |2010 (pour une résolution maximale de 1920x288)  <br/> |Non applicable  <br/> |
|Envoi vidéo panoramique  <br/> |H. 264 et RTVideo  <br/> |190  <br/> |2515 ²  <br/> |Non applicable  <br/> |

1. La vidéo RT est envoyée en plus de H. 264 lorsque les clients Lync 2010 sont connectés à la Conférence.

2. S’il existe plusieurs flux, ils partagent dynamiquement la bande passante allouée.

Pour la vidéo principale, la bande passante de flux standard est la bande passante agrégée sur tous les flux vidéo reçus et le flux maximal est la bande passante sur tous les flux vidéo d’envoi. Même avec plusieurs flux vidéo, la bande passante vidéo classique est plus petite que dans le scénario P2P, car de nombreuses vidéoconférences utilisent un partage de contenu qui conduit à des fenêtres vidéo beaucoup plus petites et, par conséquent, une résolution vidéo plus petite. La bande passante de la charge vidéo totale maximale prise en charge est de 8000 Kbits/s pour les flux d’envoi et de réception qui seraient utilisés (par exemple, s’il existe deux flux vidéo 1920x1080p entrants). Les valeurs maximales sont rarement visibles dans les implémentations réelles.

Lors de la création d’une conférence à plusieurs, qui utilise la fonctionnalité d’affichage de la Galerie, l’utilisation de la bande passante augmente au départ à mesure que les participants se joignent, puis diminue à mesure que la résolution s’ajuste à la taille maximale.

||**2 participants**|**3 participants**|**4 participants**|**5 participants**|**6 participants**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Résolutions maximales reçues** <br/> |1920x1080  <br/> |1280x720  <br/> |640x360  <br/> |640x360 320x240  <br/> |640x360 320x240  <br/> |
|**Vitesse de transmission moyenne totale** <br/> |2128  <br/> |4050  <br/> |1304  <br/> |1224  <br/> |1565  <br/> |
|**Débit maximal total** <br/> |4063  <br/> |5890  <br/> |2860  <br/> |2699  <br/> |3017  <br/> |

La bande passante de flux standard pour la vidéo panoramique est basée sur les appareils qui sont uniquement diffusés en vidéo panoramique 960x144. Attendez-vous à ce que la bande passante de flux normale augmente lors de l’utilisation de périphériques avec une vidéo panoramique 1 920x288.

**Planification de la capacité audio pour PSTN**

|**Support**|**Codec type**|**Bande passante pour un flux type ( Kbits/s)**|**Bande passante maximale sans correction d’erreur de transfert**|**Bande passante maximale avec correction d’erreur de transfert**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G. 711 (cela inclut les participants PSTN dans les conférences)  <br/> |64,8  <br/> |97  <br/> |161  <br/> |
|Audio  <br/> |Bande étroite RTAudio  <br/> |30,9  <br/> |44,8  <br/> |56,6  <br/> |

Les valeurs de bande passante pour le réseau contenues dans ces tableaux représentent uniquement le trafic unidirectionnel et incluent 5 Kbits/s pour le trafic RTCP pour chaque flux.

## <a name="managing-quality-of-service"></a>Gestion de la qualité de service
<a name="man_QOS"> </a>

La qualité de service (QoS) est une technologie de mise en réseau qui est utilisée dans certaines organisations afin de fournir une expérience utilisateur final optimale pour les communications audio et vidéo. La qualité de service est la plus fréquente sur les réseaux où la bande passante est limitée : avec un grand nombre de paquets réseau en concurrence pour une quantité de bande passante insuffisante, la qualité de service (QoS) permet aux administrateurs d’attribuer des priorités plus élevées aux paquets portant sur des données audio ou vidéo. En donnant à ces paquets une priorité plus élevée, les communications audio et vidéo sont susceptibles de se terminer plus rapidement et avec moins d’interruption, que les sessions réseau impliquant des transferts de fichiers, la navigation Web ou des sauvegardes de base de données. C’est la raison pour laquelle la priorité « Meilleur effort » est affectée aux paquets réseau utilisés pour les transferts de fichiers ou les sauvegardes de bases de données.

> [!NOTE]
> En règle générale, la qualité de service s’applique uniquement aux sessions de communication sur votre réseau interne. Lorsque vous implémentez QoS, vous configurez vos serveurs et routeurs de sorte qu’ils prennent en charge le marquage de paquets d’une manière spécifique qui n’est peut-être pas prise en charge sur Internet ou sur d’autres réseaux. Même si la qualité de service est prise en charge sur d’autres réseaux, il n’est pas garanti que la qualité de service sera configurée exactement de la même manière que vous avez configuré le service. Si vous utilisez MPLS, vous devez travailler avec votre fournisseur MPLS.

Skype entreprise Server n’exige pas QoS, mais il est fortement recommandé. Si vous rencontrez des problèmes de perte de paquets sur le réseau, vos solutions disponibles permettent d’ajouter davantage de bande passante ou d’implémenter la qualité de service. Si l’ajout de bande passante n’est pas possible, l’implémentation de QoS peut être votre seul payant pour résoudre le problème.

Skype entreprise Server offre une prise en charge complète de la qualité de service (QoS) : cela signifie que les organisations qui utilisent déjà QoS peuvent facilement intégrer Skype entreprise Server à leur infrastructure réseau existante. Pour ce faire, procédez comme suit :

- [Activation de la qualité de service dans Skype entreprise Server pour les appareils qui ne sont pas basés sur Windows](../../manage/network-management/qos/enabling-qos-for-devices-that-are-not-based-on-windows.md). Par défaut, QoS est désactivée pour les ordinateurs et autres périphériques (tels que les iPhones) qui exécutent d’autres systèmes d’exploitation. Bien que vous puissiez utiliser Skype entreprise Server pour activer et désactiver la qualité de service pour les appareils, vous ne pouvez généralement pas utiliser le produit pour modifier les codes DSCP utilisés par ces appareils.

- [La configuration des plages de ports et d’une stratégie de qualité de service pour vos serveurs de conférence, d’application et de médiation](../../manage/network-management/qos/configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). Vous devez réserver un ensemble unique de ports pour différents types de paquets, tels que les paquets audio et vidéo. À l’aide de Skype entreprise Server, vous n’activez pas ou ne désactivez pas la qualité de service en affectant la valeur true ou false à une propriété. Au lieu de cela, vous activez QoS en configurant des plages de ports, puis en créant et en appliquant une stratégie de groupe. Si vous décidez par la suite de ne pas utiliser QoS, vous pouvez « désactiver » la qualité de service (QoS) en supprimant les objets de stratégie de groupe appropriés.

- [La configuration des plages de ports et d’une stratégie de qualité de service pour vos serveurs Edge](../../manage/network-management/qos/configuring-port-ranges-for-your-edge-servers.md). Bien que cela ne soit pas requis, vous pouvez configurer vos serveurs Edge de façon à utiliser les mêmes plages de ports que vos autres serveurs. La configuration d’une stratégie de QoS ne doit être appliquée qu’au côté interne de vos serveurs Edge. Cela est dû au fait que la qualité de service est conçue pour être utilisée sur votre réseau interne et non sur Internet.

- [La configuration des plages de ports et d’une stratégie de qualité de service pour vos clients dans Skype entreprise Server](../../manage/network-management/qos/configuring-port-ranges-for-your-skype-clients.md). Ces plages de ports s’appliquent uniquement aux ordinateurs clients et sont généralement différentes des plages de ports configurées sur vos serveurs. Notez que Skype entreprise Server ne prend pas en charge QoS pour les systèmes d’exploitation Windows autres que Windows 10.


> [!NOTE]
> Si vous utilisez Windows Server 2012 ou Windows Server 2012 R2, le nouvel ensemble d’applets de commande Windows PowerShell disponible pour la gestion de la qualité de service sur cette plateforme est susceptible de vous intéresser. Pour plus d’informations, voir [applets de commande QoS réseau dans Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=285379).

La qualité de service (QoS) est également abordée dans le livre blanc [planification réseau, surveillance et résolution des problèmes avec Lync Server](https://www.microsoft.com/download/details.aspx?id=39084) avec des détails et une profondeur supplémentaires. Bien que le contenu soit explicitement fait référence à Lync 2010 et Lync 2013, les considérations relatives à Skype entreprise Server restent inchangées.

## <a name="see-also"></a>Voir aussi
<a name="man_QOS"> </a>

[Planifier IPv6 dans Skype entreprise](ipv6.md)

[Conditions requises pour l’équilibrage de charge pour Skype entreprise](load-balancing.md)

[Configuration DNS requise pour Skype entreprise Server](dns.md)
