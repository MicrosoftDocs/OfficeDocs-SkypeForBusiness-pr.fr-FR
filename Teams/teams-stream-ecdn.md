---
title: Mettre à l’échelle la distribution de vidéos dans Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: asteele
search.appverid: MET150
f1.keywords:
- NOCSH
description: Cet article traite de la mise à l’échelle de la distribution de vidéos et des réseaux de distribution de contenu d’entreprise (eCDN) pour les événements de streaming Microsoft Teams.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 9475ac8a99a7858221c062ccedb0bd1327f37e4c
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767945"
---
# <a name="scale-video-delivery-and-monitor-network-traffic-by-using-ecdns-with-microsoft-teams"></a>Mettre à l’échelle la distribution vidéo et surveiller le trafic réseau à l’aide d’eCDN avec Microsoft Teams

La lecture de vidéos à partir de Microsoft Teams et des événements en direct « Application ou appareil externe » (anciennement appelées productions « External Encoder ») utilisent le streaming à débit adaptatif (ABR) fourni sous forme de flux de monodiffusion. Cela signifie que chaque spectateur obtient son propre flux vidéo à partir d’Internet. Pour les événements en direct ou les vidéos envoyés à de grandes parties de votre organisation, il peut y avoir une quantité importante de bande passante réseau et Internet consommée par les téléspectateurs.

Les organisations peuvent vouloir comprendre et réduire ce trafic réseau pour les événements en direct et les vidéos populaires. Si c’est le cas, Teams peut être activé pour s’intégrer à des partenaires Microsoft approuvés qui offrent des solutions eCDN (Enterprise Content Delivery Network) qui incluent des technologies de livraison autogestion, une surveillance en temps réel et une analytique réseau approfondie. Ces plateformes eCDN permettent aux organisations de surveiller, de mettre à l’échelle et d’optimiser la distribution de flux vidéo (et parfois d’autres types de contenu) sur votre réseau d’entreprise.

## <a name="acquire-and-set-up-your-ecdn-solution-outside-of-teams"></a>Acquérir et configurer votre solution eCDN en dehors de Teams

Obtenez de l’aide d’experts sur la surveillance et la mise à l’échelle de la distribution de vidéos en faisant équipe avec des partenaires Microsoft eCDN de confiance.

Avant de pouvoir activer l’utilisation d’une solution eCDN avec Teams, vous devez acheter et configurer cette solution eCDN en dehors et séparément de Teams. Pour vous assurer que la solution répondra à vos besoins, certains partenaires proposent des essais gratuits de leurs technologies de distribution de contenu et d’analytique réseau.

Plusieurs solutions eCDN sont préintégrées et peuvent être activées pour une utilisation avec Teams. Consultez les informations des fournisseurs ci-dessous.

### <a name="hive-streaming"></a>Diffusion en continu Hive

La **plateforme Hive Streaming Video Experience Platform** comprend trois produits principaux :

- **L’optimisation vidéo Hive** est basée sur un algorithme de configuration zéro logiciel et breveté. L’optimisation optimise automatiquement la qualité et la portée de la vidéo en direct et à la demande (VOD) pour l’ensemble de l’organisation.
- **Hive Video Analytics** aide les clients à comprendre les tendances en matière d’événements en direct et de performances vidéo à la demande afin d’améliorer l’engagement des téléspectateurs au fil du temps. À mesure que l’engagement s’améliore, l’adoption de la vidéo au sein de l’entreprise s’améliore également.
- **Hive Video Operations** fournit de puissantes fonctionnalités visant à sécuriser de manière proactive le succès de la vidéo en continu avant et pendant les événements vidéo en direct. Les outils opérationnels permettent à vos équipes de streaming vidéo et d’uc de rechercher et de corriger les problèmes avant qu’ils ne se produisent.

Tous fonctionnent pour créer des expériences vidéo complètes, de la planification à l’exécution et à l’analyse. L’optimisation de l’expérience de la communication vidéo en continu est essentielle pour l’engagement des employés et l’alignement sur la mission de votre entreprise. Pour en savoir plus, consultez [ce lien](https://www.hivestreaming.com/partners/microsoft).

### <a name="kollective"></a>Kollective

**Kollective Technology** est une plateforme de distribution de contenu basée sur le cloud qui utilise le peering intelligent pour fournir des vidéos d’entreprise en direct et à la demande, fournissant une qualité vidéo 100 % et un engagement de 100 % à seulement 1 % de la bande passante. L’intégration de Kollective à Teams Live Events permet aux employés répartis dans le monde entier de consommer facilement la vidéo, d’améliorer la communication des employés, de stimuler l’engagement global et d’augmenter les opportunités de formation et de rétention.

**Kollective IQ** est une plateforme d’analyse sophistiquée et conviviale pour Microsoft Stream. Avec des rapports, des visualisations et des tableaux de bord personnalisables, il est facile de quantifier et de digérer l’expérience utilisateur et l’engagement sur des réseaux d’entreprise mondiaux complexes. Les gestionnaires de communication et les administrateurs réseau peuvent surveiller les événements en temps réel et l’activité réseau, de sorte que les goulots d’étranglement peuvent être résolus rapidement, ce qui garantit les performances réseau maximales.

Pour en savoir plus sur ces options, consultez [ce lien](https://kollective.com/microsoft-live-events/).

### <a name="microsoft-ecdn"></a>Microsoft eCDN

**Microsoft eCDN** résout le problème de congestion réseau qui se produit lors d’événements virtuels d’entreprise de grande taille, tels que des réunions à main. Microsoft eCDN forme un réseau maillé sur le réseau local qui réduit la charge de 95 % et élimine les problèmes réseau. Microsoft eCDN est le premier eCDN à utiliser WebRTC comme base, ce qui signifie qu’aucune installation logicielle ou matérielle n’est nécessaire. Les clients fortune 500 atténuent les problèmes de mise en réseau et font confiance à Peer5 pour leurs plus grands événements d’entreprise.

- La configuration réseau sans configuration pour Microsoft eCDN garantit que les travailleurs à distance et/ou le trafic vidéo important ne surchargeront pas votre réseau et ne vous obligeront pas à investir dans une infrastructure coûteuse. Il inclut la détection automatique de site, la détection VPN automatique et la traversée automatique nat/pare-feu. Pour en savoir plus, [consultez ce lien](/ecdn/how-to/enable-microsoft-ecdn-for-your-tenant).
- Les tests en mode silencieux avec Microsoft eCDN permettent aux administrateurs informatiques de simuler de grands événements en direct sur leur réseau d’entreprise, ce qui permet des tests et des dépannages approfondis et sans interruption avant un événement réel. Pour en savoir plus, [consultez ce lien](/ecdn/how-to/perform-silent-test).
- Les analyses de pointe de Microsoft eCDN fournissent des analyses granulaires et permettent aux administrateurs de trouver rapidement la cause racine de tout problème de diffusion en continu. Votre kit de ressources comprend des métriques de livraison et d’expérience utilisateur, des explorations avancées, des analyses par utilisateur et une API back-end. Pour en savoir plus, [consultez ce lien](/ecdn/technical-documentation/analytics).

### <a name="ramp"></a>Ramp

**Ramp eCDN** réduit la consommation de bande passante réseau de 90 % ou plus lors de la diffusion en continu d’événements en direct et de vidéos à la demande (VOD). Utilisez Ramp pour combiner et faire correspondre n’importe quelle combinaison de technologies eCDN (multidiffusion, mise en cache et mise en réseau d’égal à égal). Grâce à la gestion centralisée, à la surveillance et à l’analytique perspicace, vous gagnez en visibilité et en contrôle sur les performances réseau pour créer une expérience de visionneuse de la plus haute qualité.

- **Ramp Multicast+** est le moyen le plus efficace de diffuser des vidéos en direct. À l’aide du protocole de multidiffusion, vous consommez uniquement la bande passante requise pour une visionneuse, que vous ayez 100, 10 000 ou 100 000 visionneuses. Pour en savoir plus, [consultez ce lien](https://www.rampecdn.com/altitudecdn/multicast/).
- **Ramp OmniCache™** est un logiciel de mise en cache spécifique à la vidéo qui utilise des caches locaux pour diffuser des vidéos en direct et VOD à des audiences proches, ce qui réduit considérablement le nombre de flux vidéo voyageant entre vos connexions Internet et vos liaisons WAN. Pour en savoir plus, [consultez ce lien](https://www.rampecdn.com/altitudecdn/video-cache/).
- **Ramp Peer-to-Peer (P2P)** vous permet d’optimiser la bande passante même dans des emplacements avec une infrastructure limitée. P2P crée un réseau d’homologues d’appareils clients qui regardent le même contenu pour redistribuer les flux vidéo d’un appareil à un autre. Pour en savoir plus, [consultez ce lien](https://www.rampecdn.com/altitudecdn/p2p/).

### <a name="riverbed"></a>Riverbed

**Riverbed**, la norme industrielle en matière d’optimisation réseau, a étendu ses solutions d’accélération à Teams. Les clients Microsoft 365 peuvent accélérer en toute confiance le trafic Microsoft 365, y compris Teams, ainsi qu’une multitude d’autres services SaaS d’entreprise de premier plan pour augmenter la productivité de la main-d’œuvre en tout lieu. L’accélération teams peut être activée par le biais d’une configuration sans effort qui est fournie avec toute l’assurance du support de classe mondiale et de l’investissement continu de Riverbed. Pour en savoir plus, [consultez ce lien](https://www.riverbed.com/office365).

> [!NOTE]
> Votre solution eCDN choisie est soumise aux conditions d’utilisation et à la politique de confidentialité du fournisseur eCDN partenaire sélectionné, qui régissent votre utilisation de la solution du fournisseur eCDN. Votre utilisation de la solution du fournisseur eCDN ne sera pas soumise aux termes du contrat de licence en volume Microsoft ni aux conditions des services en ligne. Si vous n’acceptez pas les conditions du fournisseur tiers, n’activez pas la solution eCDN dans Microsoft Teams.

## <a name="configure-stream-encoder-type-events-for-your-ecdn-solution"></a>Configurer les événements de type d’encodeur Stream pour votre solution eCDN

Après avoir acheté et configuré votre solution eCDN, vous pouvez l’activer pour l’utiliser avec Microsoft Stream, notamment les événements en direct de l’encodeur stream créés via Microsoft Teams ou Yammer.

1. Ouvrez le Centre d’administration Teams en tant qu’administrateur général Microsoft 365 ou administrateur Teams, puis accédez à la page [des paramètres des événements en direct](https://admin.teams.microsoft.com/broadcasts/settings) .
1. Basculez le **fournisseur de distribution vidéo** sur **Activé**.
1. Choisissez un **fournisseur eCDN/SDN** dans la liste déroulante **Fournisseur de distribution vidéo** .
1. Renseignez les autres champs comme indiqué par votre fournisseur de solutions (tous les champs ne sont pas utilisés par tous les fournisseurs de solutions).
1. Sélectionnez **Enregistrer**.
1. Pour vérifier si votre configuration est correcte, sélectionnez **Vérifier l’installation**.
    - Recherchez n’importe quelle vidéo dans votre organisation avec laquelle valider.
    - Si votre fournisseur eCDN est correctement configuré, un message **de réussite** s’affiche sur l’outil de configuration de vérification.
    - Si vous n’êtes pas configuré correctement, un message **d’échec** s’affiche. Copiez le message d’événement à partager avec votre fournisseur à des fins de résolution des problèmes.

Après avoir configuré Teams pour une solution eCDN, toute vidéo ou événement en direct lu dans Teams tire automatiquement parti de cette solution.

## <a name="configure-teams-production-type-events-through-teams-and-yammer-for-your-ecdn-solution"></a>Configurer des événements de type de production Teams via Teams et Yammer pour votre solution eCDN

Si vous envisagez de créer des événements en direct Teams via Teams ou Yammer, vous devez [configurer votre fournisseur eCDN pour qu’il soit également intégré à Microsoft Teams](teams-live-events/what-are-teams-live-events.md#enterprise-content-delivery-network-ecdn) .

### <a name="get-to-video-analytics-reports-for-your-ecdn-solution"></a>Accéder aux rapports d’analyse vidéo pour votre solution eCDN

Comme indiqué ci-dessus, certaines solutions eCDN fournissent également des rapports d’analyse qui fournissent des informations plus détaillées sur les sessions de lecture, les visionneuses et la qualité de service. Si votre fournisseur vous a fourni un modèle d’URL de rapport d’analyse à configurer lorsque vous configurez le fournisseur dans le Centre d’administration Teams, les propriétaires de vidéos ou d’événements peuvent facilement accéder au rapport d’analyse pour une vidéo ou un événement spécifique.

Les propriétaires de vidéos verront un onglet Analytique directement sous la vidéo. Cet onglet contient un lien permettant aux propriétaires d’accéder au rapport d’analyse de cette vidéo spécifique dans le système du fournisseur eCDN.

Si vous êtes administrateur Teams, vous pouvez également élever votre accès pour afficher l’onglet Analyse et accéder au lien du rapport d’analyse eCDN, même si vous n’êtes pas propriétaire de l’événement ou de la vidéo en direct.

1. En tant qu’administrateur Teams, accédez à la page du lecteur vidéo.
1. Sélectionnez **Paramètres**.
1. Sélectionnez **Afficher en mode administrateur**.
1. Sélectionnez l’onglet **Analytique** .

## <a name="troubleshooting-issues"></a>Résolution des problèmes

Assurez-vous que votre solution eCDN est correctement configurée dans votre réseau et que vous avez correctement configuré Teams pour activer le fournisseur en fonction de leurs instructions et chaînes de configuration spécifiques. Si vous rencontrez toujours des problèmes, certaines des informations ci-dessous peuvent vous aider.

### <a name="verify-setup-tool"></a>Vérifier l’outil d’installation

Si vous rencontrez des problèmes avec votre solution eCDN, vous pouvez toujours revenir et exécuter l’outil **Vérifier la configuration** . Les messages d’événement du fournisseur eCDN affichés pour votre vidéo de test peuvent vous donner, ainsi qu’à votre fournisseur eCDN, plus d’informations sur ce qui ne fonctionne pas.

- Accédez à **Paramètres** >  **Administration Fournisseur** > **eCDN** Paramètres  > **Vérifier l’installation**

### <a name="disable-ecdn-for-a-specific-session-via-url-query-string"></a>Désactiver eCDN pour une session spécifique via une chaîne de requête d’URL

Pour déterminer si un problème que vous rencontrez est lié à la solution eCDN ou à Teams, vous pouvez facilement désactiver la solution eCDN pour une session de lecture spécifique via une chaîne de requête.

- Si votre URL de lecture comporte déjà un point d’interrogation **, ?**, ajoutez **&disableSDN=true**.
- Si votre URL de lecture n’a pas de point d’interrogation **, ?**, ajoutez **alors ?disableSDN=true**.

### <a name="view-ecdn-info-in-browser-console"></a>Afficher les informations eCDN dans la console du navigateur

Si votre fournisseur de solutions eCDN le prend en charge, il peut imprimer des informations de débogage lors de l’initialisation de la lecture via sa solution. Ces informations supplémentaires peuvent être utiles pour déterminer ce qui se passe mal. Vous pouvez activer des messages de débogage de console supplémentaires via la chaîne de requête.

- Si votre URL de lecture comporte déjà un point d’interrogation **, ?**, ajoutez **&isSDNDebug=true**.
- Si votre URL de lecture n’a pas de point d’interrogation **, ?**, ajoutez **?isSDNDebug=true**.

Sélectionnez **F12** sur votre clavier lorsque votre navigateur est actif et basculez vers l’onglet **Console** pour afficher toutes les informations imprimées pendant le chargement de la page avec la chaîne de requête isSDNDebug=true définie sur l’URL de lecture.
