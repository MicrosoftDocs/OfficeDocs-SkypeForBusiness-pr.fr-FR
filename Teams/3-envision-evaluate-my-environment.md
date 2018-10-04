---
title: Évaluer l’environnement pour des charges de travail voix Teams Microsoft cloud
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Utilisez personnages et analyse réseau à évaluer la préparation de votre organisation, ouvrir les ports TCP et UDP corrects, effectuer la mise à jour n’importe quel réseau.
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: a00bf784b283f1f2d948e82d90ce54b0a67a6439
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373313"
---
# <a name="evaluate-my-environment"></a>Évaluer mon environnement

Cet article donne une vue d’ensemble de la configuration requise pour correctement évaluer votre environnement actuel à l’aide de services de téléphonie sur le nuage. En évaluant votre environnement, vous identifiez les risques et les exigences qui influencent votre déploiement de voix globale dans le nuage. En identifiant ces éléments au préalable, vous pouvez ajuster votre planification pour la réussite du lecteur.

## <a name="introduction-to-evaluating-your-environment"></a>Introduction à l’évaluation de votre environnement 

Pour obtenir vos résultats principaux objectifs (OKRs), vous avez apportées précédemment décisions clés du service. L’étape suivante consiste à effectuer la recherche de l’environnement pour évaluer tous les aspects liés à votre service informatique et l’infrastructure de téléphonie, mise en réseau et opérations pour vérifier que votre organisation est prête pour implémenter la solution.

Découverte de l’environnement doit inclure l’évaluation de préparation de réseau pour vous assurer de que votre réseau peut prendre en charge l’implémentation de la conférence ou un système téléphonique avec services de planification de l’appel.

Vous identifiez les risques techniques dans le cadre d’une évaluation de l’environnement et l’évaluation de préparation d’adoption et développez un plan d’atténuation pour chaque risque identifié.
Vous devez incorporer ces informations dans le Registre de l’analyse de risque.

<!--ENDOFSECTION-->

## <a name="current-environment"></a>Environnement actuel

Dans le cadre de la découverte de votre environnement, inclure toutes les questions liées à l’informatique pour l’utilisateur final, tels que des ordinateurs et des périphériques mobiles pour prendre en charge la conférence Audio et le système téléphonique avec l’appel de planifier les exemples d’utilisation, à partir de la configuration matérielle requise pour une évaluation de préparation configuration logicielle requise.

Découverte de l’environnement peut révéler également si vous devez [transférer les numéros de téléphone à Microsoft](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365).
Sachant cela aideront votre organisation ajuster son plan de projet en conséquence et préparer les informations nécessaires au numéro portage. Vous pouvez utiliser la [détection de l’environnement pour le déploiement des équipes Microsoft](environmental-discovery-for-microsoft-teams-rollout.md) de MyAdvisor pour effectuer la recherche de l’environnement.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Qui sera responsable de l’évaluation de l’environnement ?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Les résultats de l’évaluation de l’environnement du document.</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="adoption-and-change-management-assessment-capabilities"></a>Fonctionnalités d’évaluation gestion d’adoption et de modification 

Déploiement sur une nouvelle technologie place à portée de main d’un utilisateur, mais les résultats commerciaux sont réalisées uniquement une fois que les utilisateurs adoptent réellement cette solution en tant que leurs propres. Pour garantir la bonne d’adoption d’une nouvelle solution, vous devez consacrer vos efforts de préparation des utilisateurs et de gestion du changement. Pour des résultats optimaux, effectuer la préparation des utilisateurs en tant qu’un flux de travail en parallèle à vos activités de préparation des techniques de planification et intégrer les activités suivantes :

-   **D’organisation et la gestion des profils utilisateur :** Analyse des receptiveness d’organisation à modifier en plus des cas et personnage analyse

-   **La préparation de la préparation et de ressources :** Création de sensibilisation ciblée et large portée, des formations et des ressources de support, y compris axés sur la valeur pour accélérer l’achat de l’utilisateur de messagerie

Utilisez les considérations suivantes pour évaluer la préparation de votre organisation à la gestion de modification adresse utilisateur.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Avez-vous eu succès précédent avec l’adoption par les utilisateurs de logiciels ou services ?</li><li>Vous pouvez suivre pour comprendre l’utilisation ?</li><li>Avez-vous besoin de ressources pour concevoir et gérer un initial&mdash;et&mdash;campagne d’adoption (sensibilisation, des formations et prise en charge) ?</li><li>Disposez-vous d’une équipe de gestion d’adoption/Modifier utilisateur dédié, ou si vous pouvez investir dans ces ressources afin de garantir des résultats commerciaux ?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Si vous avez répondu &quot;Oui&quot; à tous les éléments ci-dessus, identifier les parties prenantes gestion utilisateur change et commencer votre planification de la disponibilité utilisateur.</li><li>Si vous avez répondu &quot;aucun&quot; à tout ou partie des éléments ci-dessus, tenez compte des agréable à l’extérieur des ressources pour vous aider à conduite des activités d’adoption pour votre organisation et la gestion des modifications.</li></ol></td></tr>
</table>


<!--ENDOFSECTION-->

## <a name="network-readiness"></a>Préparation du réseau

Équipes utilise audio et vidéo technologie (codecs) qui peut s’adapter aux — et par conséquent exécuter mieux sous — plus les conditions de réseau. Pour garantir des performances optimales et cohérentes, vous devez préparer votre réseau pour les équipes.

![Diagramme décrivant les trois composants de qualité et de la gestion des services chevauche les trois composants. En mettant l’accent sur le réseau.] (media/evaluate-my-environment-image1.png "Diagramme décrivant les trois composants de qualité et de la gestion des services chevauche les trois composants. En mettant l’accent sur le réseau.")

## <a name="key-takeaways"></a>Points clés

Voici les principaux points à partir de ce guide. Il le faut :

-   Ouvrir les ports TCP 80 et 443 sortant de clients qui utiliseront les équipes.

-   Ouvrir les ports UDP 3478 via 3481 sortants à partir de clients qui utiliseront les équipes.

-   Assurez-vous que vous disposez de suffisamment de bande passante pour le déploiement d’équipes en effectuant le [Planificateur de réseau](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner).

-   Exécutez l' [Outil d’évaluation de réseau](https://www.microsoft.com/download/details.aspx?id=53885) et vérifiez que vous respectez les exigences décrites dans les [performances de connectivité réseau et de qualité multimédia](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) à partir du segment edge et le segment client.

## <a name="why-should-you-prepare-your-network"></a>Pourquoi vous devez préparer votre réseau ?

Avant d’examiner les mesures à prendre, il est important de comprendre ce qui peut affecter les performances des équipes et, par conséquent satisfaction et bonheur de l’utilisateur.
Trois zones principales risque peuvent affecter la façon dont les utilisateurs sachent qualité du réseau :

-   La bande passante disponible

-   Bloqueurs de pare-feu et proxy

-   TROUBLES réseau telles que la perte de gigue et de paquets

Les étapes décrites ci-dessous vous aidera à déterminer que si votre déploiement peut-être être affecté par un de ces facteurs et aide à vous déplacez vers une solution.
Pour préparer votre réseau défectueux entraînera probablement pas du tout satisfait aux utilisateurs et les correctifs d’ad hoc coûteuses. En préparation de votre réseau et votre organisation : pour les équipes, vous pouvez considérablement augmenter vos chances de réussite.

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>Planification de la bande passante

La première étape de préparation du réseau est de vous assurer que votre réseau dispose de suffisamment de bande passante disponible pour les modalités que équipes fournit aux utilisateurs. La planification de suffisamment de bande passante est une tâche relativement simple et un démarrage très faible-barrière pour vérifier vos utilisateurs auront une expérience d’équipes de haute qualité.

Vous démarrez votre planification voyage au pays pour les équipes sur le [site Web mon conseiller](https://myadvisor.fasttrack.microsoft.com/) en utilisant le Planificateur de réseau de bande passante. Le Planificateur de réseau fournit la bande passante par site planification des équipes et propose des recommandations pour optimiser les performances réseau.

### <a name="local-internet-egress"></a>Local sortant internet

De nombreux réseaux ont été conçus pour utiliser un concentrateur de topologie en étoile. Dans cette topologie, le trafic internet parcourt généralement le réseau étendu à un centre de données central avant il ressort (egresses) à internet. Souvent, cette opération est effectuée pour centraliser les périphériques de sécurité réseau dans le but de réduire le coût global.

Back-tirer le trafic sur le réseau étendu à l’augmentation de la latence et a un impact négatif sur la qualité et l’expérience utilisateur. Microsoft Teams s’exécute sur le réseau global volumineux de Microsoft, il est souvent un emplacement homologation réseau proche de l’utilisateur. Un utilisateur sera probablement obtenir améliorer les performances en egressing dès que possible en dehors d’un point d’internet local a presque atteint leur emplacement et notre réseau optimisé pour la voix. Pour certaines charges de travail, les requêtes DNS sont utilisés pour envoyer le trafic vers le plus proche du serveur frontal. Dans ce cas, il est important que lorsque vous utilisez un point de sortie local, elle est associée à la résolution DNS locale.

Optimisation du chemin d’accès réseau réseau globale de Microsoft pour améliorer les performances et finalement fournir la meilleure expérience pour les utilisateurs. Pour plus d’informations, consultez le blog de [l’obtention de la connectivité et les performances dans Office 365 meilleures](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

### <a name="vpn"></a>VPN

Réseaux privés virtuels fournissent un service précieux à de nombreuses organisations. Malheureusement, ils sont généralement pas conçus ou configurés pour prendre en charge les médias en temps réel. Certains réseaux privés virtuels peuvent également pas en charge UDP. Réseaux privés virtuels introduisent également un niveau supplémentaire de chiffrement par-dessus le trafic multimédia qui est déjà chiffré. En outre, la connectivité au service équipes est peut-être pas efficace en raison de l’épinglage de cheveux le trafic via un périphérique VPN.
En outre, ils ne sont pas nécessairement conçus à partir d’un point de vue de la capacité à prendre en charge les charges anticipées nécessiteront des équipes.

Il est recommandé de fournir un chemin d’accès de substitution contournant le réseau VPN pour le trafic des équipes. Cela est généralement appelé *split-tunnel VPN*. Fractionner tunnel signifie que le trafic pour Office 365 ne traversent le réseau VPN, mais est dirigés directement vers Office 365. Cette modification aura un impact positif sur la qualité, mais également offre l’avantage secondaire permettant de réduire la charge de périphériques VPN et le réseau de l’organisation.

Pour implémenter un tunnel de fractionnement, consultez votre fournisseur de réseau privé virtuel pour les détails de configuration.

### <a name="wi-fi"></a>Wi-Fi

Comme VPN, les réseaux Wi-Fi ne sont pas nécessairement conçus ou configurés pour prendre en charge les médias en temps réel. Planification d’ou optimisation, un réseau Wi-Fi pour prendre en charge des équipes est une considération importante pour un déploiement de haute qualité.

Il existe plusieurs facteurs qui entrent en jeu pour l’optimisation d’un réseau Wi-Fi :

-   L’implémentation de QoS ou Wi-Fi multimédia (WMM) pour vous assurer que le trafic multimédia est prise hiérarchisée en conséquence sur les réseaux Wi-Fi.

-   Planification et optimisation les bandes Wi-Fi et access point de positionnement. 2,4 GHz peut fournir une expérience adéquate en fonction de l’emplacement du point d’accès, mais les points d’accès sont souvent concernées par d’autres appareils qui fonctionnent dans cette plage. La plage de 5 GHz est mieux adaptée aux médias en temps réel en raison de leur plage haute densité mais requiert plusieurs points d’accès pour obtenir la couverture suffisante. Points de terminaison doivent également prendre en charge cette plage et être configurés pour tirer parti de ces bandes en conséquence.

-   Si les réseaux Wi-Fi double bande sont déployés, envisagez d’implémenter la direction de la bande. Bande de direction est utilisée par les fournisseurs Wi-Fi pour influencer le double bande aux clients d’utiliser la plage 5 GHz technique.

-   Lorsque les points d’accès du même canal sont trop proches, ils peuvent entraîner la superposition du signal et concurrence involontairement, ce qui entraîne une mauvaise expérience de l’utilisateur. Assurez-vous que les points d’accès qui sont en regard de chacun des autres sont sur les canaux qui ne se chevauchent pas.

Chaque fournisseur sans fil possède son propre recommandations pour le déploiement de sa solution sans fil. Nous vous conseillons de consulter votre fournisseur pour obtenir des instructions spécifiques.

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>Configuration requise du pare-feu et proxy

Microsoft Teams se connecte à Microsoft Online Services et a besoin de la connectivité internet pour ce. Pour les équipes de fonctionner correctement, vous devez ouvrir les ports TCP 80 et 443 à partir des clients à internet et les ports UDP 3478 3481 à partir des clients à internet par le biais de. Les ports TCP sont utilisés pour se connecter au contenu web tels que SharePoint Online, Exchange Online et les services de conversation des équipes.
Plug-ins et aux connecteurs de se connectent sur ces ports TCP. Les quatre ports UDP sont utilisés pour les médias audio et vidéo, pour s’assurer qu’ils arrivent correctement.

L’ouverture de ces ports est essentielle pour un déploiement équipes fiable. Blocage de ces ports est pris en charge et aura une incidence sur la qualité des médias.

Si votre organisation requiert que vous spécifiez les plages d’adresses IP et les domaines auxquels ces ports doivent être ouverts exacte, vous pouvez restreindre les plages d’adresses IP cible et les domaines de ces ports. Pour obtenir la liste des ports exactes, des protocoles et des plages d’adresses IP, voir [Office 365 URL et plages d’adresses IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams).
Si vous choisissez de limiter les plages d’adresses IP cible et les domaines, vous devez vous assurer que vous la liste des ports et des plages de mise à jour, car ils peuvent varier. Vous pouvez vous abonner à [ce flux RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) à mettre à jour lorsque des modifications se produisent. Il est également recommandé de vérifier si tous les ports sont ouverts en exécutant la [Skype pour l’outil d’évaluation réseau Business](https://www.microsoft.com/download/details.aspx?id=53885) régulièrement. Vous trouverez plus d’informations sur les fonctionnalités de cet outil dans la section suivante.

En cas d’un serveur proxy en cours de déploiement, nous vous recommandons d’ignorer le serveur proxy pour tous les services d’équipes. À l’aide d’un proxy risque de ne pas fonctionner, mais il est très probable que la qualité sera réduite en raison du média contraints d’utiliser TCP au lieu de UDP. Pour plus d’informations sur les serveurs proxy et de contournement, voir [Office 365 URL et plages d’adresses IP](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges).

<!--ENDOFSECTION-->

## <a name="test-the-network"></a>Tester le réseau

Une fois que vous avez terminé la préparation de votre réseau et de planification —, y compris la mise à niveau de la bande passante et ouverture de ports dans le pare-feu, vous devez tester les performances de votre réseau. Les résultats de ce test sera peindre éclaircit l’image de l’optimisation du réseau ou de correction requis pour la réussite de votre système téléphonique ou de conférence Audio avec l’appel de planifier la mise en œuvre.

Vous pouvez télécharger le [Skype pour l’outil d’évaluation réseau métiers](https://www.microsoft.com/download/details.aspx?id=53885) pour vérifier que votre réseau est prêt pour les équipes. L’outil offre deux fonctionnalités : elle permet de tester si tous les ports appropriés ont été ouverts, et il peut tester pour troubles du réseau.

Une fois que vous téléchargez et installez l’outil, vous pouvez les trouver dans c :\\Program Files\\Microsoft Skype pour l’outil d’évaluation réseau Business. Un guide détaillé pour l’utilisation de l’outil, Usage.docx, est inclus dans ce répertoire.

### <a name="test-for-opened-ports"></a>Test des ports ouverts

Ouvrez une fenêtre d’invite de commandes et accédez au répertoire outil d’évaluation réseau en entrant **cd C:\\Program Files\\Microsoft Skype pour l’outil d’évaluation réseau Business**. À l’invite de commandes, démarrez le test pour les ports ouverts en entrant **networkassessmenttool.exe /connectivitycheck**

Après avoir exécuté les contrôles, l’outil s’affiche le message « Vérifications est terminée avec succès » ou créer des rapports sur les ports qui ont été bloqués.
Il génère également un fichier nommé Connectivity_results.txt, qui contient la sortie de l’outil et le stocke dans le répertoire % userprofile\\appdata\\local\\Skype de microsoft pour l’outil d’évaluation réseau business\\ directory.

Nous vous conseillons d’exécuter les vérifications de connectivité à intervalles réguliers pour garantir les ports ont été ouverts et fonctionnent correctement.

### <a name="test-for-network-impairments"></a>Test de troubles du réseau

Pour augmenter la satisfaction des utilisateurs, vous devez limiter les troubles sur votre réseau.
Les troubles réseau les plus courants sont le délai (latence), la perte de paquets et gigue :

-   **Latence :** Il s’agit du temps que nécessaire pour obtenir un paquet IP à partir d’un point à point B sur le réseau. Ce délai de propagation de réseau est essentiellement lié à distance physique entre les deux points et la vitesse de la lumière, y compris une surcharge supplémentaire prise par les routeurs différents entre les deux.
    Latence correspond à sens unique ou aller-retour de temps.

-   **Perte de paquets**: il s’agit souvent un pourcentage des paquets sont perdus dans une fenêtre de temps donnée. Perte de paquets affecte directement la qualité audio, à partir de petite, individuel paquets perdus n’ayant presque aucun impact sur les pertes en rafale DOS à DOS que la fonctionnalité audio cause découper complètement.

-   **Gigue arrivée entre les paquets ou simplement gigue :** Il s’agit de la variation moyenne de retard entre les paquets successives. Plus modernes logiciels de VoIP, notamment Skype pour les entreprises, peut s’adapter aux certains niveaux de gigue par le biais de mise en mémoire tampon. Il est uniquement lorsque la gigue dépasse la mise en mémoire tampon qu’un participant remarqueront les effets de gigue.

Les valeurs maximales de ces troubles sont décrits dans les [performances de connectivité réseau et de qualité multimédia](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).
Lors du test de ces troubles, nous faire la distinction entre deux segments distincts :

-   Le *segment edge* est le segment dans lequel se trouve votre routeur. Il s’agit du segment de réseau logique le plus proche connecté à internet à chacun de vos emplacements. Dans la plupart des cas, il s’agit du point de connexion du routeur, ou éventuellement un réseau de périmètre (également appelé *zone DMZ*, *zone démilitarisée*et *sous-réseau filtré*). Aucun trafic supplémentaire qui affecte des périphériques autres que le routeur ne doit avoir lieu entre ce segment et internet.

-   Le *segment client* est le segment de réseau logique dans laquelle résident vos clients.

Vous devez tester les deux segments à l’aide de l’outil d’évaluation réseau. Pour tester le segment, accédez au répertoire et entrez **networkassessmenttool.exe** à l’invite de commandes. Les résultats sont écrites dans un fichier nommé Results.tsv, et les comparer à la [Configuration requise](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) pour chaque segment.

Notez que les deux segments doivent remplir les conditions d’un déploiement de haute qualité. Nous vous recommandons d’exécuter l’outil plusieurs fois pour une heure directement pour obtenir une bonne indication des performances de votre réseau.

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>Correction de réseau

Si les résultats de la planification de la bande passante, les tests du port ou test de réseau requises montrent que votre réseau actuel doit correction avant de déployer les équipes, vous pouvez le faire de plusieurs façons :

-   Pour la bande passante, mise à niveau de connexions de sorte que le trafic vers Office 365 peut passer sans encombre.

-   Pour les ports bloqués, modifier des règles de pare-feu et testez à nouveau les ports.

-   Pour troubles du réseau, toujours effectuer une analyse de la cause.

Qualité de service (QoS) peut être utilisé pour TROUBLES bataille par ordre de priorité et en séparant le trafic. Certaines organisations choisissent de déployer QoS pour résoudre les problèmes de bande passante ou limiter la quantité de trafic circulant. Cela n’améliorer la qualité et permettra de nouveaux problèmes. Une analyse des causes doit toujours être effectuée lorsque TROUBLES réseau dépassent la configuration requise. QoS peut être une solution.
Pour plus d’informations, consultez [Qualité de Service dans les équipes Microsoft](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams).

>[!NOTE]
>De nombreux réseaux évoluent au fil du temps en raison des mises à niveau, une expansion ou autres impératifs d’entreprise. Assurez-vous que vous disposez des processus opérationnels en place pour mettre à jour ces zones dans le cadre de votre planification de la gestion de service.


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Qui sera responsable des évaluations réseau appropriés sur tous les segments de réseau et les emplacements de l’organisation ?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Vous pouvez effectuer une évaluation de réseau détaillé pour vous assurer de que votre réseau est prêt pour le déploiement de Microsoft Teams. Pour plus d’informations, voir <a href="https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness" data-raw-source="[Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness)">Évaluation de préparation de réseau</a>.</li><li>Effectuer la mise à jour du réseau en fonction des résultats de l’évaluation de la disponibilité du réseau pour chaque segment de réseau.</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->