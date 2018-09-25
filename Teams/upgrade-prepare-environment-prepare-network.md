---
title: Préparer votre réseau pour la mise à niveau vers Teams - Microsoft Teams
author: turgayo
ms.author: turgayo
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Utilisez ce guide pour préparer votre réseau pour le déploiement et le lancement de Teams
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6814fde066e1b9d1fc8d5e1a5d099c1f72c81ef6
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25013714"
---
![Étapes du parcours de mise à niveau, avec un accent sur l’étape de préparation technique](media/upgrade-banner-tech-readiness.png "Étapes du parcours de mise à niveau, avec un accent sur l’étape de préparation technique")

Cet article fait partie de la phase de préparation technique de votre parcours de mise à niveau, une activité que vous effectuez en parallèle à l’étape de préparation des utilisateurs. Avant de continuer, vérifiez que vous avez terminé ces activités à partir des étapes précédentes :

-   [Inscription des parties prenantes du projet](upgrade-enlist-stakeholders.md)
-   [Définition du champ d’application de votre projet](https://aka.ms/SkypetoTeams-Scope)
-   [Compréhension de la coexistence et de l’interopérabilité de Skype Entreprise et Teams](https://aka.ms/SkypeToTeams-Coexist)
-   [Choix de votre parcours de mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prepare-your-network-for-upgrading-to-teams"></a>Préparation de votre réseau pour la mise à niveau vers Teams

Si vous déployez audio, vidéo ou des réunions, vous pouvez tirer quelques étapes supplémentaires pour optimiser votre réseau pour cette fonctionnalité. Équipes utilise audio et vidéo technologie (codecs) qui peut s’adapter aux — et par conséquent exécuter mieux sous — plus les conditions de réseau. Pour garantir des performances optimales et cohérentes, vous devez préparer votre réseau pour les équipes.

![Diagramme illustrant les trois composantes de la qualité, et comment la gestion des services recoupe les trois composantes. En mettant l'accent sur le réseau.](media/evaluate-my-environment-image1.png "Diagramme illustrant les trois composantes de la qualité, et comment la gestion des services recoupe les trois composantes. En mettant l'accent sur le réseau.")

## <a name="why-should-you-prepare-your-network"></a>Pourquoi devez-vous préparer votre réseau ?

Avant d’examiner les mesures à prendre, il est important de comprendre ce qui peut affecter les performances des équipes et, par conséquent satisfaction et bonheur de l’utilisateur. Trois zones principales risque peuvent affecter la façon dont les utilisateurs sachent qualité du réseau :

-   Bande passante disponible insuffisante

-   Bloqueurs de pare-feu et de proxy

-   Dégradations sur le réseau telles que déficiences et perte de paquets

Les étapes décrites ci-dessous vous aidera à déterminer que si votre déploiement peut-être être affecté par un de ces facteurs et aide à vous déplacez vers une solution. Pour préparer votre réseau défectueux entraînera probablement pas du tout satisfait aux utilisateurs et les correctifs d’ad hoc coûteuses. En préparation de votre réseau et votre organisation : pour les équipes, vous pouvez considérablement augmenter vos chances de réussite.

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>Planification de la bande passante

La première étape de préparation du réseau est de vous assurer que votre réseau dispose de suffisamment de bande passante disponible pour les modalités que équipes fournit aux utilisateurs. La planification de suffisamment de bande passante est une tâche relativement simple et un démarrage très faible-barrière pour s’assurer de vos utilisateurs auront une expérience d’équipes de haute qualité.

Vous démarrez votre planification voyage au pays pour les équipes sur le [site Web mon conseiller](https://myadvisor.fasttrack.microsoft.com/) en utilisant le Planificateur de réseau de bande passante. Le Planificateur de réseau fournit la bande passante par site planification des équipes et propose des recommandations pour optimiser les performances réseau.

> [!IMPORTANT]
> Si la bande passante requise n’est pas disponible, la pile de médias à l’intérieur des équipes diminue la qualité de la session audio/vidéo pour prendre en charge ce montant inférieur de la bande passante disponible, ce qui affecte la qualité de l’appel ou la réunion. Le client équipes tente de définir la priorité sur la qualité de la vidéo de la qualité audio. Par conséquent, il est très important de disposer de la bande passante attendue disponible.


|Activité  |Bande passante de téléchargement  |Bande passante de chargement  |Flux du trafic |
|---------|---------|---------|---------|
|**Appel audio P2P**     |0,1 Mbits/s         |0,1 Mbits/s        |Client <> Client         |
|**Appel vidéo P2P (plein écran)**     |4 Mbits/s         |4 Mbits/s         |Client <> Client          |
|**Partage de bureau de pair à pair (résolution 1920 x 1080)**     |4 Mbits/s         |4 Mbits/s         |Client <> Client          |
|**Réunion entre deux participants**     |4 Mbits/s         |4 Mbits/s         |Client <> Office 365         |
|**Réunion entre trois participants**     |8 Mbits/s         |6,5 Mbits/s         |Client <> Office 365           |
|**Réunion entre quatre participants**     |5,5 Mbits/s         |4 Mbits/s         |Client <> Office 365           |
|**Réunion entre cinq participants ou plus**     |6 Mbits/s         |1,5 Mbits/s         |Client <> Office 365           |

### <a name="local-internet-egress"></a>Sortie Internet locale

De nombreux réseaux ont été conçus pour utiliser un concentrateur de topologie en étoile. Dans cette topologie, le trafic internet parcourt généralement le réseau étendu à un centre de données central avant il ressort (egresses) à internet. Souvent, cette opération est effectuée pour centraliser les périphériques de sécurité réseau dans le but de réduire le coût global.

Back-tirer le trafic sur le réseau étendu à l’augmentation de la latence et a un impact négatif sur la qualité et l’expérience utilisateur. Microsoft Teams s’exécute sur le réseau global volumineux de Microsoft, il est souvent un emplacement homologation réseau proche de l’utilisateur. Un utilisateur sera probablement obtenir améliorer les performances en egressing dès que possible en dehors d’un point d’internet local a presque atteint leur emplacement et notre réseau optimisé pour la voix. Pour certaines charges de travail, les requêtes DNS sont utilisés pour envoyer le trafic vers le plus proche du serveur frontal. Dans ce cas, il est important que lorsque vous utilisez un point de sortie local, elle est associée à la résolution DNS locale.

Optimisation du chemin d’accès réseau réseau globale de Microsoft pour améliorer les performances et finalement fournir la meilleure expérience pour les utilisateurs. Pour plus d’informations, consultez le blog de [l’obtention de la connectivité et les performances dans Office 365 meilleures](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).


Pour obtenir une expérience optimale en utilisant des médias en temps réel dans Microsoft Teams, vous devez satisfaire la configuration réseau requise pour Office 365. Pour plus d’informations, consultez la rubique [Qualité des médias et performances de connectivité réseau dans Skype Entreprise Online](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).

Les deux segments réseau de définition (client vers Microsoft Edge et côté client vers Microsoft Edge) doivent respecter les conditions requises suivantes :


|**Valeur**  |**Client vers Microsoft Edge**  |**Côté client vers Microsoft Edge**  |
|---------|---------|---------|
|**Latence (unidirectionnelle)**     |< 50 ms          |< 30 ms          |
|**Latence (durée des boucles ou RTT)** |< 100 ms         |< 60 ms         |
|**Perte de paquets en rafale**    |< 10 % sur un intervalle de 200 ms         |< 1% sur un intervalle de 200 ms         |
|**Perte de paquets**     |< 1% sur un intervalle de 15 sec          |< 0,1% sur un intervalle de 15 sec         |
|**Instabilité entre les arrivées de paquets**    |< 30 ms sur un intervalle de 15 sec         |< 15 ms sur un intervalle de 15 sec         |
|**Réorganisation des paquets**    |< 0,05 % paquets désorganisés         |< 0,01% paquets désorganisés         |

Pour tester les deux segments réseau, vous pouvez utiliser l’[Outil d'évaluation du réseau](https://go.microsoft.com/fwlink/?linkid=855799). Cet outil peut être déployé sur le PC client directement et sur un PC connecté au périphérique réseau client. Il inclut une documentation restreinte, mais une documentation plus approfondie concernant l’utilisation de l’outil est disponible ici : [Évaluation de la préparation du réseau](https://go.microsoft.com/fwlink/?linkid=855800). En exécutant cet outil d’évaluation de la préparation du réseau, vous pouvez valider la préparation de votre réseau à exécuter des applications multimédias en temps réel telles que Microsoft Teams.

> [!NOTE]
> Il s'agit de la même évaluation de la préparation du réseau que celle que nous recommandons pour les clients qui souhaitent déployer Skype Entreprise avec succès.


### <a name="vpn"></a>VPN

Réseaux privés virtuels fournissent un service précieux à de nombreuses organisations. Malheureusement, ils sont généralement pas conçus ou configurés pour prendre en charge les médias en temps réel. Certains réseaux privés virtuels peuvent également pas en charge UDP. Réseaux privés virtuels introduisent également un niveau supplémentaire de chiffrement par-dessus le trafic multimédia qui est déjà chiffré. En outre, la connectivité au service équipes est peut-être pas efficace en raison de l’épinglage de cheveux le trafic via un périphérique VPN. En outre, ils ne sont pas nécessairement conçus à partir d’un point de vue de la capacité à prendre en charge les charges anticipées nécessiteront des équipes.

Il est recommandé de fournir un chemin d’accès de substitution contournant le réseau VPN pour le trafic des équipes. Cela est généralement appelé *split-tunnel VPN*. Fractionner tunnel signifie que le trafic pour Office 365 ne traversent le réseau VPN, mais est dirigés directement vers Office 365. Cette modification aura un impact positif sur la qualité, mais également offre l’avantage secondaire permettant de réduire la charge de périphériques VPN et le réseau de l’organisation.

Pour mettre en œuvre un tunnel segmenté, consultez votre fournisseur VPN pour les détails de configuration.

### <a name="wi-fi"></a>Wi-Fi

Comme VPN, les réseaux Wi-Fi ne sont pas nécessairement conçus ou configurés pour prendre en charge les médias en temps réel. Planification d’ou optimisation, un réseau Wi-Fi pour prendre en charge des équipes est une considération importante pour un déploiement de haute qualité.

Plusieurs facteurs entrent en jeu pour optimiser un réseau Wi-Fi :

-   Mettre en œuvre la QoS ou le Wi-Fi Multimedia (WMM) pour s'assurer que le trafic média est priorisé en conséquence sur les réseaux Wi-Fi.

-   Planification et optimisation les bandes Wi-Fi et access point de positionnement. 2,4 GHz peut fournir une expérience adéquate en fonction de l’emplacement du point d’accès, mais les points d’accès sont souvent concernées par d’autres appareils qui fonctionnent dans cette plage. La plage de 5 GHz est mieux adaptée aux médias en temps réel en raison de leur plage haute densité mais requiert plusieurs points d’accès pour obtenir la couverture suffisante. Points de terminaison doivent également prendre en charge cette plage et être configurés pour tirer parti de ces bandes en conséquence.

-   Si les réseaux Wi-Fi double bande sont déployés, envisagez d’implémenter la direction de la bande. _Bande de direction_ est utilisée par les fournisseurs Wi-Fi pour influencer le double bande aux clients d’utiliser la plage 5 GHz technique.

-   Lorsque les points d’accès du même canal sont trop proches, ils peuvent entraîner la superposition du signal et concurrence involontairement, ce qui entraîne une mauvaise expérience de l’utilisateur. Assurez-vous que les points d’accès qui sont en regard de chacun des autres sont sur les canaux qui ne se chevauchent pas.

Chaque fournisseur sans fil possède son propre recommandations pour le déploiement de sa solution sans fil. Nous vous conseillons de consulter votre fournisseur pour obtenir des instructions spécifiques.

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>Conditions requises pour le pare-feu et le proxy

Microsoft Teams se connecte à Microsoft Online Services et a besoin de la connectivité internet pour ce. Pour les équipes de fonctionner correctement, vous devez ouvrir les ports TCP 80 et 443 à partir des clients à internet et les ports UDP 3478 3481 à partir des clients à internet par le biais de. Les ports TCP sont utilisés pour se connecter au contenu web tels que SharePoint Online, Exchange Online et les services de conversation des équipes. Plug-ins et aux connecteurs de se connectent sur ces ports TCP. Les quatre ports UDP sont utilisés pour les médias audio et vidéo, pour s’assurer qu’ils arrivent correctement.

L’ouverture de ces ports est essentielle pour un déploiement équipes fiable. Blocage de ces ports est pris en charge et a une incidence sur la qualité des médias.

Si votre organisation requiert que vous spécifiez les plages d’adresses IP et les domaines auxquels ces ports doivent être ouverts exacte, vous pouvez restreindre les plages d’adresses IP cible et les domaines de ces ports. Pour obtenir la liste des ports exactes, des protocoles et des plages d’adresses IP, voir [Office 365 URL et plages d’adresses IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). Si vous choisissez de limiter les plages d’adresses IP cible et les domaines, vous devez vous assurer que vous la liste des ports et des plages de mise à jour, car ils peuvent varier. Vous pouvez vous abonner à [ce flux RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) à mettre à jour lorsque des modifications se produisent. Il est également recommandé de vérifier si tous les ports sont ouverts en exécutant la [Skype pour l’outil d’évaluation réseau Business](https://www.microsoft.com/download/details.aspx?id=53885) régulièrement. Vous trouverez plus d’informations sur les fonctionnalités de cet outil dans la section suivante.

En cas d’un serveur proxy en cours de déploiement, nous vous recommandons d’ignorer le serveur proxy pour tous les services d’équipes. À l’aide d’un proxy risque de ne pas fonctionner, mais il est très probable que la qualité sera réduite en raison du média contraints d’utiliser TCP au lieu de UDP. Pour plus d’informations sur les serveurs proxy et de contournement, voir [Office 365 URL et plages d’adresses IP](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges).

<!--ENDOFSECTION-->

## <a name="additional-network-considerations"></a>Remarques supplémentaires relatives au réseau
### <a name="external-name-resolution"></a>Résolution des noms externes

Assurez-vous que tous les ordinateurs client exécutant Teams peuvent résoudre les requêtes DNS externes pour détecter les services fournis par Office 365.

### <a name="nat-pool-size"></a>Taille du pool NAT

Lorsque plusieurs utilisateurs/périphériques accèdent à Office 365 à l'aide de la traduction d'adresses réseau (NAT) ou de la traduction d'adresses de port (PAT), vous devez vous assurer que les périphériques placés derrière chaque adresse IP publiquement routable n'excèdent pas le nombre pris en charge.

Pour atténuer ce risque, assurez-vous adéquate des adresses IP publiques sont affectés aux pools de NAT pour éviter l’épuisement du port. Si les ports sont insuffisants, les utilisateurs finaux internes et les périphériques rencontreront des problèmes lorsqu'ils se connecteront aux services Office 365. Pour plus d’informations, consultez la rubrique [Prise en charge NAT avec Office 365](https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365).

### <a name="intrusion-detection-and-prevention-guidance"></a>Instructions pour la détection et la prévention d'intrusion

Si votre environnement comporte un système de détection des intrusions et/ou un système de prévention des intrusions déployé pour une couche supplémentaire de sécurité pour les connexions sortantes, assurez-vous que tout le trafic ayant des URL Office 365 comme destination est placé sur liste blanche.

## <a name="test-the-network"></a>Tester le réseau

Une fois que vous avez terminé la préparation de votre réseau et de planification —, y compris la mise à niveau de la bande passante et ouverture de ports dans le pare-feu, vous devez tester les performances de votre réseau. Les résultats de ce test sera peindre éclaircit l’image de l’optimisation du réseau ou de correction requis pour la réussite de votre implémentation d’équipes.

Vous pouvez télécharger le [Skype pour l’outil d’évaluation réseau métiers](https://www.microsoft.com/download/details.aspx?id=53885) pour vérifier que votre réseau est prêt pour les équipes. L’outil offre deux fonctionnalités : elle permet de tester si tous les ports appropriés ont été ouverts, et il peut tester pour troubles du réseau.

Une fois que vous téléchargez et installez l’outil, vous pouvez les trouver dans c :\\Program Files\\Microsoft Skype pour l’outil d’évaluation réseau Business. Un guide détaillé pour l’utilisation de l’outil, Usage.docx, est inclus dans ce répertoire.

### <a name="test-for-opened-ports"></a>Tester les ports ouverts

Ouvrez une fenêtre d’invite de commandes et accédez au répertoire outil d’évaluation réseau en entrant **cd C:\\Program Files\\Microsoft Skype pour l’outil d’évaluation réseau Business**. À l’invite de commandes, démarrez le test pour les ports ouverts en entrant **networkassessmenttool.exe /connectivitycheck**

Après avoir exécuté les contrôles, l’outil s’affiche le message « Vérifications est terminée avec succès » ou créer des rapports sur les ports qui ont été bloqués. Il génère également un fichier nommé Connectivity_results.txt, qui contient la sortie de l’outil et le stocke dans le répertoire % userprofile\\appdata\\local\\Skype de microsoft pour l’outil d’évaluation réseau business\\ directory.

Nous vous recommandons d’exécuter régulièrement les contrôles de connectivité pour vous assurer que les ports ont été ouverts et fonctionnent correctement.

### <a name="test-for-network-impairments"></a>Tester les déficiences du réseau

Pour augmenter la satisfaction des utilisateurs, vous devez limiter les troubles sur votre réseau. Les troubles réseau les plus courants sont le délai (latence), la perte de paquets et gigue :

-   **Latence :** Il s’agit du temps que nécessaire pour obtenir un paquet IP à partir d’un point à point B sur le réseau. Ce délai de propagation de réseau est essentiellement lié à distance physique entre les deux points et la vitesse de la lumière, y compris une surcharge supplémentaire prise par les routeurs différents entre les deux. Latence correspond à sens unique ou aller-retour de temps.

-   **Perte de paquets**: il s’agit souvent un pourcentage des paquets sont perdus dans une fenêtre de temps donnée. Perte de paquets affecte directement la qualité audio, à partir de petite, individuel paquets perdus n’ayant presque aucun impact sur les pertes en rafale DOS à DOS que la fonctionnalité audio cause découper complètement.

-   **Gigue arrivée entre les paquets ou simplement gigue :** Il s’agit de la variation moyenne de retard entre les paquets successives. Plus modernes logiciels de VoIP, notamment Skype pour les entreprises, peut s’adapter aux certains niveaux de gigue par le biais de mise en mémoire tampon. Il est uniquement lorsque la gigue dépasse la mise en mémoire tampon qu’un participant remarqueront les effets de gigue.

Les valeurs maximales de ces troubles sont décrits dans les [performances de connectivité réseau et de qualité multimédia](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance). Lors du test de ces troubles, nous faire la distinction entre deux segments distincts :

-   Le *segment edge* est le segment dans lequel se trouve votre routeur. Il s’agit du segment de réseau logique le plus proche connecté à internet à chacun de vos emplacements. Dans la plupart des cas, il s’agit du point de connexion du routeur, ou éventuellement un réseau de périmètre (également appelé *zone DMZ*, *zone démilitarisée*et *sous-réseau filtré*). Aucun trafic supplémentaire qui affecte des périphériques autres que le routeur ne doit avoir lieu entre ce segment et internet.

-   Le *segment de client* est le segment de réseau dans lequel résident vos clients.

Vous devez tester les deux segments à l’aide de l’outil d’évaluation réseau. Pour tester le segment, accédez au répertoire et entrez **networkassessmenttool.exe** à l’invite de commandes. Les résultats sont écrites dans un fichier nommé Results.tsv, et les comparer à la [Configuration requise](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) pour chaque segment.

Notez que les deux segments doivent remplir les conditions d’un déploiement de haute qualité. Nous vous recommandons d’exécuter l’outil plusieurs fois pour une heure directement pour obtenir une bonne indication des performances de votre réseau.

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>Correction du réseau

Si les résultats de la planification de la bande passante, du test des ports ou du test des conditions requises pour le réseau indiquent que votre réseau actuel doit être corrigé avant de déployer Teams, vous pouvez le faire de différentes manières : 

-   Si la bande passante est insuffisante, mettez à niveau les connexions afin que le trafic vers Office 365 puisse circuler sans entrave.

-   Si des ports sont bloqués, modifiez les règles de pare-feu et testez à nouveau les ports.

-   En cas de déficiences du réseau, effectuez toujours une analyse de cause première.

Qualité de service (QoS) peut être utilisé pour TROUBLES bataille par ordre de priorité et en séparant le trafic. Certaines organisations choisissent de déployer QoS pour résoudre les problèmes de bande passante ou limiter la quantité de trafic circulant. Cela n’améliorer la qualité et permettra de nouveaux problèmes. Une analyse des causes doit toujours être effectuée lorsque TROUBLES réseau dépassent la configuration requise. QoS peut être une solution. Pour plus d’informations, consultez [Qualité de Service dans les équipes Microsoft](qos-in-teams.md).

>[!NOTE]
>De nombreux réseaux évoluent au fil du temps en raison des mises à niveau, une expansion ou autres impératifs d’entreprise. Assurez-vous que vous disposez des processus opérationnels en place pour mettre à jour ces zones dans le cadre de votre planification de la gestion de service.


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Point de décision</td><td><ul><li>Qui sera chargé des évaluations du réseau nécessaires sur tous les segments du réseau et sites de l'organisation ?</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul><li>Vous pouvez effectuer une évaluation de réseau détaillé pour vous assurer de que votre réseau est prêt pour le déploiement de Microsoft Teams. Pour plus d’informations, voir [Évaluation de préparation de réseau](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness).</li><li>Effectuez une correction du réseau en fonction des résultats de l’évaluation de la préparation réseau pour chaque segment du réseau.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="key-takeaways"></a>Principaux points à retenir

Voici les principaux points à partir de ce guide. Il le faut :

-   Ouvrir les ports TCP 80 et 443 sortant des clients qui utiliseront Teams.

-   Ouvrir les ports TDP 3478 à 3481 sortant des clients qui utiliseront Teams.

-   Vérifier que vous disposez de suffisamment de bande passante pour déployer Teams en complétant le [Planificateur de réseau](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner).

-   Exécuter [l'outil d'évaluation du réseau](https://www.microsoft.com/download/details.aspx?id=53885) et vous assurer que vous respectez les conditions requises décrites dans la rubrique [Qualité des médias et performances de connectivité réseau](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) pour le segment de périphérie et le segment de client.
