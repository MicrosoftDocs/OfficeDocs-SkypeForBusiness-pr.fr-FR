---
title: En savoir plus sur les applications dans Microsoft Teams
ms.reviewer: ''
description: Découvrez les applications et décidez des applications à autoriser dans Teams en fonction du profil de votre organisation et des exigences métier.
ms.topic: conceptual
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
audience: admin
ms.service: msteams
ms.subservice: teams-apps
ms.date: 10/01/2022
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020; intro-overview; intro-hub-or-landing
ms.openlocfilehash: 7ded369ab991a37e711c416a7448447f148c069c
ms.sourcegitcommit: 339a35e461c84ee309ade1a53299ba12231df7a3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/29/2022
ms.locfileid: "69677414"
---
# <a name="understand-microsoft-teams-apps-and-their-capabilities"></a>Comprendre Microsoft applications Teams et leurs fonctionnalités

Les applications dans Teams aident les utilisateurs à rassembler leurs outils et services d’espace de travail et à collaborer avec d’autres personnes. Par exemple, les utilisateurs finaux utilisent une application Calendrier épinglée dans Teams pour collaborer rapidement avec d'autres personnes, une application avec une fonctionnalité de bots informant les utilisateurs de la qualité d'un service web dans un canal Teams, et une application pour partager et assigner des tâches à divers utilisateurs finaux dans un canal. Microsoft les applications Teams sont des applications SaaS web qui n’ont pas besoin d’être déployées localement.

En tant qu’administrateur, vous définissez un processus de gouvernance des applications qui équilibre les exigences étendues des utilisateurs finaux, ainsi que les stratégies informatiques, les normes et les profils de risque de votre organisation.

Notre [vaste catalogue](https://appsource.microsoft.com/marketplace/apps?product=office%3Bteams&page=1) d’applications Teams validées et sécurisées permet aux utilisateurs finaux d’accéder aux outils et services dont votre organisation a besoin chaque jour. Le Centre d’administration Teams fournit aux administrateurs des contrôles et des configurations de niveau entreprise pour régir les applications. Vous contrôlez la disponibilité des applications pour chaque utilisateur dans les différents contextes tels que les réunions, les chats et les canaux.

Cet article vous aide à comprendre les types d'applications et l'endroit d'où vos utilisateurs accèdent à ces applications. Pour en savoir plus sur l'utilisation des applications, lisez [Vue d'ensemble des applications pour les utilisateurs finaux](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0).

Les différents types d’applications que vos utilisateurs finaux peuvent utiliser dans Teams sont les suivants :

* [Applications principales qui font partie de Teams](#core-apps).
* Autres [applications créées par Microsoft](#apps-created-by-microsoft).
* [Applications tierces](#third-party-apps-created-by-independent-app-developers) créées par des partenaires (validées par Microsoft).
* [Applications personnalisées créées](#custom-apps-created-within-an-organization-for-internal-use) par votre propre organisation.

## <a name="core-apps"></a>Applications principales

Certaines fonctionnalités de Teams, telles que le flux d'activité, les équipes, les conversations, le calendrier, les appels, les fichiers et les devoirs (clients de l’éducation) sont disponibles par défaut et épinglées par défaut pour faciliter l'accès des utilisateurs finaux. Pour les employés de première ligne, seules les activités, les shifts, les conversations et les appels sont disponibles et épinglés. En tant qu'administrateur, vous pouvez modifier ce comportement par défaut en utilisant la [stratégie de configuration](/microsoftteams/teams-app-setup-policies).

:::image type="content" source="media/core-apps-pinned1.png" alt-text="Les applications principales sont les applications épinglées dans Teams par défaut." lightbox="media/core-apps-pinned2.png":::

## <a name="apps-created-by-microsoft"></a>Applications créées par Microsoft

Microsoft fournit de nombreuses applications pour améliorer la productivité et la collaboration. Vous et les utilisateurs finaux pouvez trouver ces applications en recherchant Microsoft répertorié en tant qu’éditeur dans le Centre d’administration Teams ou répertorié en tant que fournisseur dans Teams Store.

Teams insère un ensemble d’applications intégrées, notamment Listes, Tâches, Compliments, Approbations, etc. Nous vous recommandons d'inclure les applications recommandées, telles que Planner, dans votre déploiement initial de Teams.

:::image type="content" source="media/microsoft-apps-in-tac1.png" alt-text="Capture d’écran montrant la liste des applications Microsoft dans le Centre d’administration Teams." lightbox="media/microsoft-apps-in-tac2.png":::

## <a name="third-party-apps-created-by-independent-app-developers"></a>Applications tierces créées par des développeurs d’applications indépendants

En plus des applications Microsoft fournies, vous pouvez utiliser des applications tierces. Microsoft valide rigoureusement les fonctionnalités et la sécurité de toutes ces applications. Des tests manuels et automatisés élaborés sont exécutés avant de rendre ces applications disponibles dans le magasin Teams et de nombreux tests se poursuivent à une cadence régulière même après la publication en direct des applications. Pour comprendre les avantages de la validation des applications, consultez [validation des applications tierces](overview-of-app-validation.md). Certaines applications s’abonnent au [programme de conformité Microsoft](overview-of-app-certification.md) pour faire l’objet de plusieurs niveaux de vérifications supplémentaires au-delà de la validation.

:::image type="content" source="media/3p-apps-in-teams.png" alt-text="Capture d’écran d’un exemple d’applications tierces dans le magasin Teams.":::

## <a name="custom-apps-created-within-an-organization-for-internal-use"></a>Applications personnalisées créées au sein d’une organisation pour une utilisation interne

Les applications créées par les développeurs de votre organisation sont appelées applications personnalisées ( ou applications de secteur d'activité). Votre organisation peut commander la création d'applications personnalisées pour répondre à des besoins spécifiques. Vous avez la possibilité d'autoriser ou de bloquer ces applications pour l'ensemble de l'organisation ou pour des utilisateurs spécifiques. Les développeurs de votre organisation peuvent créer des solutions personnalisées à faible code en utilisant l'intégration de Teams avec [Microsoft Power Plateforme](/microsoftteams/platform/samples/teams-low-code-solutions).

Une fois qu’un administrateur autorise l’utilisation d’applications personnalisées, les utilisateurs finaux peuvent rechercher ces applications en cliquant sur **Conçu pour votre organisation** dans le volet de navigation gauche de Teams Store.

:::image type="content" source="media/built-for-your-org1.png" alt-text="Capture d’écran des applications personnalisées dans le magasin Teams dans l’application de bureau teams." lightbox="media/built-for-your-org2.png":::

Pour plus d’informations, consultez [Comprendre et gérer les applications personnalisées et chargées de manière indépendante](custom-app-overview.md).

## <a name="about-app-templates"></a>À propos des modèles d’application

À l’aide des méthodes de développement d’applications, Microsoft crée et fournit des exemples d’applications fonctionnelles et prêtes pour la production. Collectivement, ces applications sont appelées modèles d’application pour Teams et sont fournies à :

* Illustrez quelques cas d’usage de collaboration dans Teams.
* Présenter les meilleures pratiques et méthodes de développement d’applications.
* Fournissez des applications open source que les développeurs peuvent étendre pour créer leurs propres applications.

Les développeurs de votre organisation personnalisent les modèles d’application avec des modifications simples du code source fourni. Vous fournissez ces applications en tant qu’applications personnalisées pour vos utilisateurs finaux afin de répondre aux besoins de toute organisation.

Pour en savoir plus, consultez [Modèles d’application Microsoft Teams](https://adoption.microsoft.com/microsoft-teams/app-templates/).

## <a name="discover-and-use-apps-in-teams"></a>Découvrir et utiliser des applications dans Teams

Les utilisateurs peuvent afficher toutes les applications disponibles dans Teams à partir du magasin d’applications Teams dans un client web ou de bureau Teams. Les utilisateurs peuvent rechercher par nom, parcourir par catégorie et parcourir les applications créées pour votre organisation et générées avec Power Platform pour découvrir et installer des applications dans Teams.

Les applications peuvent être épinglées à Teams pour faciliter l’accès. Les utilisateurs peuvent [épingler des applications par eux-mêmes](https://support.microsoft.com/office/pin-an-app-for-easy-access-3045fd44-6604-4ba7-8ecc-1c0d525e89ec) si leur stratégie d’installation le permet et si l’application est autorisée par l’administrateur Teams. Les administrateurs peuvent épingler des applications et contrôler le comportement des applications épinglées. Pour plus d’informations, consultez Stratégies de [configuration](/microsoftteams/teams-app-setup-policies) des applications.

:::image type="content" source="media/user-app-experience-find-apps.png" alt-text="Capture d’écran montrant tous les endroits où les utilisateurs peuvent parcourir les applications dans Microsoft Teams." lightbox="media/user-app-experience-find-apps-full.png":::

Les utilisateurs peuvent rechercher et ajouter des applications à Teams à partir de l’App Store Teams. Ils peuvent également ajouter des applications directement à partir du contexte dans lequel ils travaillent, comme l’onglet conversation ou canal, la réunion Teams ou la zone de messagerie. Pour plus d’informations, consultez [Ajouter une application à Microsoft Teams](https://support.microsoft.com/office/add-an-app-to-microsoft-teams-b2217706-f7ed-4e64-8e96-c413afd02f77).

Un utilisateur peut ajouter et utiliser une application uniquement lorsqu’un administrateur autorise l’application et que l’application est mise à la disposition de l’utilisateur via des [stratégies d’autorisation](teams-app-permission-policies.md). L’administrateur informatique d’une organisation a un contrôle total sur les personnes autorisées à installer les applications dans quel contexte. Les utilisateurs ne peuvent pas ajouter d’applications bloquées. Toute application avec une icône de verrou dans le magasin Teams est bloquée pour l’utilisateur. Toutefois, [les utilisateurs peuvent demander l’approbation de l’administrateur informatique de leur organisation](https://support.microsoft.com/office/request-apps-that-require-approval-by-your-org-924e3a9e-33f0-44c2-9e81-e875214c05ae). Une fois l’application approuvée, les utilisateurs peuvent ajouter l’application à partir du magasin Teams.

> [!NOTE]
> Seules les personnes peuvent demander une approbation pour ajouter une application dans Teams.

## <a name="understand-app-capabilities"></a>Comprendre les fonctionnalités de l’application

Les fonctionnalités des applications Teams sont les principales fonctionnalités que les développeurs créent dans une application pour répondre à différents cas d’usage des applications Teams. Les applications contiennent une ou plusieurs des fonctionnalités suivantes. Toutes ces fonctionnalités sont différentes des applications Teams et les administrateurs régissent ces applications à l’aide des [méthodes de gouvernance](manage-apps.md) des applications courantes.

<!---
        :::image type="content" source="media/teams-app-capabilities-group.png" alt-text="Graphic that shows the app capabilities of a Microsoft Teams app." border="false":::
--->

* **Bots** : les bots sont également appelés chatbot ou bot conversationnel. Il s’agit d’une application qui exécute des tâches simples et répétitives. Une interaction de bot peut être une question et une réponse rapides, ou il peut s’agir d’une conversation complexe qui fournit l’accès aux services ou à l’assistance. Les utilisateurs peuvent avoir une conversation avec un bot dans une conversation personnelle, un canal ou une conversation de groupe. Pour plus d’informations, consultez [Bots dans Microsoft Teams](/microsoftteams/platform/bots/what-are-bots).

* **Onglets : les** onglets sont des pages web prenant en compte Teams épinglées en haut d’un canal ou d’une conversation. Les onglets vous permettent d’interagir avec du contenu et des services avec une expérience web. Il s’agit de balises HTML `iframe` simples qui peuvent être ajoutées dans le cadre d’un canal à l’intérieur d’une équipe, d’une conversation de groupe ou d’une application personnelle pour un utilisateur individuel. Pour plus d’informations, consultez [Microsoft onglets Teams](/microsoftteams/platform/tabs/what-are-tabs).

* **Webhooks et connecteurs** : les webhooks et les connecteurs permettent de connecter différents services web à des canaux et des équipes dans Microsoft Teams. Les webhooks sont un rappel HTTP défini par l’utilisateur qui avertit les utilisateurs de toute action qui a eu lieu dans le canal Teams. Il s’agit d’un moyen pour une application d’obtenir des données en temps réel. Les connecteurs permettent aux utilisateurs de s’abonner pour recevoir des notifications et des messages des services web. Pour plus d’informations, consultez [Webhooks et connecteurs](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors).

  Pour permettre aux utilisateurs d’utiliser des connecteurs personnalisés dans Teams, consultez [Utiliser des connecteurs personnalisés dans Teams](office-365-custom-connectors.md).

* **Extensions de messagerie** : les extensions de messagerie sont des raccourcis permettant d’insérer du contenu d’application ou d’agir sur un message sans que les utilisateurs finaux n’ont à quitter la conversation. Les utilisateurs peuvent rechercher ou lancer des actions dans un système externe à partir de la zone de rédaction de message, de la zone de commande ou directement à partir d’un message. Pour plus d’informations, consultez [Extensions de message](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions?tabs=dotnet).

* **Extensions de réunion** : les utilisateurs peuvent améliorer l’expérience de réunion en intégrant des extensions de message dans les réunions et rendre les réunions plus productives. Vous pouvez identifier différents rôles de participant et types d’utilisateurs, obtenir des événements de réunion et générer des boîtes de dialogue en réunion. Pour plus d’informations, consultez [Réunions d’applications pour Teams](/microsoftteams/platform/apps-in-teams-meetings/teams-apps-in-meetings).

<!---
* **Cards and task modules**: Cards provide users with various visual, audio, and selectable messages and help in conversation flow. Task modules help you create modal pop-up experiences in Microsoft Teams. They're useful for starting and completing the tasks, or displaying rich information like videos or Power business intelligence (BI) dashboards. For more information, see [Cards and task modules](/microsoftteams/platform/task-modules-and-cards/cards-and-task-modules).
--->

* **Flux d’activité** : le flux d’activité dans Teams contient une notification de toute l’activité dans différentes étendues telles que les canaux et les conversations. Les applications peuvent diffuser un message à tous les membres d’une équipe ou d’un canal pour notifier les mises à jour. Les utilisateurs peuvent personnaliser les notifications qu’ils affichent.

Pour afficher les cas d’usage courants mappés aux fonctionnalités Teams, consultez [Mapper vos cas d’usage aux fonctionnalités de l’application Teams](/microsoftteams/platform/concepts/design/map-use-cases).

## <a name="related-articles"></a>Articles connexes

* [En savoir plus sur les modèles d’application pour Teams](/microsoftteams/platform/samples/app-templates).
* [Mises à jour des applications Teams et rôle d’administrateur](apps-update-experience.md)
* [Vue d’ensemble de la gestion et de la gouvernance des applications dans le Centre d’administration Teams](manage-apps.md)
