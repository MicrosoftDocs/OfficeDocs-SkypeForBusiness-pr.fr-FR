---
title: Évaluer votre environnement pour les charges de travail vocales dans le cloud
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 06/11/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Utilisez des personnage et une analyse du réseau pour évaluer la disponibilité de votre organisation, ouvrir les ports TCP et UDP corrects, et effectuer des corrections réseau.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0fbbc32c1a22fb5a2144231964b8498291ca009d
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58730723"
---
# <a name="evaluate-my-environment"></a>Évaluer mon environnement

Cet article donne une vue d’ensemble des conditions requises pour évaluer correctement votre environnement actuel pour l’utilisation des services vocaux cloud. En évaluez votre environnement, vous identifiez les risques et les exigences qui auront une incidence sur votre déploiement vocal dans le cloud. En identifiant au préalable ces éléments, vous pouvez ajuster votre planification pour être réussi.

## <a name="introduction-to-evaluating-your-environment"></a>Introduction à l’évaluation de votre environnement

Pour obtenir les résultats de votre clé d’objectif (OKR), vous avez précédemment pris des décisions importantes en matière de service. L’étape suivante consiste à effectuer la découverte de l’environnement afin d’évaluer tous les aspects liés à votre infrastructure informatique et téléphonique, votre réseau et vos opérations pour confirmer que votre organisation est prête à implémenter la solution.

La détection de l’environnement doit inclure une évaluation de la préparation du réseau pour garantir que votre réseau puisse prendre en charge l’implémentation de l’audioconférence ou de la Système téléphonique avec les services de plan d’appel.

Vous identifiez les risques techniques dans le cadre d’une évaluation de l’environnement et de l’évaluation de la préparation pour l’adoption, et développez un plan d’atténuation pour chaque risque identifié.
Vous devez incorporer ces informations dans le registre des risques.

<!--ENDOFSECTION-->

## <a name="current-environment"></a>Environnement actuel

Dans le cadre de votre détection de l’environnement, incluez toutes les questions liées à l’informatique des utilisateurs finaux, telles qu’une évaluation de la préparation des PC et des appareils mobiles pour prendre en charge l’Audioconférence et la Système téléphonique avec les cas d’utilisation d’un plan d’appel pour les entreprises, des configurations matérielles aux configurations logicielles requises.

La découverte de l’environnement peut également découvrir si vous devez [transférer des numéros de téléphone à Microsoft.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)
Le fait de le savoir permettra à votre organisation d’ajuster en conséquence son plan de projet et de préparer les informations nécessaires au portage de numéro. Vous pouvez utiliser la découverte de l’environnement [pour Microsoft Teams de projet](environmental-discovery-for-microsoft-teams-rollout.md) pour effectuer la découverte de l’environnement.

<table>
<tr><td>Titre</td><td>Description</td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Points de décision</td><td><ul><li>Qui vous serez responsable de l’évaluation de l’environnement ?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Étapes suivantes</td><td><ul><li>Documenter les résultats de l’évaluation de l’environnement.</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="adoption-and-change-management-assessment-capabilities"></a>Fonctionnalités d’évaluation de l’adoption et de la gestion des changements

Le déploiement permet de placer une nouvelle technologie à portée de main d’un utilisateur, mais les résultats d’entreprise ne se réalisent qu’après que les utilisateurs adoptent véritablement cette solution comme leur propre solution. Pour garantir une adoption durable d’une nouvelle solution, vous devez concentrer vos efforts sur la préparation des utilisateurs et la gestion du changement. Pour obtenir des résultats optimaux, planifiez la préparation des utilisateurs comme flux de travail parallèle à vos activités de préparation technique et incorporez les activités suivantes :

-   **Profil d’organisation et d’utilisateur :** Analyse de l’évolution de l’organisation en plus de l’utilisation de l’analyse des cas et des personnage

-   **Préparation et préparation des ressources :** Création de ressources de sensibilisation, de formation et de support ciblées et à grande portée, notamment la messagerie de valeurs ciblées pour accélérer l’accès des utilisateurs

Utilisez les considérations suivantes pour évaluer la préparation de votre organisation en matière de gestion des changements utilisateur.

<table>
<tr><td>Titre</td><td>Description</td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Points de décision</td><td><ul><li>Avez-vous déjà réussi avec l’adoption des logiciels ou services par les utilisateurs ?</li><li>Pouvez-vous suivre l’utilisation insérez-vous ?</li><li>Avez-vous les ressources nécessaires pour concevoir et gérer une campagne d’adoption initiale et en cours &mdash; &mdash; (sensibilisation, formation et support) ?</li><li>Disposez-vous d’une équipe dédiée d’adoption ou de gestion des changements des utilisateurs, ou pouvez-vous investir dans ces ressources pour garantir des résultats d’entreprise ?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Étapes suivantes</td><td><ul><li>Si vous avez répondu oui à toutes les réponses ci-dessus, identifiez les parties prenantes concernées pour la gestion du changement d’utilisateur et commencez votre planification de &quot; &quot; disponibilité des utilisateurs.</li><li>Si vous avez répondu non à tout ou partie des questions &quot; ci-dessus, songez à faire participer des ressources externes pour contribuer à la gestion du changement et aux activités d’adoption pour &quot; votre organisation.</li></ol></td></tr>
</table>


<!--ENDOFSECTION-->

## <a name="network-readiness"></a>État de préparation du réseau

Teams utilise des technologies audio et vidéo (codecs) qui peuvent s’adapter à la plupart des conditions réseau et donc mieux les utiliser. Pour garantir des performances optimales et cohérentes, vous devez préparer votre réseau pour Teams.

![Diagramme décrivant les trois composants de la qualité.](media/evaluate-my-environment-image1.png "Diagramme décrivant les trois composants de la qualité et la manière dont la gestion des services chevauche les trois composants. Avec le focus sur le réseau.")

## <a name="key-takeaways"></a>Points de suite clés

Voici les principales recommandations de ces conseils. Il le faut:

-   Ouvrez les ports TCP 80 et 443 sortants des clients qui utiliseront Teams.

-   Ouvrez les ports UDP 3478 à 3481 sortants des clients qui utiliseront Teams.

-   Assurez-vous que vous avez suffisamment de bande passante pour déployer Teams.

-   Exécutez [l’outil d’évaluation](https://www.microsoft.com/download/details.aspx?id=53885) du réseau et assurez-vous de répondre aux exigences décrites dans la qualité des médias et les [performances](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) de connectivité réseau à partir du segment edge et du segment client.

## <a name="why-should-you-prepare-your-network"></a>Pourquoi devez-vous préparer votre réseau ?

Avant d’examiner les étapes à suivre, il est important de comprendre ce qui peut affecter les performances d’Teams et par conséquent le plaisir et la satisfaction de l’utilisateur.
Trois zones de risque majeures peuvent affecter la manière dont les utilisateurs perçoivent la qualité du réseau :

-   Bande passante insuffisante disponible

-   Bloqueurs de pare-feu et de proxy

-   Troubles du réseau tels que la gigue et la perte de paquets

Les étapes décrites ci-dessous vous permettent de déterminer si votre déploiement peut être affecté par l’un de ces facteurs et vous aide à atteindre une résolution.
L’échec de la préparation de votre réseau risque d’entraîner des utilisateurs non satisfaits et des correctifs ad hoc coûteux. En préparez votre réseau, et votre organisation, pour Teams, vous pouvez considérablement augmenter vos chances de succès.

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>Planification de la bande passante

La première étape vers la préparation du réseau consiste à s’assurer que votre réseau dispose de suffisamment de bande passante disponible pour les Teams qualité fourni aux utilisateurs. La planification d’une bande passante suffisante est une tâche relativement simple, qui constitue un début très faible pour s’assurer que vos utilisateurs ont une expérience d’Teams haute qualité.

### <a name="local-internet-egress"></a>Sortie Internet locale

De nombreux réseaux ont été conçus pour utiliser une topologie de hub et parlée. Dans cette topologie, le trafic Internet traverse généralement le WAN jusqu'à un centre de données central avant qu'il n'émerge (sorties) vers Internet. Souvent, cela est fait pour centraliser les dispositifs de sécurité du réseau dans le but de réduire les coûts globaux.

Relayer le trafic sur le WAN augmente la latence et a un impact négatif sur la qualité et l'expérience utilisateur. Étant Microsoft Teams sur le grand réseau global de Microsoft, un emplacement d’peering réseau est souvent proche de l’utilisateur. Un utilisateur obtiendra probablement de meilleures performances en sortant d'un point Internet local près de son emplacement et sur notre réseau à voix optimisée dès que possible. Pour certaines charges de travail, les requêtes DNS sont utilisées pour envoyer du trafic vers le serveur frontal le plus proche. Dans de tels cas, il est important que lorsque vous utilisez un point de sortie local, celui-ci soit associé à la résolution DNS locale.

L’optimisation du chemin réseau vers le réseau global de Microsoft améliore les performances et offre en fin de compte la meilleure expérience aux utilisateurs. Pour plus de détails, voir l'article du blog [Obtenir la meilleure connectivité et les meilleures performances dans Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

### <a name="vpn"></a>VPN

Les VPN fournissent un service de valeur à de nombreuses organisations. Malheureusement, ils ne sont généralement pas conçus ou configurés pour prendre en charge les médias en temps réel. Certains VPN peuvent également ne pas prendre en charge UDP. Les VPN offrent également une phase supplémentaire de chiffrement au-dessus du trafic multimédia déjà chiffré. De plus, la connectivité au service Teams peut ne pas être efficace en raison de l’épinglage de cheveux via un appareil VPN.
De plus, ils ne sont pas nécessairement conçus dans une perspective de capacité pour tenir compte des charges Teams à prévoir.

La recommandation est de fournir un chemin alternatif qui contourne le VPN pour le trafic de Teams. Ce réseau privé virtuel (VPN) est communément appelé *VPN avec tunnel fractionnel.* La tunnellation fractionnée signifie que le trafic pour Microsoft 365 ou Office 365 ne traversera pas le VPN, mais qu’il sera directement Microsoft 365 ou Office 365. Cette modification aura un impact positif sur la qualité, mais offre également l’avantage secondaire de réduire la charge provenant des appareils VPN et du réseau de l’organisation.

Pour mettre en œuvre un tunnel segmenté, consultez votre fournisseur VPN pour les détails de configuration.

### <a name="wi-fi"></a>Wi-Fi

Comme un réseau VPN, Wi-Fi réseaux privés ne sont pas nécessairement conçus ou configurés pour prendre en charge les médias en temps réel. La planification ou l’optimisation d’un réseau Wi-Fi de gestion des Teams constitue une considération importante pour un déploiement de haute qualité.

Plusieurs facteurs sont pris en compte pour optimiser un Wi-Fi réseau :

-   Mettre en œuvre la QoS ou le Wi-Fi Multimedia (WMM) pour s'assurer que le trafic média est priorisé en conséquence sur les réseaux Wi-Fi.

-   Planifiez et optimisez les bandes Wi-Fi et le placement des points d’accès. La gamme de 2,4 GHz peut fournir une expérience adéquate en fonction de l'emplacement des points d'accès, mais les points d'accès sont souvent affectés par d'autres appareils grand public qui fonctionnent dans cette gamme. La gamme de 5 GHz est mieux adaptée aux médias en temps réel en raison de leur portée dense, mais nécessite plus de points d'accès pour obtenir une couverture suffisante. Les points de terminaison doivent également prendre en charge cette plage et être configurés pour exploiter ces bandes en conséquence.

-   Si des réseaux à Wi-Fi bande double sont déployés, songez à implémenter la stratégie de bande. La politique de bande est une technique implémentée par les Wi-Fi en place pour influencer les clients à double bande pour utiliser la plage à 5 GHz.

-   Lorsque les points d’accès du même canal sont trop proches les uns des autres, ils peuvent entraîner un chevauchement du signal et une concurrence involontaire, ce qui peut entraîner une mauvaise expérience pour l’utilisateur. Veillez à ce que les points d'accès voisins se trouvent sur des canaux qui ne se superposent pas.

Chaque fournisseur de services sans fil a ses propres recommandations pour le déploiement de sa solution sans fil. Nous vous recommandons de consulter votre fournisseur pour obtenir des conseils spécifiques.

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>Pare-feu et proxy requis

Microsoft Teams se connecte à Microsoft Online Services et a besoin d’une connectivité Internet pour ce problème. Pour que Teams fonctionne correctement, vous devez ouvrir les ports TCP 80 et 443 des clients vers Internet, et les ports UDP 3478 à 3481 des clients vers Internet. Les ports TCP sont utilisés pour se connecter au contenu web, tel que SharePoint Online, Exchange Online et les services Teams Conversation.
Les plug-ins et les connecteurs se connectent également sur ces ports TCP. Les quatre ports UDP sont utilisés pour le média tel que l’audio et la vidéo, afin de s’assurer qu’ils s’écoulent correctement.

L’ouverture de ces ports est essentielle pour un déploiement Teams fiable. Le blocage de ces ports n’est pas pris en cas de support et a un effet sur la qualité des médias.

Si votre organisation exige que vous spécifiez les plages d’adresses IP et domaines exacts pour lesquels ces ports doivent être ouverts, vous pouvez limiter les plages d’adresses IP et domaines cibles pour ces ports. Pour obtenir la liste des ports, protocoles et plages d’adresses IP exacts, voir Microsoft 365 ou [Office 365 des plages d’adresses IP.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams)
Si vous choisissez de limiter les plages et domaines d’adresses IP cibles, vous devez vous assurer de maintenir la liste des ports et des plages à jour, car ils peuvent changer. Vous pouvez vous abonner [à ce flux RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) pour être mis à jour en cas de modification. Il est également pratique de tester si tous les ports sont ouverts en exécutant régulièrement l’outil d’évaluation [Skype Entreprise](https://www.microsoft.com/download/details.aspx?id=53885) du site. Pour plus d’informations sur les fonctionnalités de cet outil, voir la section suivante.

En cas de déploiement d’un serveur proxy, nous vous recommandons d’ignorer le serveur proxy pour tous Teams services. Bien que l’utilisation d’un proxy puisse fonctionner, il est très probable que la qualité sera réduite en raison d’un média forcé d’utiliser TCP au lieu du protocole UDP. Pour plus d’informations sur les serveurs proxy et la contournement, voir Microsoft 365 [ou Office 365 URL et plages d’adresses IP.](./office-365-urls-ip-address-ranges.md)

<!--ENDOFSECTION-->

## <a name="test-the-network"></a>Tester le réseau

Une fois que vous avez terminé votre planification et la préparation du réseau (mise à niveau de la bande passante et ouverture de ports dans le pare-feu), vous devez tester les performances de votre réseau. Les résultats de ces tests clairement images de l’optimisation ou des corrections réseau requises pour la réussite de votre audioconférence ou de votre Système téléphonique avec l’implémentation d’un plan d’appel.

Vous pouvez télécharger [l’outil Skype Entreprise d’évaluation](https://www.microsoft.com/download/details.aspx?id=53885) du réseau pour vérifier si votre réseau est prêt à Teams. L’outil offre deux fonctionnalités : il peut tester l’ouverture de tous les ports corrects et la possibilité de tester la déficience du réseau.

Après avoir téléchargé et installé l’outil, vous pouvez le trouver dans C : \\ Program Files Microsoft Skype Entreprise Network Assessment \\ Tool. Un guide détaillé sur l’utilisation de l’outil, Usage.docx' est inclus dans ce répertoire.

### <a name="test-for-opened-ports"></a>Test pour les ports ouverts

Ouvrez une fenêtre d’invite de commandes et accédez au répertoire de l’outil d’évaluation du réseau en entrant le cd C : Fichiers de programme **\\ Microsoft \\ Skype Entreprise’outil d’évaluation réseau.** À l’invite de commandes, démarrez le test des ports ouverts ennetworkassessmenttool.exe **/connectivitycheck**

Une fois les vérifications effectuées, l’outil affiche le message « Vérifications effectuées avec succès » ou un rapport sur les ports qui ont été bloqués.
Elle génère également un fichier nommé Connectivity_results.txt, qui contient la sortie de l’outil et le stocke dans le répertoire d’outils d’évaluation du réseau Microsoft skype Entreprise local %userprofile%. \\ \\ \\ \\

Nous vous recommandons d’exécuter régulièrement les vérifications de connectivité pour vous assurer que les ports ont été ouverts et fonctionnent correctement.

### <a name="test-for-network-impairments"></a>Tester les déficiences du réseau

Pour augmenter la satisfaction des utilisateurs, vous devez limiter les déficiences sur votre réseau.
Les troubles du réseau les plus fréquents sont le retard (latence), la perte de paquets et la gigue :

-   **Latence :** C’est le temps d’obtenir un paquet IP du point A au point B sur le réseau. Ce retard de propagation sur le réseau est essentiellement lié à la distance physique entre les deux points et la vitesse de la lumière, notamment à la surcharge des divers routeurs entre les deux.
    La latence se mesure en durée à sens inverse ou durée de l’aller-retour.

-   **Perte de paquets**: cette perte est souvent définie comme le pourcentage de paquets perdus dans une période donnée. La perte de paquets affecte directement la qualité audio, de petits paquets individuels perdus, pratiquement sans impact sur les pertes en rafale dos-à-dos qui entraînent une coupure complète de l’audio.

-   **Gigue entre les arrivées de paquets, ou simplement gigue :** Il s’agit de la variation moyenne de délai entre les paquets successifs. La plupart des logiciels de VoIP modernes, Skype Entreprise, peuvent s’adapter à certains niveaux de gigue grâce à la mise en mémoire tampon. C’est seulement lorsque la gigue est supérieure au tampon qu’un participant constatera une gigue.

Les valeurs maximales de ces troubles sont décrites dans la qualité des médias et les [performances de connectivité réseau.](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)
Lors du test de ces troubles, nous faisons la distinction entre deux segments distincts :

-   Le *segment de périphérie* est le segment dans lequel se trouve votre routeur. Il s’agit du segment de réseau logique le plus proche connecté à Internet à chacun de vos emplacements. Dans la plupart des cas, il s’agit du point de connexion du routeur, ou éventuellement d’un réseau de périmètre (également appelé *DMZ,* *zone demilitarisée* et sous-réseau *filtré).* Aucun autre trafic affectant d’autres appareils que le routeur ne doit se produire entre ce segment et Internet.

-   Le *segment client est* le segment réseau logique dans lequel résident vos clients.

Vous devez tester les deux segments à l’aide de l’outil d’évaluation du réseau. Pour tester le segment, accédez au répertoire et entrez **votre** networkassessmenttool.exeà l’invite de commandes. Les résultats sont écrits dans un fichier nommé Results.tsv, et vous pouvez les comparer aux exigences [pour](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) chaque segment.

Notez que les deux segments doivent répondre aux exigences requises pour un déploiement de haute qualité. Nous vous recommandons d’exécuter l’outil plusieurs fois de suite pendant une heure afin d’obtenir une bonne indication des performances de votre réseau.

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>Correction du réseau

Si les résultats de la planification de la bande passante, du test des ports ou du test de la exigences réseau montrent que votre réseau actuel nécessite une correction avant de déployer Teams, vous pouvez effectuer ceci de plusieurs façons :

-   Pour une bande passante insuffisante, vous pouvez mettre à niveau les connexions de sorte que le trafic vers Microsoft 365 ou Office 365 flux sans encombre.

-   Pour les ports bloqués, modifiez les règles de pare-feu et testez de nouveau les ports.

-   Pour les problèmes de réseau, effectuez toujours une analyse de la cause racine.

La qualité de service (QoS) peut être utilisée pour lutter contre les déficiences en hiérérisant et en séparant le trafic. Certaines organisations choisissent de déployer QoS pour contourner les problèmes de bande passante ou limiter la quantité de trafic qui s’écoule. Cela n’améliorera pas la qualité et entraînera de nouveaux problèmes. Une analyse de la cause racine doit toujours être effectuée lorsque les déficiences du réseau dépassent les exigences. La QoS peut être une solution.
Pour plus d’informations, [voir Qualité de service dans Microsoft Teams.](./qos-in-teams.md)

>[!NOTE]
>De nombreux réseaux évoluent au fil du temps en raison des mises à niveau, de l'expansion ou d'autres exigences commerciales. Assurez-vous d'avoir des processus opérationnels en place pour maintenir ces secteurs dans le cadre de la planification de la gestion des services.


<table>
<tr><td>Titre</td><td>Description</td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Points de décision</td><td><ul><li>Qui vous aurez la responsabilité d’effectuer les analyses réseau correctes sur tous les segments réseau et tous les emplacements de l’organisation ?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Étapes suivantes</td><td><ul><li>Vous pouvez effectuer une évaluation détaillée du réseau pour vous assurer que votre réseau est prêt pour Microsoft Teams déploiement.</li><li>Effectuez des corrections réseau basées sur les résultats de l’analyse pour chaque segment réseau.</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->