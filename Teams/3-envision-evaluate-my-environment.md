---
title: Évaluer votre environnement pour les charges de travail des fonctionnalités vocales de Microsoft Teams dans le cloud
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 06/11/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Utiliser des personnages et une analyse réseau pour évaluer la disponibilité de votre organisation, ouvrir les ports TCP et UDP appropriés, effectuer une correction du réseau.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8ad3700b3b0186ba3e95d8f55ad704f37cf33bc7
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925075"
---
# <a name="evaluate-my-environment"></a>Évaluer mon environnement

Cet article fournit une vue d’ensemble des exigences relatives à l’évaluation correcte de votre environnement actuel pour l’utilisation des services vocaux Cloud. En évaluant votre environnement, vous identifiez les risques et les exigences qui influenceront votre déploiement global de voix sur le Cloud. En identifiant ces éléments à l’aide de la commande, vous pouvez ajuster la planification du succès.

## <a name="introduction-to-evaluating-your-environment"></a>Introduction à l’évaluation de votre environnement 

Pour obtenir les résultats de votre clé objective (OKRs), vous avez déjà effectué des décisions relatives aux services clés. L’étape suivante consiste à effectuer une recherche environnementale pour évaluer tous les aspects liés à votre infrastructure et à votre infrastructure de téléphonie et de téléphonie, afin de vérifier que votre organisation est prête à implémenter la solution.

La découverte environnementale doit inclure une évaluation de la compatibilité réseau pour s’assurer que votre réseau peut prendre en charge l’implémentation de l’audioconférence ou du système téléphonique avec les services de plan d’appel.

Vous identifiez les risques techniques dans le cadre d’une analyse environnementale et de l’évaluation de l’adoption, et vous développez un plan d’atténuation pour chaque risque identifié.
Vous devez incorporer ces informations dans le registre de risques.

<!--ENDOFSECTION-->

## <a name="current-environment"></a>Environnement actuel

Dans le cadre de votre découverte environnementale, incluez toutes les informations relatives à l’utilisation de l’utilisateur final, par exemple, l’évaluation de la compatibilité des PC et des appareils mobiles pour la prise en charge de l’audioconférence et du système téléphonique pour les appels de plan d’utilisation pour les entreprises. configuration logicielle requise.

La découverte environnementale peut également vous indiquer si vous avez besoin de [transférer des numéros de téléphone vers Microsoft](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).
Le fait de savoir que cela aidera votre organisation à ajuster son plan de projet en conséquence et à préparer les informations nécessaires au transfert de numéro. Vous pouvez utiliser la [découverte environnementale pour le lancement de Microsoft teams](environmental-discovery-for-microsoft-teams-rollout.md) pour effectuer une découverte environnementale.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Points de décision</td><td><ul><li>Qui sera chargé d’effectuer une évaluation de l’environnement ?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Étapes suivantes</td><td><ul><li>Documentez les résultats de l’évaluation de l’environnement.</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="adoption-and-change-management-assessment-capabilities"></a>Fonctionnalités d’évaluation et d’adoption de la gestion des modifications 

Le déploiement met une nouvelle technologie à la portée de l’utilisateur, mais les résultats commerciaux ne sont réalisés qu’après que les utilisateurs ont réellement adopté cette solution comme leurs siennes. Pour garantir une adoption soutenue d’une nouvelle solution, vous devez vous concentrer sur les efforts de préparation et de gestion des utilisateurs. Pour des résultats optimaux, procédez à la planification de la préparation des utilisateurs en tant que flux de flux parallèle à vos activités techniques de compatibilité et intégrez les activités suivantes :

-   **Profil de l’organisation et de l’utilisateur :** Analyse du receptiveness d’organisation à modifier en plus de l’analyse de cas d’utilisation et de personnages

-   **Préparation et préparation des ressources :** Création de ressources de sensibilisation, de formation et de support ciblées et à grande portée, y compris la messagerie de valeur prioritaire permettant d’accélérer l’achat des utilisateurs

Utilisez les considérations suivantes pour évaluer la préparation de votre organisation à la gestion des modifications de l’utilisateur.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Points de décision</td><td><ul><li>Avez-vous déjà réussi à avoir adopté des logiciels ou des services pour les utilisateurs ?</li><li>Est-il possible d’effectuer le suivi de l’utilisation ?</li><li>Avez-vous les ressources nécessaires pour concevoir et gérer une&mdash;campagne d'&mdash;adoption initiale et en cours (sensibilisation, formation et assistance) ?</li><li>Avez-vous une équipe dédiée de gestion des changements ou d’adoption d’utilisateurs, ou pouvez-vous investir dans ces ressources pour garantir les résultats de votre entreprise ?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Étapes suivantes</td><td><ul><li>Si vous &quot;répondez&quot; Oui à tous les éléments ci-dessus, identifiez les principales parties prenantes en matière de gestion du changement d’utilisateur et commencez votre planification de préparation des utilisateurs.</li><li>Si vous &quot;répondez&quot; non à tout ou partie des éléments ci-dessus, envisagez d’utiliser des ressources externes pour faciliter la gestion des modifications et les activités liées à l’adoption pour votre organisation.</li></ol></td></tr>
</table>


<!--ENDOFSECTION-->

## <a name="network-readiness"></a>Compatibilité réseau

Teams utilise une technologie audio et vidéo (codecs) pouvant s’adapter à la plupart des conditions de réseau. Pour garantir des performances optimales et cohérentes, vous devez préparer votre réseau pour Teams.

![Diagramme décrivant les trois composantes de la qualité](media/evaluate-my-environment-image1.png "Diagramme décrivant les trois composantes de la qualité et la façon dont la gestion de service empiète sur les trois composants. Avec le focus du réseau.")

## <a name="key-takeaways"></a>Points clés

Voici les principaux points à retenir dans ces instructions. Il le faut:

-   Ouvrez les ports TCP 80 et 443 sortants des clients qui utiliseront Teams.

-   Ouvrez les ports UDP 3478 à 3481 sortants des clients qui utiliseront Teams.

-   Vérifiez que vous disposez d’assez de bande passante pour déployer Teams.

-   Exécutez l' [outil d’évaluation du réseau](https://www.microsoft.com/download/details.aspx?id=53885) et assurez-vous de respecter les exigences décrites dans la section [qualité multimédia et performances de connectivité réseau](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) du segment du réseau et du segment client.

## <a name="why-should-you-prepare-your-network"></a>Pourquoi dois-je préparer votre réseau ?

Avant de passer en revue les étapes à suivre, il est important de comprendre ce qui peut affecter les performances des équipes et donc le bonheur et la satisfaction des utilisateurs.
Trois domaines principaux de risques peuvent influer sur la qualité du réseau :

-   Bande passante disponible insuffisante

-   Pare-feu et bloqueurs de proxy

-   Déficiences du réseau comme le scintillement et la perte de paquets

Les étapes décrites ci-dessous vous aideront à déterminer si votre déploiement sera affecté par l’un de ces facteurs et vous aideront à vous déplacer vers une résolution.
Le non-respect de votre réseau risque de provoquer des problèmes d’insatisfaction des utilisateurs et des correctifs ad hoc coûteux. En préparant votre réseau (et votre organisation) pour les équipes, vous pouvez augmenter considérablement votre chance de succès.

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>Planification de la bande passante

La première étape de préparation du réseau consiste à s’assurer que votre réseau dispose d’une bande passante suffisante pour permettre aux utilisateurs de se servir de la bande passante disponible. La planification d’une bande passante suffisante est une tâche relativement simple et un début de faible entrave pour s’assurer que vos utilisateurs disposent d’une qualité d’équipes de grande qualité.

### <a name="local-internet-egress"></a>Sortie Internet locale

De nombreux réseaux ont été conçus pour utiliser une topologie de hub et parlée. Dans cette topologie, le trafic Internet traverse généralement le WAN jusqu'à un centre de données central avant qu'il n'émerge (sorties) vers Internet. Souvent, cela est fait pour centraliser les dispositifs de sécurité du réseau dans le but de réduire les coûts globaux.

Relayer le trafic sur le WAN augmente la latence et a un impact négatif sur la qualité et l'expérience utilisateur. Comme Microsoft Teams fonctionne sur le vaste réseau mondial de Microsoft, il existe souvent un emplacement réseau de pairage à proximité de l'utilisateur. Un utilisateur obtiendra probablement de meilleures performances en sortant d'un point Internet local près de son emplacement et sur notre réseau à voix optimisée dès que possible. Pour certaines charges de travail, les requêtes DNS sont utilisées pour envoyer du trafic vers le serveur frontal le plus proche. Dans de tels cas, il est important que lors de l'utilisation d'un point d'évacuation local, il soit couplé avec la résolution DNS locale.

L'optimisation du chemin d'accès au réseau mondial de Microsoft améliorera les performances et, en fin de compte, offrira la meilleure expérience aux utilisateurs. Pour plus de détails, voir l'article du blog [Obtenir la meilleure connectivité et les meilleures performances dans Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

### <a name="vpn"></a>VPN

Les VPN fournissent un service de valeur à de nombreuses organisations. Malheureusement, il n’est généralement pas conçu ou configuré pour prendre en charge les contenus multimédias en temps réel. Certains VPN peuvent également ne pas prendre en charge UDP. Les réseaux privés virtuels introduisent également une couche supplémentaire de chiffrement au-dessus du trafic multimédia déjà crypté. Par ailleurs, la connectivité au service teams peut ne pas être efficace en raison du trafic d’épinglage par le biais d’un appareil VPN.
Par ailleurs, elles ne sont pas nécessairement conçues à partir d’un point de vue de la capacité pour s’adapter aux efforts prévus qui seront nécessaires aux équipes.

La recommandation est de fournir un chemin alternatif qui contourne le VPN pour le trafic de Teams. C’est communément connu sous le nom de *VPN de tunneling scindé*. Le tunneling fractionné signifie que le trafic destiné à Office 365 ne traverse pas le VPN, mais qu’il accède directement à Office 365. Ce changement aura un impact positif sur la qualité, mais aussi l'avantage secondaire de réduire la charge des dispositifs VPN et du réseau de l'organisation.

Pour mettre en œuvre un tunnel segmenté, consultez votre fournisseur VPN pour les détails de configuration.

### <a name="wi-fi"></a>Wi-Fi

Comme VPN, les réseaux Wi-Fi ne sont pas nécessairement conçus ou configurés pour prendre en charge les contenus multimédias en temps réel. La planification d’un réseau Wi-Fi pour la prise en charge des équipes est une considération importante pour un déploiement de grande qualité.

Il existe plusieurs facteurs qui entrent en jeu pour optimiser un réseau Wi-Fi :

-   Mettre en œuvre la QoS ou le Wi-Fi Multimedia (WMM) pour s'assurer que le trafic média est priorisé en conséquence sur les réseaux Wi-Fi.

-   Planification et optimisation des bandes Wi-Fi et du placement des points d’accès. La gamme de 2,4 GHz peut fournir une expérience adéquate en fonction de l'emplacement des points d'accès, mais les points d'accès sont souvent affectés par d'autres appareils grand public qui fonctionnent dans cette gamme. La gamme de 5 GHz est mieux adaptée aux médias en temps réel en raison de leur portée dense, mais nécessite plus de points d'accès pour obtenir une couverture suffisante. Les points de terminaison doivent également prendre en charge cette plage et être configurés pour exploiter ces bandes en conséquence.

-   Si les réseaux Wi-Fi bibande sont déployés, envisagez d’implémenter la direction de bandes. La direction de bandes est une technique mise en œuvre par les fournisseurs de réseaux Wi-Fi pour influencer les clients à double bande et utiliser la plage de 5 GHz.

-   Lorsque les points d’accès du même canal sont trop proches, ils peuvent provoquer le chevauchement du signal et la concurrence involontaire, ce qui engendre une mauvaise utilisation de l’utilisateur. Assurez-vous que les points d’accès adjacents s’exécutent sur des canaux qui ne se chevauchent pas.

Chaque fournisseur de services sans fil a ses propres recommandations pour le déploiement de sa solution sans fil. Nous vous recommandons de consulter votre fournisseur pour obtenir des conseils spécifiques.

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>Configuration requise pour le pare-feu et les proxys

Microsoft teams se connecte aux services en ligne de Microsoft et nécessite une connectivité Internet pour cela. Pour que teams fonctionne correctement, vous devez ouvrir les ports TCP 80 et 443 de clients vers Internet, ainsi que les ports UDP 3478 à 3481 des clients vers Internet. Les ports TCP sont utilisés pour se connecter à du contenu Web tel que SharePoint Online, Exchange Online et les services de chat d’équipe.
Les plug-ins et connecteurs se connectent également via ces ports TCP. Les quatre ports UDP sont utilisés pour les contenus multimédias tels que les fichiers audio et vidéo, afin de s’assurer que le flux fonctionne correctement.

L’ouverture de ces ports est essentielle pour un déploiement d’équipes fiable. Le blocage de ces ports n’est pas pris en charge et aura un impact sur la qualité multimédia.

Si votre organisation nécessite que vous spécifiiez les plages d’adresses IP et les domaines exacts auxquels ces ports doivent être ouverts, vous pouvez limiter les plages d’adresses IP cibles et les domaines pour ces ports. Pour obtenir la liste des ports, protocoles et plages d’adresses IP exacts, voir [URL et plages d’adresses IP Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams).
Si vous choisissez de limiter les plages d’adresses IP et les domaines cibles, vous devez veiller à ce que la liste des ports et des plages soit à jour, car elles peuvent changer. Vous pouvez vous abonner à [ce flux RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) pour être mis à jour lorsque des modifications se produisent. Il est également recommandé de tester si tous les ports sont ouverts en exécutant l' [outil d’évaluation du réseau Skype entreprise](https://www.microsoft.com/download/details.aspx?id=53885) régulièrement. Vous pouvez en savoir plus sur les fonctionnalités de cet outil dans la section suivante.

Dans le cas d’un serveur proxy déployé, nous vous recommandons de ne pas utiliser le serveur proxy pour tous les services Teams. Bien que l’utilisation d’un proxy puisse fonctionner, il est très probable que la qualité soit réduite en raison de l’utilisation forcée du protocole TCP au lieu du protocole UDP. Pour plus d’informations sur les serveurs proxy et la contournement, voir [URL et plages d’adresses IP Office 365](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges).

<!--ENDOFSECTION-->

## <a name="test-the-network"></a>Test du réseau

Une fois que vous avez terminé votre planification et préparation du réseau, y compris la mise à niveau de la bande passante et l’ouverture des ports dans le pare-feu, vous devez tester les performances de votre réseau. Les résultats de ces tests peignent une image plus claire de l’optimisation du réseau ou de la correction requise pour le succès de votre audioconférence ou de votre système téléphonique avec l’implémentation d’un plan d’appels.

Vous pouvez télécharger l' [outil d’évaluation du réseau Skype entreprise](https://www.microsoft.com/download/details.aspx?id=53885) pour tester si votre réseau est prêt pour les équipes. L’outil offre une double fonctionnalité : il peut tester si tous les ports corrects ont été ouverts et tester les problèmes de réseau.

Une fois que vous avez téléchargé et installé l’outil, vous pouvez le trouver\\dans le\\fichier de programmation Microsoft Skype entreprise Network Assessment outil. Un guide détaillé pour l’utilisation de l’outil, utilisation. docx, est inclus dans ce répertoire.

### <a name="test-for-opened-ports"></a>Tester les ports ouverts

Ouvrez une fenêtre d’invite de commandes et naviguez jusqu’au répertoire de l’outil d’évaluation du réseau en entrant le **CD-C :\\Program Files\\Microsoft Skype entreprise Network Assessment Tool**. À l’invite de commandes, démarrez le test pour les ports ouverts en entrant **networkassessmenttool. exe/connectivitycheck**

Après avoir exécuté les tests, l’outil affiche le message « vérification réussie » ou rapport sur les ports qui ont été bloqués.
Il génère également un fichier nommé Connectivity_results. txt, qui contient la sortie de l’outil et l'\\enregistre dans le\\\\\\ dossier% UserProfile% AppData de l’outil d’évaluation du réseau Skype entreprise local.

Nous vous recommandons d’exécuter les vérifications de connectivité régulièrement pour vous assurer que les ports ont été ouverts et qu’ils fonctionnent correctement.

### <a name="test-for-network-impairments"></a>Test pour les problèmes de réseau

Pour renforcer la satisfaction des utilisateurs, vous devez limiter les troubles de votre réseau.
Le plus souvent, les déficiences du réseau sont les délais (latence), perte de paquets et gigue :

-   **Latence :** Il s’agit du temps nécessaire à l’obtention d’un paquet IP du point A au point B sur le réseau. Ce délai de propagation du réseau est essentiellement lié à la distance physique entre les deux points et la vitesse de la lumière, y compris la surcharge supplémentaire prélevée par les différents routeurs entre eux.
    La latence est mesurée comme une seule ou pour une seule boucle.

-   **Perte de paquets**: il s’agit généralement du pourcentage de paquets perdus dans une période donnée. La perte de paquets a un effet direct sur la qualité audio (par le biais de petits paquets perdus individuels) n’ayant quasiment aucun impact sur les pertes de Burst en retour à la fin de l’audio.

-   **Scintillement du son entre les paquets ou simplement gigue :** Il s’agit de la modification moyenne du délai entre les paquets successifs. La plupart des logiciels VoIP modernes, dont Skype entreprise, peuvent s’adapter à certains niveaux de scintillement par le biais de la mise en mémoire tampon. C’est uniquement lorsque l’instabilité est supérieure à la mise en mémoire tampon qu’un participant notera les effets de gigue.

Les valeurs maximales de ces déficiences sont décrites dans la section [qualité du média et performances de connectivité réseau](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).
Lorsque vous testez ces déficiences, nous faisons la distinction entre deux segments séparés :

-   Le *segment de périphérie* correspond au segment qui habite votre routeur. Il s’agit du segment réseau logique le plus proche connecté à Internet à chaque emplacement. Dans la plupart des cas, il s’agit du point de connexion du routeur, ou éventuellement d’un réseau de périmètre (également connu sous le nom de *DMZ*, *zone démilitarisée*et *sous-réseau à écran*). Aucun trafic supplémentaire n’affectant les appareils autres que le routeur ne doit se produire entre ce segment et Internet.

-   Le *segment de client* est le segment réseau logique dans lequel résident vos clients.

Testez les deux segments à l’aide de l’outil d’évaluation du réseau. Pour tester le segment, accédez au répertoire et entrez **networkassessmenttool. exe** à l’invite de commandes. Les résultats sont écrits dans un fichier nommé results. TSV et vous pouvez les comparer aux [exigences](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) de chaque segment.

Notez que les deux segments doivent respecter les exigences requises pour un déploiement de grande qualité. Nous vous recommandons d’exécuter l’outil plusieurs fois pour une heure pour obtenir une bonne indication des performances de votre réseau.

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>Correction de réseau

Si les résultats de la planification de la bande passante, du test de port ou du test des exigences réseau indiquent que votre réseau actuel a besoin d’une correction avant le déploiement d’équipes, vous pouvez procéder de plusieurs manières :

-   Dans le cas d’une bande passante insuffisante, mettez les connexions à niveau de sorte que le trafic vers Office 365 puisse être mis en place.

-   Pour les ports bloqués, modifiez les règles de pare-feu et testez à présent les ports.

-   Pour les handicaps réseau, effectuez toujours une analyse de cause profonde.

La qualité de service (QoS) peut être utilisée pour lutter contre les troubles en hiérarchisant et en séparant le trafic. Certaines organisations choisissent de déployer la qualité de service (QoS) pour résoudre les problèmes de bande passante ou limiter le nombre de flux de trafic. Cela n’améliorera pas la qualité et provoquera de nouveaux problèmes. Une analyse de cause initiale doit toujours être effectuée lorsque les contraintes réseau dépassent les exigences. La qualité de service (QoS) peut être une solution.
Pour plus d’informations, reportez-vous à la section [qualité de service de Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams).

>[!NOTE]
>De nombreux réseaux évoluent au fil du temps en raison des mises à niveau, de l'expansion ou d'autres exigences commerciales. Assurez-vous d'avoir des processus opérationnels en place pour maintenir ces secteurs dans le cadre de la planification de la gestion des services.


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Points de décision</td><td><ul><li>Qui est responsable de l’exécution correcte des évaluations réseau sur tous les segments réseau et emplacements de l’Organisation ?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Étapes suivantes</td><td><ul><li>Vous pouvez effectuer une analyse du réseau détaillée pour vous assurer que votre réseau est prêt pour le déploiement de Microsoft Teams.</li><li>Effectuez une correction du réseau en fonction des résultats de l’évaluation de chaque segment réseau.</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->