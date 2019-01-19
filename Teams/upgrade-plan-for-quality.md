---
title: Planifier la gestion des services et la qualité | Préparation technique
author: turgayo
ms.author: turgayo
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Utilisez ce guide pour en savoir plus sur les conditions qui sont nécessaires pour fournir et mettre à jour un déploiement de Microsoft Teams haute qualité.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: 59c881c6c40b8877fee46e3956970a0c305d0a4a
ms.sourcegitcommit: 716d39077784417c3545a91e501ae26ff56ebdf4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/19/2019
ms.locfileid: "29349528"
---
![Étapes du voyage mise à niveau, en mettant l’accent sur l’étape de préparation technique] (media/upgrade-banner-tech-readiness.png "Étapes du voyage mise à niveau, en mettant l’accent sur l’étape de préparation technique")

Cet article fait partie de la phase de préparation technique de votre parcours de mise à niveau, une activité que vous effectuez en parallèle à l’étape de préparation des utilisateurs. Avant de continuer, vérifiez que vous avez terminé ces activités à partir des étapes précédentes :

- [Inscrit les parties prenantes du projet](upgrade-enlist-stakeholders.md)
- [Définies par l’étendue de votre projet](https://aka.ms/SkypetoTeams-Scope)
- [Comprendre la coexistence et l’interopérabilité de Skype pour professionnels et les équipes](https://aka.ms/SkypeToTeams-Coexist)
- [Choisi votre parcours de mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<!-- [!INCLUDE [envision-planning-for-service-management-and-quality-complete-guide](envision-planning-for-service-management-and-quality-complete-guide.md)]-->

# <a name="plan-for-quality"></a>Prévoir la qualité

Si vous déployez audio, vidéo ou des réunions, vous pouvez tirer quelques étapes supplémentaires pour optimiser votre environnement pour cette fonctionnalité. Ce contenu fournit une vue d’ensemble de la configuration requise qui sont nécessaires pour fournir et mettre à jour un déploiement de Microsoft Teams haute qualité. Pour garantir un déploiement réussi à la planification de la gestion des services et de qualité, avant le premier déploiement pilote ou de production.

Les instructions sont organisées dans les sections suivantes :

- Tout d’abord est une vue d’ensemble de l’expérience utilisateur et les composants clés base qualité. Cela met en évidence les zones à consacrer avant l’intégration à Microsoft Teams.

- Deuxièmement, est fournie pour la planification d’un modèle de prise en charge pour gérer Microsoft Teams avant le premier déploiement pilote ou de production. Cette section décrit les tâches qui doivent être effectuées régulièrement pour maintenir un déploiement d’équipes de haute qualité. En outre, cette section vous présente des instructions supplémentaires que vous pouvez utiliser pour comprendre et à mettre en application ces tâches.

- Troisième des instructions spécifiques permet à la planification de votre réseau et les points de terminaison dans votre organisation pour prendre en charge Microsoft Teams.

- Enfin, les étapes suivantes sont résumées avec des références vers du contenu connexe.

## <a name="key-technical-components-that-affect-user-experience"></a>Composants techniques clés qui affectent l’expérience utilisateur

Les composants techniques clés qui affectent l’expérience utilisateur seront revus dans cette section. Avant d’examiner les composants clés, il est essentiel de bien comprendre l’expérience utilisateur et son importance dans la réalisation des objectifs de votre organisation. Examinons comment nous définir tout d’abord l’expérience utilisateur.

### <a name="user-experience-defined"></a>Expérience utilisateur défini

Objectifs de l’entreprise peuvent être réalisés lorsque vous déployez Microsoft Teams et lorsque les utilisateurs prennent des équipes de leur solution de collaboration et de communication de base. Qualité peut aider à garantir une expérience utilisateur positive, un attribut de clé dans la conduite d’utilisation et d’adoption. En fournissant un service de haute qualité qui Cajun delights personnes, personnes et les équipes peuvent obtenir le niveau de confiance et trouvez une manière innovante d’utilisation du service bénéfices ce lecteur.

Au cœur de ceci est l’expérience utilisateur avec des équipes — émotions et attitude le service de la personne. Ce qui contribue à l’expérience utilisateur ? Il est compris entre des utilisateurs savoir pourquoi et comment utiliser les équipes et les intégrer dans leur travail quotidien à la qualité des appels exceptionnelles et de se connecter en toute sécurité, où qu’ils soient. Expérience utilisateur est très vaste nature ; Cet article se concentre uniquement sur les éléments techniques qui peuvent être contrôlés par votre organisation. Vous trouverez plus d’informations sur la préparation des utilisateurs dans [votre organisation pour les équipes de préparer](https://aka.ms/SkypeToTeams-UserReadiness).

Il existe des exigences spécifiques au déploiement qui sont extrêmement importantes pour fournir une expérience utilisateur fantastique, en particulier lorsque à l’aide de la voix dans le nuage fonctionnalités dans les équipes. Il est essentiel de traiter Teams Microsoft comme un acteur avec d’autres investissements de communication et de collaboration, ordre de priorité le trafic en temps réel en conséquence. La section suivante donne une vue d’ensemble des composants clés qui affectent l’expérience utilisateur. Dans les autres sections, nous vous proposons des instructions sur la façon de commencer à planifier déployer et gérer les composants clés qui composent la qualité.

### <a name="key-components-of-quality"></a>Composants clés de la qualité

Une organisation ou un partenaire de prise en charge doit démarrer pendant la phase de préparation technique d’un déploiement d’équipes de planification pour les trois composants principaux : gestion, réseau et points de terminaison de service. La combinaison de tous les trois zones est essentielle pour la qualité de l’expérience utilisateur.

![Diagramme illustrant les trois composants de qualité et de la gestion des services chevauche les trois composants.] (media/envision-planning-for-service-management-and-quality-complete-guide-image1.png "Diagramme illustrant les trois composants de qualité et de la gestion des services chevauche les trois composants.")

#### <a name="service-management"></a>Gestion des services

Gestion de service peut être répartis en deux catégories distinctes de responsabilité :

- **Responsabilité de Microsoft**. Microsoft est chargé pour les composants d’infrastructure qui comprend le service Office 365. Microsoft est responsable pour les clients pour s’assurer qu’une de leurs utilisateurs se connectent aux équipes est fourni avec une expérience fiable et de haute qualité.

- **Responsabilité du client**. Vous et votre organisation sont chargés de gérer les différents aspects du service Office 365, réseau local et points de terminaison utilisateur. Par exemple, comme les nouvelles adresses IP sont ajoutées à Office 365, vous devez mettre à jour le pare-feu pour permettre la communication aux nouveaux points de terminaison pour éviter les interruptions de l’utilisateur approprié.

Pour obtenir des instructions détaillées pour la gestion des services de planification, voir [planifier la gestion des services](#plan-for-service-management).

#### <a name="network"></a>Réseau

Dans la plupart des organisations, réseaux ont été initialement conçus pour fournir un accès aux données et les applications qui se trouvaient dans leurs centres de données. Les applications basées sur le nuage tels qu’Office 365 nécessitent des modifications apportées à ces réseaux pour prendre en charge les nouveaux flux accéder aux données et qui nécessite des équipes. Avant de pouvoir activer les utilisateurs pour les équipes de votre organisation, vous devez évaluer et optimiser votre réseau actuel. Il est essentiel en tirant parti des fonctionnalités de voix dans le nuage.

Dans les réseaux traditionnels, les utilisateurs devront traverser les réseaux de périmètre d’une organisation pour accéder aux équipes. Bon nombre d’organisations ont basée sur la sécurité des appareils tels que des serveurs proxy, les pare-feu et VPN qui peuvent bloquer, entraver ou fournissent un chemin d’accès non optimisé pour le trafic réseau.

En outre, les réseaux internes principaux doivent être optimisée et adaptée pour fournir suffisamment de capacité et de qualité pour prendre en charge les charges de travail d’équipes, y compris les médias en temps réel. Vous pouvez utiliser la bande passante de la planification, la mise à jour, et l’optimisation pour s’assurer de votre réseau fournit un chemin d’accès de haute qualité et efficace à Office 365.

Pour obtenir des instructions détaillées sur la planification du réseau, voir [planifier la qualité du réseau](#plan-for-network-quality).

#### <a name="endpoints"></a>Points de terminaison

Teams Microsoft prend en charge une variété de systèmes d’extrémité. De PC tablettes aux téléphones, vous pouvez accéder aux équipes n’importe où à partir de n’importe quel appareil.

Pour donner aux utilisateurs la meilleure expérience possible, vous devez prendre en compte ces aspects importants : vos points de terminaison répondent aux exigences matérielles et logicielles équipes ? Avez-vous configurée et optimisée des points de terminaison pour prendre en charge les réseaux Wi-Fi ? Les périphériques utilisera pour émettre et recevoir des appels vocaux ? Ces périphériques optimisés pour les équipes ?

Pour obtenir des instructions détaillées sur la planification du point de terminaison, voir [Plan pour la qualité du point de terminaison](#plan-for-endpoint-quality).

## <a name="plan-for-service-management"></a>Plan de gestion des services

Gestion des services est un sujet vaste qui traite des opérations quotidiennes du service Microsoft Teams après que qu’il a été déployé et activé pour les utilisateurs. Le service d’équipes englobe Microsoft Office 365 et les composants d’infrastructure qui sont déploiement en local (par exemple, mise en réseau).

La notion de gestion des services n’est probablement pas un nouveau concept pour la plupart des organisations. Vous probablement avez déjà mise en œuvre des processus et les tâches qui sont associés à des services existants. Cela étant dit, vous pouvez enrichir probablement que vous avez en place lorsque vous planifiez aujourd'hui pour la gestion de service prendre en charge Microsoft Teams à l’avenir.

Gestion des services comprend toutes les activités et processus impliqués dans la gestion de Microsoft Teams bout en bout. Comme décrit précédemment, certains composants de gestion de service, les composants d’infrastructure qui comprend le service Office 365 lui-même — sont responsabilité de Microsoft, tandis que le client est responsable à ses utilisateurs à gérer les différents aspects des équipes, le réseau et qu’ils fournissent des points de terminaison. Cette section du document se concentreront sur la responsabilité du client à partir d’un point de vue de gestion de service.

![Diagramme illustrant les trois composants de qualité et de la gestion des services chevauche les trois composants. Accent sur la gestion des services.] (media/envision-planning-for-service-management-and-quality-complete-guide-image2.png "Diagramme illustrant les trois composants de qualité et de la gestion des services chevauche les trois composants. Accent sur la gestion des services.")

### <a name="introduction-to-the-operations-guide"></a>Introduction au Guide des opérations

**Les** **personnes**et **comment** sont trois questions importantes qui doivent être posées en matière de gestion des services.

Vous pouvez utiliser le [Guide des opérations](1-drive-value-operate-my-service.md) pour vous aider à résoudre les trois de ces questions. Le guide fournit une liste d’activités à effectuer sur tous les jours, toutes les semaines, tous les mois, et en fonction des besoins. Ces tâches et activités sont essentielles pour la maintenance d’un déploiement d’équipes de haute qualité. Déterminer qui sera chargé d’effectuer des activités spécifiques dans la gestion de service est un aspect essentiel de la planification que vous devrez faire au début de la [phase de planification](upgrade-enlist-stakeholders.md) pour réussir le déploiement. Une fois que vous avez trouvé les tâches et activités, ils doivent être comprises et suivi des groupes ou des personnes que vous leur attribuez. Le Guide des opérations fournit des instructions sur la façon d’effectuer chacune des tâches et la base de connaissances, et/ou les références à un contenu externe.

### <a name="operational-role-mapping"></a>Mappage de rôle opérationnel

Planification de la gestion de service au début est un jalon critique, car la phase de fonctionnement commence lorsque les premier utilisateurs du pilote sont activés. L’équipe de projet doit étudier et accepter les tâches et activités requises, identifier l’équipe chargée de chaque tâche opérationnelle, puis obtenez un engagement et approbation de chaque équipe respectif.

Une fois l’approbation terminée, l’équipe responsable doit commencer puis à mettre en application ces rôles et les responsabilités. Cela peut inclure la formation et préparation, mise à jour le modèle de dotation en personnel ou en vous assurant que les partenaires externes sont prêts à fournir.

Mappage des rôles opérationnels lors de la collecte de votre [équipe de projet](upgrade-enlist-stakeholders.md) permet de toutes les équipes démarrer leurs tâches opérationnelles pendant le pilote et découvrez les opérations et de vous assurer que tout est prête une fois le déploiement démarre.

Le Guide des opérations fournit une liste des tâches courantes mappés à des rôles par défaut qui doivent être valides dans la plupart des scénarios. Vous devez personnaliser ces responsabilités à utiliser pour votre organisation.

### <a name="the-quality-champion-role"></a>Le rôle Champion de qualité

Un groupe ou individuel doit être responsables de la qualité dans toutes les organisations. Il s’agit d’un rôle essentiel dans la gestion de service. Le poids lourd qualité est un rôle de client qui est affecté à une personne ou un groupe qui est passionné sur l’expérience des utilisateurs. Ce rôle nécessite les compétences nécessaires pour identifier les tendances dans l’environnement et le soutien pour travailler avec d’autres équipes pour diriger la mise à jour. La mieux adaptée à la qualité poids lourd est généralement le propriétaire du service client qui, selon la taille et la complexité de l’organisation, peut être une personne ou un groupe qui est passionné sur l’expérience utilisateur.

Le poids lourd qualité tire parti des outils existants et identifient les tendances de qualité des processus documentés, tels que le tableau de bord de qualité des appels (CQD) et de la qualité expérience consulter le Guide, surveiller l’expérience utilisateur et correction du lecteur lorsque cela est nécessaire. Le poids lourd qualité fonctionne avec les équipes respectifs pour exécuter des actions de mise à jour, création de rapports à un comité directeur de leur progression et les problèmes en cours.

Les tâches et activités associées au rôle ont été documentées dans le Guide des opérations. Ce rôle doit être affecté au cours de la [phase de planification](https://aka.ms/SkypeToTeams-Plan). Une étape clée dans le rôle de poids lourd qualité à mettre en application gagne la base de connaissances requis pour le rôle et vérifier les conditions préalables sont en place pour fournir des tâches. Les tâches importantes pour ce rôle exécute une expérience de qualité régulièrement.

### <a name="introduction-to-the-quality-experience-review-guide"></a>Introduction au Guide de révision expérience qualité

La qualité expérience consulter le Guide dispose d’un ensemble d’activités évaluer et fournissent des instructions de mise à jour dans les zones clés qui ont le plus grand impact pour améliorer l’expérience utilisateur comme indiqué dans la figure ci-dessous.

![Un diagramme qui illustre les zones clés qui sont examinés lors d’une révision de l’expérience de qualité.] (media/envision-planning-for-service-management-and-quality-complete-guide-image3.png "Un diagramme qui illustre les zones clés qui sont examinés lors d’une révision de l’expérience de qualité.")

En permanence évaluer et corriger les zones décrites dans ce document, vous pouvez réduire leur potentiel pour un impact négatif sur l’expérience utilisateur. La plupart des problèmes d’expérience utilisateur dans un déploiement peuvent être regroupées dans les catégories suivantes :

- Configuration de pare-feu ou proxy incomplète

- Une mauvaise couverture Wi-Fi

- Bande passante insuffisante

- VPN

- Utilisation de périphériques audio non optimisées ou intégrés

- Sous-réseaux problématiques ou périphériques réseau

Les instructions fournies dans le Guide de révision de l’expérience de qualité se concentre sur l’utilisation en ligne de tableau de bord de la qualité des appels (CQD) comme le principal outil d’examiner chaque zone décrite, en mettant l’accent sur l’audio à optimiser l’impact d’adoption et de signaler. Les optimisations apportées au réseau pour améliorer l’expérience audio auront également directement des améliorations dans le partage du bureau et vidéo.

Nous vous recommandons de vous désigner le poids lourd qualité dès le début. Après avoir en cours désignés, ils doivent démarrer à se familiariser avec le contenu de l’expérience de qualité consulter le Guide.

Vous pouvez trouver les consulter le Guide de l’expérience qualité [ici](https://aka.ms/qerguide).

## <a name="plan-for-network-quality"></a>Prévoir la qualité du réseau

Planification de la qualité du réseau est activé pour la section suivante.

![Diagramme illustrant les trois composants de qualité et de la gestion des services chevauche les trois composants. En mettant l’accent sur le réseau.] (media/envision-planning-for-service-management-and-quality-complete-guide-image4.png "Diagramme illustrant les trois composants de qualité et de la gestion des services chevauche les trois composants. En mettant l’accent sur le réseau.")

Comme mentionné précédemment, planification pour la qualité du réseau avant l’intégration à Microsoft Teams est critique. Pour obtenir des instructions pour la mise en réseau, voir [préparer le réseau de votre organisation pour les équipes Microsoft](prepare-network.md).

Dans la plupart des organisations, les réseaux peuvent comprendre des réseaux gérés et non gérés.

Réseaux gérés sont des composants de l’infrastructure réseau qui une organisation a un contrôle direct. Par conséquent, les réseaux gérés ont un impact direct sur la qualité qui peut être distribué aux charges de travail le trafic en temps réel.

Inversement, réseaux non gérés sont des segments du réseau qu’un client a limité contrôle ou aucun contrôle, plus.

Connexions Internet entre l’organisation et Office 365 sont des réseaux où d’un client a un contrôle limité. Les réseaux sont gérées par un fournisseur de services Internet, mais les organisations doivent être en mesure d’influencer la qualité du réseau à leur bande passante, recommandation pour les optimisations itinéraire de mise à niveau ou, si le problème persiste, commutation des fournisseurs de services Internet.

Accueil ou réseaux dans hôtels ou les restaurants sont des exemples de réseaux où un client n’a aucun contrôle.

Dans les sections suivantes, nous nous concentrerons sur les exigences de qualité de réseaux gérés.

### <a name="key-network-planning-areas"></a>Planification des zones clés du réseau

Les sections suivantes se concentrent sur les aspects importants permettant de fournir un réseau de haute qualité.

> [!NOTE]
> De nombreux réseaux évoluent au fil du temps en raison des mises à niveau, une expansion ou autres impératifs d’entreprise. Assurez-vous que vous disposez des processus opérationnels en place pour mettre à jour ces zones dans le cadre de votre planification de la gestion de service.

#### <a name="bandwidth"></a>Bande passante

Planification de la bande passante est un aspect critique de l’activité de préparation du réseau. Il est impératif de s’assurer qu’il y a suffisamment de bande passante pour les charges de travail Microsoft Teams. Pour être en mesure de taille droite un réseau existant, vous devez comprendre ce qui a actuellement mis en service, l’utilisation actuelle, et, enfin — la bande passante disponible restante.

Pour mesurer l’utilisation actuelle, vous devez surveiller le réseau. Cette mesure permet comme point de départ pour la planification de la bande passante. En outre, le réseau doit en permanence surveillé lors du déploiement et après le déploiement pour vous assurer que le réseau est suffisamment approvisionné.

> [!NOTE]
> Lors de l’analyse de l’utilisation du réseau, il est important éviter d’utiliser les moyennes sur la journée. Ces moyennes peuvent inclure des heures non principales incliner le résultat. Moyennes peuvent masquer les périodes de forte et masquer un problème sous-jacent.

Le [Planificateur de réseau](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) vous aide à déterminer et organiser la configuration réseau requise pour votre déploiement en quelques étapes simples. À l’aide de l’outil pour recueillir plus d’informations sur les réseaux et l’utilisation de la voix dans le Cloud de votre organisation, vous pouvez obtenir un calcul approximatif de la configuration réseau requise vous aurez besoin pour votre déploiement de voix dans le nuage, gérer et exporter ces informations pour la création de rapports et d’afficher zones pour l’analyse approfondie et suivre les étapes ci-après.

#### <a name="quality-of-service-qos"></a>Qualité de service (QoS)

QoS doit être implémentée sur tous les segments du réseau géré, voire les réseaux qui ont été correctement mis en service pour la bande passante. Dans ce cas, QoS agit comme une atténuation des risques en cas de charge réseau inattendues. Lorsque la qualité de service est implémentée, le trafic vocal est prioritaires afin que ces événements imprévus n’affectent pas la qualité.

Une implémentation de QoS doit inclure les zones du réseau, le point de terminaison aux points de sortie et les points de sortie sur le point de terminaison. Cela permet de garantir que le trafic vocal est priorité dans les deux sens. QoS doit être implémentée sur les deux filaire et les réseaux Wi-Fi.

Pour l’implémentation de QoS sur votre réseau, les conseils suivants peuvent aider à [La qualité de Service dans les équipes Microsoft](qos-in-teams.md)

#### <a name="proxy-servers"></a>Serveurs proxy

Bon nombre d’organisations afficher le trafic destiné à internet comme un risque de sécurité, et ils réduire ce risque en surveiller et évaluer le trafic sur les points de sortie dans le réseau. Les serveurs proxy sont une classe de périphériques qui peuvent être déployés pour répondre à cette exigence.

Un serveur proxy peut présenter des problèmes lors de l’exécution des paquets ou modification de la charge utile. Cela peut entraîner pour appeler les échecs d’installation, appels abandonnés et appel de mauvaise qualité. Si les médias en temps réel est forcé de parcourir un serveur proxy, la pile de médias dans les équipes est forcée basculer sur TCP, qui permet de réduire la qualité. UDP est toujours préféré sur TCP.

En outre, un serveur proxy ne peut pas conçu pour gérer la charge supplémentaire d’Office 365 et plus particulièrement les charges de travail Microsoft Teams, y compris les médias en temps réel.

En raison d’un serveur proxy peut entraîner des problèmes potentiels et les problèmes de capacité supplémentaire, Microsoft recommande en contournant le serveur proxy et d’une connexion directe à Office 365.

La configuration requise pour contourner le serveur proxy varie selon les fournisseurs, mais l’approche courante implique généralement la mise à jour le fichier de configuration automatique (CAP) proxy. Le fichier PAC est un fichier de configuration qui décrivent le trafic passe par le proxy et le trafic qu’il ignore.

Certains fournisseurs de serveurs proxy fournissent un processus automatisé pour garantir la configuration est à jour. Si votre fournisseur ne fournit pas ce processus automatique, vous pouvez télécharger un fichier PAC mis à jour à partir de <https://aka.ms/o365proxies>.

[Serveurs proxy de Skype pour des activités en ligne et les équipes](/SkypeForBusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online)

#### <a name="firewalls"></a>Pare-feu

S’assurer que les protocoles et les ports droite sont ouverts pour toutes les URL et les adresses IP d’Office 365 est requis pour accéder à Microsoft Teams. Il est également critique pour un déploiement de haute qualité. Simplement un appel ou participer à une conférence téléphonique n’est pas suffisant pour vous assurer que votre pare-feu est configuré correctement.

Si seul TCP est ouvert sur le pare-feu, la session est établie, mais le transport par défaut (UDP) n’est pas négocié. TCP et UDP doivent être ouverts sur le pare-feu pour fournir la meilleure expérience utilisateur.

En raison de la nature dynamique, TCP n’est pas par défaut pour les médias en temps réel et est fourni comme moyen de transport réseau la restauration pour Microsoft Teams. Avec TCP, s’il existe retard des paquets ou perte, les paquets doivent être redirigées jusqu'à ce qu’elles sont reconnues. Cela peut entraîner des paquets de médias qui ne sont plus pertinents concurrents de remise en temps voulu des paquets de médias en cours. Client des équipes de l’utilisateur essaie d’étirer audio et peut générer des bruits audibles en fonction des conditions de réseau. Avec la surcharge supplémentaire du protocole TCP, une expérience généralement acceptable puisse passer à une expérience utilisateur médiocre. Pour cette raison, le transport sans état réseau UDP est requis.

L’aide complète pour ouvrir le pare-feu pour Microsoft Teams est fournie dans l’article [Office 365 URL et plages d’adresses IP](https://aka.ms/o365ips) .

Une fois que le pare-feu est ouvert, vous pouvez utiliser l' [Outil d’évaluation réseau Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) pour valider la connectivité pour les fonctionnalités de voix dans le nuage.

> [!IMPORTANT]
> Les URL et les adresses IP de Microsoft Office 365 va évoluer. Dans le cadre de la planification de gestion de service, il est important de garantir un processus opérationnel est en place et un groupe est responsable pour surveiller [Office 365 URL et plages d’adresses IP](https://aka.ms/o365ips) et de mettre à jour en conséquence.

#### <a name="local-internet-egress"></a>Local sortant internet

De nombreux réseaux ont été conçus pour utiliser un concentrateur de topologie en étoile. Dans cette topologie, le trafic internet parcourt généralement le réseau étendu à un centre de données central avant il ressort (egresses) à internet. Souvent, cette opération est effectuée pour centraliser les périphériques de sécurité réseau dans le but de réduire le coût global.

Back-tirer le trafic sur le réseau étendu à l’augmentation de la latence et a un impact négatif sur la qualité et l’expérience utilisateur. Microsoft Teams s’exécute sur le réseau global volumineux de Microsoft, il est souvent un emplacement homologation réseau proche de l’utilisateur. Un utilisateur sera probablement obtenir améliorer les performances en egressing dès que possible en dehors d’un point d’internet local a presque atteint leur emplacement et notre réseau optimisé pour la voix. Pour certaines charges de travail, les requêtes DNS sont utilisés pour envoyer le trafic vers le plus proche du serveur frontal. Dans ce cas, il est important que lorsque vous utilisez un point de sortie local, elle est associée à la résolution DNS locale.

Optimisation du chemin d’accès réseau réseau globale de Microsoft pour améliorer les performances et finalement fournir la meilleure expérience pour les utilisateurs. Pour plus d’informations, consultez le blog de [l’obtention de la connectivité et les performances dans Office 365 meilleures](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

#### <a name="vpn"></a>VPN

Réseaux privés virtuels fournissent un service précieux à de nombreuses organisations. Malheureusement, ils sont généralement pas conçus ou n’est configurés pour prendre en charge les médias en temps réel. Certains réseaux privés virtuels peuvent également pas en charge UDP. Réseaux privés virtuels introduisent également un niveau supplémentaire de chiffrement par-dessus le trafic multimédia déjà chiffré. En outre, la connectivité au service Microsoft Teams est peut-être pas efficace en raison de l’épinglage de cheveux le trafic via un périphérique VPN. En outre, ils ne sont pas nécessairement conçus à partir d’un point de vue de la capacité à prendre en charge les charges anticipées nécessiteront des équipes.

Il est recommandé de fournir un chemin d’accès de substitution contournant le réseau VPN pour le trafic des équipes. Cela est généralement appelé split-tunnel VPN. Fractionnement tunnel signifie que le trafic pour Office 365 ne parcourt pas le réseau VPN mais est dirigés directement vers Office 365. Cette modification aura un impact positif sur la qualité, mais également offre l’avantage secondaire permettant de réduire la charge de périphériques VPN et le réseau de l’organisation.

Pour implémenter un tunnel de fractionnement, consultez votre fournisseur de réseau privé virtuel pour les détails de configuration.

#### <a name="wi-fi"></a>Wi-Fi

Comme VPN, réseaux Wi-Fi ne sont pas nécessairement conçus ou configurés pour prendre en charge les médias en temps réel. Planification de, et/ou d’optimisation, un réseau Wi-Fi pour prendre en charge des équipes est une considération importante pour un déploiement de qualité.

Il existe plusieurs facteurs qui entrent en jeu pour l’optimisation d’un réseau Wi-Fi.

- L’implémentation de QoS ou Wi-Fi multimédia (WMM) pour vous assurer que le trafic multimédia est prise hiérarchisée en conséquence sur les réseaux Wi-Fi.

- Planification et optimisation les bandes W-Fi et access point de positionnement. 2,4 GHz peut fournir une expérience adéquate en fonction de l’emplacement du point d’accès, mais les points d’accès sont souvent concernées par d’autres appareils qui fonctionnent dans cette plage. La plage de 5 GHz est mieux adaptée aux médias en temps réel en raison de leur plage haute densité mais requiert plusieurs points d’accès pour obtenir la couverture suffisante. Points de terminaison doivent également prendre en charge cette plage et être configurés pour tirer parti de ces bandes en conséquence.

- Si les réseaux Wi-Fi double bande sont déployés, envisagez d’implémenter la direction de la bande. Bande de direction est utilisée par les fournisseurs Wi-Fi pour influencer le double bande aux clients d’utiliser la plage 5Ghz technique.

- Chevauchement de canal – lorsque les points d’accès du même canal sont trop proches ils peuvent entraîner la superposition du signal et concurrence involontairement, ce qui entraîne une mauvaise expérience de l’utilisateur. Assurez-vous que le point d’accès qui sont en regard de chacun des autres sont sur des canaux que ne se chevauchent ne pas.

Chaque fournisseur sans fil possède son propre recommandations pour le déploiement de sa solution sans fil. Nous vous conseillons de consulter votre fournisseur pour obtenir des instructions spécifiques.

### <a name="network-readiness-assessment"></a>Évaluation de la préparation réseau

Partie sur les activités de préparation du réseau comprend une évaluation de réseau. Une fois que vous avez terminé la planification et la configuration, l’évaluation peut vous fournir une connaissance de base de la qualité de votre réseau avant d’utilisateurs intégrés à Microsoft Teams. Les résultats de l’évaluation seront également vous aider à identifier et hiérarchiser les efforts de correction avant d’activer les utilisateurs pour les équipes.

L’évaluation du réseau doit être exécutée sur les deux filaire et réseaux Wi-Fi pour tous les bâtiments activées pour en nuage des fonctionnalités vocales dans les équipes.

L’évaluation de réseau peut être effectuée à l’aide de l' [outil d’évaluation du réseau Microsoft](https://www.microsoft.com/download/details.aspx?id=53885), des outils tiers ou un partenaire Microsoft. Nous avons également fournissent des conseils supplémentaires sur l’exécution de l’évaluation à l’aide de l’outil d’évaluation du réseau Microsoft dans le cadre de notre Guide de préparation [ici](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_3_0_2,4_3_0_3,4_3_0_5,4_3_0_6,4_3_0_7,4_3_0_8,4_3_0_10,4_3_0_11).

## <a name="plan-for-endpoint-quality"></a>Plan pour la qualité du point de terminaison

Comme vous pouvez le constater dans le diagramme ci-dessous, points de terminaison sont un bloc de construction important à fournir une expérience de haute qualité pour les utilisateurs.

![Diagramme illustrant les trois composants de qualité et de la gestion des services chevauche les trois composants. En mettant l’accent sur les points de terminaison.] (media/envision-planning-for-service-management-and-quality-complete-guide-image5.png "Diagramme illustrant les trois composants de qualité et de la gestion des services chevauche les trois composants. En mettant l’accent sur les points de terminaison.")

Points de terminaison Teams Microsoft peuvent s’exécuter sur de nombreux périphériques, y compris les PC, Mac, tablettes et les appareils mobiles. Partie de l’expérience englobe non seulement l’appareil, mais comment un utilisateur se connecte à l’appareil — par exemple, à l’aide de micro/haut-parleur intégré du périphérique, écouteurs par ou un casque optimisé. À l’aide d’un casque optimisé permettre enrichir l’expérience utilisateur globale.

Les instructions suivantes sur la planification de point de terminaison vous aideront à vérifier que votre organisation dispose d’une intégration réussie expérience des équipes.

### <a name="endpoint-capability"></a>Fonctionnalité du point de terminaison

La première partie de la planification consiste à vérifier tous les PC et autres périphériques de votre organisation peuvent exécuter Microsoft Teams. Cela implique pas la consultation de la configuration matérielle requise, mais également comprendre que fait le PC en arrière-plan. Bon nombre d’organisations exécuter d’autres logiciels, y compris les systèmes de détection d’intrusion et logiciels anti-programmes malveillants, ce qui peut affecter les performances de base d’un périphérique.

Microsoft Teams a clients disponibles pour le site web, du bureau (Windows et Mac) et mobile (Android, iOS et Windows Mobile). Pour plus d’informations sur la configuration logicielle requise pour chaque plateforme, voir [obtenir des clients pour les équipes Microsoft](get-clients.md).

### <a name="endpoint-firewalls"></a>Pare-feu de point de terminaison

Pare-feu côté client peuvent avoir un impact significatif sur l’expérience utilisateur. Pare-feu côté client peuvent affecter la qualité des appels en plus empêche l’établissement d’un appel. Configurez les exclusions appropriées sur le pare-feu du client en fonction des informations dans [Office 365 URL et plages d’adresses IP](https://aka.ms/o365ips). Votre fournisseur tiers auront des instructions spécifiques sur la façon de créer les exclusions.

> [!NOTE]
> Microsoft Teams met automatiquement à jour le pare-feu Windows avec une configuration de pare-feu appropriée.

### <a name="wi-fi-recommendations-for-endpoints"></a>Recommandations en matière de points de terminaison Wi-Fi

Planification et déploiement d’un réseau Wi-Fi optimisé pour prendre en charge des charges de travail en temps réel dans Microsoft Teams nécessite significative de planification. Les sections suivantes fournissent des conseils d’ordre général qui peuvent vous aider à éviter les pièges lors de la planification des points de terminaison.

#### <a name="wi-fi-drivers"></a>Pilotes Wi-Fi

Certains pilotes Wi-Fi peuvent être problématiques. Par exemple, un pilote peut avoir très agressifs comportements itinérance entre les points d’accès, entraînant l’appel de mauvaise qualité. Ce n’est pas une chose courants, mais il est important de vérifier que les pilotes Wi-Fi sur le PC ont été mis à jour et testés avant le déploiement.

#### <a name="wi-fi-bands"></a>Bandes Wi-Fi

Il existe principalement deux types de bandes utilisées dans Wi-Fi équipement aujourd'hui, 2,4 GHz et GHz 5.0. Si votre organisation fournit les deux bandes, vous devez configurer les paramètres de votre pilote pour préfèrent la bande GHz 5.0. Cette bande est beaucoup plus dense en termes de débit et moins affectés à des interférences apparaît dans la bande 2,4 GHz. Cette recommandation suppose que vous avez correctement optimisé la bande de réseau GHz 5.0.

#### <a name="wi-fi-radio-type"></a>Type de radio Wi-Fi

Planifier les appareils qui prennent en charge les nouveaux types de radio Wi-Fi. Vous pouvez obtenir très bonnes performances Wi-Fi, notamment si vous faites 802.11ac ou plus récente sur les appareils que vous mettez en service.

#### <a name="wireless-avoidance"></a>Réductions sans fil

Certaines organisations préfèrent éviter Wi-Fi. Parfois ce guide est fourni par le biais de recommandation pour les utilisateurs se connectent directement à un réseau câblé. Dans certains cas, l’ordre de liaison réseau peut-être par défaut de la connexion sans fil et continuer à utiliser cette connexion, même si l’ordinateur est connecté à une connexion câblée. Pour éviter ce comportement involontaire, configurez l’ordre de liaison pour éviter ce scénario.

#### <a name="80211-power-save-protocol"></a>protocole d’économie d’énergie 802.11

Si votre organisation utilise des points d’accès sans fil ou les routeurs qui ne prennent pas en charge la puissance 802.11 enregistrement protocole, vous pouvez être confronté appels abandonnés ou la qualité des appels médiocre dans Teams Microsoft en cours d’exécution sur les périphériques Windows. Si elle n’est pas possible de mettre à niveau votre point d’accès sans fil ou les routeurs, vous devez mettre à jour Windows Power planifier les paramètres sur les appareils qui s’exécutent sur la batterie. Conseils de détail et de configuration supplémentaire est fournie dans le suivants [prennent en charge de l’article](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you).

### <a name="devices-for-teams"></a>Périphériques pour les équipes

Microsoft Teams utilisable pour les réunions ou en tant qu’un système téléphonique. Lorsque vous utilisez ces fonctionnalités, le périphérique d’interface qui est utilisé pour les équipes joue un rôle important dans l’expérience utilisateur.

À l’aide d’un haut-parleur PC et un microphone intégrés peut sembler acceptable pour l’utilisateur ayant cette configuration. Mais généralement ces périphériques ne sont pas optimisés pour la suppression du bruit, et n’importe quel type de bruit peut avoir un impact en aval sur d’autres lors de l’appel. Tirer parti des appareils optimisés pour ces scénarios afin de garantir une expérience de haute qualité.

Chaque périphérique doit répondre aux besoins de vos utilisateurs. Vous devrez adapter les appareils tels que des casques pour les personnages différents et en cas d’utilisation dans votre organisation. Un exercice personnage-à mappage des périphériques doit être effectué dans le cadre du processus de planification.

Une fois que vous avez sélectionné les périphériques, les inclure dans le plan de test pilote pour la validation finale. Tirer parti des enquêtes pendant le pilote pour recueillir les commentaires pour vous assurer de votre stratégie de périphérique est optimal.

À ce stade, nous recommandons l’utilisation de périphériques audio qui ont été certifiés par le biais de la Skype pour le programme de Certification d’entreprise. Pour rechercher des périphériques certifiés sous ce programme, reportez-vous au catalogue de solutions [Certifiés de périphériques USB pour Skype pour les entreprises](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) .

Pour plus d’informations, consultez [clients et périphériques - atelier Préparation](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_13)

## <a name="client-updates"></a>Mises à jour du client

Un des principaux avantages de Microsoft Teams est que le client est mis à jour automatiquement. Les clients sur le PC et Mac sont mis à jour à l’aide d’un processus d’arrière-plan qui vérifie les nouvelles versions et télécharge le nouveau client lorsque l’application est inactive. La taille de téléchargement du client est à peu près de 100 Mo.

Une organisation ne possède pas de tout contrôle ou un accès à un paramètre de stratégie pour gérer le processus de mise à jour. Pour réduire le risque d’un problème qui peut être découvert dans une version plus récente, la dernière bonne version est conservée sur le point de terminaison. Cas de problème avec une nouvelle version, le service Microsoft Teams peut rétablir automatiquement le point de terminaison à la version précédente.

## <a name="next-steps-and-references"></a>Étapes suivantes et références

Ce tableau propose un résumé des activités de planification avec des liens vers du contenu connexe.

| Zone | Détails | Références |
|---|---|---|
| Plan de gestion des services | Réaliser un exercice de mappage de rôle opérationnel <br/> Approbation des équipes responsables <br/> Préparation de rôle | [Guide des opérations](1-drive-value-operate-my-service.md) |
| | Désigner la qualité Champion(s) <br/> Préparation Champion de qualité| [Découvrez CQD](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Academy?SOFTrainings=Leverage%20the%20Investigate%20Media%20Quality%20using%20CQD%20Videos) <br/> [Consulter le Guide de l’expérience qualité](https://aka.ms/qerguide) |
| | Installer des modèles de révision de l’expérience de qualité <br/> Télécharger un fichier de construction | [Modèles de QERLite](https://aka.ms/qertemplates) <br/> [Informations de création de téléchargement](turning-on-and-using-call-quality-dashboard.md)|
| Prévoir la qualité du réseau | Exécutez le Planificateur de réseau | [Planificateur de réseau](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) |
| | Mettre en œuvre QoS | [Qualité de Service dans les équipes Microsoft](qos-in-teams.md) |
| | Ignorer les serveurs proxy | [Conseils de proxy](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a) |
| | Implémenter le fractionnement-tunnel VPN | [Conseils de Tunnel VPN fractionné](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9) |
| | Optimiser les réseaux Wi-Fi pour les médias en temps réel | Consulter les fournisseurs tiers |
| | Mettre en œuvre local sortant internet | [Internet local sortant](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694) |
| | Mettre en œuvre la connectivité réseau <br/> Valider la connectivité réseau | [URL d’Office 365 et adresses IP](https://aka.ms/o365ips) |
| | | [Outil d’évaluation de réseau](https://www.microsoft.com/download/details.aspx?id=53885) |
| | Évaluer le réseau | [Évaluation de préparation de réseau](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_3_0_2,4_3_0_3,4_3_0_5,4_3_0_6,4_3_0_7,4_3_0_8,4_3_0_10,4_3_0_11) |
| Plan pour la qualité du point de terminaison | Mise à jour du point de terminaison pare-feu | [URL d’Office 365 et adresses IP](https://aka.ms/o365ips) |
| | Valider la configuration logicielle requise | [Obtenir des clients pour Microsoft Teams](get-clients.md) |
| | Recommandations de point de terminaison Wi-Fi | Consulter les fournisseurs tiers |
| | Personnage conduite aux périphériques mappage <br/> Configurer les périphériques et les pilotes | [Clients et périphériques - atelier Préparation](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_13) <br/> [Catalogue de périphérique](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) |

Une fois que vous avez terminé la planification, passez à l’étape suivante : [préparer votre environnement pour les équipes](https://aka.ms/SkypeToTeams-TechnicalReadiness).