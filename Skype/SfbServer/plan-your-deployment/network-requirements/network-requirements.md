---
title: Plan network requirements for Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
description: 'Résumé: passez en revue les considérations relatives aux composants réseau ci-dessous avant d’implémenter Skype entreprise Server.'
ms.openlocfilehash: 56e8b00a4b662d19fd928b439ae8fafb7bcbdb3d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297035"
---
# <a name="plan-network-requirements-for-skype-for-business"></a>Plan network requirements for Skype for Business

**Résumé:** Passez en revue les considérations relatives aux composants réseau ci-dessous avant d’implémenter Skype entreprise Server.

Les informations contenues dans ces rubriques sont également abordées dans le livre blanc [planification du réseau, surveillance et résolution des problèmes liés à Lync Server](https://www.microsoft.com/en-us/download/details.aspx?id=39084) et informations supplémentaires. Même si le contenu fait référence explicitement à Lync 2010 et à Lync 2013, les considérations relatives à Skype entreprise Server ne sont pas modifiées.

De même, si votre réseau utilise le Wi-Fi ainsi que l’accès filaire, le livre blanc [sur les communications en temps réel de Lync 2013 sur un réseau Wi-Fi](https://www.microsoft.com/en-us/download/details.aspx?id=36494) est une bonne référence et est également applicable à Skype entreprise Server.

<!-- Deprecated tools
Network performance and needs are directly linked to the traffic load placed on them. When planning your network and server implementations we recommend making use of the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md), the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md), and the [Skype for Business Server 2015 Stress and Performance Tool](../../management-tools/stress-and-performance-tool/stress-and-performance-tool.md).    -->

## <a name="server-hardware"></a>Matériel serveur
<a name="S_hard"> </a>

La carte réseau de chaque serveur dans la topologie de Skype entreprise Server doit prendre en charge au moins 1 Gbit/s (Gbit/s). En règle générale, vous devez connecter tous les rôles de serveur dans la topologie de Skype entreprise Server à l’aide d’une faible latence et d’un réseau local à bande passante (LAN). La taille du réseau local dépend de la taille de la topologie :

- Dans les topologies Standard Edition, les serveurs doivent se trouver dans un réseau qui prend en charge Ethernet 1 Gbit ou équivalent.

- Dans les topologies Enterprise Edition, la plupart des serveurs doivent se trouver dans un réseau qui prend en charge plus de 1 Gbit/s, en particulier lors de la prise en charge du partage de conférences et d’applications audio/vidéo (A/V).

Dans le cas de l'intégration au réseau téléphonique commuté (RTC ou, en anglais, PSTN pour Public Switched Telephone Network), vous pouvez utiliser les lignes T1/E1 ou les jonctions SIP.

## <a name="audiovideo-network-requirements"></a>Conditions de réseau requises pour les fonctionnalités audio/vidéo
<a name="AV_req"> </a>

La configuration réseau requise pour les appels audio/vidéo (A/V) dans un déploiement de Skype entreprise Server comprend les éléments suivants:

- Si vous déployez un serveur Edge unique ou un pool Edge à l’aide de l’équilibrage de charge DNS, vous pouvez configurer le pare-feu _externe_ pour effectuer la traduction d’adresses réseau (NAT). Vous ne pouvez pas configurer le pare-feu _internal_ pour effectuer la traduction NAT. Pour plus d’informations, consultez la section [planification de port et de pare-feu](../edge-server-deployments/edge-environmental-requirements.md#port-and-firewall-planning).

    > [!IMPORTANT]
    > Si vous disposez d’un pool Edge et que vous utilisez un dispositif d’équilibrage de la charge matérielle, vous devez utiliser des adresses IP publiques sur les serveurs de périphérie et vous ne pouvez pas utiliser la traduction d’adresses réseau pour les serveurs ou le pool sur votre appareil compatible NAT (par exemple, un dispositif de pare-feu ou un commutateur LAN). Pour plus d’informations, reportez-vous à la rubrique [scénarios de serveur Edge dans Skype entreprise Server](../edge-server-deployments/scenarios.md).

- Si votre organisation utilise une infrastructure de qualité de service (QoS), le sous-système multimédia est compatible avec cette infrastructure.

- Si vous utilisez le protocole IPSec, nous vous recommandons de le désactiver sur les plages de ports utilisées pour le trafic A/V. Pour plus d’informations, consultez la section [exceptions IPSec](#ipsec-exceptions).

Pour fournir une qualité optimale lors de l'utilisation des fonctionnalités multimédias, procédez comme suit :

- Configurez les liens réseau pour qu'ils prennent en charge un débit de 65 kilobits par seconde (Kbits/s) par flux audio et 500 Kbits/s par flux vidéo, s'ils sont activés, pendant les périodes d'utilisation de pointe. Une session audio ou vidéo bidirectionnelle utilise deux flux, aussi une connexion audio/ téléphonique simple aura besoin de 130 Kbits/s pour couvrir chaque flux. La vidéo 1000 utilisera de la même manière pour une connexion en amont et en aval.

- Pour faire face à des pics inattendus dans le temps et une utilisation accrue au fil du temps, les points de terminaison de Skype entreprise Server Media peuvent s’adapter à des conditions de réseau variables et supporter trois fois le débit de l’audio et de la vidéo tout en préservant la qualité acceptable. Ne supposez pas que cette capacité de connexion masque le problème quand un réseau est sous-configuré. Dans un réseau sous-configuré, la capacité des points de terminaison Skype entreprise Server Media est réduite à des conditions de réseau variables (par exemple, une perte temporaire de paquets).

- Pour les liaisons réseau dont la mise en service s'avère à la fois coûteuse et difficile, vous serez peut-être contraint à prendre en charge un trafic moins important. Dans ce scénario, l’élasticité des points de terminaison du serveur Skype entreprise Server absorbe la différence entre le volume de trafic et le niveau de trafic de pointe, au coût d’une diminution de la qualité de la voix. En outre, on constatera une réduction de la capacité de traitement supplémentaire pouvant normalement absorber les soudaines augmentations de trafic.

- Dans le cas des liaisons ne pouvant pas bénéficier d'un débit optimal à court terme, par exemple dans un réseau étendu utilisant des liaisons de qualité médiocre, vous devez envisager de désactiver les fonctionnalités vidéo pour certains utilisateurs.

- Configurez le réseau pour garantir un retard maximal (temps de réponse) de 150 millisecondes (ms) de bout en bout en cas de pic de charge. La latence correspond à une déficience du réseau qui empêche les composants multimédias de Skype entreprise Server de réduire, et il est important de rechercher et d’éliminer les points faibles.

- Pour les serveurs exécutant un logiciel antivirus, incluez tous les serveurs exécutant Skype entreprise Server dans la liste des exceptions afin d’offrir des performances et une qualité audio optimales.

## <a name="ipsec-exceptions"></a>Exceptions IPsec

Pour les réseaux d’entreprise pour lesquels la sécurité du protocole Internet (IPsec) (voir IETF RFC 4301-4309) a été déployée, le protocole IPsec doit être désactivé sur la plage de ports utilisée pour la remise de la vidéo audio, vidéo et de panorama. Cette recommandation s’explique par la nécessité d’éviter tout retard dans l’affectation des ports multimédias lors de la négociation IPsec.

Le tableau suivant présente les paramètres recommandés pour les exceptions IPsec.

**Exceptions recommandées pour IPsec**

|Nom de la règle |Adresse IP source |Adresse IP de destination |Protocole |Port source |Port de destination |Besoin d’authentification |
|:--- |:--- |:--- |:--- |:---|:---|:--- |
|Serveur Edge A/V, ports internes/entrants|Indifférente  |Serveur Edge A/V - interne|UDP et TCP|Indifférente  |Indifférente |Ne pas authentifier|
|Serveur Edge A/V, ports externes/entrants|Indifférente  |Serveur Edge A/V - externe|UDP et TCP|Indifférente  |Indifférente |Ne pas authentifier|
|Serveur Edge A/V, ports internes/sortants|Serveur Edge A/V - interne  |Serveur Edge A/V - externe |UDP et TCP|Indifférente  |Indifférente |Ne pas authentifier|
|Serveur Edge A/V, ports externes/sortants|Serveur Edge A/V - externe |Indifférente |UDP et TCP|Indifférente  |Indifférente |Ne pas authentifier|
|Serveur de médiation, ports entrants|Indifférente  |Serveur de médiation |UDP et TCP|Indifférente  |Indifférente |Ne pas authentifier|
|Serveur de médiation, ports sortants|Serveur de médiation  |Indifférente|UDP et TCP|Indifférente  |Indifférente |Ne pas authentifier|
|Intendant Conférence entrant|Indifférente  |Serveur frontal exécutant l’Intendant Conférence |UDP et TCP|Indifférente  |Indifférente |Ne pas authentifier|
|Intendant Conférence sortant|Serveur frontal exécutant l’Intendant Conférence  |Indifférente|UDP et TCP|Indifférente  |Indifférente |Ne pas authentifier|
|Serveur de conférence A/V, ports entrants|Indifférente|serveurs frontaux|UDP et TCP|Indifférente  |Indifférente |Ne pas authentifier|
|Conférence A/V, ports sortants|Serveurs frontaux|Indifférente|UDP et TCP|Indifférente  |Indifférente |Ne pas authentifier|
|Exchange, ports entrants|Indifférente|Messagerie unifiée Exchange|UDP et TCP|Indifférente  |Indifférente |Ne pas authentifier|
|Serveurs de partage d’application, ports entrants|Indifférente|Serveurs de partage d’application|UDP et TCP|Indifférente  |Indifférente |Ne pas authentifier|
|Serveur de partage d’application, ports sortants|Serveurs de partage d’application| Indifférente |UDP et TCP|Indifférente  |Indifférente |Ne pas authentifier|
|Exchange, ports sortants|Messagerie unifiée Exchange|Indifférente|UDP et TCP|Indifférente  |Indifférente |Ne pas authentifier|
|Clients| Indifférente  |Indifférente|UDP et TCP|Indifférente  |Indifférente |Ne pas authentifier|
|         |         |         |         |         |         |         |


## <a name="conferencing-network-requirements"></a>Conditions de réseau requises pour les fonctionnalités de conférence web
<a name="Conf_req"> </a>

La bande passante utilisée pour télécharger le contenu d’une conférence à partir du serveur Internet Information Services (IIS) dépend de la taille du contenu. Vous pouvez surveiller l'utilisation réelle de la bande passante et ajuster la planification de la bande passante en conséquence.

## <a name="network-bandwidth-requirements-for-media-traffic"></a>Configuration requise de la bande passante pour le trafic multimédia
<a name="Conf_req"> </a>

Dans le cadre de la planification du réseau, il est important de s’assurer que votre réseau peut gérer le trafic multimédia généré par Skype entreprise Server. Cette section vous aide à planifier le trafic multimédia.

### <a name="media-traffic-network-usage"></a>Utilisation du réseau pour le trafic multimédia
<a name="Net_req"> </a>

L'utilisation de la bande passante par le trafic multimédia peut être difficile à calculer en raison du nombre de variables différentes, comme l'utilisation du codec, la résolution et les niveaux d'activité. L'utilisation de la bande passante est une fonction du codec utilisé et de l'activité du flux, pouvant varier d'un scénario à l'autre. Le tableau suivant répertorie les codecs audio généralement utilisés dans les scénarios Skype entreprise Server.

**Bande passante du codec audio**

|**Codec audio**|**Scénario**|**Vitesse de transmission de la charge utile audio (Kbits/s)**|**Charge utile audio de la bande passante et en-tête IP uniquement (Kbits/s)**|**Charge utile audio de la bande passante, en-tête IP, UDP, RTP et SRTP (Kbits/s)**|**Charge utile audio de la bande passante, en-tête IP, UDP, RTP, SRTP et correction d'erreur de transfert (Kbits/s)**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Large bande RTAudio  <br/> |Égal à égal  <br/> |29.0  <br/> |45.0  <br/> |57.0  <br/> |86.0  <br/> |
|Bande étroite RTAudio  <br/> |Égal à égal, PSTN  <br/> |11.8  <br/> |27.8  <br/> |39.8  <br/> |51.6  <br/> |
|G.722  <br/> |Téléconférence  <br/> |64.0  <br/> |80.0  <br/> |95.6  <br/> |159.6  <br/> |
|Stéréo G.722  <br/> |Égal à égal, conférence  <br/> |128.0  <br/> |144.0  <br/> |159.6  <br/> |223.6  <br/> |
|G.711  <br/> |RTC, conférence  <br/> |64.0  <br/> |80.0  <br/> |92.0  <br/> |156.0  <br/> |
|Siren  <br/> |Téléconférence  <br/> |16.0  <br/> |32.0  <br/> |47.6  <br/> |63.6  <br/> |
|SILK bande large  <br/> |Égal à égal  <br/> |36.0  <br/> |52.0  <br/> |64.0  <br/> |100.0  <br/> |
|SILK bande large  <br/> |Égal à égal  <br/> |26.0  <br/> |42.0  <br/> |54.0  <br/> |80.0  <br/> |
|SILK bande large  <br/> |Égal à égal  <br/> |20.0  <br/> |36.0  <br/> |48.0  <br/> |68.0  <br/> |
|Bande ultralarge soie  <br/> |Égal à égal  <br/> |13.0  <br/> |29.0  <br/> |41.0  <br/> |54.0  <br/> |

> [!NOTE]
> Les appels RTC du client Skype entreprise utilisent généralement le codec G. 711, qui nécessite une bande passante élevée. S’il n’y a pas assez de bande passante disponible pour ce codec, les appels peuvent échouer en utilisant une erreur qui ressemble à ce qui suit dans les journaux multimédia: au **moins un codec doit être activé, hr: c0042004**. Les journaux multimédias (. blogs) sont chiffrés et ne peuvent être décodés que par le personnel du support Microsoft.

Les valeurs de bande passante contenues dans le tableau ci-dessus reposent sur la mise en paquets 20 ms (50 paquets par seconde) et pour Siren et G.722 incluent le protocole SRTP (Secure Real-Time Transport Protocol) en plus des scénarios de conférence et supposent que le flux est entièrement actif. La correction d'erreur de transfert (FEC) est utilisée dynamiquement en cas de perte de paquet sur la liaison afin de maintenir la qualité du flux audio. 

La version stéréo du codec G.722 est utilisée par les systèmes basés sur Lync Room System, qui s'appuie sur un micro stéréo unique ou une paire de micro mono pour permettre aux participants de mieux distinguer les différents intervenants dans une salle de réunion.

**Bande passante de la résolution vidéo**

|**Codec vidéo**|**Résolution et proportions**|**Vitesse de transmission de la charge utile vidéo maximale (Kbits/s)**|**Vitesse de transmission de la charge utile vidéo minimale (Kbits/s)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |320x180 (16:9)  <br/> 212x160 (4:3)  <br/> |250  <br/> |0,15  <br/> |
|H.264/RTVideo  <br/> |424x240 (16:9)  <br/> 320x240 (4:3)  <br/> |350  <br/> |100  <br/> |
|H.264  <br/> |480x270 (16:9)  <br/> 424x320 (4:3)  <br/> |450  <br/> |200  <br/> |
|H.264/RTVideo  <br/> |640x360 (16:9)  <br/> 640x480 (4:3)  <br/> |800  <br/> |300  <br/> |
|H.264  <br/> |848x480 (16:9)  <br/> |1500  <br/> |400  <br/> |
|H.264  <br/> |960x540 (16:9)  <br/> |2000  <br/> |500  <br/> |
|H.264/RTVideo  <br/> |1 280 x 720 (16:9)  <br/> |2500  <br/> |700  <br/> |
|H.264  <br/> |1 920 x 1 080 (16:9)  <br/> |4000  <br/> |1500  <br/> |
|H.264/RTVideo  <br/> |960x144 (20:3)  <br/> |500  <br/> |0,15  <br/> |
|H.264  <br/> |1 280 x 192 (20:3)  <br/> |1000  <br/> |250  <br/> |
|H.264  <br/> |1 920 x 288 (20:3)  <br/> |2000  <br/> |500  <br/> |

Pour la vidéo, le codec par défaut est la norme H.264/MPEG-4 Part 10 Advanced Video Coding avec ses extensions de codage vidéo évolutives pour une extensibilité dans le temps. Pour préserver l’interopérabilité avec les clients hérités, le codec RTVideo est toujours utilisé pour les appels d’égal à égal entre Skype entreprise Server et les clients hérités. Dans les sessions de conférence avec Skype entreprise Server et les clients hérités, le point de terminaison de Skype entreprise Server est susceptible de coder la vidéo à l’aide de codecs vidéo et d’envoyer le flux binaire H. 264 aux clients Skype entreprise Server et au flux binaire RTVideo à l’ancien. clients.

La bande passante nécessaire dépend de la résolution, de la qualité et de la fréquence d'images. Pour chaque résolution, deux vitesses de transmission pertinentes sont disponibles :

- **Débit maximal de charge utile** Il s’agit de la vitesse de transmission utilisée par un point de terminaison à la fréquence d’images maximale. Cette valeur permet la qualité vidéo et audio maximale.

- **Taux minimal de bits de charge utile** Il s’agit du débit inférieur au-dessous duquel un point de terminaison Skype entreprise Server basculera vers la résolution immédiatement inférieure. Afin de garantir une certaine résolution, la vitesse de transmission de la charge utile vidéo disponible ne doit pas être comprise dans la vitesse de transmission minimale pour cette résolution. Cette valeur permet de comprendre la valeur la plus basse possible lorsque l’utilisation de la vitesse de transmission maximale n’est pas disponible ou pratique. Pour certains utilisateurs, cette vitesse faible peut être considérée comme inacceptable ; ces vitesses de transmission doivent donc être utilisées avec prudence. Notez que pour des vidéos avec peu ou pas de mouvements, la vitesse de transmission réelle peut temporairement être inférieure à la vitesse de transmission minimale.

Skype entreprise Server prend en charge de nombreuses résolutions. Cela permet à Skype entreprise Server d’ajuster différentes bandes passantes réseau et de recevoir les fonctionnalités des clients. Le rapport hauteur-largeur par défaut de Skype entreprise Server est 16:9. Le ratio d’aspect 4:3 hérité est toujours pris en charge pour les webcams qui n’autorisent pas la capture dans les proportions 16:9.

Le FEC vidéo est toujours intégré à la vitesse de transmission de la charge utile vidéo le cas échéant ce qui évite d’avoir des valeurs distinctes avec et sans le FEC vidéo.

Les points de terminaison ne transmettent pas les paquets audio ou vidéo en continu. Selon le scénario, les niveaux d'activité de flux sont différents, ce qui indique à quelle fréquence les paquets sont envoyés pour un flux. L'activité d'un flux varie en fonction du support et du scénario et non pas du codec qui est utilisé. Dans un scénario poste à poste : 

- Les points de terminaison envoient les flux audio uniquement lorsque les intervenants parlent.

- Les deux participants reçoivent des flux audio.

- En cas d'utilisation de la vidéo, les deux points de terminaison envoient et reçoivent des flux vidéo pendant l'appel.

- Pour des vidéos statiques, la vitesse de transmission réelle peut être temporairement très faible, car le codec vidéo n'encodera pas les régions de la vidéo qui ne sont pas modifiées depuis l'extraction de l'échantillon préalable.

Dans un scénario de conférence :

- Les points de terminaison envoient des flux audio uniquement lorsque les utilisateurs parlent.

- Tous les participants reçoivent des flux audio.

- Si la vidéo est utilisée, tous les participants peuvent recevoir jusqu'à cinq flux vidéo entrants et un flux panoramique (par exemple, proportions 20:3). Par défaut, les cinq flux vidéo entrants sont basés sur l'historique du haut-parleur actif, mais les utilisateurs peuvent également manuellement sélectionner les participants desquels ils souhaitent recevoir un flux vidéo. Si la multi-vidéo est activée, la configuration requise pour la résolution et la bande passante peut être inférieure pour chaque flux vidéo.

- Chaque participant qui active le flux vidéo d’envoi de l’utilisateur envoie un ou plusieurs flux vidéo. Skype entreprise Server est capable d’envoyer jusqu’à cinq flux vidéo pour optimiser la qualité vidéo de tous les clients de réception. Le nombre réel de flux vidéo envoyé est déterminé par l'émetteur en fonction de la capacité du processeur, de la bande passante montante disponible et du nombre de clients de réception qui demandent un flux vidéo spécifique. Dans le cas le plus courant, un flux vidéo H.264 et un flux vidéo RTVideo sont envoyés quand un client hérité participe à une conférence. Il se peut également que plusieurs flux vidéo H.264 (par exemple, avec différentes résolutions vidéo) soient envoyés pour différentes demandes.

Outre la bande passante requise pour le trafic RTP (Real-Time Transport Protocol) pour les supports audio et vidéo, le protocole RTCP (Real-Time Transport Control Protocol) a lui aussi besoin de bande passante. RTCP est utilisé pour le signalement des statistiques et le contrôle hors-bande du flux RTP. Pour la planification, utilisez les valeurs de bande passante contenues dans le tableau ci-dessous pour le trafic RTCP. Ces valeurs représentent la bande passante maximale utilisée pour le trafic RTCP et varient pour les flux audio et vidéo en raison des différences dans les données de contrôle.

**Bande passante RTCP**

|**Media**|**Bande passante maximale RTCP (Kbits/s)**|
|:-----|:-----|
|Audio  <br/> |5  <br/> |
|Vidéo (uniquement H.264 ou RTVideo envoyé/reçu)  <br/> |0,10  <br/> |
|Vidéo (H.264 et RTVideo envoyé/reçu)  <br/> |0,15  <br/> |

Pour planifier la capacité, les deux statistiques suivantes sont intéressantes :

- **Bande passante maximale sans FEC** Bande passante maximale qu’un flux utilisera. Il s’agit de l’activité type du flux et du codec classique utilisé dans le scénario sans FEC. Il s’agit de la bande passante lorsque le flux correspond à une activité de 100% et qu’il n’y a pas de perte de paquets déclenchant l’utilisation de FEC. Cela est utile pour le calcul de la quantité de bande passante qui doit être allouée pour permettre l’utilisation du codec dans un scénario donné. FEC ne doit pas nécessairement être une exigence sur un réseau géré.

- **Bande passante maximale avec FEC** Bande passante maximale qu’un flux utilise. Il s’agit de l’activité type du flux et du codec classique utilisé dans le scénario avec FEC. Il s’agit de la bande passante lorsque le flux correspond à une activité de 100% et qu’il n’y a pas de perte de paquets déclenchant l’utilisation de FEC pour améliorer la qualité. Cela peut s’avérer utile pour le calcul de la bande passante qui doit être allouée pour permettre l’utilisation du codec dans un scénario donné et permettre l’utilisation de FEC pour préserver la qualité en conditions de perte de paquets.

Les tableaux suivants répertorient également une valeur de bande passante supplémentaire, une **bande passante classique**. Il s’agit de la bande passante moyenne qu’un flux utilise. Il s’agit de l’activité type du flux et du codec classique utilisé dans le scénario. Cette bande passante peut être utilisée pour déterminer approximativement la quantité de bande passante consommée par le trafic multimédia à un moment précis, mais ne doit pas être utilisée pour la planification de la capacité, car les appels individuels seront supérieurs à cette valeur lorsque le niveau d’activité est supérieur à la moyenne. La bande passante classique de flux vidéo dans les tableaux ci-dessous est basée sur une combinaison de résolutions vidéo différentes comme observées dans les données de clients mesurées, et d’autres installations plus petites peuvent avoir des nombres réels qui diffèrent des données de la table. Par exemple, dans le cadre d’une session d’égal à égal, la plupart des utilisateurs utiliseront la fenêtre de rendu vidéo par défaut, car le pourcentage d’utilisateurs augmenterait ou augmentait l’application Skype entreprise Server de façon à offrir de meilleures résolutions vidéo.

Les tableaux ci-dessous fournissent les valeurs pour les divers scénarios.

**Planification de la capacité audio/vidéo pour des sessions poste à poste**

|**Media**|**Codec**|**Bande passante pour un flux type ( Kbits/s)**|**Bande passante maximale sans correction d'erreur de transfert**|**Bande passante maximale avec correction d'erreur de transfert**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |Large bande RTAudio  <br/> |39.8  <br/> |62  <br/> |91  <br/> |
|Audio  <br/> |Bande étroite RTAudio  <br/> |29.3  <br/> |44.8  <br/> |56.6  <br/> |
|Audio  <br/> |SILK bande large  <br/> |44.3  <br/> |69  <br/> |105  <br/> |
|Vidéo principale lors de l’appel de points de terminaison Skype entreprise Server  <br/> |H.264  <br/> |460  <br/> |4 010 (pour une résolution maximale de 1 920 x 1 080)  <br/> |Déjà inclus  <br/> |
|Vidéo principale lors de l’appel de points de terminaison Lync 2010 ou Office Communicator 2007 R2  <br/> |RTVideo  <br/> |460  <br/> |2 510 (pour une résolution maximale de 1 280 x 720)  <br/> |Déjà inclus  <br/> |
|Vidéo panoramique lors de l’appel de points de terminaison Skype entreprise Server  <br/> |H.264  <br/> |190  <br/> |2 010 (pour une résolution maximale de 1 920 x 288)  <br/> |Déjà inclus  <br/> |
|Vidéo panoramique lors de l’appel de points de terminaison Lync 2010  <br/> |RTVideo  <br/> |190  <br/> |510 (pour une résolution maximale de 960x144)  <br/> |Déjà inclus  <br/> |

**Planification de la capacité audio/vidéo pour les conférences**

|**Media**|**Codec type**|**Bande passante pour un flux type ( Kbits/s)**|**Bande passante maximale sans correction d'erreur de transfert**|**Bande passante maximale avec correction d'erreur de transfert**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G.722  <br/> |46.1  <br/> |100.6  <br/> |164.6  <br/> |
|Audio  <br/> |Siren  <br/> |25.5  <br/> |52.6  <br/> |68.6  <br/> |
|Réception vidéo principale  <br/> |H.264 et RTVideo¹  <br/> |260  <br/> |8015  <br/> |Non applicable  <br/> |
|Envoi vidéo principal  <br/> |H.264 et RTVideo  <br/> |270  <br/> |8015  <br/> |Non applicable  <br/> |
|Réception vidéo panoramique  <br/> |H.264 et RTVideo  <br/> |190  <br/> |2 010 (pour une résolution maximale de 1 920 x 288)  <br/> |Non applicable  <br/> |
|Envoi vidéo panoramique  <br/> |H.264 et RTVideo  <br/> |190  <br/> |2 515²  <br/> |Non applicable  <br/> |

1. La vidéo RT est envoyée en plus de H. 264 lorsque les clients Lync 2010 sont connectés à la Conférence.

2. S’il existe plusieurs flux, ils partagent dynamiquement la bande passante allouée.

Pour la vidéo principale, la vitesse de transmission du flux type est la bande passante agrégée divisée par tous les flux vidéo reçus et la vitesse de transmission du flux maximale est la bande passante agrégée divisée par tous les flux vidéo envoyés. Même avec plusieurs flux vidéo, la bande passante type est plus petite que dans un scénario d'égal à égal, car de nombreuses conférences vidéo utilisent le partage de contenu, ce qui entraîne des fenêtres vidéo plus petites et donc des résolutions vidéo plus petites. La bande passante de charge utile vidéo agrégée maximum prise en charge est 8 000 Kbits/s pour les flux envoyés et reçus, par exemple pour deux flux vidéo 1 920x1 080p entrants. Il est rare que les valeurs maximales soient atteintes dans les implémentations du monde réel.

Lors de la création d’une conférence à plusieurs éléments qui utilise la fonctionnalité d’affichage Galerie, l’utilisation de la bande passante augmente le niveau d’utilisation de la bande passante pour les participants.

||**2 participants**|**3 participants**|**4 participants**|**5 participants**|**6 participants**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Résolutions maximales reçues** <br/> |1920x1080  <br/> |1280x720  <br/> |640x360  <br/> |640x360 320x240  <br/> |640x360 320x240  <br/> |
|**Débit moyen total** <br/> |2128  <br/> |4050  <br/> |1304  <br/> |1224  <br/> |1565  <br/> |
|**Débit maximal total** <br/> |4063  <br/> |5890  <br/> |2860  <br/> |2699  <br/> |3017  <br/> |

La bande passante de flux type pour la vidéo panoramique est basée sur les périphériques capables de diffuser des flux de vidéo panoramique d'une résolution maximale de 960x144. Attendez-vous à une augmentation de la bande passante de flux type lors de l'utilisation de périphériques avec une vidéo panoramique de 1 920x288. 

**Planification de la capacité audio pour PSTN**

|**Media**|**Codec type**|**Bande passante pour un flux type ( Kbits/s)**|**Bande passante maximale sans correction d'erreur de transfert**|**Bande passante maximale avec correction d'erreur de transfert**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G. 711 (cela inclut les participants PSTN en conférences)  <br/> |64.8  <br/> |97  <br/> |161  <br/> |
|Audio  <br/> |Bande étroite RTAudio  <br/> |30.9  <br/> |44.8  <br/> |56.6  <br/> |

Les valeurs de bande passante pour le réseau contenues dans ces tableaux représentent uniquement le trafic unidirectionnel et incluent 5 Kbits/s pour le trafic RTCP pour chaque flux.

## <a name="managing-quality-of-service"></a>Gestion de la qualité de service
<a name="man_QOS"> </a>

La Qualité de service (QoS) est une technologie réseau utilisée dans certaines organisations afin de fournir des performances optimales à l'utilisateur final pour les communications audio et vidéo. QoS est le plus souvent utilisée sur les réseaux où la bande passante est limitée : avec un grand nombre de paquets réseau simultanés pour une quantité de bande passante disponible relativement faible, QoS permet aux administrateurs d'affecter une priorité supérieure aux paquets transportant des données audio ou vidéo. Le fait d'affecter une priorité supérieure à ces paquets permet aux communications audio et vidéo de s'effectuer plus rapidement, et avec moins d'interruption, que les sessions réseau impliquant des opérations telles que des transferts de fichiers, de la navigation web ou des sauvegardes de bases de données. C'est la raison pour laquelle la priorité « Meilleur effort » est affectée aux paquets réseau utilisés pour les transferts de fichiers ou les sauvegardes de bases de données.

> [!NOTE]
> En règle générale, la QoS s'applique uniquement aux sessions de communication sur votre réseau interne. Lorsque vous implémentez QoS, vous configurez vos serveurs et routeurs afin de prendre en charge le marquage de paquets qui ne peut pas être pris en charge sur Internet et d'autres réseaux. Même si la qualité de service est prise en charge sur d’autres réseaux, il n’y a aucune garantie que la qualité de service (QoS) soit configurée exactement de la même manière que pour le service. Si vous utilisez MPLS, vous devrez contacter votre fournisseur MPLS

Skype entreprise Server n’est pas requis par QoS, mais il est fortement recommandé. Si vous rencontrez des problèmes de perte de paquets sur le réseau, il est possible d’ajouter de la bande passante ou d’implémenter QoS. Si l'ajout de bande passante n'est pas possible, l'implémentation de QoS peut constituer la seule solution au problème.

Skype entreprise Server offre une prise en charge complète de QoS: cela signifie que les organisations qui utilisent déjà QoS peuvent facilement intégrer Skype entreprise Server à leur infrastructure réseau existante. Pour ce faire, procédez comme suit :

- [Activation de la qualité de service (QoS) dans Skype entreprise Server pour les appareils qui ne sont pas basés sur Windows](../../manage/network-management/qos/enabling-qos-for-devices-that-are-not-based-on-windows.md). Par défaut, QoS est désactivée pour les ordinateurs et autres appareils (tels que les iPhones) qui exécutent d'autres systèmes d'exploitation. Même si vous pouvez utiliser Skype entreprise Server pour activer et désactiver la qualité de service des appareils, vous ne pouvez pas utiliser le produit pour modifier les codes DSCP utilisés par ces appareils.

- [Configuration de plages de ports et d’une stratégie de qualité de service pour vos serveurs de conférence, d’application et de médiation](../../manage/network-management/qos/configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). Vous devez réserver un ensemble unique de ports pour différents types de paquets, tels que les paquets audio et vidéo. Lorsque vous utilisez Skype entreprise Server, vous n’activez ou ne désactivez pas la QoS en définissant une valeur de propriété sur true ou false. Au lieu de cela, vous activez QoS en configurant des plages de ports, puis en créant et en appliquant une stratégie de groupe. Si vous décidez de ne pas utiliser la qualité de service (QoS), vous pouvez désactiver la qualité de service (QoS) en supprimant les objets de stratégie de groupe appropriés.

- [La configuration de plages de ports et d’une stratégie de qualité de service pour vos serveurs de périphérie](../../manage/network-management/qos/configuring-port-ranges-for-your-edge-servers.md). Bien que cela ne soit pas requis, vous pouvez configurer vos serveurs Edge de façon à utiliser les mêmes plages de ports que vos autres serveurs. La configuration d’une stratégie de QoS est uniquement réalisée pour le côté interne de vos serveurs Edge. En effet, la QoS est conçue pour être utilisée sur votre réseau interne, et non sur Internet.

- [Configuration de plages de ports et d’une politique de qualité de service pour vos clients dans Skype entreprise Server](../../manage/network-management/qos/configuring-port-ranges-for-your-skype-clients.md). Ces plages de ports s'appliquent uniquement aux ordinateurs clients et sont généralement différents des plages de ports configurées sur vos serveurs. Notez que Skype entreprise Server ne prend pas en charge la qualité de service (QoS) pour les systèmes d’exploitation Windows autres que Windows 10.


> [!NOTE]
> Si vous utilisez Windows Server 2012 ou Windows Server 2012 R2, vous serez peut-être intéressé par le nouveau jeu de cmdlets Windows PowerShell disponible pour gérer la qualité de service (QoS) sur cette plateforme. Pour plus d’informations, voir [applets de connexion de QoS réseau dans Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=285379).

La qualité de service (QoS) est également abordée dans la [planification du réseau du réseau, la surveillance et la résolution des problèmes liés à Lync Server](https://www.microsoft.com/en-us/download/details.aspx?id=39084) . Même si le contenu fait référence explicitement à Lync 2010 et à Lync 2013, les considérations relatives à Skype entreprise Server ne sont pas modifiées.

## <a name="see-also"></a>Voir aussi
<a name="man_QOS"> </a>

[Planifier IPv6 dans Skype Entreprise](ipv6.md)

[Configuration requise pour l’équilibrage de charge pour Skype Entreprise](load-balancing.md)

[Configuration requise pour le service DNS pour Skype entreprise Server](dns.md)
