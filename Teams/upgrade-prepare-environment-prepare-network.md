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
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 465112aa154620f4cabf59aa1e6d4c70aa74eb16
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887804"
---
![Étapes du parcours de mise à niveau, avec un accent sur l’étape de préparation technique](media/upgrade-banner-tech-readiness.png "Étapes du parcours de mise à niveau, avec un accent sur l’étape de préparation technique")

Cet article entre dans le cadre de l’étape de préparation technique de votre parcours de mise à niveau, une activité que vous effectuez parallèlement à l’étape de préparation des utilisateurs. Avant de poursuivre, vérifiez que vous avez terminé les activités des étapes précédentes :

-   [Inscription des parties prenantes du projet](upgrade-enlist-stakeholders.md)
-   [Définition du champ d’application de votre projet](https://aka.ms/SkypetoTeams-Scope)
-   [Compréhension de la coexistence et de l’interopérabilité de Skype Entreprise et Teams](https://aka.ms/SkypeToTeams-Coexist)
-   [Choix de votre parcours de mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prepare-your-network-for-upgrading-to-teams"></a>Préparation de votre réseau pour la mise à niveau vers Teams

Si vous déployez l’audio, la vidéo ou les réunions, vous pouvez effectuer des étapes supplémentaires pour optimiser votre réseau pour cette fonctionnalité. Teams utilise une technologie audio et vidéo (codecs) qui peut s’adapter à - et donc être plus performante dans - certaines conditions de réseau. Pour garantir des performances optimales et constantes, vous devez préparer votre réseau pour Teams.

![Diagramme illustrant les trois composantes de la qualité, et comment la gestion des services recoupe les trois composantes. En mettant l'accent sur le réseau.](media/evaluate-my-environment-image1.png "Diagramme illustrant les trois composantes de la qualité, et comment la gestion des services recoupe les trois composantes. En mettant l'accent sur le réseau.")

## <a name="why-should-you-prepare-your-network"></a>Pourquoi devez-vous préparer votre réseau ?

Avant d’aborder la procédure à suivre, il est important de comprendre ce qui peut avoir une incidence sur les performances de Teams et donc la satisfaction des utilisateurs. Trois zones de risque principales peuvent avoir une incidence sur la perception des utilisateurs de la qualité du réseau :

-   Bande passante disponible insuffisante

-   Bloqueurs de pare-feu et de proxy

-   Dégradations sur le réseau telles que déficiences et perte de paquets

La procédure décrite ci-dessous vous permettra de déterminer si votre déploiement risque d’être affecté par ces facteurs et vous aidera à trouver une solution. Si vous n’avez pas préparé votre réseau, les utilisateurs seront probablement insatisfaits et cela entraînera l’application de correctifs ponctuels onéreux. En préparant votre réseau - et votre organisation - pour Teams, vous aurez beaucoup plus de chances de réussir.

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>Planification de la bande passante

La première étape de préparation du réseau consiste à s’assurer qu'il comporte suffisamment de bande passante disponible pour les fonctionnalités que Teams fournira aux utilisateurs. La planification d’une bande passante suffisante est une tâche plutôt simple et un point de départ présentant très peu d’obstacles pour vous assurer que vos utilisateurs auront une expérience de Teams optimale.

Vous commencez votre parcours de planification de la bande passante pour Teams sur le [site Web My Advisor](https://myadvisor.fasttrack.microsoft.com/) à l’aide du Planificateur de réseau. Le Planificateur de réseau fournit une planification de la bande passante pour Teams par site, ainsi que des recommandations pour optimiser les performances du réseau.

> [!IMPORTANT]
> Si la bande passante requise n'est pas disponible, la pile multimédia de Teams dégradera la qualité de la session audio/vidéo pour s'adapter à la quantité de bande passante disponible plus faible, ce qui affectera la qualité de l'appel ou de la réunion. Le client Teams tentera de privilégier la qualité de l'audio plutôt que la vidéo. C'est pourquoi il est très important de disposer de la bande passante requise.


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

De nombreux réseaux ont été conçus pour utiliser une topologie de hub et parlée. Dans cette topologie, le trafic Internet traverse généralement le WAN jusqu'à un centre de données central avant qu'il n'émerge (sorties) vers Internet. Souvent, cela est fait pour centraliser les dispositifs de sécurité du réseau dans le but de réduire les coûts globaux.

Relayer le trafic sur le WAN augmente la latence et a un impact négatif sur la qualité et l'expérience utilisateur. Comme Microsoft Teams fonctionne sur le vaste réseau mondial de Microsoft, il existe souvent un emplacement réseau de pairage à proximité de l'utilisateur. Un utilisateur obtiendra probablement de meilleures performances en sortant d'un point Internet local près de son emplacement et sur notre réseau à voix optimisée dès que possible. Pour certaines charges de travail, les requêtes DNS sont utilisées pour envoyer du trafic vers le serveur frontal le plus proche. Dans de tels cas, il est important que lors de l'utilisation d'un point d'évacuation local, il soit couplé avec la résolution DNS locale.

L'optimisation du chemin d'accès au réseau mondial de Microsoft améliorera les performances et, en fin de compte, offrira la meilleure expérience aux utilisateurs. Pour plus de détails, voir l'article du blog [Obtenir la meilleure connectivité et les meilleures performances dans Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).


Pour bénéficier d'une expérience optimale avec le multimédia en temps réel dans Microsoft Teams, la configuration réseau requise pour Office 365 doit être satisfaite. Pour plus d’informations, consultez la rubrique [Qualité des médias et performances de connectivité réseau dans Skype Entreprise Online](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).

Les deux segments réseau de définition (client vers Microsoft Edge et côté client vers Microsoft Edge) doivent respecter les conditions requises suivantes :


|**Valeur**  |**Client vers Microsoft Edge**  |**Côté client vers Microsoft Edge**  |
|---------|---------|---------|
|**Latence (unidirectionnelle)**     |< 50 ms          |< 30 ms          |
|**Latence (durée des boucles ou RTT)** |< 100 ms         |< 60 ms         |
|**Perte de paquets en rafale**    |< 10 % sur un intervalle de 200 ms         |< 1% sur un intervalle de 200 ms         |
|**Perte de paquets**     |< 1% sur un intervalle de 15 sec          |< 0,1% sur un intervalle de 15 sec         |
|**Instabilité entre les arrivées de paquets**    |< 30 ms sur un intervalle de 15 sec         |< 15 ms sur un intervalle de 15 sec         |
|**Réorganisation des paquets**    |< 0,05 % paquets désorganisés         |< 0,01% paquets désorganisés         |

Pour tester les deux segments réseau, vous pouvez utiliser l’[Outil d'évaluation du réseau](https://go.microsoft.com/fwlink/?linkid=855799). Cet outil peut être déployé sur le PC client directement et sur un PC connecté au périphérique réseau client. Il inclut une documentation restreinte, mais une documentation plus approfondie concernant l’utilisation de l’outil est disponible ici : [Évaluation de la préparation du réseau](https://go.microsoft.com/fwlink/?linkid=855800). En exécutant cet outil d’évaluation de la préparation du réseau, vous pouvez valider l’état de préparation de votre réseau à exécuter des applications multimédias en temps réel telles que Microsoft Teams.

> [!NOTE]
> Il s'agit de la même évaluation de la préparation du réseau que celle que nous recommandons pour les clients qui souhaitent déployer Skype Entreprise avec succès.


### <a name="vpn"></a>VPN

Les VPN fournissent un service de valeur à de nombreuses organisations. Malheureusement, ils ne sont généralement pas conçus ou configurés pour prendre en charge le multimédia en temps réel. Certains VPN peuvent également ne pas prendre en charge UDP. Les VPN introduisent également une couche supplémentaire de chiffrement en plus du trafic multimédia déjà chiffré. En outre, la connectivité au service Teams pourrait ne pas être efficace en raison du trafic d’agrégation via un périphérique VPN. De plus, ils ne sont pas nécessairement conçus du point de vue de la capacité pour répondre aux charges prévues nécessaires pour Teams.

La recommandation est de fournir un chemin alternatif qui contourne le VPN pour le trafic de Teams. C’est ce qu’on appelle généralement un *VPN en tunnel segmenté*. La segmentation de tunnel signifie que le trafic d'Office 365 ne traversera pas le VPN mais ira directement vers Office 365. Ce changement aura un impact positif sur la qualité, mais aussi l'avantage secondaire de réduire la charge des dispositifs VPN et du réseau de l'organisation.

Pour mettre en œuvre un tunnel segmenté, consultez votre fournisseur VPN pour les détails de configuration.

### <a name="wi-fi"></a>Wi-Fi

Tout comme le VPN, les réseaux Wi-Fi ne sont pas nécessairement conçus ou configurés pour prendre en charge le multimédia en temps réel. La planification et/ou l'optimisation d'un réseau Wi-Fi pour prendre en charge Teams est une considération importante pour un déploiement de qualité.

Plusieurs facteurs entrent en jeu pour optimiser un réseau Wi-Fi :

-   Mettre en œuvre la QoS ou le Wi-Fi Multimedia (WMM) pour s'assurer que le trafic média est priorisé en conséquence sur les réseaux Wi-Fi.

-   Planification et optimisation des bandes W-Fi et de l'emplacement des points d'accès. La gamme de fréquences de 2,4 GHz peut fournir une expérience adéquate en fonction de l'emplacement des points d'accès, mais les points d'accès sont souvent affectés par d'autres périphériques grand public qui fonctionnent dans cette gamme. La gamme de 5 GHz est mieux adaptée aux médias en temps réel en raison de leur portée dense, mais nécessite plus de points d'accès pour obtenir une couverture suffisante. Les points de terminaison doivent également prendre en charge cette plage et être configurés pour exploiter ces bandes en conséquence.

-   Si des réseaux Wi-Fi à double bande sont déployés, songez à mettre en place un système de direction de bande. La _direction de bande_ est une technique mise en œuvre par les fournisseurs de Wi-Fi pour inciter les clients à double bande à utiliser la gamme de fréquences de 5 Ghz.

-   Lorsque les points d'accès d'un même canal sont trop proches les uns des autres, ils peuvent provoquer une superposition des signaux et une concurrence involontaire, ce qui entraîne une mauvaise expérience pour l'utilisateur. Veillez à ce que les points d'accès voisins se trouvent sur des canaux qui ne se superposent pas.

Chaque fournisseur de services sans fil a ses propres recommandations pour le déploiement de sa solution sans fil. Nous vous recommandons de consulter votre fournisseur pour obtenir des conseils spécifiques.

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>Conditions requises pour le pare-feu et le proxy

Microsoft Teams se connecte à Microsoft Online Services et a besoin pour cela d'une connectivité internet. Pour que Teams fonctionne correctement, vous devez ouvrir les ports TCP 80 et 443 des clients à internet, et les ports UDP 3478 à 3481 des clients à internet. Les ports TCP sont utilisés pour se connecter au contenu sur le Web comme les services SharePoint Online, Exchange Online et de conversation Teams. Les plug-ins et les connecteurs se connectent également via ces ports TCP. Les autre ports UDP sont utilisés pour les médias comme l’audio et la vidéo, afin d’assurer qu’ils circulent correctement.

Ouvrir ces ports est essentiel pour un déploiement fiable de Teams. Le blocage de ces ports n’est pas pris en charge et aura une incidence sur la qualité multimédia.

Si votre organisation requiert que les plages d’adresses IP exactes et les domaines auxquels ces ports doivent être ouverts soient spécifiés, vous pouvez restreindre les plages d’adresses IP et les domaines vers ces ports. Pour obtenir la liste des ports, protocoles et adresses IP exacts, reportez-vous à l’article [Plages d'adresses URL et IP d’Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). Si vous choisissez de restreindre les plages d’adresses IP et les domaines, vous devez vous assurer de maintenir à jour la liste des ports et des plages, car elle peut être modifiée. Vous pouvez vous abonner à ce [flux RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) pour être averti des modifications. Une autre bonne pratique consiste à tester si tous les ports sont ouverts en exécutant régulièrement [l'outil d’évaluation du réseau de Skype Entreprise](https://www.microsoft.com/download/details.aspx?id=53885). Vous trouverez des informations plus détaillées sur les fonctionnalités de cet outil dans la section suivante.

Si un serveur proxy est déployé, nous vous recommandons de le contourner pour tous les services Teams. Bien que l’utilisation d'un proxy puisse fonctionner, il est très probable que la qualité sera réduite car le média sera forcé d’utiliser TCP au lieu d’UDP. Pour plus d'informations sur les serveurs proxy et le contournement, reportez-vous à l’article [Plages d'adresses URL et IP d’Office 365](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges).

<!--ENDOFSECTION-->

## <a name="additional-network-considerations"></a>Remarques supplémentaires relatives au réseau
### <a name="external-name-resolution"></a>Résolution des noms externes

Assurez-vous que tous les ordinateurs client exécutant Teams peuvent résoudre les requêtes DNS externes pour détecter les services fournis par Office 365.

### <a name="nat-pool-size"></a>Taille du pool NAT

Lorsque plusieurs utilisateurs/périphériques accèdent à Office 365 à l'aide de la traduction d'adresses réseau (NAT) ou de la traduction d'adresses de port (PAT), vous devez vous assurer que les périphériques placés derrière chaque adresse IP publiquement routable n'excèdent pas le nombre pris en charge.

Pour atténuer ce risque, assurez-vous que les adresses IP publiques adéquates sont affectées aux pools NAT pour éviter toute insuffisance de ports. Si les ports sont insuffisants, les utilisateurs finaux internes et les périphériques rencontreront des problèmes lorsqu'ils se connecteront aux services Office 365. Pour plus d’informations, consultez la rubrique [Prise en charge NAT avec Office 365](https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365).

### <a name="intrusion-detection-and-prevention-guidance"></a>Instructions pour la détection et la prévention d'intrusion

Si votre environnement comporte un système de détection des intrusions et/ou un système de prévention des intrusions déployé pour une couche supplémentaire de sécurité pour les connexions sortantes, assurez-vous que tout le trafic ayant des URL Office 365 comme destination est placé sur liste blanche.

## <a name="test-the-network"></a>Tester le réseau

Lorsque vous avez terminé la planification et la préparation du réseau - y compris la mise à niveau de la bande passante et l'ouverture des ports dans le pare-feu, vous devez tester les performances du réseau. Les résultats de ce test donneront une image plus claire de l’optimisation du réseau ou de la correction requises pour réussir votre implémentation de Teams.

Pour tester si votre réseau est prêt pour Teams, vous pouvez télécharger [l'outil d'évaluation du réseau de Skype Entreprise](https://www.microsoft.com/download/details.aspx?id=53885). Cet outil offre deux fonctionnalités : il peut tester si tous les ports corrects ont été ouverts et si le réseau est instable.

Après avoir téléchargé et installé l'outil, vous le trouverez dans C:\\Program Files\\Microsoft Skype for Business Network Assessment Tool. Un guide détaillé d’utilisation de cet outil, Usage.docx, est inclus dans ce répertoire.

### <a name="test-for-opened-ports"></a>Tester les ports ouverts

Ouvrez une fenêtre d’invite de commande et accédez au répertoire Network Assessment Tool directory en saisissant **cd C:\\Program Files\\Microsoft Skype for Business Network Assessment Tool**. Dans l'invite de commande, démarrez le test des ports ouverts en saisissant **networkassessmenttool.exe /connectivitycheck**

Après avoir exécuté les contrôles, l'outil affichera le message « Verifications Completed Successfully » ou signalera les ports qui étaient bloqués. Il génère également le fichier Connectivity_results.txt, qui contient le résultat de l’outil et le stocke dans le répertoire %userprofile%\\appdata\\local\\microsoft skype for business network assessment tool\\.

Nous vous recommandons d’exécuter régulièrement les contrôles de connectivité pour vous assurer que les ports ont été ouverts et fonctionnent correctement.

### <a name="test-for-network-impairments"></a>Tester les déficiences du réseau

Afin d’améliorer la satisfaction des utilisateurs, vous devez limiter les déficiences sur votre réseau. Les déficiences du réseau les plus courantes sont un délai (latence), une perte de paquets et une instabilité.

-   **Latence :** le temps nécessaire pour qu'un paquet IP parvienne d'un point A à un point B sur le réseau. Ce délai de propagation sur le réseau est lié essentiellement à la distance physique entre les deux points et à la rapidité, notamment au traitement supplémentaire par les différents routeurs entre les deux. La latence est mesurée en durée unidirectionnelle ou des boucles.

-   **Perte de paquets** : souvent définie comme un pourcentage de paquets qui sont perdus sur une période donnée. La perte de paquets affecte directement la qualité audio - de petits paquets individuels n’ayant pratiquement aucun impact à des pertes en rafale dos-à-dos qui entraîne une coupure complète du son.

-   **Instabilité entre les arrivées de paquets, ou simplement instabilité :** il s’agit du changement de délai moyen entre les paquets successifs. Les logiciels VoIP les plus récents, y compris Skype Entreprise, peuvent s’adapter à certains niveaux d'instabilité via la mise en mémoire tampon. Un participant ne remarquera les effets d'instabilité que si l’instabilité excède la mise en mémoire tampon.

Les valeurs maximales pour ces déficiences sont décrites dans la rubrique [Qualité des médias et performances de connectivité réseau](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance). Lors du test de ces déficiences, nous distinguons deux segments distincts :

-   Le *segment de périphérie* est le segment dans lequel réside votre routeur. Il s’agit du segment de réseau logique le plus proche connecté à internet à chacun de vos emplacements. Dans la plupart des cas, c’est le point de connexion du routeur, ou éventuellement un routeur de périmètre (appelés également *DMZ*, *zone démilitarisée* et *sous-réseau filtré*). Aucun autre trafic affectant les périphériques autre que le routeur ne doit avoir lieu entre ce segment et internet.

-   Le *segment de client* est le segment de réseau dans lequel résident vos clients.

Vous devez tester les deux segments à l’aide de l’outil d'évaluation du réseau. Pour tester le segment, accédez au répertoire et entrez **networkassessmenttool.exe** dans l'invite de commande. Les résultats sont écrits dans le fichier Results.tsv, et vous pouvez les comparer aux [conditions requises](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) pour chaque segment.

Notez que les deux segments doivent répondre aux exigences pour un déploiement de haute qualité. Nous vous recommandons d’exécuter l’outil plusieurs fois pendant une heure durant pour obtenir une bonne indication des performances de votre réseau.

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>Correction du réseau

Si les résultats de la planification de la bande passante, du test des ports ou du test des conditions requises pour le réseau indiquent que votre réseau actuel doit être corrigé avant de déployer Teams, vous pouvez le faire de différentes manières : 

-   Si la bande passante est insuffisante, mettez à niveau les connexions afin que le trafic vers Office 365 puisse circuler sans entrave.

-   Si des ports sont bloqués, modifiez les règles de pare-feu et testez à nouveau les ports.

-   En cas de déficiences du réseau, effectuez toujours une analyse de cause première.

QoS (qualité du service) peut être utilisé pour empêcher les déficiences en priorisant et en séparant le trafic. Certaines organisations choisissent de déployer QoS pour résoudre les problèmes de bande passante ou restreindre la qualité de trafic circulant. Cela n’améliorera pas la qualité et générera de nouveaux problèmes. Une analyse de cause première doit toujours être effectuée lorsque les déficiences du réseau excèdent les conditions requises. QoS peut être une solution. Pour pour plus d’informations, reportez-vous à la rubrique [Qualité de service dans Microsoft Teams](qos-in-teams.md).

>[!NOTE]
>De nombreux réseaux évoluent au fil du temps en raison des mises à niveau, de l'expansion ou d'autres exigences commerciales. Assurez-vous d'avoir des processus opérationnels en place pour maintenir ces secteurs dans le cadre de la planification de la gestion des services.


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Point de décision</td><td><ul><li>Qui sera chargé des évaluations du réseau nécessaires sur tous les segments du réseau et sites de l'organisation ?</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul><li>Vous pouvez effectuer une évaluation du réseau détaillée pour vous assurer que votre réseau est prêt pour le déploiement de Microsoft Teams. Pour plus d'informations, reportez-vous à la section [Évaluation de la préparation du réseau](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness).</li><li>Effectuez une correction du réseau en fonction des résultats de l’évaluation de la préparation réseau pour chaque segment du réseau.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="key-takeaways"></a>Principaux points à retenir

Voici les principaux points de ce guide à retenir. Vous devez :

-   Ouvrir les ports TCP 80 et 443 sortant des clients qui utiliseront Teams.

-   Ouvrir les ports TDP 3478 à 3481 sortant des clients qui utiliseront Teams.

-   Vérifier que vous disposez de suffisamment de bande passante pour déployer Teams en complétant le [Planificateur de réseau](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner).

-   Exécuter [l'outil d'évaluation du réseau](https://www.microsoft.com/download/details.aspx?id=53885) et vous assurer que vous respectez les conditions requises décrites dans la rubrique [Qualité des médias et performances de connectivité réseau](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) pour le segment de périphérie et le segment de client.
