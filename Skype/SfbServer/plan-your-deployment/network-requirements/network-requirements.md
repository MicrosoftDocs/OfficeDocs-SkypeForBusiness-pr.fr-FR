---
title: Planifier les exigences réseau pour les Skype Entreprise
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
description: 'Résumé : Examinez les considérations sur les composants réseau ci-dessous avant d’implémenter Skype Entreprise Server.'
ms.openlocfilehash: 0441b64014f7754d30f8040d059f2fac15c9cb5d
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014668"
---
# <a name="plan-network-requirements-for-skype-for-business"></a>Planifier les exigences réseau pour les Skype Entreprise

**Résumé :** Examinez les considérations sur les composants réseau ci-dessous avant d’implémenter Skype Entreprise Server.

Les informations de ces rubriques sont également abordées dans le livre blanc Network [Planning, Monitoring, and Troubleshooting with Lync Server](https://www.microsoft.com/download/details.aspx?id=39084) with additional details and depth. Bien que le contenu se réfère explicitement à Lync 2010 et Lync 2013, les considérations pour Skype Entreprise Server restent inchangées.

De même, si votre réseau implique un accès wi-fi et câblé, le livre blanc [Delivering Lync 2013 Real-Time Communications over Wi-Fi](https://www.microsoft.com/download/details.aspx?id=36494) est une bonne référence et s’applique également aux Skype Entreprise Server.

<!-- Deprecated tools
Network performance and needs are directly linked to the traffic load placed on them. When planning your network and server implementations we recommend making use of the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md), the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md), and the [Skype for Business Server 2015 Stress and Performance Tool](../../management-tools/stress-and-performance-tool/stress-and-performance-tool.md).    -->

## <a name="server-hardware"></a>Matériel serveur
<a name="S_hard"> </a>

La carte réseau de chaque serveur de la topologie Skype Entreprise Server doit prendre en charge au moins 1 gigabit par seconde (Gbits/s). En règle générale, vous devez connecter tous les rôles serveur au sein de la topologie Skype Entreprise Server à l’aide d’un réseau local à faible latence et à bande passante élevée. La taille du lan dépend de la taille de la topologie :

- Dans Édition Standard topologies, les serveurs doivent être dans un réseau qui prend en charge 1 Gbps Ethernet ou un équivalent.

- Dans Êdition Entreprise topologies, la plupart des serveurs doivent être dans un réseau qui prend en charge plus de 1 Gbps, en particulier lors de la prise en charge des conférences audio/vidéo (A/V) et du partage d’applications.

Pour l’intégration du réseau téléphonique commuté (PSTN), vous pouvez l’intégrer à l’aide de lignes T1/E1 ou d’une trunking SIP.

## <a name="audiovideo-network-requirements"></a>Conditions requises pour le réseau audio/vidéo
<a name="AV_req"> </a>

Les conditions réseau requises pour l’audio/vidéo (A/V) dans un déploiement Skype Entreprise Server sont les suivantes :

- Si vous déployez un serveur Edge unique ou un pool de serveurs Edge  à l’aide de l’équilibrage de charge DNS, vous pouvez configurer le pare-feu externe pour effectuer la traduction d’adresses réseau (NAT). Vous ne pouvez pas configurer le pare-feu _interne_ pour effectuer la nat. Pour plus d’informations, voir [Planification des ports et des pare-feu.](../edge-server-deployments/edge-environmental-requirements.md#port-and-firewall-planning)

    > [!IMPORTANT]
    > Si vous avez un pool de serveurs Edge et que vous utilisez un équilibreur de charge matérielle, vous devez utiliser des adresses IP publiques sur les serveurs Edge et vous ne pouvez pas utiliser nat pour les serveurs ou le pool sur votre périphérique nat (par exemple, un dispositif de pare-feu ou un commutateur LAN. Pour plus d’informations, [voir scénarios de serveur Edge dans Skype Entreprise Server](../edge-server-deployments/scenarios.md).

- Si votre organisation utilise une infrastructure de qualité de service (QoS), le sous-système multimédia est compatible avec cette infrastructure.

- Si vous utilisez la sécurité du protocole Internet (IPsec), nous vous recommandons de désactiver IPsec sur les plages de ports utilisées pour le trafic A/V. Pour plus d’informations, voir [exceptions IPsec.](#ipsec-exceptions)

Pour fournir une qualité de média optimale, faites les choses suivantes :

- Approvisionnement des liaisons réseau pour prendre en charge le débit de 65 kilobits par seconde (Kbits/s) par flux audio et 500 Kbits/s par flux vidéo, si elles sont activées, pendant les périodes d’utilisation maximales. Une session audio ou vidéo double utilise deux flux, de sorte qu’une simple connexion audio/téléphonique nécessite 130 Kbits/s pour couvrir chaque flux. La vidéo utilisera également un total de 1 000 Kbits/s pour effectuer une connexion en amont et en aval.

- Pour faire face à des pics inattendus du trafic et à une utilisation accrue au fil du temps, les points de terminaison multimédias Skype Entreprise Server peuvent s’adapter à différentes conditions réseau et prendre en charge trois fois le débit pour l’audio et la vidéo tout en conservant une qualité acceptable. Ne supposez pas que cette capacité d’adaptation masquera le problème lorsqu’un réseau est sous-mis en service. Dans un réseau sous-mis en service, la capacité des points de terminaison multimédias Skype Entreprise Server à gérer dynamiquement différentes conditions réseau (par exemple, une perte de paquets élevée temporaire) est réduite.

- Pour les liaisons réseau où l’approvisionnement est très coûteux et difficile, vous de devez envisager la mise en service pour un volume de trafic inférieur. Dans ce scénario, laissez l’souplesse des points de terminaison multimédias Skype Entreprise Server s’ensoquent de la différence entre le volume de trafic et le niveau de trafic de pointe, au prix d’une réduction de la qualité de la voix. En outre, il y aura une diminution de l’espace d’en-tête autrement disponible pour assimiler les pics soudains du trafic.

- Pour les liaisons qui ne peuvent pas être correctement mise en service à court terme (par exemple, un site qui utilise des liaisons WAN très médiocres), envisagez de désactiver la vidéo pour certains utilisateurs.

- Mettre en service le réseau pour garantir un délai maximal de bout en bout (latence) de 150 millisecondes (ms) en charge maximale. La latence est la seule altération du réseau que les composants multimédias Skype Entreprise Server ne peuvent pas réduire, et il est important de rechercher et d’éliminer les points faibles.

- Pour les serveurs qui exécutent un logiciel antivirus, incluez tous les serveurs qui exécutent des Skype Entreprise Server dans la liste des exceptions pour fournir des performances et une qualité audio optimales.

## <a name="ipsec-exceptions"></a>Exceptions IPsec

Dans les réseaux d’entreprise où la sécurité du protocole Internet (IPsec, Internet Protocol security) a été déployée (voir les RFC 4301-4309 de l’IETF), IPsec doit être désactivée sur la plage de ports utilisée pour la transmission des données audio/vidéo et des panoramas vidéo. Cette recommandation s’explique par la nécessité d’éviter tout retard dans l’affectation des ports multimédias lors de la négociation IPsec.

Le tableau suivant présente les paramètres recommandés pour les exceptions IPsec.

**Exceptions recommandées pour IPsec**

|Nom de la règle |Adresse IP source |Adresse IP de destination |Protocole |Port source |Port de destination |Besoin d’authentification |
|:--- |:--- |:--- |:--- |:---|:---|:--- |
|Serveur Edge A/V, ports internes/entrants|N’importe lequel  |Serveur Edge A/V - interne|UDP et TCP|N’importe lequel |N’importe lequel |Ne pas authentifier|
|Serveur Edge A/V, ports externes/entrants|N’importe lequel  |Serveur Edge A/V - externe|UDP et TCP|N’importe lequel |N’importe lequel |Ne pas authentifier|
|Serveur Edge A/V, ports internes/sortants|Serveur Edge A/V - interne  |Serveur Edge A/V - externe |UDP et TCP|N’importe lequel |N’importe lequel |Ne pas authentifier|
|Serveur Edge A/V, ports externes/sortants|Serveur Edge A/V - externe |N’importe lequel |UDP et TCP|N’importe lequel |N’importe lequel |Ne pas authentifier|
|Serveur de médiation, ports entrants|N’importe lequel  |Serveur(s) de médiation |UDP et TCP|N’importe lequel |N’importe lequel |Ne pas authentifier|
|Serveur de médiation, ports sortants|Serveur(s) de médiation  |N’importe lequel|UDP et TCP|N’importe lequel |N’importe lequel |Ne pas authentifier|
|Intendant Conférence entrant|N’importe lequel  |Serveur frontal exécutant l’Intendant Conférence |UDP et TCP|N’importe lequel |N’importe lequel |Ne pas authentifier|
|Intendant Conférence sortant|Serveur frontal exécutant l’Intendant Conférence  |N’importe lequel|UDP et TCP|N’importe lequel |N’importe lequel |Ne pas authentifier|
|Serveur de conférence A/V, ports entrants|N’importe lequel|Serveurs frontaux|UDP et TCP|N’importe lequel |N’importe lequel |Ne pas authentifier|
|Conférence A/V, ports sortants|Serveurs frontaux|N’importe lequel|UDP et TCP|N’importe lequel |N’importe lequel |Ne pas authentifier|
|Exchange, ports entrants|N’importe lequel|Messagerie unifiée Exchange|UDP et TCP|N’importe lequel |N’importe lequel |Ne pas authentifier|
|Serveurs de partage d’application, ports entrants|N’importe lequel|Serveurs de partage d’application|UDP et TCP|N’importe lequel |N’importe lequel |Ne pas authentifier|
|Serveur de partage d’application, ports sortants|Serveurs de partage d’application| N’importe lequel |UDP et TCP|N’importe lequel |N’importe lequel |Ne pas authentifier|
|Exchange, ports sortants|Messagerie unifiée Exchange|N’importe lequel|UDP et TCP|N’importe lequel |N’importe lequel |Ne pas authentifier|
|Clients| N’importe lequel  |N’importe lequel|UDP et TCP|N’importe lequel |N’importe lequel |Ne pas authentifier|
|         |         |         |         |         |         |         |


## <a name="conferencing-network-requirements"></a>Conditions requises pour le réseau de conférence
<a name="Conf_req"> </a>

La bande passante utilisée pour télécharger le contenu des conférences à partir du serveur IIS (Internet Information Services) dépend de la taille du contenu. Vous pouvez choisir de surveiller l’utilisation réelle et d’ajuster la planification de la bande passante en conséquence.

## <a name="network-bandwidth-requirements-for-media-traffic"></a>Besoins en bande passante réseau pour le trafic multimédia
<a name="Conf_req"> </a>

Une partie importante de la planification réseau consiste à s’assurer que votre réseau peut gérer le trafic multimédia généré par Skype Entreprise Server. Cette section vous aide à planifier le trafic multimédia.

### <a name="media-traffic-network-usage"></a>Utilisation du réseau de trafic multimédia
<a name="Net_req"> </a>

L’utilisation de la bande passante par le trafic multimédia peut être difficile à calculer en raison du nombre de variables différentes, comme l’utilisation du codec, la résolution et les niveaux d’activité. L’utilisation de la bande passante est une fonction du codec utilisé et de l’activité du flux, qui peut varier d’un scénario à l’autre. Le tableau suivant répertorie les codecs audio généralement utilisés dans les scénarios Skype Entreprise Server.

**Bande passante du codec audio**

|**Audio codec**|**Scénario**|**Vitesse de bits de la charge utile audio (KBPS)**|**Charge utile audio de la bande passante et en-tête IP uniquement (Kbits/s)**|**Charge utile audio de la bande passante, en-tête IP, UDP, RTP et SRTP (Kbits/s)**|**Charge utile audio de la bande passante, en-tête IP, UDP, RTP, SRTP et correction d’erreur de transfert (Kbits/s)**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Large bande RTAudio  <br/> |Pair à pair  <br/> |29.0  <br/> |45.0  <br/> |57.0  <br/> |86.0  <br/> |
|Bande étroite RTAudio  <br/> |PSTN d’égal à égal  <br/> |11.8  <br/> |27.8  <br/> |39.8  <br/> |51.6  <br/> |
|G.722  <br/> |Conférence  <br/> |64.0  <br/> |80.0  <br/> |95.6  <br/> |159.6  <br/> |
|Stéréo G.722  <br/> |Conférence d’égal à égal  <br/> |128.0  <br/> |144.0  <br/> |159.6  <br/> |223.6  <br/> |
|G.711  <br/> |PSTN, Conférence  <br/> |64.0  <br/> |80.0  <br/> |92.0  <br/> |156.0  <br/> |
|Siren  <br/> |Conférence  <br/> |16.0  <br/> |32.0  <br/> |47.6  <br/> |63.6  <br/> |
|SILK Wideband  <br/> |Pair à pair  <br/> |36.0  <br/> |52.0  <br/> |64.0  <br/> |100.0  <br/> |
|SILK Wideband  <br/> |Pair à pair  <br/> |26.0  <br/> |42.0  <br/> |54.0  <br/> |80.0  <br/> |
|SILK Wideband  <br/> |Pair à pair  <br/> |20.0  <br/> |36.0  <br/> |48.0  <br/> |68.0  <br/> |
|BANDE LARGEBANDE/bande étroite  <br/> |Pair à pair  <br/> |13.0  <br/> |29.0  <br/> |41.0  <br/> |54.0  <br/> |

> [!NOTE]
> Les appels PSTN du client Skype Entreprise utilisent généralement le codec G.711, qui nécessite une bande passante élevée. Si suffisamment de bande passante n’est pas disponible pour ce codec, les appels peuvent échouer avec une erreur semblable à celle-ci dans les journaux multimédias : **Atleast one codec must be enabled, hr: c0042004**. Les journaux multimédias (fichiers .blog) sont chiffrés et ne peuvent être décodés que par le support technique de Microsoft.

Les numéros de bande passante du tableau précédent sont basés sur la paquetisation de 20 ms (50 paquets par seconde) et, pour les codecs Siren et G.722, incluent la surcharge SRTP (Secure Real-Time Transport Protocol) supplémentaire des scénarios de conférence et supposent que le flux est actif à 100 %. La correction des erreurs de forward (FEC) est utilisée dynamiquement en cas de perte de paquets sur le lien afin de maintenir la qualité du flux audio.

La version stéréo du codec G.722 est utilisée par les systèmes basés sur le système de salle Lync, qui utilise un microphone stéréo unique ou une paire de microphones mono pour permettre aux écouteurs de mieux distinguer les haut-parleurs dans la salle de réunion.

**Bande passante de la résolution vidéo**

|**Codec vidéo**|**Résolution et proportions**|**Vitesse de bits de charge utile vidéo maximale (Kbits/s)**|**Vitesse de bits de charge utile vidéo minimale (Kbits/s)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |320 x 180 (16:9)  <br/> 212 x 160 (4:3)  <br/> |250  <br/> |15   <br/> |
|H.264/RTVideo  <br/> |424 x 240 (16:9)  <br/> 320 x 240 (4:3)  <br/> |350  <br/> |100  <br/> |
|H.264  <br/> |480 x 270 (16:9)  <br/> 424 x 320 (4:3)  <br/> |450  <br/> |200  <br/> |
|H.264/RTVideo  <br/> |640 x 360 (16:9)  <br/> 640 x 480 (4:3)  <br/> |800  <br/> |300  <br/> |
|H.264  <br/> |848 x 480 (16:9)  <br/> |1500  <br/> |400  <br/> |
|H.264  <br/> |960 x 540 (16:9)  <br/> |2000  <br/> |500  <br/> |
|H.264/RTVideo  <br/> |1280 x 720 (16:9)  <br/> |2500  <br/> |700  <br/> |
|H.264  <br/> |1920x1080 (16:9)  <br/> |4000  <br/> |1500  <br/> |
|H.264/RTVideo  <br/> |960 x 144 (20:3)  <br/> |500  <br/> |15   <br/> |
|H.264  <br/> |1280 x 192 (20:3)  <br/> |1000  <br/> |250  <br/> |
|H.264  <br/> |1920 x 288 (20:3)  <br/> |2000  <br/> |500  <br/> |

Le codec par défaut de la vidéo est la norme H.264/MPEG-4 Part 10 Advanced Video Coding, ainsi que ses extensions de codage vidéo évolutives pour l’évolutivité temporelle. Pour maintenir l’interopérabilité avec les clients hérités, le codec RTVideo est toujours utilisé pour les appels d’égal à égal entre Skype Entreprise Server clients hérités. Dans les sessions de conférence avec des clients Skype Entreprise Server et hérités, le point de terminaison Skype Entreprise Server peut encoder la vidéo à l’aide de codecs vidéo et envoyer le flux bitstream H.264 aux clients Skype Entreprise Server et rtVideo bitstream aux clients hérités.

La bande passante requise dépend de la résolution, de la qualité, de la fréquence d’images et de la quantité de mouvement ou de changement dans l’image. Pour chaque résolution, il existe deux taux de bits pertinents :

- **Vitesse de bits de charge utile maximale** Il s’agit de la vitesse de bits qu’un point de terminaison utilisera pour la résolution à la fréquence d’images maximale. Il s’agit de la valeur qui permet la meilleure qualité vidéo et sonore.

- **Vitesse de bits de charge utile minimale** Il s’agit de la vitesse de bits en dessous de laquelle Skype Entreprise Server point de terminaison passe à la résolution inférieure suivante. Pour garantir une certaine résolution, la vitesse de bits de la charge utile vidéo disponible ne doit pas être inférieure à cette vitesse de bits minimale pour cette résolution. Cette valeur vous permet de comprendre la valeur la plus faible possible si la vitesse de bit maximale n’est pas disponible ou pratique. Pour certains utilisateurs, une telle vidéo à faible vitesse de bits peut offrir une expérience vidéo inacceptable, donc utilisez avec précaution ces vitesses de bits de charge utile vidéo minimales. Notez que pour les scènes vidéo statiques et immuables, la vitesse de bits réelle peut temporairement être inférieure à la vitesse de bits minimale.

Skype Entreprise Server prend en charge de nombreuses résolutions. Cela permet aux Skype Entreprise Server de s’ajuster à différentes bandes passantes réseau et aux fonctionnalités du client de réception. Le rapport d’aspect par Skype Entreprise Server est de 16:9. Les proportions 4:3 héritées sont toujours pris en charge pour les webcams qui n’autorisent pas la capture dans les proportions 16:9.

Le FEC vidéo est toujours inclus dans la vitesse de bits de la charge utile vidéo lorsqu’il est utilisé. Il n’existe donc pas de valeurs distinctes pour le FEC vidéo et sans fec vidéo.

Les points de terminaison ne transmettent pas les paquets audio ou vidéo en continu. Selon le scénario, les niveaux d’activité de flux sont différents, ce qui indique à quelle fréquence les paquets sont envoyés pour un flux. L’activité d’un flux varie en fonction du support et du scénario et non pas du codec qui est utilisé. Dans un scénario poste à poste :

- Les points de terminaison envoient uniquement des flux audio lorsque les utilisateurs parlent.

- Les deux participants reçoivent des flux audio.

- Si la vidéo est utilisée, les deux points de terminaison envoient et reçoivent des flux vidéo pendant l’appel.

- Pour les scènes vidéo statiques, la vitesse de bits réelle peut temporairement être très faible, car le codec vidéo ignore les zones d’encodage de la vidéo sans modification depuis l’exemple précédent.

Dans un scénario de conférence :

- Les points de terminaison envoient des flux audio uniquement lorsque les utilisateurs parlent.

- Tous les participants reçoivent des flux audio.

- Si la vidéo est utilisée, tous les participants peuvent recevoir jusqu’à cinq flux vidéo entrants et un flux panoramique (par exemple, proportions 20:3). Par défaut, les cinq flux vidéo entrants sont basés sur l’historique du haut-parleur actif, mais les utilisateurs peuvent également manuellement sélectionner les participants desquels ils souhaitent recevoir un flux vidéo. Si la multi-vidéo est activée, la résolution et la bande passante requises pour chacun des flux vidéo seront inférieures.

- Chaque participant qui active le flux vidéo d’envoi de l’utilisateur envoie un ou plusieurs flux vidéo. Skype Entreprise Server a la possibilité d’envoyer jusqu’à cinq flux vidéo pour optimiser la qualité de la vidéo pour tous les clients de réception. Le nombre réel de flux vidéo envoyé est déterminé par l’émetteur en fonction de la capacité du processeur, de la bande passante montante disponible et du nombre de clients de réception qui demandent un flux vidéo spécifique. Dans le cas le plus courant, un flux vidéo H.264 et un flux vidéo RTVideo sont envoyés quand un client hérité participe à une conférence. Il se peut également que plusieurs flux vidéo H.264 (par exemple, avec différentes résolutions vidéo) soient envoyés pour différentes demandes.

Outre la bande passante requise pour le trafic RTP (Real-Time Transport Protocol) pour les supports audio et vidéo, le protocole RTCP (Real-Time Transport Control Protocol) a lui aussi besoin de bande passante. RTCP est utilisé pour le signalement des statistiques et le contrôle hors-bande du flux RTP. Pour la planification, utilisez les valeurs de bande passante contenues dans le tableau ci-dessous pour le trafic RTCP. Ces valeurs représentent la bande passante maximale utilisée pour le protocole RTCP et sont différentes pour les flux audio et vidéo en raison des différences dans les données de contrôle.

**Bande passante RTCP**

|**Media**|**Bande passante maximale RTCP (Kbits/s)**|
|:-----|:-----|
|Audio  <br/> |5  <br/> |
|Vidéo (uniquement H.264 ou RTVideo envoyé/reçu)  <br/> |10  <br/> |
|Vidéo (H.264 et RTVideo envoyé/reçu)  <br/> |15   <br/> |

Pour la planification de la capacité, les deux statistiques suivantes sont d’intérêt :

- **Bande passante maximale sans FEC** Bande passante maximale consommée par un flux. Cela inclut l’activité classique du flux et le codec classique utilisé dans le scénario sans FEC. Il s’agit de la bande passante lorsque l’activité du flux est maximale et qu’aucune perte de paquets ne vient déclencher l’utilisation de la correction d’erreur de transfert. Cela est utile pour calculer la quantité de bande passante qui doit être allouée pour permettre l’utilisation du codec dans un scénario donné. La fec n’est pas attendue comme une exigence sur un réseau géré.

- **Bande passante maximale avec fec** Bande passante maximale consommée par un flux. Cela inclut l’activité classique du flux et le codec classique utilisé dans le scénario avec FEC. Il s’agit de la bande passante lorsque l’activité du flux est maximale et qu’une perte de paquets vient déclencher l’utilisation de la correction d’erreur de transfert pour améliorer la qualité. Cela est utile pour calculer la quantité de bande passante qui doit être allouée pour permettre l’utilisation du codec dans un scénario donné et permettre l’utilisation de la fec pour préserver la qualité dans des conditions de perte de paquets.

Les tableaux ci-dessous répertorient également une valeur de bande passante supplémentaire, la **bande passante type**. Il s’agit de la bande passante moyenne consommée par un flux. Cela inclut l’activité classique du flux et le codec type utilisé dans le scénario. Cette bande passante peut être utilisée pour l’aroximation de la quantité de bande passante consommée par le trafic multimédia à un moment spécifique, mais ne doit pas être utilisée pour la planification de la capacité, car les appels individuels dépasseront cette valeur lorsque le niveau d’activité est supérieur à la moyenne. La bande passante de flux vidéo classique dans les tableaux ci-dessous est basée sur une combinaison de différentes résolutions vidéo telles que observées dans les données client mesurées, et les installations plus petites sont susceptibles d’avoir des nombres réels qui diffèrent des données du tableau. Par exemple, dans les sessions d’égal à égal, la plupart des utilisateurs utilisent la fenêtre de rendu vidéo par défaut, tandis qu’un pourcentage d’utilisateurs augmente ou agrandit l’application Skype Entreprise Server pour permettre de meilleures résolutions vidéo.

Les tableaux suivants fournissent des valeurs pour les différents scénarios.

**Planification de la capacité audio/vidéo pour des sessions poste à poste**

|**Media**|**Codec**|**Bande passante pour un flux type ( Kbits/s)**|**Bande passante maximale sans correction d’erreur de transfert**|**Bande passante maximale avec correction d’erreur de transfert**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |Large bande RTAudio  <br/> |39.8  <br/> |62  <br/> |91  <br/> |
|Audio  <br/> |Bande étroite RTAudio  <br/> |29.3  <br/> |44.8  <br/> |56.6  <br/> |
|Audio  <br/> |SILK Wideband  <br/> |44.3  <br/> |69  <br/> |105  <br/> |
|Vidéo principale lors de l’appel Skype Entreprise Server points de terminaison  <br/> |H.264  <br/> |460  <br/> |4010 (pour une résolution maximale de 1920x1080)  <br/> |Déjà inclus  <br/> |
|Vidéo principale lors de l’appel de Lync 2010 Office Communicator 2007 R2  <br/> |RTVideo  <br/> |460  <br/> |2510 (pour une résolution maximale de 1280x720)  <br/> |Déjà inclus  <br/> |
|Vidéo panoramique lors de l’appel Skype Entreprise Server points de terminaison  <br/> |H.264  <br/> |190  <br/> |2010 (pour une résolution maximale de 1920x288)  <br/> |Déjà inclus  <br/> |
|Vidéo panoramique lors de l’appel de points de terminaison Lync 2010  <br/> |RTVideo  <br/> |190  <br/> |510 (pour une résolution maximale de 960x144)  <br/> |Déjà inclus  <br/> |

**Planification de la capacité audio/vidéo pour les conférences**

|**Media**|**Codec type**|**Bande passante pour un flux type ( Kbits/s)**|**Bande passante maximale sans correction d’erreur de transfert**|**Bande passante maximale avec correction d’erreur de transfert**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G.722  <br/> |46.1  <br/> |100.6  <br/> |164.6  <br/> |
|Audio  <br/> |Siren  <br/> |25.5  <br/> |52.6  <br/> |68.6  <br/> |
|Réception vidéo principale  <br/> |H.264 et RTVideo¹  <br/> |260  <br/> |8015  <br/> |Non applicable  <br/> |
|Envoi vidéo principal  <br/> |H.264 et RTVideo  <br/> |270  <br/> |8015  <br/> |Non applicable  <br/> |
|Réception vidéo panoramique  <br/> |H.264 et RTVideo  <br/> |190  <br/> |2010 (pour une résolution maximale de 1920x288)  <br/> |Non applicable  <br/> |
|Envoi vidéo panoramique  <br/> |H.264 et RTVideo  <br/> |190  <br/> |2515 ²  <br/> |Non applicable  <br/> |

1. Rt Video est envoyé en plus de H.264 lorsque les clients Lync 2010 sont connectés à la conférence.

2. S’il existe plusieurs flux, ils partagent dynamiquement la bande passante allouée.

Pour la vidéo principale, la bande passante de flux type est la bande passante agrégée sur tous les flux vidéo reçus et la bande passante maximale sur tous les flux vidéo d’envoi. Même avec plusieurs flux vidéo, la bande passante vidéo classique est plus petite que dans le scénario pair à pair, car de nombreuses conférences vidéo utilisent le partage de contenu qui entraîne des fenêtres vidéo beaucoup plus petites et donc des résolutions vidéo plus petites. La bande passante de charge utile vidéo agrégée maximale prise en charge est de 8 000 Kbits/s pour les deux, les flux d’envoi et de réception qui seront utilisés (par exemple, s’il existe deux flux vidéo entrants de 1920x1080p). Les valeurs maximales sont rarement visibles dans les implémentations réelles.

Lors de la création d’une conférence à plusieurs qui utilise la fonctionnalité d’affichage galerie, l’utilisation de la bande passante augmente initialement au fil de la participation des participants, puis diminue à mesure que les résolutions sont abandonnées pour s’adapter au maximum.

||**2 participants**|**3 participants**|**4 participants**|**5 participants**|**6 participants**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Résolutions maximales reçues** <br/> |1920x1080  <br/> |1280 x 720  <br/> |640 x 360  <br/> |640 x 360 320 x 240  <br/> |640 x 360 320 x 240  <br/> |
|**Vitesse de bits moyenne totale** <br/> |2128  <br/> |4050  <br/> |1304  <br/> |1224  <br/> |1565  <br/> |
|**Vitesse de bits maximale totale** <br/> |4063  <br/> |5890  <br/> |2860  <br/> |2699  <br/> |3017  <br/> |

La bande passante de flux type pour la vidéo panoramique est basée sur les appareils qui diffusent uniquement des vidéos panoramiques de 960 x 144. Attendez-vous à ce que la bande passante de flux classique augmente lors de l’utilisation d’appareils avec une vidéo panoramique de 1920 x 288.

**Planification de la capacité audio pour PSTN**

|**Media**|**Codec type**|**Bande passante pour un flux type ( Kbits/s)**|**Bande passante maximale sans correction d’erreur de transfert**|**Bande passante maximale avec correction d’erreur de transfert**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G.711 (cela inclut les participants PSTN aux conférences)  <br/> |64.8  <br/> |97  <br/> |161  <br/> |
|Audio  <br/> |Bande étroite RTAudio  <br/> |30.9  <br/> |44.8  <br/> |56.6  <br/> |

Les valeurs de bande passante pour le réseau contenues dans ces tableaux représentent uniquement le trafic unidirectionnel et incluent 5 Kbits/s pour le trafic RTCP pour chaque flux.

## <a name="managing-quality-of-service"></a>Gestion de la qualité de service
<a name="man_QOS"> </a>

La qualité de service (QoS) est une technologie réseau utilisée dans certaines organisations pour fournir une expérience optimale aux utilisateurs finaux pour les communications audio et vidéo. La QoS est le plus souvent utilisée sur les réseaux où la bande passante est limitée : avec un grand nombre de paquets réseau concurrents pour une quantité assez faible de bande passante disponible, QoS permet aux administrateurs d’affecter des priorités plus élevées aux paquets transportant des données audio ou vidéo. En accordant à ces paquets une priorité plus élevée, les communications audio et vidéo sont susceptibles de se terminer plus rapidement et avec moins d’interruption que les sessions réseau impliquant des éléments tels que les transferts de fichiers, la navigation web ou les sauvegardes de bases de données. C’est la raison pour laquelle la priorité « Meilleur effort » est affectée aux paquets réseau utilisés pour les transferts de fichiers ou les sauvegardes de bases de données.

> [!NOTE]
> En règle générale, la QoS s’applique uniquement aux sessions de communication sur votre réseau interne. Lorsque vous implémentez QoS, vous configurez vos serveurs et routeurs pour prendre en charge le marquage de paquets d’une manière particulière qui n’est peut-être pas prise en charge sur Internet ou sur d’autres réseaux. Même si la qualité de service est prise en charge sur d’autres réseaux, il n’est pas garanti que QoS sera configuré exactement de la même façon que vous avez configuré le service. Si vous utilisez MPLS, vous devez travailler avec votre fournisseur MPLS.

Skype Entreprise Server ne nécessite pas QoS, mais il est vivement recommandé. Si vous avez des problèmes de perte de paquets sur le réseau, les solutions disponibles sont d’ajouter davantage de bande passante ou d’implémenter QoS. Si l’ajout de bande passante n’est pas possible, l’implémentation de QoS peut être votre seul frais pour résoudre le problème.

Skype Entreprise Server offre une prise en charge complète de la qualité de service : cela signifie que les organisations qui utilisent déjà QoS peuvent facilement intégrer des Skype Entreprise Server à leur infrastructure réseau existante. Pour ce faire, vous devez suivre les étapes suivantes :

- [Activation de la QoS dans Skype Entreprise Server pour les appareils qui ne sont pas basés sur Windows](../../manage/network-management/qos/enabling-qos-for-devices-that-are-not-based-on-windows.md). Par défaut, QoS est désactivée pour les ordinateurs et autres périphériques (tels que les iPhones) qui exécutent d’autres systèmes d’exploitation. Bien que vous pouvez utiliser Skype Entreprise Server pour activer et désactiver la qualité de service pour les appareils, vous ne pouvez généralement pas utiliser le produit pour modifier les codes DSCP utilisés par ces appareils.

- [Configuration des plages de ports et d’une](../../manage/network-management/qos/configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)stratégie de qualité de service pour vos serveurs de conférence, d’application et de médiation. Vous devez réserver un ensemble unique de ports pour différents types de paquets, tels que les paquets audio et vidéo. En utilisant Skype Entreprise Server vous n’activez pas ou ne désactivez pas QoS en activant une valeur de propriété sur True ou False. Au lieu de cela, vous activez QoS en configurant des plages de ports, puis en créant et en appliquant une stratégie de groupe. Si vous décidez ultérieurement de ne pas utiliser QoS, vous pouvez « désactiver » la QoS en supprimant les objets de stratégie de groupe appropriés.

- [Configuration des plages de ports et d’une stratégie de qualité de service pour vos serveurs Edge.](../../manage/network-management/qos/configuring-port-ranges-for-your-edge-servers.md) Bien que cela ne soit pas requis, vous pouvez configurer vos serveurs Edge de façon à utiliser les mêmes plages de ports que vos autres serveurs. La configuration d’une stratégie QoS s’fait uniquement pour le côté interne de vos serveurs Edge. En raison du fait que la QoS est conçue pour une utilisation sur votre réseau interne et non sur Internet.

- [Configuration des plages de ports et d’une](../../manage/network-management/qos/configuring-port-ranges-for-your-skype-clients.md)stratégie de qualité de service pour vos clients dans Skype Entreprise Server . Ces plages de ports s’appliquent uniquement aux ordinateurs clients et sont généralement différentes des plages de ports configurées sur vos serveurs. Notez que Skype Entreprise Server ne prend pas en charge la QoS pour les Windows d’exploitation autres que Windows 10.


> [!NOTE]
> Si vous utilisez Windows Server 2012 ou Windows Server 2012 R2, vous pouvez être intéressé par le nouvel ensemble de cmdlets Windows PowerShell disponibles pour la gestion de QoS sur cette plateforme. Pour plus d’informations, [voir Windows PowerShell Cmdlets for Networking](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj717268(v=ws.11)).

QoS est également abordée dans le livre blanc Network [Planning, Monitoring, and Troubleshooting with Lync Server](https://www.microsoft.com/download/details.aspx?id=39084) with additional details and depth. Bien que le contenu se réfère explicitement à Lync 2010 et Lync 2013, les considérations pour Skype Entreprise Server restent inchangées.

## <a name="see-also"></a>Voir aussi
<a name="man_QOS"> </a>

[Planifier IPv6 dans Skype Entreprise](ipv6.md)

[Exigences relatives à l’équilibrage de charge Skype Entreprise](load-balancing.md)

[DNS requirements for Skype Entreprise Server](dns.md)
