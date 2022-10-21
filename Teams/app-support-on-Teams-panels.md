---
title: Applications Microsoft Teams/Prise en charge des applications métier (LOB) dans les panneaux Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 8/5/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Décrit la prise en charge des applications Teams/applications métier.
ms.collection:
- M365-voice
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c8d28a3f985a38e174030ddbe0e6d43e2153738
ms.sourcegitcommit: 1161cddd077056a9c1e2da99a84e35be0380b1b1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68656070"
---
# <a name="microsoft-teams-appsline-of-business-lob-app-support-on-teams-panels"></a>Applications Microsoft Teams/Prise en charge des applications métier (LOB) dans les panneaux Teams

Les panneaux Teams ajoutent la prise en charge [des applications Teams/](/microsoftteams/platform/overview)métier. Cela permettra aux entreprises d’ajouter des expériences supplémentaires sur les panneaux pour répondre aux besoins de votre organisation. Cette version prend en charge le contenu web statique.

> [!IMPORTANT]
> Cette fonctionnalité n’est disponible qu’après la mise à jour de vos appareils de panneau Teams. Vous devez disposer de l’application Teams version 1449/1.0.97.2021070601 ou ultérieure pour disposer d’une prise en charge des applications dans les panneaux Teams.

## <a name="teams-app-experience-on-teams-panels"></a>Expérience de l’application Teams dans les panneaux Teams

![Capture d’écran du Centre d’administration Teams montrant la section permettant aux utilisateurs d’accéder aux applications.](media/tac1update.png)

*L’écran d’accueil des volets Teams inclut des options de navigation dans l’application, présentées dans la capture d’écran en rouge. Notez qu’il s’agit d’exemples d’icônes qui peuvent ne pas être disponibles.*

![Capture d’écran du canevas d’application dans lequel des applications peuvent être ajoutées.](media/appscreen.png)

*Lorsqu’un utilisateur final appuie sur l’une des icônes de l’application, l’écran de l’application Teams s’affiche dans la capture d’écran précédente. Le rectangle gris de la capture d’écran est l’endroit où les applications sont affichées sur le écran Teams. La barre de l’application est fixe et fait partie de l’application de panneaux Teams.*

## <a name="set-up-and-manage-teams-panels-apps-in-teams-admin-center"></a>Configurer et gérer des applications de panneaux Teams dans le Centre d’administration Teams

Les applications Microsoft Teams apportent des informations clés, des outils courants et des processus approuvés là où les gens se rassemblent, apprennent et travaillent. Les applications Teams [fonctionnent via des fonctionnalités intégrées](/microsoftteams/platform/concepts/capabilities-overview). Désormais, en tant qu’administrateur informatique, vous avez le choix entre les applications à inclure dans les panneaux Teams de votre organisation et à personnaliser les autorisations via le [Centre d’administration Teams](https://admin.teams.microsoft.com/).

Vous pouvez désormais utiliser les volets Des applications Teams dans Teams et personnaliser l’expérience utilisateur en fonction des besoins de votre organisation. Vous pouvez choisir l’application web à laquelle vos utilisateurs peuvent accéder, l’utiliser et hiérarchiser les vues d’application. Certaines options, telles que les fonctionnalités de bot et de messagerie, ne sont pas prises en charge pour l’instant. En savoir plus sur [les applications Teams](/microsoftteams/platform/overview) et [sur la gestion de vos appareils dans Microsoft Teams](/microsoftteams/devices/device-management).

## <a name="manage-apps-on-teams-panels-in-teams-admin-center"></a>Gérer les applications sur les panneaux Teams dans le Centre d’administration Teams

**Remarque** : Vous devez être administrateur général ou administrateur de service Teams pour accéder au [Centre d’administration Teams](https://admin.teams.microsoft.com/).

Les utilisateurs finaux peuvent afficher mais pas installer des applications dans les panneaux Teams. En tant qu’administrateur, vous pouvez afficher et gérer toutes les applications Teams pour votre organisation via le Centre d’administration Teams. Apprenez-en davantage sur la façon dont vous pouvez [gérer vos applications dans le Centre d’administration Microsoft Teams](/microsoftteams/manage-apps) via la page **Gérer les applications** . La page **Gérer les applications** dans le Centre d’administration Teams vous permet également de charger [des applications personnalisées](/microsoftteams/manage-apps#publish-a-custom-app-to-your-organizations-app-store).

Après avoir configuré les applications, vous pouvez utiliser des [stratégies d’autorisation d’application](/microsoftteams/teams-app-permission-policies) et des [stratégies de configuration d’application](/microsoftteams/teams-app-setup-policies) pour configurer l’expérience d’application pour des comptes de salle spécifiques dans votre organisation.

## <a name="pin-apps-on-teams-panels-with-app-setup-policies"></a>Épingler des applications dans les panneaux Teams avec des stratégies de configuration d’application

Étant donné que Teams offre la possibilité d’afficher un large éventail d’applications, les administrateurs peuvent décider des applications les plus essentielles pour l’organisation et les épingler uniquement pour l’écran **d’accueil** des panneaux Teams pour un accès rapide. S’il existe plus de cinq applications épinglées ou des applications non épinglées, elles s’affichent sous l’écran **Plus** . Microsoft recommande de créer une stratégie personnalisée dans la stratégie de configuration des applications spécifiquement pour les panneaux Teams.

![Capture d’écran de l’interface utilisateur de la page des stratégies de configuration de l’application.](media/appsetup1.png)

Pour gérer les applications épinglées affichées dans les volets Teams, connectez-vous au Centre d’administration Teams de votre organisation et accédez à **Applications Teams** \> **Stratégies d’installation** \> **Sélectionnez ou créez une stratégie** \> **Applications épinglées**.

![Capture d’écran de la section applications épinglées dans l’interface utilisateur.](media/appsetup2.png)

*Les applications incluses dans cette image ne sont que des exemples et peuvent ne pas être disponibles.*

Microsoft vous recommande de désactiver **charger des applications personnalisées** et **l’épinglage utilisateur** pour optimiser l’expérience d’application Teams dans les panneaux Teams.

Pour plus d’informations sur l’épinglage des applications, consultez [Gérer les stratégies de configuration des applications](/microsoftteams/teams-app-setup-policies).

## <a name="manage-apps-display-order-in-teams-panels"></a>Gérer l’ordre d’affichage des applications dans les panneaux Teams

![Capture d’écran de la section applications dans l’interface utilisateur.](media/appsetup3.png)

*Les applications incluses dans cette image ne sont que des exemples et peuvent ne pas être disponibles.*

Pour gérer l’ordre dans lequel les applications sont affichées dans les volets Teams, connectez-vous au Centre d’administration Teams de votre organisation et accédez à **Applications Teams** \> **Stratégies d’installation** \> **Sélectionnez les** **applications épinglées** de \> stratégie : **Monter/descendre**.

## <a name="assigning-setup-policies-to-a-room-resource-account"></a>Affectation de stratégies d’installation à un compte de ressources de salle

Après avoir créé la stratégie d’installation, l’administrateur doit affecter cette stratégie au compte de ressource de salle qui sera connecté aux panneaux Teams. Pour plus d’informations, consultez [Affecter des stratégies à des utilisateurs et des groupes](/microsoftteams/assign-policies-users-and-groups).

## <a name="faq"></a>FAQ

### <a name="how-long-does-it-take-for-teams-panels-to-get-the-new-or-updated-app-setup-policies"></a>Combien de temps faut-il pour que les panneaux Teams obtiennent les stratégies de configuration d’application nouvelles ou mises à jour ?

Après avoir modifié ou affecté de nouvelles stratégies dans le Centre d’administration Teams, l’application des modifications peut prendre jusqu’à 24 heures. Les administrateurs peuvent essayer de se déconnecter/se connecter à partir du panneau, appuyer sur l’icône **Paramètres** , puis revenir à l’écran **d’accueil** pour essayer d’actualiser les stratégies.

### <a name="what-is-the-ordering-of-the-apps-on-the-more-screen"></a>Quel est l’ordre des applications sur l’écran « Plus » ?

Dans la page **Plus** d’applications, les applications épinglées s’affichent en premier. Ensuite, toutes les autres applications installées s’affichent par ordre alphabétique.

### <a name="why-are-bot-apps-not-showing-up-on-teams-panels"></a>Pourquoi les applications de bot n’apparaissent-elles pas dans les panneaux Teams ?

Seul le contenu web des onglets statiques est pris en charge pour l’instant.

### <a name="why-are-native-teams-apps-such-as-calendar-and-tasks-not-appearing-on-teams-panels"></a>Pourquoi les applications Teams natives, telles que Calendrier et Tâches, n’apparaissent-elles pas dans les panneaux Teams ?

Les applications Teams natives, telles que Calendrier et Tâches, ne sont pas affichées dans les panneaux Teams.

### <a name="in-the-teams-admin-center-under-the-setup-policies-section-what-is-the-difference-between-installed-apps-and-pinned-apps"></a>Dans le Centre d’administration Teams, sous la section Stratégies d’installation, quelle est la différence entre les applications installées et les applications épinglées ?

Pour les panneaux Teams, Microsoft recommande d’utiliser des applications épinglées, afin que l’administrateur puisse sélectionner l’application souhaitée et réorganiser son ordre.

**Note:** Certaines applications ne prennent pas en charge l’épinglage des applications. Contactez le développeur de l’application pour activer la fonctionnalité d’épinglage des applications.

### <a name="why-are-other-apps-appearing-in-the-more-screen-even-though-they-are-not-part-of-the-installed-or-pinned-apps-in-the-teams-app-setup-policy-section"></a>Pourquoi d’autres applications apparaissent-elles dans l’écran « Plus », même si elles ne font pas partie des applications installées ou épinglées dans la section Stratégie de configuration des applications Teams ?

Si les applications ont été précédemment installées via d’autres stratégies d’application ou manuellement dans les clients de bureau/web Teams pour le compte de ressource de salle utilisé dans les panneaux Teams, l’administrateur peut avoir besoin de se connecter au compte de ressources de salle dans Teams et désinstaller manuellement les applications en cliquant avec le bouton droit sur l’application, puis en sélectionnant **Désinstaller**.

### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Pourquoi ne puis-je pas trouver une application dans le volet « Ajouter des applications épinglées » ?

Certaines applications ne peuvent pas être épinglées à Teams via une stratégie de configuration des applications. Cette fonctionnalité n’est pas prise en charge par toutes les applications. Pour rechercher les applications qui peuvent être épinglées, recherchez l’application dans le volet **Ajouter des applications épinglées**. Pour plus d’informations, reportez-vous au [FAQ dans Utilisation des stratégies de configuration d’application](/microsoftteams/teams-app-setup-policies#why-cant-i-find-an-app-in-the-add-pinned-apps-pane).

### <a name="why-am-i-seeing-an-user-pinning-pop-up-in-the-setup-policies-panel-after-i-turn-off-user-pinning"></a>Pourquoi une fenêtre contextuelle « Épinglage utilisateur » s’affiche-t-elle dans le panneau des stratégies d’installation après avoir désactivé « Épinglage utilisateur ? »

![Capture d’écran de la section stratégie de configuration dans l’interface utilisateur avec une fenêtre contextuelle confirmant que l’épinglage de l’utilisateur est actif.](media/appsetup4.png)

*Les applications incluses dans cette image ne sont que des exemples et peuvent ne pas être disponibles.*

Ce comportement est attendu pour un appareil dans un espace partagé et permet d’éviter l’épinglage involontaire des applications.
