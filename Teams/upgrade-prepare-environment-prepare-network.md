---
title: Préparer votre réseau Microsoft Teams |  Configuration requise du pare-feu de port
author: turgayo
ms.author: turgayo
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Utilisez ce guide pour préparer votre réseau pour le déploiement et le lancement de Teams
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 950786a6d1014b322c76d1f4cd35afaec789f177
ms.sourcegitcommit: 889295b507c77a93b10b3a5e826f2b0c79c31f75
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2019
ms.locfileid: "30771781"
---
![Étapes du parcours de mise à niveau, avec un accent sur l’étape de préparation technique](media/upgrade-banner-tech-readiness.png "Étapes du parcours de mise à niveau, avec un accent sur l’étape de préparation technique")

Cet article entre dans le cadre de l’étape de préparation technique de votre parcours de mise à niveau, une activité que vous effectuez parallèlement à l’étape de préparation des utilisateurs. Avant de poursuivre, vérifiez que vous avez terminé les activités des étapes précédentes :

- [Inscription des parties prenantes du projet](upgrade-enlist-stakeholders.md)
- [Définition du champ d’application de votre projet](https://aka.ms/SkypetoTeams-Scope)
- [Compréhension de la coexistence et de l’interopérabilité de Skype Entreprise et Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Choix de votre parcours de mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

> [!Tip]
> Regarder la session suivante pour en savoir comment les équipes s’appuie sur votre réseau et comment mieux planifier la connectivité réseau optimale : [Planification des équipes réseau](https://aka.ms/teams-networking)

# <a name="prepare-your-network-for-upgrading-to-teams"></a>Préparation du réseau pour la mise à niveau vers des équipes

Si vous déployez audio, vidéo ou des réunions, vous pouvez tirer quelques étapes supplémentaires pour optimiser votre réseau pour cette fonctionnalité. Équipes utilise audio et vidéo technologie (codecs) qui peut s’adapter aux — et par conséquent exécuter mieux sous — plus les conditions de réseau. Pour garantir des performances optimales et cohérentes, vous devez préparer votre réseau pour les équipes.

![Diagramme décrivant les trois composants de qualité et de la gestion des services chevauche les trois composants. En mettant l’accent sur le réseau.] (media/evaluate-my-environment-image1.png "Diagramme décrivant les trois composants de qualité et de la gestion des services chevauche les trois composants. En mettant l’accent sur le réseau.")

## <a name="why-should-you-prepare-your-network"></a>Pourquoi vous devez préparer votre réseau ?

Avant d’examiner les mesures à prendre, il est important de comprendre ce qui peut affecter les performances des équipes et, par conséquent satisfaction et bonheur de l’utilisateur. Trois zones principales risque peuvent affecter la façon dont les utilisateurs sachent qualité du réseau :

- La bande passante disponible

- Bloqueurs de pare-feu et proxy

- TROUBLES réseau telles que la perte de gigue et de paquets

Les étapes décrites ci-dessous vous aidera à déterminer que si votre déploiement peut-être être affecté par un de ces facteurs et aide à vous déplacez vers une solution. Pour préparer votre réseau défectueux entraînera probablement pas du tout satisfait aux utilisateurs et les correctifs d’ad hoc coûteuses. En préparation de votre réseau et votre organisation : pour les équipes, vous pouvez considérablement augmenter vos chances de réussite.

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>Planification de la bande passante


Teams Microsoft offre les meilleures audio, vidéo et contenu expérience indépendamment de vos conditions réseau. Avec les codecs variables, média peut être négocié dans les environnements de bande passante limitée avec un impact minimal. Mais où la bande passante n’est pas un problème, une expérience peut être optimisée pour la qualité, y compris des résolution vidéo 1080p, jusqu'à 30 i/s pour la vidéo et 15 i/s pour le contenu et les paramètres audio haute fidélité.


Cet article décrit une version concise de la bande passante est utilisée par les équipes en temps réel audio, vidéo et modalités dans différents cas d’utilisation de partage du bureau. Les équipes est toujours estime sur l’utilisation de la bande passante et peut fournir une qualité vidéo HD dans 1.2Mbps sous. La consommation de bande passante réelle dans chaque appel audio/vidéo ou la réunion varie en fonction de plusieurs facteurs, tels que la vidéo mise en page, la résolution vidéo et vidéo images par seconde.Lorsque plus de bande passante est disponible qualité et l’utilisation augmente afin d’offrir la meilleure expérience.

|Bandwidth(up/down) |Scénarios |
|---|---|
|30 Kbits/s |Appel audio d’égal à égal |
|130 Kbits/s |Appel audio d’égal à égal et de partage d’écran |
|500 Kbits/s |Égal à égal qualité vidéo appelant p 360 à 30 i/s |
|1.2 Mbits/s |Vidéo de qualité HD égal-à-l’appel avec une résolution de HD 720 pixels à 30 i/s |
|1,5 Mbits/s |Vidéo de qualité HD égal-à-l’appel avec une résolution de HD 1080p 30 i/s |
|500 Kbits/s/1 Mbits/s |Groupe d’appel vidéo |
|1 Mbits/s/2 |Groupe HD vidéo appelant (vidéos 540p sur écran 1080p) |

### <a name="local-internet-egress"></a>Sortie Internet locale

De nombreux réseaux ont été conçus pour utiliser une topologie de hub et parlée. Dans cette topologie, le trafic Internet traverse généralement le WAN jusqu'à un centre de données central avant qu'il n'émerge (sorties) vers Internet. Souvent, cela est fait pour centraliser les dispositifs de sécurité du réseau dans le but de réduire les coûts globaux.

Relayer le trafic sur le WAN augmente la latence et a un impact négatif sur la qualité et l'expérience utilisateur. Comme Microsoft Teams fonctionne sur le vaste réseau mondial de Microsoft, il existe souvent un emplacement réseau de pairage à proximité de l'utilisateur. Un utilisateur obtiendra probablement de meilleures performances en sortant d'un point Internet local près de son emplacement et sur notre réseau à voix optimisée dès que possible. Pour certaines charges de travail, les requêtes DNS sont utilisées pour envoyer du trafic vers le serveur frontal le plus proche. Dans de tels cas, il est important que lors de l'utilisation d'un point d'évacuation local, il soit couplé avec la résolution DNS locale.

L'optimisation du chemin d'accès au réseau mondial de Microsoft améliorera les performances et, en fin de compte, offrira la meilleure expérience aux utilisateurs. Pour plus de détails, voir l'article du blog [Obtenir la meilleure connectivité et les meilleures performances dans Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

Pour obtenir une expérience optimale en utilisant des médias en temps réel dans Microsoft Teams, vous devez satisfaire la configuration réseau requise pour Office 365. Pour plus d’informations, voir [la qualité des médias et des performances pour la connectivité réseau pour Skype pour Business Online](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).

Les segments de réseau définissant deux (Client pour Microsoft Edge) et côté client pour Microsoft Edge doivent remplir les conditions suivantes :

|**Valeur** |**Client Microsoft Edge** |**Côté client pour Microsoft Edge** |
|---|---|---|
|**Latence (unidirectionnelle)** |< 50 ms |< 30 ms |
|**Latence (temps d’aller-retour ou durée aller-retour)** |< 100 ms |< 60 ms |
|**Perte de paquets en rafale** |<10 % au cours de l’intervalle de 200-ms |<1 % au cours de l’intervalle de 200-ms |
|**Perte de paquets** |<1 % au cours de l’intervalle de 15-s |<0.1% pendant l’intervalle de 15-s |
|**Gigue arrivée entre des batteries de paquets** |<30 ms pendant l’intervalle de 15-s |<15 ms pendant l’intervalle de 15-s |
|**Réorganisation des paquets** |paquets d’ordre <0.05% |paquets d’ordre <0.01% |

Pour tester les deux segments réseau, vous pouvez utiliser l' [Outil d’évaluation de réseau](https://go.microsoft.com/fwlink/?linkid=855799). Cet outil peut être déployé sur le client PC directement et sur un PC connecté à la périphérie du réseau client. L’outil comprend une documentation limitée, mais une documentation plue autour de l’utilisation de l’outil se trouvent ici : [Évaluation de préparation de réseau](https://go.microsoft.com/fwlink/?linkid=855800). En exécutant cette évaluation de préparation du réseau, vous pouvez valider la préparation de votre réseau d’exécuter des applications multimédia en temps réel, tels que Microsoft Teams.

> [!NOTE]
> Il s’agit de la même évaluation de préparation de réseau que nous vous recommandons d’être exécutée par les clients qui souhaitent pour déployer Skype pour les entreprises.

### <a name="vpn"></a>VPN

Les VPN fournissent un service de valeur à de nombreuses organisations. Malheureusement, ils sont généralement pas conçus ou configurés pour prendre en charge les médias en temps réel. Certains VPN peuvent également ne pas prendre en charge UDP. Réseaux privés virtuels introduisent également un niveau supplémentaire de chiffrement par-dessus le trafic multimédia qui est déjà chiffré. En outre, la connectivité au service équipes est peut-être pas efficace en raison de l’épinglage de cheveux le trafic via un périphérique VPN. En outre, ils ne sont pas nécessairement conçus à partir d’un point de vue de la capacité à prendre en charge les charges anticipées nécessiteront des équipes.

La recommandation est de fournir un chemin alternatif qui contourne le VPN pour le trafic de Teams. Cela est généralement appelé *split-tunnel VPN*. Fractionner tunnel signifie que le trafic pour Office 365 ne traversent le réseau VPN, mais est dirigés directement vers Office 365. Ce changement aura un impact positif sur la qualité, mais aussi l'avantage secondaire de réduire la charge des dispositifs VPN et du réseau de l'organisation.

Pour mettre en œuvre un tunnel segmenté, consultez votre fournisseur VPN pour les détails de configuration.

### <a name="wi-fi"></a>Wi-Fi

Comme VPN, les réseaux Wi-Fi ne sont pas nécessairement conçus ou configurés pour prendre en charge les médias en temps réel. Planification d’ou optimisation, un réseau Wi-Fi pour prendre en charge des équipes est une considération importante pour un déploiement de haute qualité.

Il existe plusieurs facteurs qui entrent en jeu pour l’optimisation d’un réseau Wi-Fi :

- Mettre en œuvre la QoS ou le Wi-Fi Multimedia (WMM) pour s'assurer que le trafic média est priorisé en conséquence sur les réseaux Wi-Fi.

- Planification et optimisation les bandes Wi-Fi et access point de positionnement. 2,4 GHz peut fournir une expérience adéquate en fonction de l’emplacement du point d’accès, mais les points d’accès sont souvent concernées par d’autres appareils qui fonctionnent dans cette plage. La gamme de 5 GHz est mieux adaptée aux médias en temps réel en raison de leur portée dense, mais nécessite plus de points d'accès pour obtenir une couverture suffisante. Les points de terminaison doivent également prendre en charge cette plage et être configurés pour exploiter ces bandes en conséquence.

- Si les réseaux Wi-Fi double bande sont déployés, envisagez d’implémenter la direction de la bande. _Bande de direction_ est utilisée par les fournisseurs Wi-Fi pour influencer le double bande aux clients d’utiliser la plage 5 GHz technique.

- Lorsque les points d’accès du même canal sont trop proches, ils peuvent entraîner la superposition du signal et concurrence involontairement, ce qui entraîne une mauvaise expérience de l’utilisateur. Assurez-vous que les points d’accès qui sont en regard de chacun des autres sont sur les canaux qui ne se chevauchent pas.

Chaque fournisseur de services sans fil a ses propres recommandations pour le déploiement de sa solution sans fil. Nous vous recommandons de consulter votre fournisseur pour obtenir des conseils spécifiques.

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>Configuration requise du pare-feu et proxy

Microsoft Teams se connecte à Microsoft Online Services et a besoin de la connectivité internet pour ce. Pour les équipes de fonctionner correctement, vous devez ouvrir les ports TCP 80 et 443 à partir des clients à internet et les ports UDP 3478 3481 à partir des clients à internet par le biais de. Les ports TCP sont utilisés pour se connecter au contenu web tels que SharePoint Online, Exchange Online et les services de conversation des équipes. Plug-ins et aux connecteurs de se connectent sur ces ports TCP. Les quatre ports UDP sont utilisés pour les médias audio et vidéo, pour s’assurer qu’ils arrivent correctement.

L’ouverture de ces ports est essentielle pour un déploiement équipes fiable. Blocage de ces ports est pris en charge et a une incidence sur la qualité des médias.

Si votre organisation requiert que vous spécifiez les plages d’adresses IP et les domaines auxquels ces ports doivent être ouverts exacte, vous pouvez restreindre les plages d’adresses IP cible et les domaines de ces ports. Pour obtenir la liste des ports exactes, des protocoles et des plages d’adresses IP, voir [Office 365 URL et plages d’adresses IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). Si vous choisissez de limiter les plages d’adresses IP cible et les domaines, vous devez vous assurer que vous la liste des ports et des plages de mise à jour, car ils peuvent varier. Vous pouvez vous abonner à [ce flux RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) à mettre à jour lorsque des modifications se produisent. Il est également recommandé de vérifier si tous les ports sont ouverts en exécutant la [Skype pour l’outil d’évaluation réseau Business](https://www.microsoft.com/download/details.aspx?id=53885) régulièrement. Vous trouverez plus d’informations sur les fonctionnalités de cet outil dans la section suivante.

En cas d’un serveur proxy en cours de déploiement, nous vous recommandons d’ignorer le serveur proxy pour tous les services d’équipes. À l’aide d’un proxy risque de ne pas fonctionner, mais il est très probable que la qualité sera réduite en raison du média contraints d’utiliser TCP au lieu de UDP. Pour plus d’informations sur les serveurs proxy et de contournement, voir [Office 365 URL et plages d’adresses IP](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges).

<!--ENDOFSECTION-->

## <a name="additional-network-considerations"></a>Considérations relatives au réseau supplémentaires

### <a name="external-name-resolution"></a>Résolution de nom externe

Assurez-vous que tous les ordinateurs clients exécutant le client équipes peuvent résoudre les requêtes DNS externes pour découvrir les services fournis par Office 365.

### <a name="nat-pool-size"></a>Taille du pool de NAT

Lorsque plusieurs utilisateurs et des périphériques access Office 365 à l’aide de la traduction d’adresses réseau (NAT) ou la traduction d’adresse de Port (PAT), vous devez vous assurer que les périphériques derrière chaque adresse IP routable publiquement ne dépassent le nombre pris en charge.

Pour atténuer ce risque, assurez-vous adéquate des adresses IP publiques sont affectés aux pools de NAT pour éviter l’épuisement du port. Épuisement port entraînera interne aux utilisateurs et des périphériques de face problèmes lors de la connexion aux services Office 365. Pour plus d’informations, voir [prise en charge NAT avec Office 365](https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365).

### <a name="intrusion-detection-and-prevention-guidance"></a>Conseils de détection et de prévention des intrusions

Si votre environnement comporte un système de détection d’intrusion et/ou le système de prévention des intrusions déployé pour un niveau supplémentaire de sécurité pour les connexions sortantes, vérifiez que tout le trafic qui a Office 365 URL comme sa destination est la liste d’autorisation.

## <a name="test-the-network"></a>Tester le réseau

Une fois que vous avez terminé la préparation de votre réseau et de planification —, y compris la mise à niveau de la bande passante et ouverture de ports dans le pare-feu, vous devez tester les performances de votre réseau. Les résultats de ce test sera peindre éclaircit l’image de l’optimisation du réseau ou de correction requis pour la réussite de votre implémentation d’équipes.

Vous pouvez télécharger le [Skype pour l’outil d’évaluation réseau métiers](https://www.microsoft.com/download/details.aspx?id=53885) pour vérifier que votre réseau est prêt pour les équipes. L’outil offre deux fonctionnalités : elle permet de tester si tous les ports appropriés ont été ouverts, et il peut tester pour troubles du réseau.

Une fois que vous téléchargez et installez l’outil, recherchez-le dans C:\Program Files (x86) \Microsoft Skype pour l’outil d’évaluation réseau Business. Un guide détaillé pour l’utilisation de l’outil, Usage.docx, est inclus dans ce répertoire.

### <a name="test-for-opened-ports"></a>Test des ports ouverts

Ouvrez une fenêtre d’invite de commandes et accédez au répertoire outil d’évaluation réseau en entrant **cd C:\Program Files (x86) \Microsoft Skype pour l’outil d’évaluation réseau Business**. À l’invite de commandes, démarrez le test pour les ports ouverts en entrant **networkassessmenttool.exe /connectivitycheck**

Après avoir exécuté les contrôles, l’outil s’affiche le message « Vérifications est terminée avec succès » ou créer des rapports sur les ports qui ont été bloqués. Il génère également un fichier nommé Connectivity_results.txt, qui contient la sortie de l’outil et le stocke dans le répertoire % userprofile\\appdata\\local\\Skype de microsoft pour l’outil d’évaluation réseau business\\ directory.

Nous vous conseillons d’exécuter les vérifications de connectivité à intervalles réguliers pour garantir les ports ont été ouverts et fonctionnent correctement.

### <a name="test-for-network-impairments"></a>Test de troubles du réseau

Pour augmenter la satisfaction des utilisateurs, vous devez limiter les troubles sur votre réseau. Les troubles réseau les plus courants sont le délai (latence), la perte de paquets et gigue :

- **Latence :** Il s’agit du temps que nécessaire pour obtenir un paquet IP à partir d’un point à point B sur le réseau. Ce délai de propagation de réseau est essentiellement lié à distance physique entre les deux points et la vitesse de la lumière, y compris une surcharge supplémentaire prise par les routeurs différents entre les deux. Latence correspond à sens unique ou aller-retour de temps.

- **Perte de paquets**: il s’agit souvent un pourcentage des paquets sont perdus dans une fenêtre de temps donnée. Perte de paquets affecte directement la qualité audio, à partir de petite, individuel paquets perdus n’ayant presque aucun impact sur les pertes en rafale DOS à DOS que la fonctionnalité audio cause découper complètement.

- **Gigue arrivée entre les paquets ou simplement gigue :** Il s’agit de la variation moyenne de retard entre les paquets successives. Plus modernes logiciels de VoIP, notamment Skype pour les entreprises, peut s’adapter aux certains niveaux de gigue par le biais de mise en mémoire tampon. Il est uniquement lorsque la gigue dépasse la mise en mémoire tampon qu’un participant remarqueront les effets de gigue.

Les valeurs maximales de ces troubles sont décrits dans les [performances de connectivité réseau et de qualité multimédia](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance). Lors du test de ces troubles, nous faire la distinction entre deux segments distincts :

- Le *segment edge* est le segment dans lequel se trouve votre routeur. Il s’agit du segment de réseau logique le plus proche connecté à internet à chacun de vos emplacements. Dans la plupart des cas, il s’agit du point de connexion du routeur, ou éventuellement un réseau de périmètre (également appelé *zone DMZ*, *zone démilitarisée*et *sous-réseau filtré*). Aucun trafic supplémentaire qui affecte des périphériques autres que le routeur ne doit avoir lieu entre ce segment et internet.

- Le *segment client* est le segment de réseau logique dans laquelle résident vos clients.

Vous devez tester les deux segments à l’aide de l’outil d’évaluation réseau. Pour tester le segment, accédez au répertoire et entrez **networkassessmenttool.exe** à l’invite de commandes. Les résultats sont écrites dans un fichier nommé Results.tsv, et les comparer à la [Configuration requise](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) pour chaque segment.

Notez que les deux segments doivent remplir les conditions d’un déploiement de haute qualité. Nous vous recommandons d’exécuter l’outil plusieurs fois pour une heure directement pour obtenir une bonne indication des performances de votre réseau.

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>Correction de réseau

Si les résultats de la planification de la bande passante, les tests du port ou test de réseau requises montrent que votre réseau actuel doit correction avant de déployer les équipes, vous pouvez le faire de plusieurs façons :

- Pour la bande passante, mise à niveau de connexions de sorte que le trafic vers Office 365 peut passer sans encombre.

- Pour les ports bloqués, modifier des règles de pare-feu et testez à nouveau les ports.

- Pour troubles du réseau, toujours effectuer une analyse de la cause.

Qualité de service (QoS) peut être utilisé pour TROUBLES bataille par ordre de priorité et en séparant le trafic. Certaines organisations choisissent de déployer QoS pour résoudre les problèmes de bande passante ou limiter la quantité de trafic circulant. Cela n’améliorer la qualité et permettra de nouveaux problèmes. Une analyse des causes doit toujours être effectuée lorsque TROUBLES réseau dépassent la configuration requise. QoS peut être une solution. Pour plus d’informations, consultez [Qualité de Service dans les équipes Microsoft](qos-in-teams.md).

>[!NOTE]
>De nombreux réseaux évoluent au fil du temps en raison des mises à niveau, de l'expansion ou d'autres exigences commerciales. Assurez-vous d'avoir des processus opérationnels en place pour maintenir ces secteurs dans le cadre de la planification de la gestion des services.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Point de décision</td><td><ul><li>Qui sera responsable des évaluations réseau appropriés sur tous les segments de réseau et les emplacements de l’organisation ?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Vous pouvez effectuer une évaluation de réseau détaillé pour vous assurer de que votre réseau est prêt pour le déploiement de Microsoft Teams. Pour plus d’informations, voir <a href="https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness" data-raw-source="[Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness)">Évaluation de préparation de réseau</a>.</li><li>Effectuer la mise à jour du réseau en fonction des résultats de l’évaluation de la disponibilité du réseau pour chaque segment de réseau.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="key-takeaways"></a>Points clés

Voici les principaux points à partir de ce guide. Il le faut :

- Ouvrir les ports TCP 80 et 443 sortant de clients qui utiliseront les équipes.

- Ouvrir les ports UDP 3478 via 3481 sortants à partir de clients qui utiliseront les équipes.

- Assurez-vous que vous disposez de suffisamment de bande passante pour le déploiement d’équipes en effectuant le [Planificateur de réseau](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner).

- Exécutez l' [Outil d’évaluation de réseau](https://www.microsoft.com/download/details.aspx?id=53885) et vérifiez que vous respectez les exigences décrites dans les [performances de connectivité réseau et de qualité multimédia](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) à partir du segment edge et le segment client.

## <a name="related-topics"></a>Rubriques connexes

[Vidéo : Planification du réseau](https://aka.ms/teams-networking)
