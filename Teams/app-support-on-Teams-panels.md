---
title: Prise en charge des applications Microsoft Teams/métier dans les panneaux Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 8/5/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Décrit la prise en charge des applications Teams/des applications métier.
ms.collection:
- M365-voice
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: 75548acc44d1f360e13dd5946e6e39726c744bb6
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270679"
---
# <a name="microsoft-teams-appsline-of-business-lob-app-support-on-teams-panels"></a>Prise en charge des applications Microsoft Teams/métier dans les panneaux Teams

Les panneaux Teams ajoutent la prise en charge [des applications Teams/des applications métier.](/microsoftteams/platform/overview) Cela permettra aux entreprises d’ajouter des expériences supplémentaires sur les panneaux pour répondre aux besoins de votre organisation. Cette version prend en charge le contenu web statique.

> [!IMPORTANT]
> Cette fonctionnalité n’est disponible qu’après la mise à jour de vos appareils de panneaux Teams. Vous devez disposer de l’application Teams version 1449/1.0.97.2021070601 ou ultérieure pour prendre en charge les applications dans les panneaux Teams.

## <a name="teams-app-experience-on-teams-panels"></a>Expérience d’application Teams dans les panneaux Teams

![Capture d’écran du Centre d’administration Teams montrant la section qui permettra aux utilisateurs d’accéder aux applications.](media/tac1update.png)

*L’écran d’accueil des panneaux Teams inclut des options de navigation d’application, décrites dans la capture d’écran en rouge. Notez qu’il s’agit d’exemples d’icônes qui peuvent ne pas être utilisables.*

![Capture d’écran du canevas d’application dans lequel les applications peuvent être ajoutées.](media/appscreen.png)

*Lorsqu’un utilisateur final appuie sur l’une des icônes de l’application, l’écran de l’application Teams s’affiche dans la capture d’écran précédente. Le rectangle gris de la capture d’écran montre où les applications sont affichées sur le écran Teams. La barre de l’application est fixe et fait partie de l’application de panneaux Teams.*

## <a name="set-up-and-manage-teams-panels-apps-in-teams-admin-center"></a>Configurer et gérer des applications de panneaux Teams dans le Centre d’administration Teams

Les applications Microsoft Teams apportent des informations clés, des outils courants et des processus approuvés à l’endroit où les utilisateurs se rassemblent, apprennent et travaillent. Les applications Teams [fonctionnent via des fonctionnalités intégrées](/microsoftteams/platform/concepts/capabilities-overview). À présent, en tant qu’administrateur informatique, vous avez le choix entre les applications à inclure dans l’appareil de panneaux Teams de votre organisation et à personnaliser les autorisations via le [Centre d’administration Teams](https://admin.teams.microsoft.com/).

Vous pouvez désormais utiliser les applications Teams dans les panneaux Teams et personnaliser l’expérience utilisateur en fonction des besoins de votre organisation. Vous pouvez décider quelle application web vos utilisateurs peuvent accéder et utiliser et hiérarchiser les vues d’application. Certaines options, telles que le bot et les fonctionnalités de messagerie, ne sont pas prises en charge pour l’instant. En savoir plus sur [les applications Teams](/microsoftteams/platform/overview) et [sur la gestion de vos appareils dans Microsoft Teams](/microsoftteams/devices/device-management).

## <a name="manage-apps-on-teams-panels-in-teams-admin-center"></a>Gérer les applications dans les panneaux Teams dans le Centre d’administration Teams

**Remarque** : vous devez être un administrateur général ou un administrateur de service Teams pour accéder au [Centre d’administration Teams](https://admin.teams.microsoft.com/).

Les utilisateurs finaux peuvent afficher les applications, mais pas les installer sur les panneaux Teams. En tant qu’administrateur, vous pouvez afficher et gérer toutes les applications Teams pour votre organisation via le Centre d’administration Teams. Pour en savoir plus sur la façon dont vous pouvez [gérer vos applications dans le Centre d’administration Microsoft Teams](/microsoftteams/manage-apps) , consultez la page **Gérer les applications** . La page **Gérer les applications** dans le Centre d’administration Teams vous permet également de charger des [applications personnalisées](/microsoftteams/manage-apps#publish-a-custom-app-to-your-organizations-app-store).

Après avoir configuré des applications, vous pouvez utiliser des [stratégies d’autorisation d’application](/microsoftteams/teams-app-permission-policies) et des [stratégies d’installation d’application](/microsoftteams/teams-app-setup-policies) pour configurer l’expérience d’application pour des comptes de salle spécifiques dans votre organisation.

## <a name="pin-apps-on-teams-panels-with-app-setup-policies"></a>Épingler des applications sur des panneaux Teams avec des stratégies d’installation d’application

Étant donné que Teams offre la possibilité d’afficher un large éventail d’applications, les administrateurs peuvent décider quelles applications sont les plus essentielles pour l’organisation et épingler uniquement celles-ci pour l’écran **d’accueil** des panneaux Teams pour un accès rapide. S’il existe plus de cinq applications épinglées ou d’applications non épinglées, elles apparaissent sous l’écran **Plus** . Microsoft recommande de créer une stratégie de configuration d’application personnalisée spécifiquement pour les panneaux Teams.

![Capture d’écran de l’interface utilisateur de la page stratégies d’installation de l’application.](media/appsetup1.png)

Pour gérer les applications épinglées affichées dans les panneaux Teams, connectez-vous au Centre d’administration Teams pour votre organisation et accédez aux stratégies **d’installation** \> des **applications** \> Teams **Sélectionnez ou créez une nouvelle** \> **stratégie d’applications épinglées**.

![Capture d’écran de la section Applications épinglées dans l’interface utilisateur.](media/appsetup2.png)

*Les applications incluses dans cette image ne sont que des exemples et peuvent ne pas être utilisables.*

Microsoft vous recommande de désactiver **le chargement d’applications personnalisées** et **l’épinglage d’utilisateur** pour la meilleure expérience d’application Teams sur les panneaux Teams.

Pour plus d’informations sur l’épinglage d’applications, consultez [Gérer les stratégies d’installation des applications](/microsoftteams/teams-app-setup-policies).

## <a name="manage-apps-display-order-in-teams-panels"></a>Gérer l’ordre d’affichage des applications dans les panneaux Teams

![Capture d’écran de la section Applications dans l’interface utilisateur.](media/appsetup3.png)

*Les applications incluses dans cette image ne sont que des exemples et peuvent ne pas être utilisables.*

Pour gérer l’ordre dans lequel les applications sont affichées dans les panneaux Teams, connectez-vous au Centre d’administration Teams pour votre organisation et accédez aux **stratégies** \> d’installation des **applications** \> Teams **Sélectionnez les** **applications épinglées** de stratégie \> : **Monter/descendre**.

## <a name="assigning-setup-policies-to-a-room-resource-account"></a>Affectation de stratégies d’installation à un compte de ressources de salle

Après avoir créé la stratégie d’installation, l’administrateur doit affecter cette stratégie au compte de ressources de salle qui sera connecté aux panneaux Teams. Pour plus d’informations, [reportez-vous à Affecter des stratégies aux utilisateurs et aux groupes](/microsoftteams/assign-policies-users-and-groups).

## <a name="faq"></a>FAQ

### <a name="how-long-does-it-take-for-teams-panels-to-get-the-new-or-updated-app-setup-policies"></a>Combien de temps faut-il aux panneaux Teams pour obtenir les stratégies d’installation d’applications nouvelles ou mises à jour ?

Après avoir modifié ou affecté de nouvelles stratégies dans le Centre d’administration Teams, l’application des modifications peut prendre jusqu’à 24 heures. Les administrateurs peuvent essayer de se déconnecter/se connecter à partir du panneau, d’appuyer sur l’icône **Paramètres** et de revenir à l’écran **d’accueil** pour essayer d’actualiser les stratégies.

### <a name="what-is-the-ordering-of-the-apps-on-the-more-screen"></a>Quel est l’ordre des applications sur l’écran « Plus » ?

Dans la page **Plus** d’applications, les applications épinglées apparaissent en premier. Ensuite, toutes les autres applications installées apparaissent dans l’ordre alphabétique.

### <a name="why-are-bot-apps-not-showing-up-on-teams-panels"></a>Pourquoi les applications de bot ne s’affichent-elles pas dans les panneaux Teams ?

Seul le contenu web des onglets statiques est pris en charge pour l’instant.

### <a name="why-are-native-teams-apps-such-as-calendar-and-tasks-not-appearing-on-teams-panels"></a>Pourquoi les applications Teams natives, telles que Calendrier et Tâches, n’apparaissent-elles pas dans les panneaux Teams ?

Les applications Native Teams, telles que Calendrier et Tâches, ne sont pas affichées dans les panneaux Teams.

### <a name="in-the-teams-admin-center-under-the-setup-policies-section-what-is-the-difference-between-installed-apps-and-pinned-apps"></a>Dans le Centre d’administration Teams, sous la section Stratégies d’installation, quelle est la différence entre les applications installées et les applications épinglées ?

Pour les panneaux Teams, Microsoft recommande d’utiliser des applications épinglées, afin que l’administrateur puisse sélectionner l’application souhaitée et réorganiser son ordre.

**Note:** Certaines applications ne prennent pas en charge l’épinglage d’application. Contactez le développeur de l’application pour activer la fonctionnalité d’épinglage d’application.

### <a name="why-are-other-apps-appearing-in-the-more-screen-even-though-they-are-not-part-of-the-installed-or-pinned-apps-in-the-teams-app-setup-policy-section"></a>Pourquoi d’autres applications apparaissent-elles dans l’écran « Plus » même si elles ne font pas partie des applications installées ou épinglées dans la section de stratégie d’installation des applications Teams ?

Si des applications ont déjà été installées via d’autres stratégies d’application ou manuellement dans les clients bureau/web Teams pour le compte de ressource de salle utilisé dans les panneaux Teams, l’administrateur peut avoir besoin de se connecter au compte de ressources de salle dans Teams et de désinstaller manuellement les applications en cliquant avec le bouton droit sur l’application, puis en sélectionnant **Désinstaller**.

### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Pourquoi ne puis-je pas trouver une application dans le volet « Ajouter des applications épinglées » ?

Toutes les applications ne peuvent pas être épinglées à Teams par le biais d’une stratégie de configuration d’application. Certaines applications ne prennent peut-être pas en charge cette fonctionnalité. Pour rechercher les applications qui peuvent être épinglées, recherchez l’application dans le volet **Ajouter des applications épinglées** . Pour plus d’informations, reportez-vous [à la faq sur l’utilisation des stratégies d’installation d’application](/microsoftteams/teams-app-setup-policies#why-cant-i-find-an-app-in-the-add-pinned-apps-pane).

### <a name="why-am-i-seeing-an-user-pinning-pop-up-in-the-setup-policies-panel-after-i-turn-off-user-pinning"></a>Pourquoi une fenêtre contextuelle « Épinglage d’utilisateur » s’affiche-t-elle dans le panneau stratégies d’installation après avoir désactivé « Épinglage de l’utilisateur ? »

![Capture d’écran de la section de stratégie d’installation dans l’interface utilisateur avec une fenêtre contextuelle confirmant que l’épinglage utilisateur est actif.](media/appsetup4.png)

*Les applications incluses dans cette image ne sont que des exemples et peuvent ne pas être utilisables.*

Ce comportement est attendu pour un appareil dans un espace partagé et permet d’éviter l’épinglage involontaire d’application.
