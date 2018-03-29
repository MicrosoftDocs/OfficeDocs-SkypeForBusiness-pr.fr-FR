---
title: Planification de la configuration réseau requise pour Skype Entreprise 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
description: 'Résumé : Passez en revue les considérations de composant réseau ci-dessous avant la mise en œuvre de Skype pour Business Server 2015.'
ms.openlocfilehash: 3d3fd2141da93a9b0b866fe44e2ed8dee6942f3b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-network-requirements-for-skype-for-business-2015"></a>Planification de la configuration réseau requise pour Skype Entreprise 2015
 
**Résumé :** Passez en revue les considérations de composant réseau ci-dessous avant la mise en œuvre de Skype pour Business Server 2015.
  
Les informations contenues dans ces rubriques sont également abordées dans le livre blanc sur la [Planification du réseau, de surveillance et le dépannage avec Lync Server](https://www.microsoft.com/en-us/download/details.aspx?id=39084) avec plus de détails et de profondeur. Bien que le contenu fait explicitement référence à Lync 2010 et Lync 2013, les considérations de Skype pour Business Server 2015 restent inchangées.
  
De même, si votre réseau implique le wi-fi ainsi qu’un accès câblé, le livre blanc [Offrant des Communications Lync 2013 en temps réel via le Wi-Fi](http://www.microsoft.com/en-us/download/details.aspx?id=36494) est une bonne référence et s’applique également aux Skype pour Business Server 2015.
  
Les performances et besoins en matière de réseau sont directement liés au volume de trafic requis. Lorsque vous planifiez vos implémentations serveur et réseau, nous vous recommandons d’utiliser le [Skype pour outil de planification Microsoft Business Server 2015](../../management-tools/planning-tool/planning-tool.md), le [Skype pour le calculateur de planification de capacité Business Server 2015](../../management-tools/capacity-planning-calculator.md)et le [Skype pour Business Server 2015 Stress et l’outil performances](../../management-tools/stress-and-performance-tool/stress-and-performance-tool.md).
  
## <a name="server-hardware"></a>Matériel serveur
<a name="S_hard"> </a>

La carte réseau de chaque serveur dans le Skype pour la topologie du serveur de l’entreprise doit prendre en charge au moins 1 gigabit par seconde (Gbps). En général, vous devez vous connecter tous les rôles de serveur au sein de la Skype pour la topologie de serveur d’entreprise à l’aide d’une faible latence et la large bande passante réseau local (LAN). La taille du réseau local dépend de la taille de la topologie : 
  
- Dans les topologies de Standard Edition, les serveurs doivent être dans un réseau qui prend en charge de 1 Gbit/s Ethernet ou équivalent.
    
- Dans les topologies Enterprise Edition, la plupart des serveurs doivent être dans un réseau qui prend en charge plus de 1 Gbit/s, en particulier lorsque le support audio/vidéo (A / V) de conférence et de partage d’application.
    
Dans le cas de l'intégration au réseau téléphonique commuté (RTC ou, en anglais, PSTN pour Public Switched Telephone Network), vous pouvez utiliser les lignes T1/E1 ou les jonctions SIP.
  
## <a name="audiovideo-network-requirements"></a>Conditions de réseau requises pour les fonctionnalités audio/vidéo
<a name="AV_req"> </a>

Configuration réseau requise pour audio/vidéo (A / V) dans un Skype pour Business Server déploiement sont les suivants :
  
- Si vous déployez un serveur Edge ou un pool de bord à l’aide de DNS de l’équilibrage de la charge, vous pouvez configurer le pare-feu _externe_ pour effectuer la traduction d’adresses réseau (NAT). Vous ne pouvez pas configurer le pare-feu _interne_ pour effectuer NAT. Pour plus d’informations, consultez [Détermination de pare-feu en matière de 50 k Port plage](http://technet.microsoft.com/library/3b849dc7-175d-40d1-820d-80e6ade6d332.aspx).
    
    > [!IMPORTANT]
    > Si vous avez un pool d’arête et que vous utilisez un équilibreur de charge matériel, vous devez utiliser des adresses IP publiques sur les serveurs Edge et vous ne pouvez pas utiliser NAT pour les serveurs ou le pool à votre périphérique NAT compatible (par exemple, une solution matérielle-logicielle de pare-feu ou commutateur de réseau local. Pour plus d’informations, consultez [Résumé de Port - mise à l’échelle de bord consolidé avec équilibreurs de charge matériels](http://technet.microsoft.com/library/91213b1e-f875-464b-83e8-fe3a351595a4.aspx). 
  
- Si votre organisation utilise une infrastructure de qualité de service (QoS), le sous-système multimédia est compatible avec cette infrastructure. 
    
- Si vous utilisez le protocole IPSec, nous vous recommandons de le désactiver sur les plages de ports utilisées pour le trafic A/V. Pour plus d’informations, consultez [Exceptions d’IPsec](http://technet.microsoft.com/library/241f1eca-6f2f-44de-90b1-2cb659cbe27c.aspx).
    
Pour fournir une qualité optimale lors de l’utilisation des fonctionnalités multimédias, procédez comme suit :
  
- Configurez les liens réseau pour qu’ils prennent en charge un débit de 65 kilobits par seconde (Kbits/s) par flux audio et 500 Kbits/s par flux vidéo, s’ils sont activés, pendant les périodes d’utilisation de pointe. Une session audio ou vidéo bidirectionnelle utilise deux flux, aussi une connexion audio/ téléphonique simple aura besoin de 130 Kbits/s pour couvrir chaque flux. Vidéo utilise 1 000 Kbits/s total de la même façon pour effectuer une connexion en amont et en aval. 
    
- Pour prendre en charge des pointes dans le trafic et l’utilisation accrue des inattendue au fil du temps, Skype pour les points de terminaison multimédia Business Server peut s’adapter aux conditions variables du réseau et prend en charge trois fois le débit audio et vidéo tout en conservant une qualité acceptable. Ne supposez pas que cette capacité d’adaptation est masque le problème lorsque le réseau est configuré sous. Dans un réseau sous-mis en service, la capacité de la Skype pour les points de terminaison multimédia Business Server traiter dynamiquement des conditions de réseau variables (par exemple, les pertes de paquets temporaire) est réduite.
    
- Pour les liaisons réseau dont la mise en service s’avère à la fois coûteuse et difficile, vous serez peut-être contraint à prendre en charge un trafic moins important. Dans ce scénario, permettent l’élasticité de la Skype pour les points de terminaison multimédia Business Server absorber la différence entre le volume de trafic et le niveau de trafic maximal, au prix d’une réduction de la qualité de la voix. En outre, on constatera une réduction de la capacité de traitement supplémentaire pouvant normalement absorber les soudaines augmentations de trafic.
    
- Dans le cas des liaisons ne pouvant pas bénéficier d’un débit optimal à court terme, par exemple dans un réseau étendu utilisant des liaisons de qualité médiocre, vous devez envisager de désactiver les fonctionnalités vidéo pour certains utilisateurs.
    
- Configurez le réseau pour garantir un retard maximal (temps de réponse) de 150 millisecondes (ms) de bout en bout en cas de pic de charge. La latence est la dépréciation d’un réseau Skype pour composants de media Business Server ne peut pas réduire, et il est important de trouver et d’éliminer les points faibles.
    
- Pour les serveurs qui exécutent un logiciel antivirus, inclure tous les serveurs qui exécutent Skype pour Business Server dans la liste des exceptions pour fournir des performances optimales et une qualité audio. 
    
## <a name="conferencing-network-requirements"></a>Conditions de réseau requises pour les fonctionnalités de conférence web
<a name="Conf_req"> </a>

La bande passante utilisée pour télécharger le contenu de la conférence à partir du serveur Internet Information Services (IIS) dépend de la taille du contenu. Vous pouvez surveiller l’utilisation réelle de la bande passante et ajuster la planification de la bande passante en conséquence.
  
## <a name="network-bandwidth-requirements-for-media-traffic"></a>Configuration requise de la bande passante pour le trafic multimédia
<a name="Conf_req"> </a>

Une partie importante de la planification du réseau est de s’assurer que votre réseau peut supporter le trafic de supports généré par Skype pour Business Server. Cette section vous aide à planifier le trafic multimédia. 
  
### <a name="media-traffic-network-usage"></a>Utilisation du réseau pour le trafic multimédia
<a name="Net_req"> </a>

L’utilisation de la bande passante par le trafic multimédia peut être difficile à calculer en raison du nombre de variables différentes, comme l’utilisation du codec, la résolution et les niveaux d’activité. L’utilisation de la bande passante est une fonction du codec utilisé et de l’activité du flux, pouvant varier d’un scénario à l’autre. Le tableau suivant répertorie les codecs audio utilisés généralement dans Skype pour les scénarios de serveur d’entreprise.
  
**Bande passante de codec audio**

|**Codec audio**|**Scénario**|**Vitesse de transmission de charge utile audio (Kbits/s)**|**Charge utile audio de la bande passante et de l’en-tête IP uniquement (Kbits/s)**|**Charge utile audio de la bande passante, l’en-tête IP, UDP, RTP et SRTP (Kbits/s)**|**Bande passante audio charge utile, IP en-tête, UDP, RTP, SRTP et correction d’erreurs (Kbits/s)**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Large bande RTAudio  <br/> |Égal à égal  <br/> |29.0  <br/> |45.0  <br/> |57,0  <br/> |86.0  <br/> |
|Bande étroite RTAudio  <br/> |Égal à égal, PSTN  <br/> |11.8  <br/> |27,8  <br/> |39,8  <br/> |51.6  <br/> |
|G.722  <br/> |Téléconférence  <br/> |64,0  <br/> |80,0  <br/> |95.6  <br/> |159.6  <br/> |
|Stéréo G.722  <br/> |Égal à égal, conférence  <br/> |128.0  <br/> |144.0  <br/> |159.6  <br/> |223.6  <br/> |
|G.711  <br/> |RTC, conférence  <br/> |64,0  <br/> |80,0  <br/> |92.0  <br/> |156.0  <br/> |
|Siren  <br/> |Téléconférence  <br/> |16.0  <br/> |32.0  <br/> |47.6  <br/> |63.6  <br/> |
|SILK bande large  <br/> |Égal à égal  <br/> |36.0  <br/> |52.0  <br/> |64,0  <br/> |100.0  <br/> |
|SILK bande large  <br/> |Égal à égal  <br/> |26.0  <br/> |42.0  <br/> |54.0  <br/> |80,0  <br/> |
|SILK bande large  <br/> |Égal à égal  <br/> |20.0  <br/> |36.0  <br/> |48.0  <br/> |68.0  <br/> |
|SOIE à large bande/à bande étroite  <br/> |Égal à égal  <br/> |13.0  <br/> |29.0  <br/> |41.0  <br/> |54.0  <br/> |
   
Les valeurs de bande passante contenues dans le tableau ci-dessus reposent sur la mise en paquets 20 ms (50 paquets par seconde) et pour Siren et G.722 incluent le protocole SRTP (Secure Real-Time Transport Protocol) en plus des scénarios de conférence et supposent que le flux est entièrement actif. La correction d'erreur de transfert (FEC) est utilisée dynamiquement en cas de perte de paquet sur la liaison afin de maintenir la qualité du flux audio.  
  
La version stéréo du codec G.722 est utilisée par les systèmes basés sur Lync Room System, qui s'appuie sur un micro stéréo unique ou une paire de micro mono pour permettre aux participants de mieux distinguer les différents intervenants dans une salle de réunion.
  
**Bande passante de résolution vidéo**

|**Codec vidéo**|**Résolution et rapport l / h**|**Vitesse de transmission de charge utile vidéo maximale (Kbits/s)**|**Vitesse de transmission minimale de charge utile vidéo (Kbits/s)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |320x180 (16:9)  <br/> 212x160 (4:3)  <br/> |250  <br/> |15  <br/> |
|H.264/RTVideo  <br/> |424x240 (16:9)  <br/> 320x240 (4:3)  <br/> |350  <br/> |100  <br/> |
|H.264  <br/> |480x270 (16:9)  <br/> 424x320 (4:3)  <br/> |450  <br/> |200  <br/> |
|H.264/RTVideo  <br/> |640x360 (16:9)  <br/> 640x480 (4:3)  <br/> |800  <br/> |300  <br/> |
|H.264  <br/> |848x480 (16:9)  <br/> |1500  <br/> |400  <br/> |
|H.264  <br/> |960x540 (16:9)  <br/> |2000  <br/> |500  <br/> |
|H.264/RTVideo  <br/> |1 280 x 720 (16:9)  <br/> |2500  <br/> |700  <br/> |
|H.264  <br/> |1 920 x 1 080 (16:9)  <br/> |4000  <br/> |1500  <br/> |
|H.264/RTVideo  <br/> |960x144 (20:3)  <br/> |500  <br/> |15  <br/> |
|H.264  <br/> |1 280 x 192 (20:3)  <br/> |1000  <br/> |250  <br/> |
|H.264  <br/> |1 920 x 288 (20:3)  <br/> |2000  <br/> |500  <br/> |
   
Pour la vidéo, le codec par défaut est la norme H.264/MPEG-4 Part 10 Advanced Video Coding avec ses extensions de codage vidéo évolutives pour une extensibilité dans le temps. Pour assurer l’interopérabilité avec les clients hérités, le codec RTVideo est encore utilisé pour les appels de peer-to-peer entre Skype pour Business Server et les clients hérités. Dans les sessions de conférence avec les deux Skype pour Business Server et les clients hérités du Skype pour Business Server point de terminaison peut encoder la vidéo à l’aide de deux codecs vidéo et envoyer le bitstream H.264 pour le Skype pour les clients de serveur d’entreprise et le flux binaire RTVideo d’ancienne génération clients.
  
La bande passante nécessaire dépend de la résolution, de la qualité et de la fréquence d'images. Pour chaque résolution, deux vitesses de transmission pertinentes sont disponibles :
  
- **Vitesse de transmission de charge utile maximale** Il s’agit de la vitesse de transmission qui utilise un point de terminaison pour la résolution de la fréquence maximale. Cette valeur permet la qualité vidéo et audio maximale.
    
- **Vitesse de transmission de charge utile minimale** Il s’agit de la vitesse de transmission au-dessous de laquelle un Skype pour point de terminaison Business Server passera à la résolution inférieure suivante. Afin de garantir une certaine résolution, la vitesse de transmission de la charge utile vidéo disponible ne doit pas être comprise dans la vitesse de transmission minimale pour cette résolution. Cette valeur permet de comprendre la valeur la plus basse possible lorsque l’utilisation de la vitesse de transmission maximale n’est pas disponible ou pratique. Pour certains utilisateurs, cette vitesse faible peut être considérée comme inacceptable ; ces vitesses de transmission doivent donc être utilisées avec prudence. Notez que pour des vidéos avec peu ou pas de mouvements, la vitesse de transmission réelle peut temporairement être inférieure à la vitesse de transmission minimale.
    
Skype pour Business Server prend en charge plusieurs résolutions. Ainsi, Skype pour Business Server pour s’ajuster à la bande passante du réseau et de la réception de fonctionnalités du client. Le rapport d’aspect par défaut pour Skype pour Business Server est de 16:9. Le rapport d’aspect de 4:3 hérité est toujours pris en charge pour les webcams qui n’autorise pas la capture dans le rapport d’aspect 16:9.
  
Le FEC vidéo est toujours intégré à la vitesse de transmission de la charge utile vidéo le cas échéant ce qui évite d’avoir des valeurs distinctes avec et sans le FEC vidéo. 
  
Les points de terminaison ne transmettent pas les paquets audio ou vidéo en continu. Selon le scénario, les niveaux d'activité de flux sont différents, ce qui indique à quelle fréquence les paquets sont envoyés pour un flux. L'activité d'un flux varie en fonction du support et du scénario et non pas du codec qui est utilisé. Dans un scénario poste à poste :  
  
- Les points de terminaison envoient les flux audio uniquement lorsque les intervenants parlent.
    
- Les deux participants reçoivent des flux audio.
    
- En cas d'utilisation de la vidéo, les deux points de terminaison envoient et reçoivent des flux vidéo pendant l'appel.
    
- Pour des vidéos statiques, la vitesse de transmission réelle peut être temporairement très faible, car le codec vidéo n'encodera pas les régions de la vidéo qui ne sont pas modifiées depuis l'extraction de l'échantillon préalable.
    
Dans un scénario de conférence :
  
- Les points de terminaison envoient des flux audio uniquement lorsque les utilisateurs parlent.
    
- Tous les participants reçoivent des flux audio.
    
- Si la vidéo est utilisée, tous les participants peuvent recevoir jusqu’à cinq flux vidéo entrants et un flux panoramique (par exemple, proportions 20:3). Par défaut, les cinq flux vidéo entrants sont basés sur l’historique du haut-parleur actif, mais les utilisateurs peuvent également manuellement sélectionner les participants desquels ils souhaitent recevoir un flux vidéo. Si la multi-vidéo est activée, la configuration requise pour la résolution et la bande passante peut être inférieure pour chaque flux vidéo.
    
- Chaque participant qui active l’utilisateur envoie le flux vidéo enverra un ou plusieurs flux vidéo. Skype pour Business Server a la capacité d’envoyer jusqu'à cinq flux vidéo afin d’optimiser la qualité vidéo pour tous les clients de réception. Le nombre réel de flux vidéo envoyé est déterminé par l’émetteur en fonction de la capacité du processeur, de la bande passante montante disponible et du nombre de clients de réception qui demandent un flux vidéo spécifique. Dans le cas le plus courant, un flux vidéo H.264 et un flux vidéo RTVideo sont envoyés quand un client hérité participe à une conférence. Il se peut également que plusieurs flux vidéo H.264 (par exemple, avec différentes résolutions vidéo) soient envoyés pour différentes demandes. 
    
Outre la bande passante requise pour le trafic RTP (Real-Time Transport Protocol) pour les supports audio et vidéo, le protocole RTCP (Real-Time Transport Control Protocol) a lui aussi besoin de bande passante. RTCP est utilisé pour le signalement des statistiques et le contrôle hors-bande du flux RTP. Pour la planification, utilisez les valeurs de bande passante contenues dans le tableau ci-dessous pour le trafic RTCP. Ces valeurs représentent la bande passante maximale utilisée pour le trafic RTCP et varient pour les flux audio et vidéo en raison des différences dans les données de contrôle. 
  
**Bande passante RTCP**

|**Media**|**Bande passante maximale RTCP (Kbits/s)**|
|:-----|:-----|
|Audio  <br/> |5  <br/> |
|Vidéo (uniquement H.264 ou RTVideo envoyé/reçu)  <br/> |10  <br/> |
|Vidéo (H.264 et RTVideo envoyé/reçu)  <br/> |15  <br/> |
   
Pour planifier la capacité, les deux statistiques suivantes sont intéressantes :
  
- **Bande passante maximale sans FEC** La bande passante maximale qui consomme un flux de données. Cela inclut l’activité typique du flux et le codec par défaut utilisé dans le scénario sans mode FEC. C’est la bande passante lorsque le flux est au niveau d’activité de 100 % et qu’il n’y a aucune perte de paquet déclencher l’utilisation du mode FEC. Cela est utile pour le calcul de la bande passante doit être alloué pour permettre le codec à utiliser dans un scénario donné. FEC n’est pas censée être une exigence d’un réseau géré.
    
- **Bande passante maximale avec FEC** La bande passante maximale qui consomme d’un flux de données. Cela inclut l’activité typique du flux et le codec par défaut utilisé dans le scénario avec le mode FEC. Il s’agit de la bande passante lorsque le flux est au niveau d’activité de 100 % et la perte de paquet déclencher l’utilisation de FEC pour améliorer la qualité. Cela est utile pour le calcul de la bande passante doit être alloué pour permettre le codec à utiliser dans un scénario donné et permettre l’utilisation de FEC à préserver la qualité dans des conditions de perte de paquet.
    
Les tableaux suivants répertorient également une valeur de bande passante supplémentaire, **la bande passante par défaut**. Il s’agit de la bande passante moyenne qui consomme d’un flux de données. Cela inclut l’activité typique du flux et le codec par défaut utilisé dans le scénario. La bande passante peut servir d’approximation de la bande passante consommée par le trafic multimédia à un moment donné, mais qu’il ne doit pas être utilisée pour la planification de la capacité, car les appels dépasse cette valeur lorsque le niveau d’activité est supérieur à la moyenne. La bande passante du flux de données vidéo standard dans les tableaux ci-dessous est basée sur un mélange de différentes résolutions vidéo comme observée dans les données mesurées et les petites installations sont susceptibles d’avoir des chiffres réels qui diffèrent des données de la table. Par exemple, dans la plupart des utilisateurs utiliserait la vidéo par défaut des sessions peer-to-peer rendu de fenêtre qu’un pourcentage d’utilisateurs devrait augmenter ou optimiser la Skype pour application Business Server permettre une meilleure résolution vidéo.
  
Les tableaux ci-dessous fournissent les valeurs pour les divers scénarios.
  
**Planification de Sessions de Peer-to-Peer de la capacité audio/vidéo**

|**Media**|**Codec**|**Bande passante du flux de données par défaut (Kbits/s)**|**Bande passante maximale de flux sans FEC**|**Bande passante maximale de flux avec FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |Large bande RTAudio  <br/> |39,8  <br/> |62  <br/> |91  <br/> |
|Audio  <br/> |Bande étroite RTAudio  <br/> |29.3  <br/> |44,8  <br/> |56,6  <br/> |
|Audio  <br/> |SILK bande large  <br/> |44.3  <br/> |69  <br/> |105  <br/> |
|Vidéo principale lors de l’appel Skype pour les points de terminaison de serveur d’entreprise  <br/> |H.264  <br/> |460  <br/> |4 010 (pour une résolution maximale de 1 920 x 1 080)  <br/> |Déjà inclus  <br/> |
|Vidéo principale lors de l’appel des points de terminaison de Lync 2010 ou Office Communicator 2007 R2  <br/> |RTVideo  <br/> |460  <br/> |2 510 (pour une résolution maximale de 1 280 x 720)  <br/> |Déjà inclus  <br/> |
|Panoramique vidéo lors de l’appel Skype pour les points de terminaison de serveur d’entreprise  <br/> |H.264  <br/> |190  <br/> |2 010 (pour une résolution maximale de 1 920 x 288)  <br/> |Déjà inclus  <br/> |
|Panoramique vidéo lors de l’appel des points de terminaison de Lync 2010  <br/> |RTVideo  <br/> |190  <br/> |510 (pour une résolution maximale de 960x144)  <br/> |Déjà inclus  <br/> |
   
**Planification des conférences de capacité audio/vidéo**

|**Media**|**Codec standard**|**Bande passante du flux de données par défaut (Kbits/s)**|**Bande passante maximale de flux sans FEC**|**Bande passante maximale de flux avec FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G.722  <br/> |46.1  <br/> |100.6  <br/> |164.6  <br/> |
|Audio  <br/> |Siren  <br/> |25,5  <br/> |52.6  <br/> |68.6  <br/> |
|Réception vidéo principale  <br/> |H.264 et RTVideo¹  <br/> |260  <br/> |8015  <br/> |Non applicable  <br/> |
|Envoi vidéo principal  <br/> |H.264 et RTVideo  <br/> |270  <br/> |8015  <br/> |Non applicable  <br/> |
|Réception vidéo panoramique  <br/> |H.264 et RTVideo  <br/> |190  <br/> |2 010 (pour une résolution maximale de 1 920 x 288)  <br/> |Non applicable  <br/> |
|Envoi vidéo panoramique  <br/> |H.264 et RTVideo  <br/> |190  <br/> |2 515²  <br/> |Non applicable  <br/> |
   
1. RT vidéo est envoyé en outre à H.264 lorsque les clients Lync 2010 sont connectés à la conférence.
  
2. Si plusieurs flux de données, ils répartissent de façon dynamique la bande passante allouée.
  
Pour la vidéo principale, la vitesse de transmission du flux type est la bande passante agrégée divisée par tous les flux vidéo reçus et la vitesse de transmission du flux maximale est la bande passante agrégée divisée par tous les flux vidéo envoyés. Même avec plusieurs flux vidéo, la bande passante type est plus petite que dans un scénario d'égal à égal, car de nombreuses conférences vidéo utilisent le partage de contenu, ce qui entraîne des fenêtres vidéo plus petites et donc des résolutions vidéo plus petites. La bande passante de charge utile vidéo agrégée maximum prise en charge est 8 000 Kbits/s pour les flux envoyés et reçus, par exemple pour deux flux vidéo 1 920x1 080p entrants. Il est rare que les valeurs maximales soient atteintes dans les implémentations du monde réel.
  
Lors de la création d’une conférence à plusieurs participants qui utilise la fonctionnalité d’affichage de la galerie, l’utilisation de la bande passante augmente initialement en tant que participants jointure, puis diminue lorsque les résolutions sont supprimées pour s’ajuster à la valeur maximale. 
  
||**2 participants**|**3 participants**|**4 derniers participants**|**5 participants**|**6 participants**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Résolutions maximales reçues** <br/> |1920 x 1080.  <br/> |1280 x 720  <br/> |640 x 360  <br/> |320 640 x 360 x 240  <br/> |320 640 x 360 x 240  <br/> |
|**Débit moyen total** <br/> |2128  <br/> |4050  <br/> |1304  <br/> |1224  <br/> |1565  <br/> |
|**Débit maximal total** <br/> |4063  <br/> |5890  <br/> |2860  <br/> |2699  <br/> |3017  <br/> |
   
La bande passante de flux type pour la vidéo panoramique est basée sur les périphériques capables de diffuser des flux de vidéo panoramique d'une résolution maximale de 960x144. Attendez-vous à une augmentation de la bande passante de flux type lors de l'utilisation de périphériques avec une vidéo panoramique de 1 920x288.  
  
**Planification pour RTPC audio de la capacité**

|**Media**|**Codec standard**|**Bande passante du flux de données par défaut (Kbits/s)**|**Bande passante maximale de flux sans FEC**|**Bande passante maximale de flux avec FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G.711 (y compris les participants RTPC dans les conférences)  <br/> |64.8  <br/> |97  <br/> |161  <br/> |
|Audio  <br/> |Bande étroite RTAudio  <br/> |30,9  <br/> |44,8  <br/> |56,6  <br/> |
   
Les valeurs de bande passante pour le réseau contenues dans ces tableaux représentent uniquement le trafic unidirectionnel et incluent 5 Kbits/s pour le trafic RTCP pour chaque flux. 
  
## <a name="managing-quality-of-service"></a>Gestion de la qualité de service
<a name="man_QOS"> </a>

La Qualité de service (QoS) est une technologie réseau utilisée dans certaines organisations afin de fournir des performances optimales à l'utilisateur final pour les communications audio et vidéo. QoS est le plus souvent utilisée sur les réseaux où la bande passante est limitée : avec un grand nombre de paquets réseau simultanés pour une quantité de bande passante disponible relativement faible, QoS permet aux administrateurs d'affecter une priorité supérieure aux paquets transportant des données audio ou vidéo. Le fait d'affecter une priorité supérieure à ces paquets permet aux communications audio et vidéo de s'effectuer plus rapidement, et avec moins d'interruption, que les sessions réseau impliquant des opérations telles que des transferts de fichiers, de la navigation web ou des sauvegardes de bases de données. C'est la raison pour laquelle la priorité « Meilleur effort » est affectée aux paquets réseau utilisés pour les transferts de fichiers ou les sauvegardes de bases de données.
  
> [!NOTE]
> En règle générale, la QoS s'applique uniquement aux sessions de communication sur votre réseau interne. Lorsque vous implémentez QoS, vous configurez vos serveurs et routeurs afin de prendre en charge le marquage de paquets qui ne peut pas être pris en charge sur Internet et d'autres réseaux. Même si QoS est pris en charge sur d'autres réseaux, il n'est pas garanti que la configuration de QoS sera identique à celle que vous avez faite de ce service. Si vous utilisez MPLS, vous devrez contacter votre fournisseur MPLS 
  
Skype pour Business Server ne nécessite pas la qualité de service, mais il est fortement recommandé. Si vous rencontrez des problèmes de perte de paquets sur le réseau vos solutions disponibles sont à ajouter davantage de bande passante ou pour implémenter QoS. Si l’ajout de bande passante n’est pas possible, l’implémentation de QoS peut constituer la seule solution au problème.
  
Skype pour Business Server offre une prise en charge intégrale de la qualité de service : que signifie que les entreprises qui utilisent déjà QoS peuvent facilement intégrer Skype pour Business Server leur infrastructure réseau existante. Pour ce faire, procédez comme suit :
  
- [L’activation de QoS pour les périphériques Non Windows](http://technet.microsoft.com/library/26f793df-aef8-4028-9e3b-6c2c37ea61b9.aspx). Par défaut, QoS est désactivée pour les ordinateurs et autres appareils (tels que les iPhones) qui exécutent d’autres systèmes d’exploitation. Vous pouvez utiliser Skype pour Business Server pour activer et désactiver la qualité de service pour les périphériques, vous ne peut pas en général utiliser le produit pour modifier les codes DSCP utilisés par ces périphériques.
    
- [Configuration des plages de Port pour votre conférence, Application et les serveurs de médiation](http://technet.microsoft.com/library/4d6eaa5d-0127-453f-be6a-e55384772d83.aspx). Vous devez réserver un ensemble unique de ports pour différents types de paquets, tels que les paquets audio et vidéo. À l’aide de Skype pour Business Server ne pas activer ou désactiver la qualité de service en définissant une valeur de propriété à True ou à False. Au lieu de cela, vous activez QoS en configurant des plages de ports, puis en créant et en appliquant une stratégie de groupe. Si vous décidez ultérieurement de ne doit ne pas utiliser QoS vous pouvez « désactiver » QoS en supprimant les objets de stratégie de groupe appropriés.
    
- [Configuration des plages de ports de vos serveurs Edge](http://technet.microsoft.com/library/6f0ae442-6624-4e3f-849a-5b9e387fb8cf.aspx). Bien que cela ne soit pas requis, vous pouvez configurer vos serveurs Edge de façon à utiliser les mêmes plages de ports que vos autres serveurs.
    
- [Configuration des plages de Port pour les Clients de Microsoft Lync](http://technet.microsoft.com/library/287d5cea-7ada-461c-9b4a-9da2af315e71.aspx). Ces plages de ports s’appliquent uniquement aux ordinateurs clients et sont généralement différents des plages de ports configurées sur vos serveurs.
    
- [Configuration d’une qualité de la politique d’assistance pour votre conférence, les applications et les serveurs de médiation](http://technet.microsoft.com/library/8adcbbc5-c9f5-476d-ab7f-72e61859cacf.aspx). Ces stratégies déterminent les codes DSCP appliqués aux différents types de paquets.
    
- [Configuration d’une qualité de Service stratégie pour vos A / V Edge serveurs](http://technet.microsoft.com/library/119ee1f5-45b9-40ba-98e5-c694dd2fc5c2.aspx). Cette opération ne doit être effectuée que pour le côté interne de vos serveurs Edge. En effet, la QoS est conçue pour être utilisée sur votre réseau interne, et non sur Internet.
    
- [Configuration de Peer-to-Peer de qualité de Service des stratégies pour les Clients fonctionnant sous Windows 7 ou de Windows 8](http://technet.microsoft.com/library/efff2b98-b3fb-4183-a4f0-329a9105ce2c.aspx). Notez que Skype pour Business Server ne gère pas la qualité de service pour d’autres systèmes d’exploitation Windows, tels que Windows Vista ou Windows XP.
    
- [Configuration de la qualité de Service sur les périphériques Microsoft Lync Phone Edition](http://technet.microsoft.com/library/a6eb2620-a512-4ab6-bdfd-eb76be43bbfe.aspx). Par défaut, QoS est activé pour les périphériques Microsoft Lync Phone Edition. Vous pouvez modifier la valeur DSCP par défaut afin de garantir que tous les paquets audio de votre organisation utilisent le même code DSCP.
    
> [!NOTE]
> Si vous utilisez Windows Server 2012 R2 ou Windows Server 2012 peut vous intéresser dans le nouveau jeu d’applets de commande Windows PowerShell disponibles pour la gestion de QoS sur cette plate-forme. Pour plus d’informations, reportez-vous à la section [Applets de commande réseau QoS dans Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=285379). 
  
QoS est également abordée dans le livre blanc sur la [Planification du réseau, de surveillance et le dépannage avec Lync Server](https://www.microsoft.com/en-us/download/details.aspx?id=39084) avec plus de détails et de profondeur. Bien que le contenu fait explicitement référence à Lync 2010 et Lync 2013, les considérations de Skype pour Business Server 2015 restent inchangées.
  
## <a name="see-also"></a>Voir aussi
<a name="man_QOS"> </a>

#### 

[Planification d’IPv6 dans Skype pour entreprise](ipv6.md)
  
[Configuration requise pour Skype pour les entreprises d’équilibrage de la charge](load-balancing.md)
  
[Configuration requise par DNS Skype pour Business Server 2015](dns.md)
  
[Configuration de ports et de protocoles pour les serveurs](ports-and-protocols.md)

