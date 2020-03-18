---
title: Préparer votre réseau pour Microsoft teams |  Configuration requise pour le pare-feu
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dearbeen
description: Utilisez ce guide pour préparer votre réseau pour le déploiement et le lancement de Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d58613bc3455d5467e9e6c6589f73d498c6e1e3b
ms.sourcegitcommit: 5d64e30a1984a4b1d9ff36e2e1721cb4bbf9e450
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/17/2020
ms.locfileid: "42706904"
---
# <a name="prepare-your-network-for-upgrading-to-teams"></a>Préparer votre réseau pour la mise à niveau vers teams

![Diagramme de route de mise à niveau, mettant l’accent sur l’étape de préparation technique](media/upgrade-banner-tech-readiness.png "Étapes du parcours de la mise à niveau, en mettant l’accent sur l’étape de préparation technique")

Cet article fait partie de l’étape de préparation technique de votre mouvement de mise à niveau, une activité que vous finalisez en parallèle avec l’étape de préparation de l’utilisateur. Avant de continuer, assurez-vous d’avoir suivi les étapes ci-dessous :

- [Inscription des parties prenantes du projet](upgrade-enlist-stakeholders.md)
- [Définition de l’objectif de votre projet](https://aka.ms/SkypetoTeams-Scope)
- [Compréhension de la coexistence et de l’interopérabilité de Skype entreprise et équipes](https://aka.ms/SkypeToTeams-Coexist)
- [Choix de votre mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

> [!Tip]
> Regardez la session suivante pour découvrir comment les équipes tirent parti de votre réseau et la meilleure façon de se préparer pour une connectivité réseau optimale : [Team Network Planning](https://aka.ms/teams-networking)

Si vous déployez des fichiers audio, vidéo ou de réunion, vous pouvez effectuer des étapes supplémentaires pour optimiser votre réseau pour cette fonctionnalité. Teams utilise une technologie audio et vidéo (codecs) pouvant s’adapter à la plupart des conditions de réseau. Pour garantir des performances optimales et cohérentes, vous devez préparer votre réseau pour Teams.

![Diagramme décrivant les trois composantes de la qualité](media/evaluate-my-environment-image1.png "Diagramme décrivant les trois composantes de la qualité et la façon dont la gestion de service empiète sur les trois composants. Avec le focus du réseau.")

## <a name="why-should-you-prepare-your-network"></a>Pourquoi dois-je préparer votre réseau ?

Avant de passer en revue les étapes à suivre, il est important de comprendre ce qui peut affecter les performances des équipes et donc le bonheur et la satisfaction des utilisateurs. Trois domaines principaux de risques peuvent influer sur la qualité du réseau :

- Bande passante disponible insuffisante

- Pare-feu et bloqueurs de proxy

- Déficiences du réseau comme le scintillement et la perte de paquets

Les étapes décrites ci-dessous vous aideront à déterminer si votre déploiement sera affecté par l’un de ces facteurs et vous aideront à vous déplacer vers une résolution. Le non-respect de votre réseau risque de provoquer des problèmes d’insatisfaction des utilisateurs et des correctifs ad hoc coûteux. En préparant votre réseau (et votre organisation) pour les équipes, vous pouvez augmenter considérablement votre chance de succès.

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>Planification de la bande passante

Microsoft teams vous offre la meilleure expérience audio, vidéo et de partage de contenu quelle que soit l’état de votre réseau. Grâce aux codecs variables, le média peut être négocié dans les environnements à bande passante limitée avec un impact minimal. Même si la bande passante n’est pas un problème, les expériences peuvent être optimisées en matière de qualité, y compris jusqu’à 1080p résolutions vidéo, jusqu’à 30 IPS pour la vidéo et 15fps pour le contenu et le son haute fidélité.

[!INCLUDE [Bandwidth requirements](includes/bandwidth-requirements.md)]

### <a name="local-internet-egress"></a>Sortie Internet locale

De nombreux réseaux ont été conçus pour utiliser une topologie de hub et parlée. Dans cette topologie, le trafic Internet traverse généralement le WAN jusqu'à un centre de données central avant qu'il n'émerge (sorties) vers Internet. Souvent, cela est fait pour centraliser les dispositifs de sécurité du réseau dans le but de réduire les coûts globaux.

Relayer le trafic sur le WAN augmente la latence et a un impact négatif sur la qualité et l'expérience utilisateur. Étant donné que Microsoft teams s’exécute sur le grand réseau mondial de Microsoft, il y a souvent un emplacement d’homologation réseau proche de l’utilisateur. Un utilisateur obtiendra probablement de meilleures performances en sortant d'un point Internet local près de son emplacement et sur notre réseau à voix optimisée dès que possible. Pour certaines charges de travail, les requêtes DNS sont utilisées pour envoyer du trafic vers le serveur frontal le plus proche. Dans ces cas, il est important que lors de l’utilisation d’un point de sortie local, il soit associé à la résolution DNS locale.

L’optimisation du chemin réseau du réseau global de Microsoft permet d’améliorer les performances et de garantir une meilleure utilisation pour les utilisateurs. Pour plus de détails, voir l'article du blog [Obtenir la meilleure connectivité et les meilleures performances dans Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

Pour bénéficier d’une meilleure utilisation de l’utilisation du contenu multimédia en temps réel au sein de Microsoft Teams, vous devez vous conformer aux exigences réseau pour Office 365. Pour plus d’informations, consultez [qualité multimédia et performances de connectivité réseau pour Skype entreprise Online](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).

Les deux méthodes de définition des segments réseau (client vers Microsoft Edge et client Edge vers Microsoft Edge) doivent respecter les exigences suivantes :

|**Valeur** |**Client vers Microsoft Edge** |**Edge du client à Microsoft Edge** |
|---|---|---|
|**Latence (unidirectionnelle)** |< 50 ms |< 30 ms |
|**Latence (durée de l’aller-retour ou RTT)** |< 100 ms |< 60 ms |
|**Perte de paquets en rafale** |<10% pendant tout intervalle 200-ms |<1% pendant tout intervalle de 200-ms |
|**Perte de paquets** |<1% pendant tout intervalle de 15 secondes |<0,1% pendant tout intervalle de 15 secondes |
|**Gigue entre les arrivées de paquets** |<30 ms pendant tout intervalle de 15 secondes |<15 ms pendant tout intervalle de 15 secondes |
|**Réorganisation des paquets** |<0,05% de paquets hors commande |<0,01% de paquets hors commande |

Pour tester les deux segments réseau, vous pouvez utiliser l' [outil d’évaluation du réseau](https://go.microsoft.com/fwlink/?linkid=855799). Cet outil peut être déployé sur le PC client directement et sur un PC connecté au bord du réseau du client. L’outil inclut une documentation limitée, mais une documentation plus approfondie sur l’utilisation de l’outil est disponible ici : [évaluation](https://go.microsoft.com/fwlink/?linkid=855800)de la disponibilité du réseau. L’exécution de cette analyse de préparation du réseau vous permet de valider la préparation de votre réseau pour exécuter des applications multimédias en temps réel, telles que Microsoft Teams.

> [!NOTE]
> Il s’agit de la même évaluation de la compatibilité réseau que recommandée par les clients qui souhaitent déployer Skype entreprise avec succès.

### <a name="vpn"></a>VPN

Les VPN fournissent un service de valeur à de nombreuses organisations. Malheureusement, il n’est généralement pas conçu ou configuré pour prendre en charge les contenus multimédias en temps réel. Certains VPN peuvent également ne pas prendre en charge UDP. Les réseaux privés virtuels introduisent également une couche supplémentaire de chiffrement au-dessus du trafic multimédia déjà crypté. Par ailleurs, la connectivité au service teams peut ne pas être efficace en raison du trafic d’épinglage par le biais d’un appareil VPN. Par ailleurs, elles ne sont pas nécessairement conçues à partir d’un point de vue de la capacité pour s’adapter aux efforts prévus qui seront nécessaires aux équipes.

La recommandation est de fournir un chemin alternatif qui contourne le VPN pour le trafic de Teams. C’est communément connu sous le nom de *VPN de tunneling scindé*. Le tunneling fractionné signifie que le trafic destiné à Office 365 ne traverse pas le VPN, mais qu’il accède directement à Office 365. Ce changement aura un impact positif sur la qualité, mais fournit également l’avantage secondaire de réduire la charge des appareils VPN et du réseau de l’organisation.

Pour mettre en œuvre un tunnel segmenté, consultez votre fournisseur VPN pour les détails de configuration.

### <a name="wi-fi"></a>Wi-Fi

Comme VPN, les réseaux Wi-Fi ne sont pas nécessairement conçus ou configurés pour prendre en charge les contenus multimédias en temps réel. La planification d’un réseau Wi-Fi pour la prise en charge des équipes est une considération importante pour un déploiement de grande qualité.

Il existe plusieurs facteurs qui entrent en jeu pour optimiser un réseau Wi-Fi :

- Mettre en œuvre la QoS ou le Wi-Fi Multimedia (WMM) pour s'assurer que le trafic média est priorisé en conséquence sur les réseaux Wi-Fi.

- Planification et optimisation des bandes Wi-Fi et du placement des points d’accès. La plage de 2,4 GHz peut offrir une connaissance appropriée en fonction du placement du point d’accès, mais les points d’accès sont souvent affectés par d’autres appareils grand public qui fonctionnent dans cette plage. La gamme de 5 GHz est mieux adaptée aux médias en temps réel en raison de leur portée dense, mais nécessite plus de points d'accès pour obtenir une couverture suffisante. Les points de terminaison doivent également prendre en charge cette plage et être configurés pour exploiter ces bandes en conséquence.

- Si les réseaux Wi-Fi bibande sont déployés, envisagez d’implémenter la direction de bandes. La _direction de bandes_ est une technique mise en œuvre par les fournisseurs de réseaux Wi-Fi pour influencer les clients à double bande et utiliser la plage de 5 GHz.

- Lorsque les points d’accès du même canal sont trop proches, ils peuvent provoquer le chevauchement du signal et la concurrence involontaire, ce qui engendre une mauvaise utilisation de l’utilisateur. Assurez-vous que les points d’accès adjacents s’exécutent sur des canaux qui ne se chevauchent pas.

Chaque fournisseur de services sans fil a ses propres recommandations pour le déploiement de sa solution sans fil. Nous vous recommandons de consulter votre fournisseur pour obtenir des conseils spécifiques.

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>Configuration requise pour le pare-feu et les proxys

Microsoft teams se connecte aux services en ligne de Microsoft et nécessite une connectivité Internet pour cela. Pour que teams fonctionne correctement, vous devez ouvrir les ports TCP 80 et 443 de clients vers Internet, ainsi que les ports UDP 3478 à 3481 des clients vers Internet. Les ports TCP sont utilisés pour se connecter à du contenu Web tel que SharePoint Online, Exchange Online et les services de chat d’équipe. Les plug-ins et connecteurs se connectent également via ces ports TCP. Les quatre ports UDP sont utilisés pour les contenus multimédias tels que les fichiers audio et vidéo, afin de s’assurer que le flux fonctionne correctement.

L’ouverture de ces ports est essentielle pour un déploiement d’équipes fiable. Le blocage de ces ports n’est pas pris en charge et peut affecter la qualité multimédia.

Si votre organisation nécessite que vous spécifiiez les plages d’adresses IP et les domaines exacts auxquels ces ports doivent être ouverts, vous pouvez limiter les plages d’adresses IP cibles et les domaines pour ces ports. Pour obtenir la liste des ports, protocoles et plages d’adresses IP exacts, voir [URL et plages d’adresses IP Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). Si vous choisissez de limiter les plages d’adresses IP et les domaines cibles, vous devez veiller à ce que la liste des ports et des plages soit à jour, car elles peuvent changer. Vous pouvez vous abonner à [ce flux RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) pour être mis à jour lorsque des modifications se produisent. Il est également recommandé de tester si tous les ports sont ouverts en exécutant l' [outil d’évaluation du réseau Skype entreprise](https://www.microsoft.com/download/details.aspx?id=53885) régulièrement. Vous pouvez en savoir plus sur les fonctionnalités de cet outil dans la section suivante.

Dans le cas d’un serveur proxy déployé, nous vous recommandons de ne pas utiliser le serveur proxy pour tous les services Teams. Bien que l’utilisation d’un proxy puisse fonctionner, il est très probable que la qualité soit réduite en raison de l’utilisation forcée du protocole TCP au lieu du protocole UDP. Pour plus d’informations sur les serveurs proxy et la contournement, voir [URL et plages d’adresses IP Office 365](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges).

<!--ENDOFSECTION-->

## <a name="additional-network-considerations"></a>Considérations relatives au réseau supplémentaire

### <a name="external-name-resolution"></a>Résolution de noms externes

Assurez-vous que tous les ordinateurs clients exécutant le client teams peuvent résoudre les requêtes DNS externes pour découvrir les services fournis par Office 365.

### <a name="nat-pool-size"></a>Taille du pool NAT

Lorsque plusieurs utilisateurs et appareils accèdent à Office 365 à l’aide de la traduction d’adresses réseau (NAT) ou de la traduction d’adresses de port (PAT), vous devez vous assurer que les périphériques cachés derrière chaque adresse IP routable publique ne dépassent pas le nombre pris en charge.

Pour atténuer ce risque, assurez-vous que les adresses IP publiques appropriées sont affectées aux pools NAT pour empêcher l’épuisement du port. L’épuisement du port permettra aux utilisateurs finaux et aux appareils internes d’affronter de rencontrer des problèmes lors de la connexion aux services Office 365. Pour plus d’informations, voir [prise en charge NAT avec Office 365](https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365).

### <a name="intrusion-detection-and-prevention-guidance"></a>Recommandations en matière de détection d’intrusion et de prévention

Si votre environnement a un système de détection des intrusions et/ou un système de prévention des intrusions déployé pour une couche supplémentaire de sécurité pour les connexions sortantes, assurez-vous que tout le trafic contenant les URL d’Office 365 comme destination est une autorisation.

## <a name="test-the-network"></a>Test du réseau

Une fois que vous avez terminé votre planification et préparation du réseau, y compris la mise à niveau de la bande passante et l’ouverture des ports dans le pare-feu, vous devez tester les performances de votre réseau. Les résultats de ces tests peignent une image plus claire de tout optimisation du réseau ou d’une correction requise pour la réussite de votre implémentation d’équipes.

Vous pouvez télécharger l' [outil d’évaluation du réseau Skype entreprise](https://www.microsoft.com/download/details.aspx?id=53885) pour tester si votre réseau est prêt pour les équipes. L’outil offre une double fonctionnalité : il peut tester si tous les ports corrects ont été ouverts et tester les problèmes de réseau.

Après avoir téléchargé et installé l’outil, vous pouvez le retrouver dans C:\Program Files (x86) \Microsoft Skype entreprise Network Assessment Tool. Un guide détaillé pour l’utilisation de l’outil, utilisation. docx, est inclus dans ce répertoire.

### <a name="test-for-opened-ports"></a>Tester les ports ouverts

Ouvrez une fenêtre d’invite de commandes et accédez au répertoire de l’outil d’évaluation réseau en entrant le **CD C:\Program Files (x86) \Microsoft Skype entreprise Network Assessment**. À l’invite de commandes, démarrez le test pour les ports ouverts en entrant **networkassessmenttool. exe/connectivitycheck**

Après avoir exécuté les tests, l’outil affiche le message « vérification réussie » ou rapport sur les ports qui ont été bloqués. Il génère également un fichier nommé Connectivity_results. txt, qui contient la sortie de l’outil et l'\\enregistre dans le\\\\\\ dossier% UserProfile% AppData de l’outil d’évaluation du réseau Skype entreprise local.

Nous vous recommandons d’exécuter les vérifications de connectivité régulièrement pour vous assurer que les ports ont été ouverts et qu’ils fonctionnent correctement.

### <a name="test-for-network-impairments"></a>Test pour les problèmes de réseau

Pour renforcer la satisfaction des utilisateurs, vous devez limiter les troubles de votre réseau. Le plus souvent, les déficiences du réseau sont les délais (latence), perte de paquets et gigue :

- **Latence :** Il s’agit du temps nécessaire à l’obtention d’un paquet IP du point A au point B sur le réseau. Ce délai de propagation du réseau est essentiellement lié à la distance physique entre les deux points et la vitesse de la lumière, y compris la surcharge supplémentaire prélevée par les différents routeurs entre eux. La latence est mesurée comme une seule ou pour une seule boucle.

- **Perte de paquets**: il s’agit généralement du pourcentage de paquets perdus dans une période donnée. La perte de paquets a un effet direct sur la qualité audio (par le biais de petits paquets perdus individuels) n’ayant quasiment aucun impact sur les pertes de Burst en retour à la fin de l’audio.

- **Scintillement du son entre les paquets ou simplement gigue :** Il s’agit de la modification moyenne du délai entre les paquets successifs. La plupart des logiciels VoIP modernes, dont Skype entreprise, peuvent s’adapter à certains niveaux de scintillement par le biais de la mise en mémoire tampon. C’est uniquement lorsque l’instabilité est supérieure à la mise en mémoire tampon qu’un participant notera les effets de gigue.

Les valeurs maximales de ces déficiences sont décrites dans la section [qualité du média et performances de connectivité réseau](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance). Lorsque vous testez ces déficiences, nous faisons la distinction entre deux segments séparés :

- Le *segment de périphérie* correspond au segment qui habite votre routeur. Il s’agit du segment réseau logique le plus proche connecté à Internet à chaque emplacement. Dans la plupart des cas, il s’agit du point de connexion du routeur, ou éventuellement d’un réseau de périmètre (également connu sous le nom de *DMZ*, *zone démilitarisée*et *sous-réseau à écran*). Aucun trafic supplémentaire n’affectant les appareils autres que le routeur ne doit se produire entre ce segment et Internet.

- Le *segment de client* est le segment réseau logique dans lequel résident vos clients.

Testez les deux segments à l’aide de l’outil d’évaluation du réseau. Pour tester le segment, accédez au répertoire et entrez **networkassessmenttool. exe** à l’invite de commandes. Les résultats sont écrits dans un fichier nommé results. TSV et vous pouvez les comparer aux [exigences](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) de chaque segment.

Notez que les deux segments doivent respecter les exigences requises pour un déploiement de grande qualité. Nous vous recommandons d’exécuter l’outil plusieurs fois pour une heure pour obtenir une bonne indication des performances de votre réseau.

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>Correction de réseau

Si les résultats de la planification de la bande passante, du test de port ou du test des exigences réseau indiquent que votre réseau actuel a besoin d’une correction avant le déploiement d’équipes, vous pouvez procéder de plusieurs manières :

- Dans le cas d’une bande passante insuffisante, mettez les connexions à niveau de sorte que le trafic vers Office 365 puisse être mis en place.

- Pour les ports bloqués, modifiez les règles de pare-feu et testez à présent les ports.

- Pour les handicaps réseau, effectuez toujours une analyse de cause profonde.

La qualité de service (QoS) peut être utilisée pour lutter contre les troubles en hiérarchisant et en séparant le trafic. Certaines organisations choisissent de déployer la qualité de service (QoS) pour résoudre les problèmes de bande passante ou limiter le nombre de flux de trafic. Cela n’améliorera pas la qualité et provoquera de nouveaux problèmes. Une analyse de cause initiale doit toujours être effectuée lorsque les contraintes réseau dépassent les exigences. La qualité de service (QoS) peut être une solution. Pour plus d’informations, reportez-vous à la section [qualité de service de Microsoft teams](qos-in-teams.md).

>[!NOTE]
>De nombreux réseaux évoluent au fil du temps en raison des mises à niveau, de l'expansion ou d'autres exigences commerciales. Assurez-vous d'avoir des processus opérationnels en place pour maintenir ces secteurs dans le cadre de la planification de la gestion des services.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Point de décision</td><td><ul><li>Qui est responsable de l’exécution correcte des évaluations réseau sur tous les segments réseau et emplacements de l’Organisation ?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Étapes suivantes</td><td><ul><li>Vous pouvez effectuer une analyse du réseau détaillée pour vous assurer que votre réseau est prêt pour le déploiement de Microsoft Teams. </li><li>Effectuez une correction du réseau en fonction des résultats de l’évaluation de la compatibilité réseau pour chaque segment réseau.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="key-takeaways"></a>Points clés

Voici les principaux points à retenir dans ces instructions. Il le faut:

- Ouvrez les ports TCP 80 et 443 sortants des clients qui utiliseront Teams.

- Ouvrez les ports UDP 3478 à 3481 sortants des clients qui utiliseront Teams.

- Vérifiez que vous disposez d’assez de bande passante pour déployer Teams.

- Exécutez l' [outil d’évaluation du réseau](https://www.microsoft.com/download/details.aspx?id=53885) et assurez-vous de respecter les exigences décrites dans la section [qualité multimédia et performances de connectivité réseau](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) du segment du réseau et du segment client.

## <a name="related-topics"></a>Rubriques connexes

[Vidéo : planification du réseau](https://aka.ms/teams-networking)
