---
title: Parcours de mise à niveau et coexistence de Skype pour les entreprises et les Teams Microsoft
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 04/04/2018
ms.topic: article
ms.service: msteams
ms.reviewer: lehewe
description: Détails de Skype pour les options de coexistence Business et Teams de Microsoft et les modes et les trajets mise à niveau pour les équipes de Skype pour les entreprises avec des exemples de scénarios.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 46967004ec571e593ea3f73e213c3d0e5b801f86
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/05/2018
---
# <a name="upgrade-journey-and-coexistence-of-skype-for-business-and-microsoft-teams"></a>Parcours de mise à niveau et coexistence de Skype pour les entreprises et les Teams Microsoft

Comme un Skype existant pour client d’entreprise, le passage complet aux équipes peut prendre du temps. Toutefois, vous pouvez commencer l’optimisation des équipes aujourd'hui, en permettant à vos utilisateurs d’utiliser des équipes avec Skype pour les entreprises. Étant donné qu’il existe certaines fonctionnalités communes entre les deux applications, nous vous conseillons d’étudier les modes de mise à niveau disponibles pour vous aider à déterminer le chemin d’accès est adapté à votre organisation. Par exemple, vous pourriez opter pour activer toutes les charges de travail sur les deux solutions sans l’interopérabilité. Ou bien, vous pouvez décider de gérer l’expérience de l’utilisateur, en introduisant progressivement des capacités des équipes ou en ciblant des groupes d’utilisateurs pour les fonctions sélectionner, jusqu'à ce que votre organisation est prête pour la mise à niveau de tout le monde à des équipes.

À l’instar de tout déploiement, nous vous encourageons fortement à [piloter votre plan prévu](pilot-essentials.md) avec un groupe sélectionné d’utilisateurs avant de déployer les équipes de votre organisation plus large. N’oubliez pas que les nouvelles technologies de présentation peut être sans interruption pour les utilisateurs. Prendre le temps d’évaluer la préparation de l’utilisateur et mettre en œuvre un plan de formation pour empêcher les utilisateurs tenu au courant et à accélérer leur acceptation des équipes et de communication. 

> [!IMPORTANT]
> Le Skype pour entreprise aux équipes de parcours de mise à niveau est en constante évolution. Cet article vous aidera à comprendre la mise à niveau des équipes à venir, mais elle n’inclut des instructions de mise à niveau de bout en bout. Une mise à niveau réussie de Skype pour entreprise inclut à la fois techniques et utilisateur des activités axées sur la disponibilité. Nous travaillons sur ce guide maintenant, et nous allons être publier bientôt.
 
## <a name="upgrade-and-coexistence-modes-defined"></a>Modes de mise à niveau et coexistence définis
Pour aider votre processus décisionnel, familiarisez-vous avec les différents modes, concepts et la terminologie appropriée à la mise à niveau de Skype pour les entreprises à des équipes.

### <a name="skype-for-business-with-teams-collaborationndashonly-mode"></a>Skype pour entreprise avec la collaboration d’équipes&ndash;mode uniquement

Dans ce mode, les équipes est configuré pour prendre en charge des équipes et des conversations à base de canaux uniquement, avec des conversations privées, appel, réunions et désactivées.

Ce mode est un excellent moyen de présenter les équipes dans votre environnement tout en continuant d’exploiter vos investissements existants dans Skype pour les entreprises. 

### <a name="skype-for-business-with-teams-collaboration-and-meetings-mode"></a>Skype pour entreprise avec la collaboration d’équipes et de mode de réunions
En utilisant des équipes pour les équipes et les conversations à base de canaux dans ce mode, les utilisateurs démarrent à l’aide des équipes de planifier et de mener des réunions. Conversations privées et voix et vidéo appel, restent sur Skype pour les entreprises.

Si les fonctionnalités que fournit pour les réunions des équipes aux besoins de votre organisation, mais business doit conserver des fonctionnalités vocales entreprise dans Skype pour les entreprises, vous pouvez configurer des équipes pour remettre Skype pour les entreprises avec des réunions et la collaboration des équipes fonctionnalités pour l’ensemble de votre organisation (ou certaines parties de celui-ci).

### <a name="islands-mode"></a>Mode des îles
Il s’agit du mode par défaut. Il permet de déployer des équipes indépendamment Skype pour les entreprises. 

Dans ce mode, les équipes les utilisateurs peuvent immédiatement utiliser équipes avec toutes ses fonctionnalités avec d’autres utilisateurs d’équipes, tandis que les autres utilisateurs peuvent continuer à utiliser Skype pour entreprise et rester productifs sans incidence sur la manière dont ils utilisent Skype pour les entreprises aujourd'hui.

> [!NOTE]
> Mode d’îles est fourni avec l’interopérabilité temporaire à sens unique qui permet l’interopérabilité de conversation des équipes Skype pour l’entreprise lorsque les conditions suivantes sont remplies :
> - L’utilisateur d’équipes est hébergé à et de Skype pour l’activité en ligne.
> - Le Skype pour l’utilisateur professionnel n’a jamais utilisé les équipes (ou n’est pas autorisé pour les équipes).
>
> Ce mode est utile lorsque vous souhaitez que les utilisateurs qui utilisent principalement des équipes pour vous connecter avec d’autres utilisateurs de l’organisation qui sont toujours à l’aide de Skype pour entreprise uniquement.
>
> Une fois que les utilisateurs ayant précédemment utilisé uniquement Skype pour entreprise commencent à utiliser des équipes, toutes leurs conversations par d’autres utilisateurs équipes arriveront dans des équipes. Cela passe ces utilisateurs en mode des îles. À partir de là, ils doivent conserver en cours d’exécution équipes pour vous assurer qu’ils restent connectés avec les autres utilisateurs d’équipes dans l’organisation.

### <a name="teams-only-mode"></a>Équipes seule
Dans ce mode de mise à niveau, le Skype pour client d’entreprise ne fournit plus de IM de base, les indicateurs de présence, chat, appel ou fonctions de réunion. Les utilisateurs qui travaillent en mode de mise à niveau doivent utiliser des équipes que leur principal outil de communication et de collaboration.

Les utilisateurs qui sont prêts à l’emploi des équipes comme leur principal outil de collaboration et de communication peuvent être mis à niveau en tant qu’utilisateurs équipes uniquement.

Un utilisateur mis à niveau ne permet le Skype pour client d’entreprise pour rejoindre Skype existant de réunions professionnelles ou les réunions sur Skype pour entreprise organisée par non mis à niveau des utilisateurs ou des intervenants externes. Un utilisateur mis à niveau peut continuer à communiquer avec d’autres utilisateurs de l’organisation qui sont toujours à l’aide de Skype pour les entreprises en utilisant les fonctionnalités d’interopérabilité entre les équipes et Skype pour les entreprises.

### <a name="skype-for-businessndashonly-mode"></a>Skype pour entreprise&ndash;mode uniquement
Les utilisateurs qui ont besoin de rester dans Skype pour l’entreprise peut être configuré comme Skype pour entreprise&ndash;uniquement les utilisateurs. Les utilisateurs configurés dans ce mode ne peuvent pas à l’aide des équipes et seront en mesure de communiquer avec des utilisateurs équipes uniquement en utilisant les fonctionnalités d’interopérabilité entre les équipes et Skype pour les entreprises.

## <a name="upgrade-and-coexistence-building-blocks"></a>Mise à niveau et coexistence des blocs de construction
Pour formellement préparer votre organisation pour son voyage aux équipes, vous avez besoin commencer à planifier pour les scénarios de mise à niveau afin de pouvoir éventuellement votre organisation adopter entièrement les équipes en tant que votre solution de collaboration et de communication unique.

Lorsque certains de vos utilisateurs sont prêts à utiliser uniquement des équipes pour leurs communications quotidiennes et de collaboration a besoin, vous pouvez démarrer la mise à niveau de ces utilisateurs à des équipes par l’activation du mode d’équipes uniquement pour les.

S’il n’est pas possible pour toute l’organisation atteindre des équipes, vous pouvez démarrer en entièrement adoptant des équipes comme une solution de collaboration de groupe tout d’abord tout en conservant les Skype pour les entreprises en tant que solution de communications unifiées de votre organisation. Une autre option consiste à commencer à déplacer les réunions d’équipes en plus de la présentation des fonctionnalités de collaboration de groupe équipes, tout en conservant le reste des fonctionnalités des communications unifiées dans Skype pour les entreprises.

![Une capture d’écran de mise à niveau de blocs de construction de Skype pour entreprise aux équipes, consistant à Skype pour entreprise avec la collaboration d’équipes&ndash;mode uniquement, Skype pour entreprise avec la collaboration des équipes et mode de réunions, mode d’îles, équipes seule et Skype pour Business&ndash;mode uniquement.](media/upgrade_and_coexistence_building_block.png)

Le tableau suivant compare les modes de mise à niveau et de coexistence.

|Mode  |Situation  |Objectifs à court terme  |Avantages  |Avertissements  |
|---------|---------|---------|---------|---------|
|Skype pour entreprise avec la collaboration d’équipes uniquement |Skype pour le déploiement d’entreprise avec des exigences qui ne sont pas encore remplies par des équipes (par exemple, avancées de conformité)<br><br>Nécessaire à long terme et/ou engagement à Skype pour entreprise|Adoption des équipes de démarrer rapidement, tout d’abord en se concentrant sur la collaboration de groupe<br><br> Pour conserver toutes les charges de travail des communications unifiées sur Skype pour entreprise pour l’instant|Pas de possibilités de chevauchements entre les équipes et Skype pour entreprise<br><br>La messagerie instantanée et le chat résidera dans Skype pour les entreprises (liée à l’appel)<br><br>|
|Skype pour entreprise avec la collaboration des équipes et des réunions |Skype pour le déploiement d’entreprise avec utilisation importante d’enterprise voice et des exigences qui ne sont pas encore remplies par des équipes d’appel<br><br>Nécessaire à long terme et/ou engagement à Skype pour entreprise<br><br>Peut être à l’aide d’un service tiers réunion|Adoption des équipes de démarrer rapidement, allant au-delà de collaboration de groupe<br><br>Améliorer l’expérience de réunions de vos utilisateurs|Pas de possibilités de chevauchements<br><br>Réunions de haute valeur dans les équipes (WebRTC, nuage vos enregistrements de réunions, etc.)|La messagerie instantanée et le chat résidera dans Skype pour les entreprises (liée à l’appel)|
|Îles |Skype plus petite ou la plus simple pour le déploiement d’entreprise<br><br>Capacité et la volonté de gérer une complexité à court terme pour atteindre plus rapidement les équipes |Aller aussi rapidement que possible à l’expérience d’équipes complet<br><br>Conduite d’une preuve de concept (PoC) des équipes |Simple de n’emploi, aucune interopérabilité<br><br>Meilleure expérience d’équipes initial pour toutes les fonctions |Exige une communication efficace pour éviter toute confusion et à l’utilisation du lecteur vers les équipes<br><br>Impose de quitter utilisateurs ont adopté entièrement équipes à la fois Skype pour entreprise est hors service.|
|Seules les équipes |Certains utilisateurs ont besoin pour rester sur Skype pour entreprise<br><br>Vous mettez à niveau votre Skype pour les utilisateurs professionnels en ligne à des équipes tout en conservant Skype pour entreprise local utilisateurs sur Skype pour Business Server<br><br>Vous a peut-être déjà déployé les utilisateurs en mode des îles et que vous êtes prêt à la retirer Skype pour l’entreprise pour les groupes d’utilisateurs |Réduire les coûts de la variable sur Skype pour les entreprises (opérations de serveur sur site, contrat de sous-traitance, etc.)<br><br>Atteindre une expérience complète équipes aussi rapidement que possible, au moins à certains utilisateurs|Limite la confusion de l’utilisateur en fournissant un seul client à utiliser|Interopérabilité prend uniquement en charge la discussion de base et l’appel entre Skype pour les entreprises et les équipes|
|Skype pour entreprise uniquement |Certains utilisateurs ont besoin pour rester sur Skype pour entreprise<br><br>|Limite la confusion de l’utilisateur en fournissant un seul client à utiliser|Continuer à répondre aux besoins de l’entreprise qui actuellement peuvent uniquement être satisfaites par Skype pour entreprise|Interopérabilité prend uniquement en charge la discussion de base et l’appel entre Skype pour les entreprises et les équipes|

> [!NOTE]
> Pour vous aider à activer chacun des modes ci-dessus, nous vous proposerons un Guide de démarrage rapide sur l’exécution de votre parcours de Skype pour entreprise aux équipes lorsque les stratégies sont disponibles à un moment ultérieur. Restez en ligne !

## <a name="upgrade-journeys"></a>Parcours de mise à niveau
Vous pouvez prendre plusieurs approches de mise à niveau à partir de Skype pour les entreprises, soit en ligne ou sur site, à des équipes :
- Dans un parcours de mise à niveau simple, vous d’abord déployez les équipes dans Skype pour entreprise avec la collaboration d’équipes&ndash;uniquement dans le cadre de l’évaluation et l’adoption anticipée et mode puis implémenter uniquement les équipes dans le but de déclassement finalement de Skype pour les entreprises à partir de la environnement pour tous les utilisateurs de l’organisation.
- Un parcours de mise à niveau progressif offre un mode de mise à niveau spécifique à un groupe spécifique d’utilisateurs (également appelé un *cohorte*), en fonction de leurs communications et les besoins de la collaboration. Au fil du temps, l’ensemble de l’organisation peut converger en utilisant uniquement des équipes et finira par remplacer Skype pour les entreprises. Toutefois, si votre organisation a des raisons commerciales incontournables pour conserver Skype pour les entreprises, par exemple une dépendance sur une solution basée sur les Communications unifiées gérés de API UCMA qui s’intègre avec les applications professionnelles de, ou une solution de mur éthique actuellement disponible pour Skype pour entreprise uniquement, vous pouvez mettre à niveau une majorité d’utilisateurs équipes seule tout en conservant de Skype pour les utilisateurs professionnels dans un de le Skype pour les modes d’entreprise pour une partie de vos utilisateurs.

> [!IMPORTANT]
> Pour les deux types de parcours de mise à niveau, si votre organisation est actuellement un Skype pour déploiement sur site de travail uniquement, vous avez besoin commencer à planifier la mise en œuvre de Skype pour hybride d’entreprise avant la mise à niveau de vos utilisateurs en mode équipes seulement. Cela vous permet également de faciliter l’interopérabilité avec les équipes.
> Utilisez [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) pour guider votre Skype pour implémentation hybride de l’activité.

> [!NOTE]
> Équipes seule nécessite que les utilisateurs qui font partie des cohortes hébergés dans Skype pour professionnels en ligne, et une relation hybride entre votre Skype pour un déploiement sur site entreprise et votre Skype pour clients d’entreprise en ligne est nécessaire pour faciliter la mise à niveau et interopérabilité entre Skype pour les entreprises et les équipes. Le déplacement à Skype pour entreprise en ligne est nécessaire pour les utilisateurs qui appartiennent à des cohortes avant qu’ils sont mis à niveau en mode équipes seulement. Skype pour Business Server 2019 et également d’une future mise à jour cumulative Skype pour 2015 de serveur d’entreprise, plan simplifier les mécanismes de mise à niveau des utilisateurs locaux à des équipes par la gestion de la migration à Skype pour Business Online et mise à niveau des utilisateurs à des équipes uniquement mode en une seule étape.

Quel voyage que vous choisissez, Microsoft est là pour vous aider dans le processus de mise à niveau. À partir des spécifications techniques aux ressources de disponibilité utilisateur, nous partagerons recommandées afin de garantir une transition réussie de Skype pour les entreprises à des équipes. Conseils de mise à niveau sera bientôt être prêt, veillez à vérifier pour plus d’informations.

### <a name="simple-upgrade-journey"></a>Parcours de mise à niveau simple
Le parcours de mise à niveau simple est illustré dans le diagramme suivant.

![Une capture d’écran du parcours de mise à niveau simple. Tous les utilisateurs initialement utilisent équipes dans Skype pour entreprise avec la collaboration d’équipes&ndash;uniquement en mode, puis transition équipes uniquement en mode, l’état final de la mise à niveau vers des équipes de toute l’organisation.](media/upgrade_and_coexistence_simple_upgrade_journey.png)

Équipes est déployé sur tous les utilisateurs de l’organisation et configuré dans Skype pour les entreprises avec la collaboration d’équipes&ndash;mode uniquement. Lorsque votre organisation détermine que les équipes est prêt à répondre à tous vos besoins de collaboration et les communications, tous les utilisateurs sont mis à niveau en mode équipes seulement. À ce stade, Skype pour entreprise peut être déclassé à partir de l’environnement.

### <a name="gradual-upgrade-journey"></a>Parcours de mise à niveau progressive
Un exemple d’un parcours de mise à niveau graduel est illustré dans le diagramme suivant.

![Dans le parcours de mise à niveau progressif, cohortes d’utilisateurs d’abord utilisent des équipes dans une variété de modes de mise à niveau, côte à côte avec Skype pour les entreprises. Une transition cohortes équipes en mode seulement, tandis qu’un groupe d’utilisateurs reste avec Skype pour entreprise avec la collaboration d’équipes et de mode de réunions.](media/upgrade_and_coexistence_gradual_upgrade_journey.png)

Équipes est déployée dans l’organisation à l’aide des différents modes de mise à niveau pour différents groupes d’utilisateurs ou des cohortes. Par exemple, un groupe d’utilisateurs peut être activé pour le mode d’îles, autre activé pour Skype pour entreprise avec la collaboration d’équipes et de mode de réunions, pendant un troisième groupe d’utilisateurs peut initialement être activé pour Skype pour entreprise avec la collaboration d’équipes&ndash;uniquement mode.

Au fil du temps, des groupes d’utilisateurs peuvent être mis à niveau en mode aux équipes seulement, suivi par le reste de l’organisation. Finalement, l’ensemble de l’organisation sera prête à déclasser Skype pour entreprise et utiliser uniquement des équipes de communication et de collaboration, ou, si des exigences commerciales imposent que Skype pour professionnels soient conservés pour un groupe spécifique, la majorité des utilisateurs dans le organisation peut utiliser des équipes uniquement. <br><br>
<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Points de décision</td><td><ul> Les parcours de mise à niveau est adapté aux besoins de votre organisation ?<br><br></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul> Identifiant votre modèle en cours de déploiement, scénarios de cas d’utilisation, et les points clés de votre organisation vous informe le voyage aux équipes qui est la mieux adapté à votre organisation.<br><br></ul></td></tr>
</table>

## <a name="upgrade-scenarios"></a>Scénarios de mise à niveau
Les recommandations suivantes selon les parcours de mise à niveau décrites plus haut dans cet article, sont fournie pour Skype spécifique pour les modèles de déploiement d’entreprise peuvent correspondre à votre modèle de déploiement actuel. 

|Modèle de déploiement  |Point de départ  |Considérations relatives à la  |Voyage  |
|---------|---------|---------|---------|
|Skype pour les entreprises en ligne uniquement avec des Plans d’appel |Clients Office 365 avec Azure AD Connect, SharePoint Online, Exchange Online et Skype pour professionnels en ligne<br><br> Système de téléphone à appeler Plans implémentée à l’aide de Skype pour l’activité en ligne pour tous les utilisateurs |Casques certifiés tirer parti de tous les utilisateurs<br><br> Réunions exigent des participants VoIP externes internes et anonymes<br><br> Messagerie inclut les contacts internes et externes |**Plan d’évolution de la messagerie**: fonctionnalité de fédération ciblée pour la version R2 de 2018<br><br> **Calendrier de réunions**: fonctionnalités sont déjà disponibles<br><br> **Feuille de route l’appel**: fonctionnalités sont déjà disponibles<br><br> Blocs de construction :<ul><li> Skype pour entreprise avec la collaboration d’équipes&ndash;mode uniquement</li><li> Équipes seule</li></ul>|
|Skype pour les entreprises en ligne avec connecteur de nuage Edition (CCE) |Clients Office 365 avec Azure AD Connect, SharePoint Online, Exchange Online et Skype pour professionnels en ligne<br><br> Système téléphonique vocale hybride via CCE implémenté à l’aide de Skype pour entreprise en ligne à plusieurs emplacements d’office<br><br> 1 000 utilisateurs sont à l’aide de la messagerie vocale charges de travail et uniquement|80 % de la population d’utilisateurs tire parti de téléphone avec voix hybride via CCE<br><br> Tous les échanges sont contenu au sein de la société<br><br> Les réunions ne sont pas en cours d’utilisation, mais il y a intérêt à l’activation d’audioconférence à l’avenir|**Plan d’évolution de la messagerie**: vous souhaitez que les fonctionnalités sont disponibles<br><br> **Calendrier de réunions**: futurs besoins<br><br> **Feuille de route l’appel**: routage à fonction d’équipes destinée au lancement du 2e trimestre de 2018 Direct <br><br> Blocs de construction :<ul><li> Skype pour entreprise avec la collaboration d’équipes et de mode de réunions</li><li> Équipes seule</li></ul> |
|Skype pour entreprise hybride |Clients Office 365 avec Azure AD Connect, SharePoint Online, Exchange Online et Skype pour professionnels en ligne<br><br> Skype pour Business Server 2015 est déployé et hybride est configuré avec Skype pour professionnels en ligne|Un nombre d’utilisateurs requiert la possibilité d’enregistrer les réunions<br><br> Il y a 10 salles de conférence, exploitant actuellement des systèmes de salle Skype v2<br><br> L’organisation souhaite profiter des équipes comme un outil de collaboration aussi rapidement que possible|**Plan d’évolution de la messagerie**: vous souhaitez que les fonctionnalités sont disponibles<br><br> **Calendrier de réunions**: enregistrement de la réunion, fonctionnalité de périphériques salle ciblée pour la version R2 de 2018 de réunion en nuage<br><br> **Feuille de route l’appel**: fonctionnalités souhaitées sont disponibles<br><br> Blocs de construction :<ul><li>Skype pour entreprise avec la collaboration d’équipes&ndash;mode uniquement</li><li> Skype pour entreprise avec la collaboration d’équipes et de mode de réunions</li><li>Mode des îles</li><li>Équipes seule</li></ul> |
|Skype pour Business Server (sur site) |Clients Office 365 avec Azure Connect d’Active Directory et Exchange Online<br><br> SharePoint et Skype pour entreprises sont déployés sur site|Fonctionnalité de voix entreprise complète définie (Skype pour Business Server 2015) actuellement en cours d’utilisation<br><br> Déployé de centre de contact<br><br> Les réunions sont menées avec les utilisateurs fédérés internes et externes, à l’aide de VoIP et conférence à distance<br><br> Communication avec les utilisateurs internes et externes|Déploiement de SharePoint en ligne<br><br> Configurer Skype pour hybride d’entreprise (domaine split)<br><br>**Plan d’évolution de la messagerie**: fonctionnalité de fédération ciblée pour la version R2 de 2018<br><br> **Calendrier de réunions**: fédérés réunion-join, fonction de salle d’attente RTPC ciblée pour la version R2 de 2018<br><br> **Feuille de route l’appel**: fonctionnalité ciblée pour la version du 4e trimestre de 2018 et à<br><br>Blocs de construction :<ul><li>Mode d’îles (pilote)</li><li>Skype pour entreprise avec la collaboration d’équipes&ndash;mode uniquement</li><li>Skype pour entreprise avec la collaboration d’équipes et de mode de réunions</li><li>Équipes seule et Skype pour entreprise&ndash;mode uniquement</li></ul><br>Recherchez la mise à niveau à Skype pour Business Server 2019|

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Points de décision</td><td><ul> Quel scénario de mise à niveau s’applique à votre organisation ?<br><br></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul> Décidez de la chronologie de parcours de mise à niveau de votre organisation en fonction de la messagerie, de réunions et en appelant les besoins de l’entreprise.<br><br> Déterminer le travail supplémentaire requis pour terminer votre parcours de mise à niveau.<br><br></ul></td></tr>
</table>

## <a name="see-also"></a>Voir aussi
[Gérer les équipes pendant la transition vers le nouveau Microsoft Teams et Skype pour Business Admin Center](manage-teams-skypeforbusiness-admin-center.md)
