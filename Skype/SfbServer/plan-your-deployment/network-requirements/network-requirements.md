---
title: Plan network requirements for Skype for Business
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
description: 'Résumé : Passez en revue les considérations de composant réseau ci-dessous avant d’implémenter Skype pour Business Server.'
ms.openlocfilehash: fd21ada12a8e2b05654fe6809dd5147480b0e306
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27214511"
---
# <a name="plan-network-requirements-for-skype-for-business"></a>Plan network requirements for Skype for Business

**Résumé :** Passez en revue les considérations de composant réseau ci-dessous avant d’implémenter Skype pour Business Server.

Les informations fournies dans ces rubriques sont également abordées de manière plus approfondie dans le livre blanc [Planification réseau, surveillance et résolution de problèmes avec Lync Server](https://www.microsoft.com/en-us/download/details.aspx?id=39084). Alors que le contenu fait référence explicitement à Lync 2010 et Lync 2013, les considérations de Skype pour Business Server restent inchangées.

De même, si votre réseau implique wi-fi ainsi qu’un accès câblé, le livre blanc [Proposer Lync 2013 Real-Time Communications en Wi-Fi](https://www.microsoft.com/en-us/download/details.aspx?id=36494) est une bonne référence et s’applique également aux Skype pour Business Server.

<!-- Deprecated tools
Network performance and needs are directly linked to the traffic load placed on them. When planning your network and server implementations we recommend making use of the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md), the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md), and the [Skype for Business Server 2015 Stress and Performance Tool](../../management-tools/stress-and-performance-tool/stress-and-performance-tool.md).    -->

## <a name="server-hardware"></a>Matériel serveur
<a name="S_hard"> </a>

La carte réseau de chaque serveur dans le Skype pour la topologie du serveur d’entreprise doit prendre en charge au moins 1 gigabit par seconde (Gbits/s). En règle générale, vous devez connecter tous les rôles de serveur au sein de la Skype pour la topologie du serveur d’entreprise à l’aide d’une faible latence et une large bande passante réseau local (LAN). La taille du réseau local dépend de la taille de la topologie :

- Dans les topologies Standard Edition, les serveurs doivent résider dans un réseau prenant en charge 1 Gbits/s Ethernet ou équivalent.

- Dans les topologies Enterprise Edition, la plupart des serveurs doivent résider dans un réseau prenant en charge plus de 1 Gbits/s, en particulier pour la prise en charge audio/vidéo (A / V) de conférence et de partage d’application.

Dans le cas de l'intégration au réseau téléphonique commuté (RTC ou, en anglais, PSTN pour Public Switched Telephone Network), vous pouvez utiliser les lignes T1/E1 ou les jonctions SIP.

## <a name="audiovideo-network-requirements"></a>Conditions de réseau requises pour les fonctionnalités audio/vidéo
<a name="AV_req"> </a>

Configuration réseau requise pour l’audio/vidéo (A / V) dans un Skype pour Business Server déploiement sont les suivants :

- Si vous déployez un serveur Edge unique ou un pool Edge à l’aide de l’équilibrage de la charge DNS, vous pouvez configurer le pare-feu _externe_ pour effectuer la traduction d’adresses réseau (NAT). Vous ne pouvez pas configurer le pare-feu _interne_ pour effectuer NAT. Pour plus d’informations, voir [planification de pare-feu et de Port](../edge-server-deployments/edge-environmental-requirements.md#port-and-firewall-planning).

    > [!IMPORTANT]
    > Si vous disposez d’un pool de serveurs Edge et que vous utilisez un équilibreur de charge matérielle, vous devez utiliser des adresses IP publiques sur les serveurs de périphérie et vous ne pouvez pas utiliser NAT pour les serveurs ou le pool à votre appareil compatible NAT (par exemple, une appliance de pare-feu ou commutateur de réseau local. Pour plus d’informations, voir [les scénarios de serveur de transport Edge dans Skype pour Business Server](../edge-server-deployments/scenarios.md).

- Si votre organisation utilise une infrastructure de qualité de service (QoS), le sous-système multimédia est compatible avec cette infrastructure.

- Si vous utilisez le protocole IPSec, nous vous recommandons de le désactiver sur les plages de ports utilisées pour le trafic A/V. Pour plus d’informations, consultez [exceptions IPsec](#ipsec-exceptions).

Pour fournir une qualité optimale lors de l'utilisation des fonctionnalités multimédias, procédez comme suit :

- Configurez les liens réseau pour qu'ils prennent en charge un débit de 65 kilobits par seconde (Kbits/s) par flux audio et 500 Kbits/s par flux vidéo, s'ils sont activés, pendant les périodes d'utilisation de pointe. Une session audio ou vidéo bidirectionnelle utilise deux flux, aussi une connexion audio/ téléphonique simple aura besoin de 130 Kbits/s pour couvrir chaque flux. Vidéo de la même manière utilise 1 000 Kbits/s total pour effectuer une connexion en amont et en aval.

- Pour prendre en charge inattendues pointes de trafic et l’utilisation accrue au fil du temps, Skype pour les points de terminaison multimédia Business Server peut s’adapter aux différentes conditions réseau et prend en charge trois fois le débit pour l’audio et vidéo tout en conservant une qualité acceptable. Ne pensez pas que ce adaptabilité sera masque le problème lorsque le réseau est configuré sous. Dans un réseau configurées sous, la possibilité du Skype pour les points de terminaison multimédia Business Server faire dynamiquement des différentes conditions de réseau (par exemple, la perte de paquets haute temporaire) est réduite.

- Pour les liaisons réseau dont la mise en service s'avère à la fois coûteuse et difficile, vous serez peut-être contraint à prendre en charge un trafic moins important. Dans ce scénario, laissez l’élasticité de la Skype pour les points de terminaison multimédia Business Server absorber la différence entre le volume de trafic et le niveau de trafic de pointe, au détriment de certains réduction de la qualité de voix. En outre, on constatera une réduction de la capacité de traitement supplémentaire pouvant normalement absorber les soudaines augmentations de trafic.

- Dans le cas des liaisons ne pouvant pas bénéficier d'un débit optimal à court terme, par exemple dans un réseau étendu utilisant des liaisons de qualité médiocre, vous devez envisager de désactiver les fonctionnalités vidéo pour certains utilisateurs.

- Configurez le réseau pour garantir un retard maximal (temps de réponse) de 150 millisecondes (ms) de bout en bout en cas de pic de charge. Latence est atteinte à un réseau qui Skype pour les composants multimédias Business Server ne peuvent pas compenser, et il est important de trouver et d’éliminer les points faibles.

- Pour les serveurs qui exécutent un logiciel antivirus, incluez tous les serveurs qui exécutent Skype pour Business Server dans la liste des exceptions pour fournir des performances optimales et une qualité audio.

## <a name="ipsec-exceptions"></a>Exceptions IPsec

Pour les réseaux d’entreprise où ne sécurité du protocole Internet (IPsec) (voir RFC IETF 4301-4309) a été déployée, il doit être désactivé sur la plage de ports utilisés pour la livraison des données audio, vidéo et vidéo panoramique. Cette recommandation s’explique par la nécessité d’éviter tout retard dans l’affectation des ports multimédias lors de la négociation IPsec.

Le tableau suivant présente les paramètres recommandés pour les exceptions IPsec.

**Exceptions recommandées pour IPsec**

|Nom de la règle |Adresse IP source |Adresse IP de destination |Protocole |Port source |Port de destination |Besoin d’authentification |
|:--- |:--- |:--- |:--- |:---|:---|:--- |
|Serveur Edge A/V, ports internes/entrants|Indifférente  |Serveur Edge A/V - interne|UDP et TCP|Indifférente |Indifférente |Ne pas authentifier|
|Serveur Edge A/V, ports externes/entrants|Indifférente  |Serveur Edge A/V - externe|UDP et TCP|Indifférente |Indifférente |Ne pas authentifier|
|Serveur Edge A/V, ports internes/sortants|Serveur Edge A/V - interne  |Serveur Edge A/V - externe |UDP et TCP|Indifférente |Indifférente |Ne pas authentifier|
|Serveur Edge A/V, ports externes/sortants|Serveur Edge A/V - externe |Indifférente |UDP et TCP|Indifférente |Indifférente |Ne pas authentifier|
|Serveur de médiation, ports entrants|Indifférente  |Ou plusieurs serveurs de médiation |UDP et TCP|Indifférente |Indifférente |Ne pas authentifier|
|Serveur de médiation, ports sortants|Ou plusieurs serveurs de médiation  |Indifférente|UDP et TCP|Indifférente |Indifférente |Ne pas authentifier|
|Intendant Conférence entrant|Indifférente  |Serveur frontal exécutant l’Intendant Conférence |UDP et TCP|Indifférente |Indifférente |Ne pas authentifier|
|Intendant Conférence sortant|Serveur frontal exécutant l’Intendant Conférence  |Indifférente|UDP et TCP|Indifférente |Indifférente |Ne pas authentifier|
|Serveur de conférence A/V, ports entrants|Indifférente|Serveurs frontaux|UDP et TCP|Indifférente |Indifférente |Ne pas authentifier|
|Conférence A/V, ports sortants|Serveurs frontaux|Indifférente|UDP et TCP|Indifférente |Indifférente |Ne pas authentifier|
|Exchange, ports entrants|Indifférente|Messagerie unifiée Exchange|UDP et TCP|Indifférente |Indifférente |Ne pas authentifier|
|Serveurs de partage d’application, ports entrants|Indifférente|Serveurs de partage d’application|UDP et TCP|Indifférente |Indifférente |Ne pas authentifier|
|Serveur de partage d’application, ports sortants|Serveurs de partage d’application| Indifférente |UDP et TCP|Indifférente |Indifférente |Ne pas authentifier|
|Exchange, ports sortants|Messagerie unifiée Exchange|Indifférente|UDP et TCP|Indifférente |Indifférente |Ne pas authentifier|
|Clients| Indifférente  |Indifférente|UDP et TCP|Indifférente |Indifférente |Ne pas authentifier|
|         |         |         |         |         |         |         |


## <a name="conferencing-network-requirements"></a>Conditions de réseau requises pour les fonctionnalités de conférence web
<a name="Conf_req"> </a>

La bande passante utilisée pour télécharger le contenu de conférence à partir du serveur Internet Information Services (IIS) dépend de la taille du contenu. Vous pouvez surveiller l'utilisation réelle de la bande passante et ajuster la planification de la bande passante en conséquence.

## <a name="network-bandwidth-requirements-for-media-traffic"></a>Configuration requise de la bande passante pour le trafic multimédia
<a name="Conf_req"> </a>

Une part importante de la planification du réseau est de vous assurer que votre réseau peut gérer le trafic multimédia généré par Skype pour Business Server. Cette section vous aide à planifier le trafic multimédia.

### <a name="media-traffic-network-usage"></a>Utilisation du réseau pour le trafic multimédia
<a name="Net_req"> </a>

L'utilisation de la bande passante par le trafic multimédia peut être difficile à calculer en raison du nombre de variables différentes, comme l'utilisation du codec, la résolution et les niveaux d'activité. L'utilisation de la bande passante est une fonction du codec utilisé et de l'activité du flux, pouvant varier d'un scénario à l'autre. Le tableau suivant répertorie les codecs audio généralement utilisés dans Skype pour les scénarios de serveur d’entreprise.

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
|Large bande/à bande étroite soie  <br/> |Égal à égal  <br/> |13.0  <br/> |29.0  <br/> |41.0  <br/> |54.0  <br/> |

Les valeurs de bande passante contenues dans le tableau ci-dessus reposent sur la mise en paquets 20 ms (50 paquets par seconde) et pour Siren et G.722 incluent le protocole SRTP (Secure Real-Time Transport Protocol) en plus des scénarios de conférence et supposent que le flux est entièrement actif. La correction d'erreur de transfert (FEC) est utilisée dynamiquement en cas de perte de paquet sur la liaison afin de maintenir la qualité du flux audio. 

La version stéréo du codec G.722 est utilisée par les systèmes basés sur Lync Room System, qui s'appuie sur un micro stéréo unique ou une paire de micro mono pour permettre aux participants de mieux distinguer les différents intervenants dans une salle de réunion.

**Bande passante de la résolution vidéo**

|**Codec vidéo**|**Résolution et proportions**|**Vitesse de transmission de la charge utile vidéo maximale (Kbits/s)**|**Vitesse de transmission de la charge utile vidéo minimale (Kbits/s)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |320x180 (16:9)  <br/> 212x160 (4:3)  <br/> |250  <br/> |15  <br/> |
|H.264/RTVideo  <br/> |424x240 (16:9)  <br/> 320x240 (4:3)  <br/> |350  <br/> |100  <br/> |
|H.264  <br/> |480x270 (16:9)  <br/> 424x320 (4:3)  <br/> |450  <br/> |200  <br/> |
|H.264/RTVideo  <br/> |640x360 (16:9)  <br/> 640x480 (4:3)  <br/> |800  <br/> |300  <br/> |
|H.264  <br/> |848x480 (16:9)  <br/> |1500  <br/> |400  <br/> |
|H.264  <br/> |960x540 (16:9)  <br/> |2000  <br/> |500  <br/> |
|H.264/RTVideo  <br/> |1 280 x 720 (16:9)  <br/> |2500  <br/> |700  <br/> |
|H.264  <br/> |1 920x1 080 (16:9)  <br/> |4000  <br/> |1500  <br/> |
|H.264/RTVideo  <br/> |960x144 (20:3)  <br/> |500  <br/> |15  <br/> |
|H.264  <br/> |1 280 x 192 (20:3)  <br/> |1000  <br/> |250  <br/> |
|H.264  <br/> |1 920 x 288 (20:3)  <br/> |2000  <br/> |500  <br/> |

Pour la vidéo, le codec par défaut est la norme H.264/MPEG-4 Part 10 Advanced Video Coding avec ses extensions de codage vidéo évolutives pour une extensibilité dans le temps. Pour assurer l’interopérabilité avec les clients hérités, le codec RTVideo est toujours utilisé pour les appels d’égal à égal entre les clients hérités et Skype pour Business Server. Dans les sessions de conférence avec les deux Skype pour Business Server et les clients hérités du Skype pour Business Server point de terminaison peut coder la vidéo à l’aide à la fois les codecs vidéo et envoyer le flux binaire H.264 à le Skype pour les clients Business Server et le flux binaire RTVideo hérité clients.

La bande passante nécessaire dépend de la résolution, de la qualité et de la fréquence d'images. Pour chaque résolution, deux vitesses de transmission pertinentes sont disponibles :

- **Vitesse de transmission maximale charge utile** Il s’agit de la vitesse de transmission qui utilise un point de terminaison pour la résolution de la fréquence maximale. Cette valeur permet la qualité vidéo et audio maximale.

- **Vitesse de transmission minimale charge utile** Il s’agit de la vitesse de transmission sous laquelle un Skype pour le point de terminaison Business Server bascule vers la résolution inférieure suivante. Afin de garantir une certaine résolution, la vitesse de transmission de la charge utile vidéo disponible ne doit pas être comprise dans la vitesse de transmission minimale pour cette résolution. Cette valeur permet de comprendre la valeur la plus basse possible lorsque l’utilisation de la vitesse de transmission maximale n’est pas disponible ou pratique. Pour certains utilisateurs, cette vitesse faible peut être considérée comme inacceptable ; ces vitesses de transmission doivent donc être utilisées avec prudence. Notez que pour des vidéos avec peu ou pas de mouvements, la vitesse de transmission réelle peut temporairement être inférieure à la vitesse de transmission minimale.

Skype pour Business Server prend en charge plusieurs résolutions. Cela permet de Skype pour Business Server pour s’ajuster à la bande passante réseau et la réception de fonctionnalités du client. Ce rapport par défaut pour Skype pour Business Server est de 16:9. Les proportions 4:3 hérité est toujours pris en charge pour les webcams qui n’autorise pas la capture dans les proportions 16:9.

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

- Chaque participant qui active l’utilisateur envoyer le flux vidéo permet d’envoyer un ou plusieurs flux vidéo. Skype pour Business Server a la possibilité d’envoyer des flux vidéo jusqu'à cinq afin d’optimiser la qualité vidéo pour tous les clients de réception. Le nombre réel de flux vidéo envoyé est déterminé par l'émetteur en fonction de la capacité du processeur, de la bande passante montante disponible et du nombre de clients de réception qui demandent un flux vidéo spécifique. Dans le cas le plus courant, un flux vidéo H.264 et un flux vidéo RTVideo sont envoyés quand un client hérité participe à une conférence. Il se peut également que plusieurs flux vidéo H.264 (par exemple, avec différentes résolutions vidéo) soient envoyés pour différentes demandes.

Outre la bande passante requise pour le trafic RTP (Real-Time Transport Protocol) pour les supports audio et vidéo, le protocole RTCP (Real-Time Transport Control Protocol) a lui aussi besoin de bande passante. RTCP est utilisé pour le signalement des statistiques et le contrôle hors-bande du flux RTP. Pour la planification, utilisez les valeurs de bande passante contenues dans le tableau ci-dessous pour le trafic RTCP. Ces valeurs représentent la bande passante maximale utilisée pour le trafic RTCP et varient pour les flux audio et vidéo en raison des différences dans les données de contrôle.

**Bande passante RTCP**

|**Media**|**Bande passante maximale RTCP (Kbits/s)**|
|:-----|:-----|
|Audio  <br/> |5  <br/> |
|Vidéo (uniquement H.264 ou RTVideo envoyé/reçu)  <br/> | 10  <br/> |
|Vidéo (H.264 et RTVideo envoyé/reçu)  <br/> |15  <br/> |

Pour planifier la capacité, les deux statistiques suivantes sont intéressantes :

- **Bande passante maximale sans FEC** La bande passante maximale qui utilisent un flux de données. Cela inclut l’activité classique du flux et le codec par défaut qui est utilisé dans le scénario sans mode FEC. Il s’agit de la bande passante lorsque le flux est au niveau d’activité de 100 % et il n’existe aucune perte de paquets déclenchement de l’utilisation du mode FEC. Cela est utile pour le calcul de la bande passante doit être alloué pour autoriser le codec à être utilisé dans un scénario donné. FEC n’est pas censée être une spécification d’un réseau géré.

- **Bande passante maximale avec FEC** La bande passante maximale qui utilise un objet stream. Cela inclut l’activité classique du flux et le codec par défaut qui est utilisé dans le scénario avec mode FEC. Il s’agit de la bande passante lorsque le flux est au niveau d’activité de 100 % et la perte de paquets déclenchement de l’utilisation de FEC pour améliorer la qualité. Cela est utile pour le calcul de la bande passante doit être alloué pour autoriser le codec à utiliser dans un scénario donné et autoriser l’utilisation de pour préserver la qualité dans des conditions de perte de paquets FEC.

Les tableaux suivants répertorient également une valeur de bande passante supplémentaires, **la bande passante par défaut**. Il s’agit de la bande passante moyenne qui utilise un objet stream. Cela inclut l’activité classique du flux et le codec par défaut qui est utilisé dans le scénario. La bande passante peut être utilisée pour rapprocher la bande passante consommée par le trafic multimédia à un moment donné, mais ne doit pas être utilisée pour la planification de capacité, car les appels dépassera cette valeur lorsque le niveau d’activité est supérieur à la moyenne. La bande passante vidéo classiques dans les tableaux ci-dessous est basée sur une combinaison de différentes résolutions vidéo telle qu’observée dans les données client mesurée et petites installations sont susceptibles d’avoir des chiffres réels qui diffèrent des données de la table. Par exemple, dans les sessions d’égal-à-la plupart des utilisateurs utiliseriez la vidéo par défaut Afficher fenêtre tandis que certaines pourcentage d’utilisateurs serait augmenter ou optimiser la Skype pour application Business Server permettre une meilleure résolution vidéo.

Les tableaux ci-dessous fournissent les valeurs pour les divers scénarios.

**Planification de la capacité audio/vidéo pour des sessions poste à poste**

|**Media**|**Codec**|**Bande passante pour un flux type ( Kbits/s)**|**Bande passante maximale sans correction d'erreur de transfert**|**Bande passante maximale avec correction d'erreur de transfert**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |Large bande RTAudio  <br/> |39.8  <br/> |62  <br/> |91  <br/> |
|Audio  <br/> |Bande étroite RTAudio  <br/> |29.3  <br/> |44.8  <br/> |56.6  <br/> |
|Audio  <br/> |SILK bande large  <br/> |44.3  <br/> |69  <br/> |105  <br/> |
|Vidéo principale lors de l’appel Skype pour systèmes d’extrémité Business Server  <br/> |H.264  <br/> |460  <br/> |4 010 (pour une résolution maximale de 1 920 x 1 080)  <br/> |Déjà inclus  <br/> |
|Vidéo principale lors de l’appel des points de terminaison Lync 2010 ou Office Communicator 2007 R2  <br/> |RTVideo  <br/> |460  <br/> |2 510 (pour une résolution maximale de 1 280 x 720)  <br/> |Déjà inclus  <br/> |
|Vidéo panoramique lors de l’appel Skype pour systèmes d’extrémité Business Server  <br/> |H.264  <br/> |190  <br/> |2 010 (pour une résolution maximale de 1 920 x 288)  <br/> |Déjà inclus  <br/> |
|Vidéo panoramique lors de l’appel des points de terminaison Lync 2010  <br/> |RTVideo  <br/> |190  <br/> |510 (pour une résolution maximale de 960x144)  <br/> |Déjà inclus  <br/> |

**Planification de la capacité audio/vidéo pour les conférences**

|**Media**|**Codec type**|**Bande passante pour un flux type ( Kbits/s)**|**Bande passante maximale sans correction d'erreur de transfert**|**Bande passante maximale avec correction d'erreur de transfert**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G.722  <br/> |46.1  <br/> |100.6  <br/> |164.6  <br/> |
|Audio  <br/> |Siren  <br/> |25.5  <br/> |52.6  <br/> |68.6  <br/> |
|Réception vidéo principale  <br/> |H.264 et RTVideo¹  <br/> |260  <br/> |8015  <br/> |Non applicable  <br/> |
|Envoi vidéo principal  <br/> |H.264 et RTVideo  <br/> |270  <br/> |8015  <br/> |Non applicable  <br/> |
|Réception vidéo panoramique  <br/> |H.264 et RTVideo  <br/> |190  <br/> |2 010 (pour une résolution maximale de 1 920 x 288)  <br/> |Non applicable  <br/> |
|Envoi vidéo panoramique  <br/> |H.264 et RTVideo  <br/> |190  <br/> |2 515²  <br/> |Non applicable  <br/> |

1. RT vidéo est envoyé en outre à H.264 lorsque les clients Lync 2010 sont connectés à la conférence.

2. S’il existe plusieurs flux, ils partagent dynamiquement la bande passante allouée.

Pour la vidéo principale, la vitesse de transmission du flux type est la bande passante agrégée divisée par tous les flux vidéo reçus et la vitesse de transmission du flux maximale est la bande passante agrégée divisée par tous les flux vidéo envoyés. Même avec plusieurs flux vidéo, la bande passante type est plus petite que dans un scénario d'égal à égal, car de nombreuses conférences vidéo utilisent le partage de contenu, ce qui entraîne des fenêtres vidéo plus petites et donc des résolutions vidéo plus petites. La bande passante de charge utile vidéo agrégée maximum prise en charge est 8 000 Kbits/s pour les flux envoyés et reçus, par exemple pour deux flux vidéo 1 920x1 080p entrants. Il est rare que les valeurs maximales soient atteintes dans les implémentations du monde réel.

Lors de la création d’une conférence à plusieurs qui utilise la fonctionnalité d’affichage galerie, la bande passante utilisée augmente initialement en tant que participants jointure, puis diminue lorsque les résolutions sont glissées pour s’ajuster à la valeur maximale.

||**2 participants**|**3 participants**|**4 participants**|**5 participants**|**6 participants**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Résolutions maximales reçues** <br/> |1920x1080  <br/> |1280x720  <br/> |640x360  <br/> |640x360 320x240  <br/> |640x360 320x240  <br/> |
|**Débit moyen total** <br/> |2128  <br/> |4050  <br/> |1304  <br/> |1224  <br/> |1565  <br/> |
|**Débit maximal total** <br/> |4063  <br/> |5890  <br/> |2860  <br/> |2699  <br/> |3017  <br/> |

La bande passante de flux type pour la vidéo panoramique est basée sur les périphériques capables de diffuser des flux de vidéo panoramique d'une résolution maximale de 960x144. Attendez-vous à une augmentation de la bande passante de flux type lors de l'utilisation de périphériques avec une vidéo panoramique de 1 920x288. 

**Planification de la capacité audio pour PSTN**

|**Media**|**Codec type**|**Bande passante pour un flux type ( Kbits/s)**|**Bande passante maximale sans correction d'erreur de transfert**|**Bande passante maximale avec correction d'erreur de transfert**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G.711 (y compris dans les conférences de participants PSTN)  <br/> |64.8  <br/> |97  <br/> |161  <br/> |
|Audio  <br/> |Bande étroite RTAudio  <br/> |30.9  <br/> |44.8  <br/> |56.6  <br/> |

Les valeurs de bande passante pour le réseau contenues dans ces tableaux représentent uniquement le trafic unidirectionnel et incluent 5 Kbits/s pour le trafic RTCP pour chaque flux.

## <a name="managing-quality-of-service"></a>Gestion de la qualité de service
<a name="man_QOS"> </a>

La Qualité de service (QoS) est une technologie réseau utilisée dans certaines organisations afin de fournir des performances optimales à l'utilisateur final pour les communications audio et vidéo. QoS est le plus souvent utilisée sur les réseaux où la bande passante est limitée : avec un grand nombre de paquets réseau simultanés pour une quantité de bande passante disponible relativement faible, QoS permet aux administrateurs d'affecter une priorité supérieure aux paquets transportant des données audio ou vidéo. Le fait d'affecter une priorité supérieure à ces paquets permet aux communications audio et vidéo de s'effectuer plus rapidement, et avec moins d'interruption, que les sessions réseau impliquant des opérations telles que des transferts de fichiers, de la navigation web ou des sauvegardes de bases de données. C'est la raison pour laquelle la priorité « Meilleur effort » est affectée aux paquets réseau utilisés pour les transferts de fichiers ou les sauvegardes de bases de données.

> [!NOTE]
> En règle générale, la QoS s'applique uniquement aux sessions de communication sur votre réseau interne. Lorsque vous implémentez QoS, vous configurez vos serveurs et routeurs afin de prendre en charge le marquage de paquets qui ne peut pas être pris en charge sur Internet et d'autres réseaux. Même si la qualité de Service est pris en charge sur d’autres réseaux, il n’existe aucune garantie que QoS vont être configurés dans exactement la même manière que vous avez configuré le service. Si vous utilisez MPLS, vous devrez contacter votre fournisseur MPLS

Skype pour Business Server ne nécessite pas de qualité de service, mais il est fortement recommandé. Si vous rencontrez des problèmes de perte de paquets sur le réseau de vos solutions disponibles sont à ajouter plus de bande passante ou pour implémenter QoS. Si l'ajout de bande passante n'est pas possible, l'implémentation de QoS peut constituer la seule solution au problème.

Skype pour Business Server offre une prise en charge complète pour QoS : que signifie que les organisations qui utilisent déjà QoS peuvent facilement intégrer Skype pour Business Server dans son infrastructure réseau existante. Pour ce faire, procédez comme suit :

- [Activation de QoS dans Skype pour Business Server pour les appareils non basés sur Windows](../../manage/network-management/qos/enabling-qos-for-devices-that-are-not-based-on-windows.md). Par défaut, QoS est désactivée pour les ordinateurs et autres appareils (tels que les iPhones) qui exécutent d'autres systèmes d'exploitation. Bien que vous pouvez utiliser Skype pour Business Server pour activer et désactiver la qualité de Service pour les périphériques, vous pouvez généralement utiliser le produit pour modifier les codes DSCP utilisés par ces périphériques.

- [Configuration des plages de ports et une stratégie de qualité de Service pour vos serveurs de conférence, Application et de médiation](../../manage/network-management/qos/configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). Vous devez réserver un ensemble unique de ports pour différents types de paquets, tels que les paquets audio et vidéo. À l’aide de Skype pour Business Server ne pas activer ou désactiver la qualité de service en définissant une valeur de propriété la valeur True ou False. Au lieu de cela, vous activez QoS en configurant des plages de ports, puis en créant et en appliquant une stratégie de groupe. Si vous décidez ultérieurement ne pas utiliser QoS vous pouvez « désactiver » QoS en supprimant les objets de stratégie de groupe appropriés.

- [Plages de ports de configuration et une stratégie de qualité de Service pour vos serveurs Edge](../../manage/network-management/qos/configuring-port-ranges-for-your-edge-servers.md). Bien que cela ne soit pas requis, vous pouvez configurer vos serveurs Edge de façon à utiliser les mêmes plages de ports que vos autres serveurs. Configuration d’une stratégie de QoS uniquement être effectuée pour le côté interne des serveurs de périphérie. En effet, la QoS est conçue pour être utilisée sur votre réseau interne, et non sur Internet.

- [Plages de ports de configuration et une stratégie de qualité de Service pour vos clients dans Skype pour Business Server](../../manage/network-management/qos/configuring-port-ranges-for-your-skype-clients.md). Ces plages de ports s'appliquent uniquement aux ordinateurs clients et sont généralement différents des plages de ports configurées sur vos serveurs. Notez que Skype pour Business Server ne prend pas en charge QoS pour Windows les systèmes d’exploitation autres que Windows 10.


> [!NOTE]
> Si vous utilisez Windows Server 2012 ou Windows Server 2012 R2 vous intéresser dans le nouvel ensemble d’applets de commande Windows PowerShell disponibles pour la gestion de la qualité de service sur cette plateforme. Pour plus d’informations, voir [Réseau QoS Cmdlets dans Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=285379).

QoS est également abordé dans le livre blanc sur la [Planification du réseau, de surveillance et dépannage avec Lync Server](https://www.microsoft.com/en-us/download/details.aspx?id=39084) avec des détails supplémentaires et la profondeur. Alors que le contenu fait référence explicitement à Lync 2010 et Lync 2013, les considérations de Skype pour Business Server restent inchangées.

## <a name="see-also"></a>Voir aussi
<a name="man_QOS"> </a>

[Planifier IPv6 dans Skype Entreprise](ipv6.md)

[Configuration requise pour l’équilibrage de charge pour Skype Entreprise](load-balancing.md)

[Enregistrements DNS requis pour Skype pour Business Server](dns.md)
