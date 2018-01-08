---
title: "Interopérabilité entre Microsoft Teams et Skype Entreprise"
author: arachmanGitHub
ms.author: MyAdvisor
manager: lolaj
ms.date: 12/12/2017
ms.topic: article
ms.service: msteams
description: "Découvrez le fonctionnement de l'interopérabilité entre Teams et Skype Entreprise et son impact sur les conversations et les appels."
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 8eca9f18d02d76fe1ab1b754ecf8a49b6b20aec3
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2017
---
<a name="microsoft-teams-and-skype-for-business-interoperability"></a>Interopérabilité entre Microsoft Teams et Skype Entreprise
=======================================================

Si votre organisation utilise Skype Entreprise et prévoit d'utiliser Teams, il est crucial de comprendre la procédure de configuration de l'interopérabilité entre ces deux applications.

> [!IMPORTANT]
> Ce document permet une évaluation anticipée de la prise en charge des forfaits d'appel pour Teams. Les détails de la stratégie d'interopérabilité de Teams devraient changer à l'avenir.

L'interopérabilité permet aux utilisateurs de Skype Entreprise et de Teams de discuter et de s'appeler tout en garantissant la fluidité des communications au sein de votre organisation. Pour aider les professionnels de l'informatique à adopter Teams, nous avons ajouté une nouvelle stratégie d'interopérabilité de Teams dont la gestion est assurée via une session Windows PowerShell à distance de Skype Entreprise à l'aide des applets de commande [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype). Utilisez cette stratégie pour configurer Teams conformément aux exigences de votre organisation.


> [!TIP]
> Pour rechercher les applets de commande PowerShell dont vous avez besoin pour l'interopérabilité, entrez « CsTeamsInteropPolicy » dans le champ **Filtre** de la [documentation des applets de commande PowerShell de Skype Entreprise](https://docs.microsoft.com/powershell/module/skype).

La stratégie d'interopérabilité de Teams permet à un professionnel de l'informatique de définir l'application dans laquelle un utilisateur préfère recevoir des appels et communiquer. Cette dernière peut être configurée pour conserver les communications dans un silo comprenant Teams et Skype Entreprise ou pour permettre à l'utilisateur de communiquer au-delà de l'application.

La stratégie d'interopérabilité de Teams est définissable au niveau du client ou de l'utilisateur. Il est même possible de la configurer pour permettre aux utilisateurs de choisir l'application dans laquelle ils souhaitent recevoir les appels et communiquer.

Cette flexibilité intégrée vise à aider votre entreprise à évaluer et migrer vers Teams suivant le rythme et l'organisation qui lui conviennent.

> [!NOTE]
> L'interopérabilité entre Teams et Skype Entreprise est prise en charge entre les utilisateurs exclusivement en ligne (Skype Entreprise Online et Teams) et les utilisateurs d'un déploiement local de Skype Entreprise au sein d'une topologie de déploiement mixte (hybride).

## <a name="what-interoperability-means"></a>Signification de l'interopérabilité
L'interopérabilité permet aux utilisateurs de Teams et de Skype Entreprise de discuter (messagerie instantanée) et de s'appeler via Teams et Skype Entreprise.

Comme les entreprises basculent de Skype Entreprise vers Teams, il devrait y avoir un mélange d'utilisateurs des différents clients au sein de l'entreprise.

Pour garantir une productivité continue, Teams permet aux utilisateurs de communiquer avec l'un ou l'autre système indépendamment de l'application utilisée (Teams ou Skype Entreprise).

L'interopérabilité se caractérise comme suit :
- Les utilisateurs de Skype Entreprise qui n'utilisent pas Teams peuvent discuter avec des utilisateurs de Teams et inversement.<p>
![Interopérabilité des conversations dans Teams](media/Interop_chat_experience_from_Teams.png)<br>
- Les utilisateurs de Skype Entreprise peuvent appeler les utilisateurs de Teams via les fonctions voix et vidéo et inversement. Les options d'appel avancées comme le transfert d'appel sont toujours opérationnelles, même dans le cas d'appels interopérables.<p>
![Interopérabilité des appels dans Teams](media/Interop_calling_experience_from_Teams.png)<br>

> [!NOTE]
> Du point de vue des utilisateurs de Skype Entreprise, les conversations et les appels de/vers Teams s'afficheront comme des conversations et appels de base dans Skype Entreprise. Consultez la section sur les [Restrictions de l'interopérabilité](#interop-experiences-limitations) pour en savoir plus.

> [!IMPORTANT]
> La présence unifiée entre Teams et Skype Entreprise n'est actuellement pas prise en charge, ce qui signifie que Teams et Skype Entreprise affichent leurs propres états de présence. Pour connaître la date de disponibilité de la présence unifiée, consultez la [Feuille de route de l'évolution des fonctionnalités entre Skype Entreprise et Microsoft Teams](https://aka.ms/skype2teamsroadmap).

## <a name="interop-requirements"></a>Exigences relatives à l'interopérabilité
Pour activer l'interopérabilité, les utilisateurs doivent satisfaire les critères suivants :
- Les utilisateurs doivent être activés (et/ou une licence doit leur être affectée) pour Teams.
- Les utilisateurs doivent être activés (et/ou une licence doit leur être affectée) pour Skype Entreprise Online.
    - Cela s'applique aux utilisateurs qui prévoient d'utiliser Teams uniquement ou Teams comme principale application de conversation et d'appel
- Dans un déploiement de Skype Entreprise hybride,
    - Les utilisateurs hébergés dans Skype Entreprise sur site (ou toute autre version Lync Server actuellement prise en charge par le déploiement d'une solution Skype Entreprise hybride) peuvent interagir avec les utilisateurs cloud de Teams
    - Les utilisateurs cloud qui prévoient d'utiliser Teams comme principale application de conversation et d'appel doivent être activés (et/ou une licence doit leur être affectée) pour Skype Entreprise Online

## <a name="supported-topologies-for-interop"></a>Topologies d'interopérabilité prises en charge
L'interopérabilité entre Teams et Skype Entreprise est principalement prise en charge pour les topologies de déploiement de Skype Entreprise suivantes :
- Skype Entreprise Online uniquement
- Skype Entreprise hybride (déploiement mixte entre Skype Entreprise Online et Skype Entreprise sur site)

### <a name="skype-for-business-online-only-topology"></a>Topologie de Skype Entreprise Online uniquement
Les entreprises qui utilisent le déploiement de Skype Entreprise uniquement peuvent profiter de la prise en charge de l'interopérabilité des conversations et des appels entre les utilisateurs de Skype Entreprise Online et les utilisateurs de Teams.

Dans cette topologie, les utilisateurs configurés avec Teams (principale application de conversation et d'appel) doivent également être activés pour Skype Entreprise Online pour que l'interopérabilité soit opérationnelle.

![Interopérabilité dans une topologie de déploiement Skype Entreprise Online uniquement](media/Interop_SkypeforBusinessOnlineOnly_topology.png)

### <a name="skype-for-business-hybrid-deployment-topology"></a>Topologie de déploiement de Skype Entreprise version hybride
Les entreprises dont le déploiement est mixte avec Skype Entreprise Online et le serveur Skype Entreprise en local dans une topologie de déploiement hybride, peuvent profiter de la prise en charge de l'interopérabilité des conversations et des appels entre les utilisateurs de Skype Entreprise (en ligne ou localement) et les utilisateurs de Teams.

Comme dans la topologie de déploiement de Skype Entreprise Online uniquement, les utilisateurs configurés avec Teams (principale application de conversation et d'appel) doivent également être activés pour et hébergés sur Skype Entreprise Online pour que l'interopérabilité soit opérationnelle.

![Interopérabilité dans une topologie de déploiement Skype Entreprise Online hybride](media/Interop_SkypeforBusinessHybrid_topology.png)

> [!IMPORTANT]
> La prise en charge de l'interopérabilité de la fonction Voix hybride de Skype Entreprise n'intègre pas les fonctionnalités vocales hybrides fournies via CCE (Cloud Connector Edition) ou la connectivité RTC locale à travers le déploiement existant (OPCH - On Prem Config Hybrid). Les utilisateurs de Teams ne peuvent pas utiliser les fonctions d'appels RTC via CCE ou OPCH.

### <a name="interop-experiences-limitations"></a>Restrictions de l'interopérabilité
Actuellement, outre l'absence de présence unifiée entre Teams et Skype Entreprise, entraînant l'indépendance des états de présence de Teams et Skype Entreprise, certaines fonctions ne sont pas disponibles lors des interactions (conversation et appel) entre Teams et Skype Entreprise.

Voici la liste des restrictions applicables à l'interopérabilité des conversations :
- Les conversations de groupe dans Teams ne peuvent inclure que des utilisateurs de Teams.
- Les conversations de groupe par messages instantanés dans Skype Entreprise ne peuvent inclure que des utilisateurs de Skype Entreprise.
- Le transfert de fichiers dans une conversation entre deux personnes ou l'ajout d'une pièce jointe (fichier) dans une conversation de groupe entre Teams et Skype Entreprise, et inversement, ne sont pas pris en charge.
- L'interopérabilité des conversations dans Teams n'est pas persistante.
- L'interopérabilité des conversations dans Teams ne prend pas en charge les repères, le texte enrichi, les jeux complets d'émoticônes, etc.

Voici la liste des restrictions applicables à l'interopérabilité des appels :
- Le partage d'écran (partage du bureau et des applications) entre Teams et Skype Entreprise n'est pas pris en charge.
- L'escalade des appels vocaux et vidéo en P2P en cours vers les appels de groupe impliquant des utilisateurs de Teams et de Skype Entreprise n'est pas prise en charge.

## <a name="managing-interoperability"></a>Gestion de l'interopérabilité
Pour gérer l'interopérabilité entre Teams et Skype Entreprise, la nouvelle stratégie d'interopérabilité de Teams peut être utilisée pour déterminer où envoyer les conversations et acheminer les appels (Teams ou Skype Entreprise). En outre, cette stratégie est configurable pour tous les utilisateurs de l'organisation (stratégie globale) ou applicable de manière individuelle. Elle est gérable via la session Windows PowerShell distante de Skype Entreprise à l'aide des applets de commande [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps).

Cette stratégie est configurée par défaut pour assurer l'utilisation de et Skype Entreprise en parallèle tout en offrant un minimum d'interopérabilité. Cette approche vise à préserver l'ininterruption des communications et des processus d'entreprise dans vos organisations suite à l'adoption de Teams.

### <a name="interop-policy-overview"></a>Présentation de la stratégie d'interopérabilité
La stratégie d'interopérabilité de Teams comprend les paramètres suivants :

|Paramètre                    |Valeurs possibles      |Description  |
|-----------------------------|---------------------|---------|
|`ChatDefaultClient`          | Par défaut, SfB, Teams | Ce paramètre spécifie l'application de conversation par défaut.        |
|`CallingDefaultClient`       | Par défaut, SfB, Teams | Ce paramètre spécifie l'application d'appel par défaut.        |
|`AllowEndUserClientOverride` | True, False         | Ce paramètre spécifie que les utilisateurs peuvent remplacer l'application de conversation et d'appel par défaut.         |

> [!WARNING]
> Alors qu'il est actuellement possible de créer une stratégie d'interopérabilité Teams avec des valeurs indépendantes pour les paramètres `ChatDefaultClient` et `CallingDefaultClient`, nous prévoyons de modifier cela à l'avenir. Pour l'heure, veillez à utiliser la même valeur pour les deux paramètres.

#### <a name="chat-default-client"></a>Client de conversation par défaut
Le paramètre `ChatDefaultClient` définit le routage des conversations entre Teams et Skype Entreprise. La valeur globale par défaut de ce paramètre est définie sur **Par défaut**.

> [!IMPORTANT]
> Le paramètre `ChatDefaultClient` n'est actuellement pas pris en charge par Teams. Nous mettrons à jour cette documentation pour décrire le comportement attendu une fois que ce paramètre sera pris en charge par Teams. Les capacités d'interopérabilité de conversation existantes entre Teams et Skype Entreprise contrôlées au niveau du client continueront de fonctionner en l'état.

#### <a name="calling-default-client"></a>Client d'appel par défaut
Le paramètre `CallingDefaultClient` définit le routage des appels entre Teams et Skype Entreprise. La valeur globale par défaut de ce paramètre est définie sur **Par défaut**.

Ci-après figure l'explication détaillée de l'influence de chaque réglage de ce paramètre sur le comportement des clients Teams et Skype Entreprise.

|Appel de l'appelant à partir de  |Réglage : Par défaut ; appel reçu sur  |Réglage : Teams ; appel reçu sur  |Réglage : SfB ; appel reçu sur  |
|---------|---------|---------|---------|
|**Skype Entreprise**     |Skype Entreprise         |Teams        |Skype Entreprise         |
|**Teams**     |Teams         |Teams         |Skype Entreprise         |
|**PSTN**   |Skype Entreprise        |Teams        |Skype Entreprise         |
|**Skype Entreprise, version fédérée**     |Skype Entreprise         |Skype Entreprise         |Skype Entreprise         |

> [!IMPORTANT]
> Basculer de `CallingDefaultClient` vers Teams affectera également les appels vers les téléphones IP Skype Entreprise. Les appels entrants ne seront pas reçus sur les téléphones et seuls les clients Teams entendront la sonnerie. Consultez la [Feuille de route de l'évolution des fonctionnalités entre Skype Entreprise et Microsoft Teams](https://aka.ms/skype2teamsroadmap) pour en savoir plus sur la prise en charge des téléphones SIP certifiés existants.

#### <a name="allowing-user-choice"></a>Autoriser l'utilisateur à choisir
Le paramètre `AllowEndUserClientOverride` accepte les valeurs booléennes (**VRAI** ou **FAUX**). Lorsqu'il est réglé sur **VRAI**, Teams autorise les utilisateurs à sélectionner l'application de réception des appels (Teams ou Skype Entreprise). En outre, les utilisateurs peuvent changer d'application principale à tout moment.

![Option d'application d'appel préférée](media/Preferred_calling_application_option.png)

La valeur générale par défaut de ce paramètre est **FAUX**, qui ne permet pas aux utilisateurs de choisir leur application principale sans intervention de l'administrateur.

## <a name="teams-interop-policy-special-cases"></a>Cas spéciaux de la stratégie d'interopérabilité de Teams
Lors de l'affectation de la stratégie d'interopérabilité de Teams, les utilisateurs restent hébergés dans Skype Entreprise sur site (dans une topologie de déploiement mixte ou hybride). Les utilisateurs de la fonction Voix hybride (via CCE ou OPCH) et les utilisateurs utilisant des flux de travail Skype Entreprise spécifiques sont considérés comme des cas spéciaux. Ils requièrent une attention particulière lorsque la stratégie leur est affectée.

### <a name="policy-for-skype-for-business-on-premises-users"></a>Stratégie pour les utilisateurs de Skype Entreprise sur site
Dans une topologie de déploiement mixte (hybride), les utilisateurs hébergés dans Skype Entreprise en local ne doivent jamais se voir attribuer la stratégie de Teams pour les paramètres `ChatDefaultClient` et `CallingDefaultClient`. Dans le cas contraire, ils ne pourront pas recevoir de messages de conversation ni d'appels. Utilisez la définition de stratégie suivante pour les utilisateurs sur site :

|Paramètre  |Valeur  |
|---------|---------|
|`ChatDefaultClient`    |Par défaut ou SfB         |
|`CallingDefaultClient`     |Par défaut ou SfB         |
|`AllowEndUserClientOverride`     |False         |

> [!IMPORTANT]
> Lors du déplacement des utilisateurs de Skype Entreprise Online vers Skype Entreprise sur site, ou inversement, vous devez veiller à ce que la stratégie d'interopérabilité de Teams affectée à l'utilisateur soit conforme au comportement attendu. N'oubliez pas que les utilisateurs sur site ne peuvent pas configurer l'utilisation de Teams comme principale application de conversation et d'appel.

### <a name="policy-for-hybrid-voice-users-cce-or-opch"></a>Stratégie pour les utilisateurs de la fonction Voix hybride (CCE ou OPCH)
Les utilisateurs de Skype Entreprise Online activés pour le système téléphonique avec Voix hybride (via CCE ou OPCH) ne peuvent pas recevoir d'appels PSTN dans Teams. Lors de l'affectation de la stratégie d'interopérabilité de Teams aux utilisateurs de la fonction Voix Hybride, appliquez la définition de stratégie suivante.

|Paramètre  |Valeur  |
|---------|---------|
|`ChatDefaultClient`    |Par défaut ou SfB ou Teams         |
|`CallingDefaultClient`     |Par défaut ou SfB         |
|`AllowEndUserClientOverride`     |False         |

### <a name="policy-for-users-with-specialized-skype-for-business-workflows"></a>Stratégie pour les utilisateurs utilisant des flux de travail Skype Entreprise spécifiques
Dans certains cas, un groupe d'utilisateurs peut utiliser des applications tierces qui reposent sur Skype Entreprise (centre d'appels, réception, etc.). Le cas échéant, vous devrez vous assurer qu'ils continuent d'utiliser Skype Entreprise jusqu'à ce que des fonctionnalités équivalentes soient disponibles dans Teams. Pour ces utilisateurs, appliquez la définition de stratégie suivante :

|Paramètre  |Valeur  |
|---------|---------|
|`ChatDefaultClient`    |Par défaut ou SfB         |
|`CallingDefaultClient`     |Par défaut ou SfB         |
|`AllowEndUserClientOverride`     |False         |