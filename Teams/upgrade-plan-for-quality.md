---
title: Planifier la gestion et la qualité du service | Compatibilité technique
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dearbeen
audience: admin
description: Servez-vous de ces instructions pour en savoir plus sur les exigences nécessaires à la fourniture et au maintien d’un déploiement de Microsoft teams de haute qualité.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7b4d9f5033e0a3fb0446709438e670f6f9408de3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236505"
---
![Diagramme de route de mise à niveau, mettant l’accent sur l’étape de préparation technique] (media/upgrade-banner-tech-readiness.png "Étapes du parcours de la mise à niveau, en mettant l’accent sur l’étape de préparation technique")

Cet article fait partie de l’étape de préparation technique de votre mouvement de mise à niveau, une activité que vous finalisez en parallèle avec l’étape de préparation de l’utilisateur. Avant de continuer, assurez-vous d’avoir suivi les étapes ci-dessous:

- [Inscription des parties prenantes du projet](upgrade-enlist-stakeholders.md)
- [Définition de l’objectif de votre projet](https://aka.ms/SkypetoTeams-Scope)
- [Compréhension de la coexistence et de l’interopérabilité de Skype entreprise et équipes](https://aka.ms/SkypeToTeams-Coexist)
- [Choix de votre mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<!-- [!INCLUDE [envision-planning-for-service-management-and-quality-complete-guide](envision-planning-for-service-management-and-quality-complete-guide.md)]-->

# <a name="plan-for-quality"></a>Prévoir la qualité

Si vous déployez des fichiers audio, vidéo ou de réunion, vous pouvez effectuer des étapes supplémentaires pour optimiser votre environnement pour cette fonctionnalité. Ce contenu fournira une vue d'ensemble des exigences nécessaires à la livraison et au maintien d'un déploiement de Microsoft Teams de haute qualité. Vous pouvez garantir un déploiement réussi en planifiant la gestion et la qualité du service avant votre premier déploiement pilote ou en production.

Les directives sont organisées dans les sections suivantes :

- Le premier est une vue d'ensemble de l'expérience utilisateur et des composants clés qui sous-tendent la qualité. Ceci met en évidence les domaines sur lesquels il faut se concentrer avant d'intégrer Microsoft Teams.

- Deuxièmement, des conseils sont donnés pour la planification d'un modèle de soutien pour gérer Microsoft Teams avant le premier pilote utilisateur ou le déploiement en production. Cette section décrit les tâches qui doivent être effectuées sur une base régulière pour maintenir un déploiement de Teams de haute qualité. De plus, cette section vous présente d'autres conseils que vous pouvez utiliser pour commencer à comprendre et à mettre en œuvre ces tâches.

- Troisièmement, des conseils spécifiques aident à planifier votre réseau et les points de terminaison dans votre organisation pour soutenir Microsoft Teams.

- Enfin, les étapes suivantes sont résumées avec des références à des contenus connexes.

## <a name="key-technical-components-that-affect-user-experience"></a>Principaux composants techniques qui influent sur l’interface utilisateur

Les principaux composants techniques qui affectent l’utilisation de l’utilisateur seront examinés dans cette section. Avant de passer en revue les éléments clés, il est essentiel que vous compreniez l'expérience utilisateur et son importance dans la réalisation des objectifs commerciaux de votre organisation. Examinons d'abord comment nous définissons l'expérience utilisateur.

### <a name="user-experience-defined"></a>Définition de l'expérience utilisateur

Les objectifs de la société peuvent être réalisés lorsque vous déployez Microsoft teams et lorsque les utilisateurs adoptent teams comme solution de collaboration et de communication de base. La qualité peut vous aider à garantir une utilisation positive de l’utilisateur, un attribut clé dans le cas de l’utilisation et de l’adoption. En fournissant un service de grande qualité qui dégage des personnes, des personnes et des équipes, vous pouvez gagner en confiance et trouver de nouvelles manières novatrices d’utilisation du service pour les avantages de l’entreprise.

Au cœur de ce projet se trouve l'expérience utilisateur avec Teams, les émotions et les attitudes de la personne à l'égard du service. Qu'est-ce qui contribue à l'expérience utilisateur ? Il s’agit de la connaissance des utilisateurs qui connaissent le mode d’utilisation des équipes et de leur intégration dans leur flux de travail quotidien pour avoir une qualité d’appel exceptionnelle et être en mesure de se connecter de façon fiable, quel que soit l’endroit où ils se trouvent. L’utilisation est très générale en nature. Cet article se concentre sur les éléments techniques qui peuvent être contrôlés par votre organisation. Pour plus d’informations sur la disponibilité des utilisateurs, reportez- [vous à la rubrique préparer votre organisation pour teams](https://aka.ms/SkypeToTeams-UserReadiness).

Il existe des exigences spécifiques au déploiement qui sont d'une importance critique pour offrir une expérience utilisateur exceptionnelle, en particulier lors de l'utilisation des fonctions Cloud Voice dans Teams. Il est essentiel de traiter Microsoft Teams comme un citoyen de première classe avec d'autres investissements de communication et de collaboration, en priorisant en conséquence le trafic en temps réel. La section suivante donne un aperçu des éléments clés qui affectent l'expérience utilisateur. Dans d'autres sections, nous vous fournirons des conseils sur la façon de commencer à planifier le déploiement et la maintenance des composants clés qui comprennent la qualité.

### <a name="key-components-of-quality"></a>Éléments clés de la qualité

Une organisation ou un partenaire de support technique doit commencer à planifier trois composants clés au cours de l’étape de préparation technique du déploiement d’équipes: gestion des services, réseau et points de terminaison. La combinaison de ces trois domaines est fondamentale pour la qualité de l'expérience utilisateur.

![Diagramme illustrant les trois composantes de la qualité] (media/envision-planning-for-service-management-and-quality-complete-guide-image1.png "Diagramme illustrant les trois composantes de la qualité et mode de superposition des trois composants par la gestion des services.")

#### <a name="service-management"></a>Gestion des services

La gestion des services peut être divisée en deux catégories distinctes de responsabilité :

- **Responsabilité de Microsoft**. Microsoft est responsable des composants d'infrastructure que le service Office 365 comprend. Microsoft est responsable envers ses clients pour s'assurer que tous les utilisateurs qui se connectent à Teams bénéficient d'une expérience fiable et de haute qualité.

- **Responsabilité du client**. Vous et votre organisation êtes responsables de la gestion des différents aspects du service Office 365, du réseau sur site et des points de terminaison des utilisateurs. Par exemple, lorsque de nouvelles adresses IP sont ajoutées à Office 365, vous devez mettre à jour les pare-feu appropriés pour permettre la communication avec les nouveaux points de terminaison afin d'éviter toute perturbation de l'utilisateur.

Pour des conseils détaillés sur la planification de la gestion des services, voir [Plan de gestion des services](#plan-for-service-management).

#### <a name="network"></a>Réseau

Dans la plupart des organisations, les réseaux ont d'abord été conçus pour donner accès aux données et aux applications qui se trouvent dans leurs centres de données. Les applications basées sur le Cloud comme Office 365 nécessitent des modifications de ces réseaux pour prendre en charge les nouveaux accès et flux de données dont Teams a besoin. Avant de pouvoir activer les utilisateurs pour Teams dans votre organisation, vous devez évaluer et optimiser votre réseau actuel. C'est d'une importance capitale lorsque l'on utilise les capacités vocales du cloud computing.

Dans les réseaux traditionnels, les utilisateurs devront traverser les réseaux périmétriques d'une organisation pour accéder à Teams. De nombreuses organisations disposent de dispositifs de sécurité tels que les serveurs proxy, les pare-feu et les VPN qui peuvent bloquer, entraver ou fournir un chemin non optimisé pour le trafic réseau.

En outre, les réseaux internes de base doivent être optimisés et dimensionnés de manière à fournir une capacité et une qualité suffisantes pour supporter les charges de travail de Teams, y compris les médias en temps réel. Vous pouvez utiliser la planification, la correction et l'optimisation de la bande passante pour vous assurer que votre réseau offre un chemin de haute qualité et efficace vers Office 365.

Pour des conseils détaillés sur la planification du réseau, voir [Planifier la qualité du réseau](#plan-for-network-quality).

#### <a name="endpoints"></a>Points de terminaison

Microsoft Teams prend en charge une variété de points de terminaison. Qu'il s'agisse de PC, de tablettes ou de téléphones, vous pouvez accéder à Teams partout et à partir de presque tous les appareils.

Pour offrir à vos utilisateurs la meilleure utilisation possible, vous devez tenir compte des aspects suivants: les points de terminaison respectent-ils les exigences en matière de matériel et de logiciels de teams? Avez-vous configuré et optimisé les points de terminaison pour prendre en charge les réseaux Wi-Fi ? Quels appareils utiliserez-vous pour passer et recevoir des appels vocaux ? Ces appareils sont-ils optimisés pour Teams ?

Pour des conseils détaillés sur points de terminaison, voir [Planifier la qualité des points de terminaison](#plan-for-endpoint-quality).

## <a name="plan-for-service-management"></a>Plan de gestion des services

La gestion des services est un vaste sujet qui couvre les opérations quotidiennes du service Microsoft Teams après son déploiement et son activation pour les utilisateurs. Le service Teams englobe Microsoft Office 365 et les composants d'infrastructure déployés sur site (par exemple, la mise en réseau).

La notion de gestion des services n'est probablement pas un concept nouveau pour la plupart des organisations. Vous avez probablement déjà mis en œuvre des processus et des tâches qui sont associés à des services existants. Cela dit, vous pouvez probablement augmenter ce que vous avez en place lorsque vous planifiez la gestion des services aujourd'hui pour soutenir Microsoft Teams à l'avenir.

La gestion des services englobe toutes les activités et processus impliqués dans la gestion de bout en bout de Microsoft Teams. Comme décrit précédemment, certaines composantes de la gestion des services, les composantes de l'infrastructure que le service Office 365 comprend lui-même, relèvent de la responsabilité de Microsoft, alors que le client est responsable devant ses utilisateurs de la gestion des différents aspects de Teams, du réseau et des points de terminaison qu'ils fournissent. Cette section du document mettra l'accent sur la responsabilité du client du point de vue de la gestion des services.

![Diagramme illustrant les trois composantes de la qualité] (media/envision-planning-for-service-management-and-quality-complete-guide-image2.png "Diagramme illustrant les trois composantes de la qualité et mode de superposition des trois composants par la gestion des services. Le focus est axé sur la gestion des services.")

### <a name="introduction-to-the-operations-guide"></a>Introduction au Guide des opérations

**Quoi**, **Qui** et **Comment** sont trois questions importantes auxquelles il faut répondre lorsqu'il s'agit de la gestion des services.

Vous pouvez utiliser le [Guide des opérations](1-drive-value-operate-my-service.md) pour vous aider à répondre à ces trois questions. Le guide fournit une liste d'activités à réaliser sur une base quotidienne, hebdomadaire, mensuelle et selon les besoins. Ces activités et tâches sont essentielles au maintien d'un déploiement de Teams de haute qualité. Le fait de déterminer qui sera responsable de l’exécution d’activités spécifiques dans le cadre de la gestion des services est un aspect essentiel de votre planification que vous devez effectuer au préalable lors de la [phase de planification](upgrade-enlist-stakeholders.md) pour garantir un déploiement réussi. Une fois les tâches et les activités déterminées, elles doivent être comprises et suivies par les groupes ou les individus que vous leur assignez. Le Guide des opérations fournit des connaissances et des conseils sur la façon d'exécuter chacune des tâches et/ou des références à des contenus extérieurs.

### <a name="operational-role-mapping"></a>Mappage des rôles opérationnels

La planification précoce de la gestion des services est une étape critique, car la phase d'exploitation commence lorsque les premiers utilisateurs pilotes sont activés. L'équipe de projet doit examiner et s'entendre sur les tâches et les activités requises, identifier l'équipe responsable de chaque tâche opérationnelle, puis obtenir l'engagement et l'approbation de chaque équipe respective.

Une fois l'approbation terminée, l'équipe responsable doit alors commencer à mettre en œuvre ces rôles et responsabilités. Cela peut comprendre la formation et l'état de préparation, la mise à jour du modèle de dotation ou l'assurance que les partenaires externes sont prêts à livrer la marchandise.

Le fait de mapper les rôles opérationnels lors de la collecte de votre [équipe de projet](upgrade-enlist-stakeholders.md) permet à toutes les équipes de démarrer leurs tâches opérationnelles au cours du test, et de vérifier que tout est prêt après le démarrage du déploiement.

Le Guide des opérations fournit une liste des tâches communes mappées aux rôles typiques qui devraient être valides dans la plupart des scénarios. Vous devez personnaliser ces responsabilités pour travailler pour votre organisation.

### <a name="the-quality-champion-role"></a>Le rôle de Champion de la qualité

Un groupe ou un individu doit être responsable de la qualité dans toutes les organisations. Il s'agit du rôle le plus important dans la gestion des services. Le Champion de la qualité est un rôle de client assigné à une personne ou à un groupe passionné par l'expérience de ses utilisateurs. Ce rôle exige les compétences nécessaires pour cerner les tendances de l'environnement et le parrainage pour travailler avec d'autres équipes afin d'orienter les mesures correctives. Le meilleur candidat pour le champion de la qualité est généralement le propriétaire du service-clients qui, en fonction de la taille et de la complexité de l'organisation, peut être toute personne ou tout groupe passionné par l'expérience utilisateur.

Le champion de la qualité s'appuie sur les outils existants et les processus documentés, comme le Tableau de bord de la qualité des appels (CQD) et le Guide d'examen de l'expérience de la qualité, afin de surveiller l'expérience utilisateur, identifier les tendances de la qualité et mettre en œuvre, le cas échéant, des mesures correctives. Le champion de la qualité doit collaborer avec les équipes appropriées pour mettre en place des mesures correctrices, fournir des rapports à un comité directeur sur la progression et les problèmes ouverts.

Les tâches et les activités associées à ce rôle ont été documentées dans le Guide des opérations. Ce rôle doit être attribué lors de la [phase de planification](https://aka.ms/SkypeToTeams-Plan). Une étape clé dans la mise en œuvre du rôle de champion de la qualité consiste à acquérir les connaissances requises pour ce rôle et à s'assurer que les conditions préalables sont en place pour accomplir les tâches. L'une des tâches clés de ce rôle est d'effectuer un examen régulier de l'expérience de la qualité.

### <a name="introduction-to-the-quality-experience-review-guide"></a>Introduction au Guide d'examen de l'expérience de la qualité

Le Guide d'examen de l'expérience de la qualité comporte un ensemble d'activités qui évaluent et fournissent des conseils en matière de remédiation dans les domaines clés qui ont le plus grand impact sur l'amélioration de l'expérience utilisateur, comme le montre la figure ci-dessous.

![Diagramme illustrant des zones examinées lors] de l’évaluation de l’interface qualité (media/envision-planning-for-service-management-and-quality-complete-guide-image3.png "Diagramme illustrant les principales zones examinées lors d’un examen de l’interface qualité.")

En évaluant et en corrigeant continuellement les zones décrites dans ce document, vous pouvez réduire leur potentiel d'affecter négativement l'expérience utilisateur. La plupart des problèmes d'expérience utilisateur rencontrés lors d'un déploiement peuvent être regroupés dans les catégories suivantes :

- Configuration incomplète du pare-feu ou du proxy

- Faible couverture Wi-Fi

- Bande passante insuffisante

- VPN

- Utilisation d'appareils audio non optimisés ou intégrés

- Sous-réseaux ou périphériques réseau problématiques

Les conseils fournis dans le Guide d'examen de l'expérience de qualité portent sur l'utilisation du CQD en ligne comme outil principal pour rapporter et enquêter sur chaque domaine décrit, en mettant l'accent sur l'audio pour maximiser l'adoption et l'impact. Toutes les optimisations apportées au réseau pour améliorer l'expérience audio se traduiront aussi directement par des améliorations dans le partage de la vidéo et du bureau.

Nous vous recommandons fortement de nommer le Champion de la qualité le plus tôt possible. Après avoir été nommé, il doit commencer à se familiariser avec le contenu dans le Guide d’examen de l’expérience qualité.

Le Guide d'examen de l'expérience de qualité se trouve [ici](https://aka.ms/qerguide).

## <a name="plan-for-network-quality"></a>Planifier la qualité du réseau

La planification de la qualité du réseau sera au centre de la section suivante.

![Diagramme illustrant les trois composantes de la qualité] (media/envision-planning-for-service-management-and-quality-complete-guide-image4.png "Diagramme illustrant les trois composantes de la qualité et mode de superposition des trois composants par la gestion des services. Avec le focus du réseau.")

Comme mentionné précédemment, la planification de la qualité du réseau avant l'intégration à Microsoft Teams est essentielle. Pour de plus amples informations sur l'état de préparation du réseau, voir [Préparer le réseau de votre organisation pour Microsoft Teams](prepare-network.md).

Dans la plupart des organisations, les réseaux peuvent comprendre des réseaux gérés et non gérés.

Les réseaux gérés sont des composantes de l'infrastructure réseau sur lesquelles une organisation exerce un contrôle direct. Par conséquent, les réseaux gérés ont une influence directe sur la qualité qui peut être fournie aux charges de travail du trafic en temps réel.

Inversement, les réseaux non gérés sont des segments du réseau sur lesquels un client n'a qu'un contrôle limité, ou aucun contrôle.

Les connexions Internet entre l'organisation et Office 365 sont des réseaux sur lesquels un client a un contrôle limité. Les réseaux sont gérés par un fournisseur d'accès Internet (FAI), mais les organisations devraient être en mesure d'influencer la qualité du réseau en améliorant leur bande passante, en préconisant l'optimisation des routes ou, en cas d'échec, en commutant les FAI.

Les réseaux domestiques ou les réseaux dans les hôtels ou les cafés sont des exemples de réseaux sur lesquels un client n'a aucun contrôle.

Dans les sections suivantes, nous concentrerons sur les exigences de qualité des réseaux gérés.

### <a name="key-network-planning-areas"></a>Principaux domaines de planification du réseau

Les sections suivantes se concentrent sur les domaines importants pour la mise en place d'un réseau de haute qualité.

> [!NOTE]
> De nombreux réseaux évoluent au fil du temps en raison des mises à niveau, de l'expansion ou d'autres exigences commerciales. Assurez-vous d'avoir des processus opérationnels en place pour maintenir ces secteurs dans le cadre de la planification de la gestion des services.

#### <a name="bandwidth"></a>Bande passante

La planification de la bande passante est un aspect critique de l'activité de préparation du réseau. Il est impératif de s'assurer qu'il y a suffisamment de bande passante pour les charges de travail de Microsoft Teams. Pour pouvoir redimensionner un réseau existant, vous devez comprendre ce qui est actuellement provisionné, l'utilisation actuelle et, finalement, la bande passante disponible restante.

Pour mesurer l'utilisation actuelle, vous devez surveiller le réseau. Cette mesure peut ensuite servir de point de départ pour la planification de la bande passante. En outre, le réseau devrait faire l'objet d'une surveillance continue pendant et après le déploiement afin de s'assurer que le réseau est suffisamment approvisionné.

> [!NOTE]
> Lorsque vous surveillez l'utilisation du réseau, il est important d'éviter d'utiliser des moyennes sur la journée. Ces moyennes peuvent inclure des heures non essentielles qui faussent le résultat. Les moyennes peuvent cacher les périodes de pointe et masquer un problème sous-jacent.

#### <a name="quality-of-service-qos"></a>Qualité de service (QoS)

La QoS devrait être mise en œuvre sur tous les segments du réseau géré, même les réseaux qui ont été suffisamment provisionnés pour la bande passante. Dans ce dernier cas, la QoS sert à atténuer les risques en cas de charge imprévue sur le réseau. Lorsque la QoS sera mise en œuvre, le trafic vocal sera priorisé afin que ces événements imprévus n'affectent pas la qualité.

Une implémentation de la QoS doit inclure des zones du réseau, depuis le point d'extrémité jusqu'aux points de sortie et depuis les points de sortie jusqu'au point de terminaison. Cela permettra de s'assurer que le trafic vocal est prioritaire dans les deux sens. La QoS doit être mise en œuvre à la fois sur les réseaux câblés et Wi-Fi.

Pour implémenter la QoS sur votre réseau, les conseils suivants peuvent vous aider à améliorer la [Qualité de service dans Microsoft Teams](qos-in-teams.md)

#### <a name="proxy-servers"></a>Serveurs proxy

De nombreuses organisations considèrent le trafic destiné à Internet comme un risque pour la sécurité, et elles atténuent ce risque en surveillant et en évaluant le trafic aux points de sortie du réseau. Les serveurs proxy sont une classe de dispositifs qui peuvent être déployés pour répondre à cette exigence.

Un serveur proxy peut introduire des problèmes lors de l'inspection des paquets ou de la modification de la charge utile. Cela peut entraîner des échecs de configuration des appels, des coupures d'appels et une mauvaise qualité d'appel. Si les médias en temps réel sont forcés de traverser un serveur proxy, la pile de médias dans les équipes sera forcée d'échouer de nouveau à TCP, ce qui peut réduire davantage la qualité. UDP est toujours préféré à TCP.

En outre, un serveur proxy peut ne pas être conçu pour gérer la charge supplémentaire d'Office 365, et plus particulièrement les charges de travail de Microsoft Teams, y compris les médias en temps réel.

En raison des problèmes potentiels qu'un serveur proxy peut introduire et de ces problèmes de capacité supplémentaire, Microsoft recommande de contourner le serveur proxy et d'établir une connexion directe avec Office 365.

La configuration requise pour contourner le serveur proxy varie d'un fournisseur à l'autre, mais l'approche courante consiste généralement à mettre à jour le fichier PAC (fichier de configuration automatique de proxy). Le fichier PAC est un fichier de configuration qui décrit quel trafic passe par le proxy et quel trafic le contourne.

Certains fournisseurs de serveurs proxy proposent un processus automatisé pour s'assurer que la configuration est à jour. Si votre fournisseur ne fournit pas ce processus automatique, vous pouvez télécharger un fichier PAC mis à jour à partir de <https://aka.ms/o365proxies>.

[Serveurs proxy pour teams ou Skype entreprise Online et Teams](proxy-servers-for-skype-for-business-online.md)

#### <a name="firewalls"></a>Pare-feu

Il est nécessaire de s'assurer que les bons ports et protocoles sont ouverts à toutes les adresses IP et URL Office 365 pour avoir accès à Microsoft Teams. C'est également essentiel pour un déploiement de haute qualité. Il ne suffit pas de passer un appel ou de participer à une conférence téléphonique pour s'assurer que votre pare-feu est correctement configuré.

Si seul TCP est ouvert sur le pare-feu, la session sera établie, mais le transport préféré (UDP) n'est pas négocié. TCP et UDP doivent être ouverts sur le pare-feu pour offrir la meilleure expérience utilisateur.

En raison de sa nature dynamique, TCP n'est pas préféré pour les médias en temps réel et n'est fourni qu'en tant que transport réseau de reprise pour Microsoft Teams. Avec TCP, en cas de retard ou de perte de paquets, ces derniers doivent être retransmis jusqu'à ce qu'ils soient reconnus. Cela peut donner lieu à des paquets de médias qui ne sont plus pertinents et qui sont en concurrence avec la livraison en temps opportun des paquets de médias actuels. Le client Teams de l'utilisateur tente d'étirer l'audio et peut produire des artefacts audibles en fonction des conditions du réseau. Avec les frais généraux supplémentaires du TCP, une expérience généralement acceptable peut se transformer en une mauvaise expérience utilisateur. Pour cette raison, le réseau de transport sans état UDP est nécessaire.

Des conseils complets sur l'ouverture du pare-feu pour Microsoft Teams sont fournis dans l'article [Plages d'adresses URL et IP d’Office 365](https://aka.ms/o365ips).

Après l'ouverture du pare-feu, vous pouvez utiliser  [l'Outil d'évaluation du réseau Microsoft](https://www.microsoft.com/download/details.aspx?id=53885)  pour valider la connectivité des capacités de Cloud Voice.

> [!IMPORTANT]
> Les adresses IP et URL de Microsoft Office 365 changeront au fil du temps. Dans le cadre de la planification de la gestion des services, il est important de s'assurer qu'un processus opérationnel est en place et qu'un groupe est responsable de surveiller les [Plages d'adresses URL et IP d’Office 365](https://aka.ms/o365ips) et d'effectuer les mises à jour en conséquence.

#### <a name="local-internet-egress"></a>Sortie Internet locale

De nombreux réseaux ont été conçus pour utiliser une topologie de hub et parlée. Dans cette topologie, le trafic Internet traverse généralement le WAN jusqu'à un centre de données central avant qu'il n'émerge (sorties) vers Internet. Souvent, cela est fait pour centraliser les dispositifs de sécurité du réseau dans le but de réduire les coûts globaux.

Relayer le trafic sur le WAN augmente la latence et a un impact négatif sur la qualité et l'expérience utilisateur. Comme Microsoft Teams fonctionne sur le vaste réseau mondial de Microsoft, il existe souvent un emplacement réseau de pairage à proximité de l'utilisateur. Un utilisateur obtiendra probablement de meilleures performances en sortant d'un point Internet local près de son emplacement et sur notre réseau à voix optimisée dès que possible. Pour certaines charges de travail, les requêtes DNS sont utilisées pour envoyer du trafic vers le serveur frontal le plus proche. Dans de tels cas, il est important que lors de l'utilisation d'un point d'évacuation local, il soit couplé avec la résolution DNS locale.

L'optimisation du chemin d'accès au réseau mondial de Microsoft améliorera les performances et, en fin de compte, offrira la meilleure expérience aux utilisateurs. Pour plus de détails, voir l'article du blog [Obtenir la meilleure connectivité et les meilleures performances dans Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

#### <a name="vpn"></a>VPN

Les VPN fournissent un service de valeur à de nombreuses organisations. Malheureusement, ils ne sont généralement pas conçus ou configurés pour prendre en charge les médias en temps réel. Certains VPN peuvent également ne pas prendre en charge UDP. Les VPN introduisent également une couche supplémentaire de cryptage en plus du trafic média déjà crypté. En outre, la connectivité au service Microsoft Teams pourrait ne pas être efficace en raison du hairpinning du trafic à travers un dispositif VPN. De plus, ils ne sont pas nécessairement conçus du point de vue de la capacité pour répondre aux charges prévues dont les é

La recommandation est de fournir un chemin alternatif qui contourne le VPN pour le trafic de Teams. Cela s’appelle généralement un VPN de tunnel segmenté. La segmentation de tunnel signifie que le trafic d'Office 365 ne traversera pas le VPN mais ira directement vers Office 365. Ce changement aura un impact positif sur la qualité, mais aussi l'avantage secondaire de réduire la charge des dispositifs VPN et du réseau de l'organisation.

Pour mettre en œuvre un tunnel segmenté, consultez votre fournisseur VPN pour les détails de configuration.

#### <a name="wi-fi"></a>Wi-Fi

Tout comme le VPN, les réseaux Wi-Fi ne sont pas nécessairement conçus ou configurés pour prendre en charge les médias en temps réel. La planification et/ou l'optimisation d'un réseau Wi-Fi pour supporter Teams est une considération importante pour un déploiement de qualité.

Plusieurs facteurs entrent en jeu pour optimiser un réseau Wi-Fi.

- Mettre en œuvre la QoS ou le Wi-Fi Multimedia (WMM) pour s'assurer que le trafic média est priorisé en conséquence sur les réseaux Wi-Fi.

- Planification et optimisation des bandes W-Fi et de l'emplacement des points d'accès. La gamme de 2,4 GHz peut fournir une expérience adéquate en fonction de l'emplacement des points d'accès, mais les points d'accès sont souvent affectés par d'autres appareils grand public qui fonctionnent dans cette gamme. La gamme de 5 GHz est mieux adaptée aux médias en temps réel en raison de leur portée dense, mais nécessite plus de points d'accès pour obtenir une couverture suffisante. Les points de terminaison doivent également prendre en charge cette plage et être configurés pour exploiter ces bandes en conséquence.

- Si des réseaux Wi-Fi à double bande sont déployés, songez à mettre en place un système de direction de bande. La direction de bande est une technique mise en œuvre par les fournisseurs de Wi-Fi pour inciter les clients à double bande à utiliser la gamme 5 Ghz.

- Superposition des canaux – Lorsque les points d'accès d'un même canal sont trop proches les uns des autres, ils peuvent provoquer une superposition des signaux et une concurrence involontaire, ce qui entraîne une mauvaise expérience pour l'utilisateur. Veillez à ce que les points d'accès voisins se trouvent sur des canaux qui ne se superposent pas.

Chaque fournisseur de services sans fil a ses propres recommandations pour le déploiement de sa solution sans fil. Nous vous recommandons de consulter votre fournisseur pour obtenir des conseils spécifiques.

### <a name="network-readiness-assessment"></a>Évaluation de la préparation réseau

Une partie des activités de préparation du réseau comprend une évaluation du réseau. Une fois que vous avez terminé votre planification et votre configuration, l'évaluation peut vous donner une compréhension de base de la qualité de votre réseau avant que ayez intégré des utilisateurs à Microsft Teams. Les résultats de l'évaluation vous aideront également à identifier et à prioriser les efforts de remédiation avant d'autoriser les utilisateurs pour les équipes.

L'évaluation du réseau devrait être effectuée à la fois sur les réseaux câblés et Wi-Fi pour tous les bâtiments qui sont activés pour les capacités de Cloud Voice dans Teams.

L'évaluation du réseau peut être effectuée à l'aide d'un partenaire Microsoft, d'outils tiers ou de l’[Outil d'évaluation du réseau Microsoft](https://www.microsoft.com/download/details.aspx?id=53885).

## <a name="plan-for-endpoint-quality"></a>Planifier la qualité des points de terminaison

Comme vous pouvez le voir sur le diagramme ci-dessous, les points de terminaison sont un élément important pour offrir une expérience de haute qualité aux utilisateurs.

![Diagramme illustrant les trois composantes de la qualité] (media/envision-planning-for-service-management-and-quality-complete-guide-image5.png "Diagramme illustrant les trois composantes de la qualité et mode de superposition des trois composants par la gestion des services. Le focus est axé sur les points de terminaison.")

Les points de terminaison Microsoft Teams peuvent fonctionner sur de nombreux appareils, y compris les PC, les Mac, les tablettes et les appareils mobiles. Une partie de l'expérience ne comprend pas seulement l'appareil, mais aussi la façon dont l'utilisateur se connecte à l'appareil, par exemple en utilisant le micro/haut-parleur intégré de l'appareil, les écouteurs ou un casque optimisé. L'utilisation d'un casque optimisé peut enrichir l'expérience globale de l'utilisateur.

Les conseils suivants sur la planification des points de terminaison vous aideront à vous assurer que votre organisation a une expérience d'intégration réussie avec Teams.

### <a name="endpoint-capability"></a>Capacité des points de terminaison

La première partie de la planification est de s'assurer que tous les PC et autres périphériques de votre organisation peuvent exécuter Microsoft Teams. Il ne s'agit pas seulement d'examiner les exigences matérielles, mais aussi de comprendre ce que le PC fait d'autre en arrière-plan. De nombreuses organisations utilisent d'autres logiciels, y compris les systèmes de détection d'intrusion et les logiciels antimalware, qui peuvent affecter les performances de base d'un appareil.

Teams dispose de clients Web, de bureau (Windows et Mac) et mobiles (Android, iOS et Windows Mobile). Pour plus d'informations sur les exigences logicielles pour chaque plateforme, voir [Obtenir des clients pour Microsoft Teams](get-clients.md).

### <a name="endpoint-firewalls"></a>Pare-feu des points de terminaison

Les pare-feu côté client peuvent avoir un impact significatif sur l'expérience utilisateur. Les pare-feu côté client peuvent affecter la qualité des appels en plus d'empêcher l'établissement d'un appel. Configurez les exclusions appropriées sur le pare-feu du client en fonction des informations contenues dans [Plages d'adresses URL et IP d’Office 365](https://aka.ms/o365ips). Votre fournisseur tiers recevra des directives précises sur la façon de créer les exclusions.

> [!NOTE]
> Les équipes Microsoft mettront automatiquement à jour le pare-feu Windows avec une configuration de pare-feu appropriée.

### <a name="wi-fi-recommendations-for-endpoints"></a>Recommandations Wi-Fi pour les points de terminaison

La planification et le déploiement d'un réseau Wi-Fi optimisé pour prendre en charge les charges de travail en temps réel dans Microsoft Teams nécessiteront une planification importante. Les sections suivantes fournissent des conseils généraux qui peuvent vous aider à éviter certains pièges courants lors de la planification des paramètres.

#### <a name="wi-fi-drivers"></a>Pilotes Wi-Fi

Certains pilotes Wi-Fi peuvent poser problème. Par exemple, un pilote peut avoir des comportements d'itinérance très agressifs entre les points d'accès, provoquant une mauvaise qualité d'appel. Il ne s'agit pas d'un phénomène courant, mais il est important de s'assurer que les pilotes Wi-Fi du PC ont été mis à jour et testés avant le déploiement.

#### <a name="wi-fi-bands"></a>Bandes Wi-Fi

Il existe principalement deux types de bandes utilisées aujourd'hui dans les équipements Wi-Fi : 2,4 GHz et 5,0 GHz. Si votre organisation fournit les deux bandes, vous devez configurer les paramètres de votre pilote pour préférer la bande 5,0 GHz. Cette bande est beaucoup plus dense en termes de débit et est moins affectée par les interférences observées dans la bande de 2,4 GHz. Cette recommandation suppose que vous avez correctement optimisé la bande de réseau de 5,0 GHz.

#### <a name="wi-fi-radio-type"></a>Type de radio Wi-Fi

Prévoyez des appareils qui prennent en charge les nouveaux types de radio Wi-Fi. Vous pouvez obtenir de très bonnes performances Wi-Fi si vous utilisez 802.11ac ou plus récent sur les appareils que vous approvisionnez.

#### <a name="wireless-avoidance"></a>Évitement sans fil

Certaines organisations préfèrent éviter complètement le Wi-Fi. Parfois, ces conseils sont fournis par le biais d'une recommandation aux utilisateurs de se connecter directement à un réseau câblé. Dans certains cas, l'ordre de liaison réseau peut avoir la préférence pour la connexion sans fil et continuer à utiliser cette connexion même si le PC est connecté à la connexion câblée. Pour éviter ce scénario involontaire, configurez l'ordre de liaison.

#### <a name="80211-power-save-protocol"></a>Protocole d'économie d'énergie 802.11

Si votre organisation utilise des points d'accès sans fil ou des routeurs qui ne prennent pas en charge le protocole d'économie d'énergie 802.11, vous pourriez constater des coupures d'appels ou une mauvaise qualité d'appel dans Microsoft Teams lorsqu'il fonctionne sur des appareils Windows. Si la mise à niveau de votre point d'accès sans fil ou de vos routeurs est impossible, vous devez mettre à jour les paramètres du plan d'alimentation Windows sur les appareils fonctionnant sur batterie. De plus amples détails et des conseils de configuration sont fournis dans l'[article de support](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you) suivant.

### <a name="devices-for-teams"></a>Appareils pour Teams

Microsoft Teams peut être utilisé pour des réunions ou comme système téléphonique. Lors de l'utilisation de ces fonctions, le dispositif d'interface utilisé pour Teams joue un rôle important dans l'expérience utilisateur.

L'utilisation d'un haut-parleur et d'un microphone d’ordinateur portable intégrés peut sembler acceptable pour l'utilisateur qui dispose de cette configuration. Toutefois, ces appareils ne sont généralement pas optimisés pour l'annulation du bruit, et tout type de bruit ambiant peut avoir un impact en aval sur les autres participants à l’appel. L'utilisation d'appareils optimisés pour ces scénarios contribuera à assurer une expérience de haute qualité.

Chaque appareil doit répondre aux besoins de vos utilisateurs. Vous devrez adapter les appareils tels que les casques pour les différentes personnes et les cas d'utilisation dans votre organisation. Un exercice de mappage personne à appareil devrait être effectué dans le cadre du processus de planification.

Une fois que vous avez sélectionné les appareils, incluez-les dans le plan d'essai pilote pour la validation finale. Tirez parti des sondages pendant le projet pilote pour recueillir des commentaires afin de vous assurer que la stratégie de votre appareil est optimale.

Pour l'instant, nous vous recommandons d'utiliser des appareils audio certifiés dans le cadre du programme de certification Skype Entreprise. Pour trouver les appareils certifiés dans le cadre de ce programme, consultez le catalogue des solutions [Appareils USB certifiés pour Skype Entreprise](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs).

## <a name="client-updates"></a>Mises à jour du client

L'un des principaux avantages de Microsoft Teams est que le client est tenu à jour automatiquement. Les clients sur PC et Mac sont mis à jour à l'aide d'un processus en arrière-plan qui vérifie les nouvelles versions et télécharge le nouveau client lorsque l'application est inactive. La taille de téléchargement du client est d'environ 100 Mo.

Une organisation n'a aucun contrôle ou accès à un paramètre de stratégie pour gérer le processus de mise à jour. Pour atténuer le risque d'un problème qui pourrait être découvert dans une nouvelle version, la dernière version valide connue est conservée sur le point de terminaison. En cas de problème avec une nouvelle version, le service Microsoft Teams peut revenir automatiquement à la version précédente.

## <a name="next-steps-and-references"></a>Prochaines étapes et références

Ce tableau comprend un résumé des activités de planification avec des liens vers des contenus connexes.

| Domaine | Détails | Références |
|---|---|---|
| Plan de gestion des services | Mener un exercice de mappage des rôles opérationnels <br/> Se déconnecter des équipes responsables <br/> Préparation des rôles | [Guide des opérations](1-drive-value-operate-my-service.md) |
| | Nommer un ou plusieurs Champions de la qualité <br/> Préparation du Champion de la qualité| <br/> [Guide d'examen de l'expérience de qualité](https://aka.ms/qerguide) |
| | Installer les modèles du Guide d'examen de l'expérience de qualité <br/> Charger un fichier de construction | [Modèles QERLite](https://aka.ms/qertemplates) <br/> [Charger les informations sur la construction](turning-on-and-using-call-quality-dashboard.md)|
| Planifier la qualité du réseau | Planification du réseau |  |
| | Mettre en œuvre la QoS | [Qualité de service (QoS) dans Microsoft Teams](qos-in-teams.md) |
| | Contourner les serveurs proxy | [Guide des proxy](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a) |
| | Implémenter un VPN en tunnel segmenté |  |
| | Optimiser les réseaux Wi-Fi pour les médias en temps réel | Consulter les fournisseurs tiers |
| | Mettre en œuvre la sortie Internet locale | [Sortie Internet locale](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694) |
| | Mettre en œuvre la connectivité réseau <br/> Valider la connectivité réseau | [URL et plages d'adresses IP Office 365](https://aka.ms/o365ips) |
| | Effectuer l'évaluation du réseau |[Outil d'évaluation du réseau](https://www.microsoft.com/download/details.aspx?id=53885)  |
| Planifier la qualité des points de terminaison | Mettre à jour les pare-feu des points de terminaison | [URL et plages d'adresses IP Office 365](https://aka.ms/o365ips) |
| | Valider les exigences logicielles | [Obtenir des clients pour Microsoft Teams](get-clients.md) |
| | Mettre en œuvre les recommandations Wi-Fi pour les points de terminaison | Consulter les fournisseurs tiers |
| | Effectuer le mappage de la personne vers les appareils <br/> Prévoir des appareils et les piloter |<br/> [Catalogue d'appareils](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) |

Lorsque vous avez terminé la planification, passez à l’étape suivante: [préparer votre environnement pour teams](https://aka.ms/SkypeToTeams-TechnicalReadiness).
