---
title: Microsoft Teams prise en charge des applications/métier sur les panneaux Teams métier
author: amandafrechinjackson
ms.author: v-amandaf
manager: jsarrasin
ms.date: 06/30/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Décrit la prise en charge de Teams/applications bureau même.
ms.collection:
- M365-voice
- M365-collaboration
- skype-for-business-itpro
- skype-for-business-online
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: f4b07078c49fd8fac9e690ed60072dfbefcfc020
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "53775101"
---
# <a name="microsoft-teams-appsline-of-business-lob-app-support-on-teams-panels"></a>Microsoft Teams prise en charge des applications/métier sur les panneaux Teams métier

Teams panneaux ajoutent la prise en charge Teams applications métier/applications métier. Les entreprises pourront ainsi ajouter des expériences supplémentaires sur les panneaux afin de répondre aux besoins de votre organisation. Cette version prend en charge le contenu web statique.

> [!IMPORTANT]
> Cette fonctionnalité n’est disponible qu’après la mise à jour Teams vos périphériques en panneaux. Vous devez avoir la version 1449/1.0.97.2021070601 ou une version plus récente de l’application Teams pour que l’application soit prise en charge dans Teams panneaux.

## <a name="set-up-and-manage-teams-panels-apps-in-teams-admin-center"></a>Configurer et gérer des applications de Teams panneaux dans le Centre Teams’administration 

Microsoft Teams applications apportent des informations clés, des outils courants et des processus de confiance dans un endroit où les personnes rassemblent, apprennent et travaillent. Teams applications [utilisent des fonctionnalités intégrées.](/platform/concepts/capabilities-overview) À présent, en tant qu’administrateur informatique, vous avez la possibilité d’inclure les applications à inclure dans l’appareil en panneaux Teams de votre organisation et de personnaliser les autorisations via le Centre d’administration Teams’entreprise.

Vous pouvez désormais utiliser les applications Teams sur des Teams et personnaliser l’expérience utilisateur en fonction des besoins de votre organisation. Vous pouvez choisir l’application web à laquelle vos utilisateurs peuvent accéder, utiliser et hiérarchiser les affichages des applications. Certaines options, telles que les bots et les fonctionnalités de messagerie, ne sont actuellement pas pris en charge. En savoir plus sur les Teams et comment gérer vos appareils dans Microsoft Teams.

## <a name="manage-apps-on-teams-panels-in-teams-admin-center"></a>Gérer les applications sur des Teams dans le Centre Teams’administration

**Remarque**: vous devez être un administrateur global ou un Teams de service pour accéder au Centre Teams’administration.

Les utilisateurs finaux peuvent afficher, mais pas installer, des applications sur Teams panneaux. En tant qu’administrateur, vous pouvez afficher et Teams toutes les applications pour votre organisation via le Centre Teams’administration. Découvrez comment gérer vos applications dans le centre d’administration Microsoft Teams via la page **Gérer les** applications. La page **Gérer les** applications du Centre Teams d’administration vous permet également de télécharger des [applications personnalisées.](/manage-apps#publish-a-custom-app-to-your-organizations-app-store)

Après avoir configuré des [](/teams-app-permission-policies) applications, vous [](/teams-app-setup-policies) pouvez utiliser des stratégies d’autorisation d’application et des stratégies de configuration d’application pour configurer l’expérience d’application pour des comptes de salle spécifiques dans votre organisation.

## <a name="pin-apps-on-teams-panels-with-app-setup-policies"></a>Épingler des applications sur Teams panneaux avec les stratégies de configuration de l’application

Étant donné que Teams permet d’afficher un large éventail d’applications, les administrateurs peuvent décider des applications les  plus essentielles pour l’organisation et épingler uniquement celles-ci pour l’écran d’accueil des panneaux Teams afin d’y accéder rapidement. S’il y a plus de cinq applications épinglées ou des applications non épinglées, elles apparaissent sous **l’écran** Plus. Microsoft recommande la création d’une stratégie de configuration d’application personnalisée spécialement pour les Teams panneaux.

![Capture d’écran de l’interface utilisateur de la page stratégies de configuration de l’application.](media/appsetup1.png) 

Pour gérer les applications épinglées affichées sur les panneaux de Teams, connectez-vous au Centre d’administration Teams pour votre organisation et accédez aux stratégies d’installation des applications **Teams** Sélectionnez ou créez une stratégie Applications épinglées. \>  \>  \> 

![Capture d’écran de la section Applications épinglées dans l’interface utilisateur.](media/appsetup2.png) 

Microsoft vous recommande  de désactiver Télécharger  applications personnalisées et d’autoriser l’épinglage des utilisateurs pour une expérience d Teams application la plus Teams personnalisées.

Pour plus d’informations sur l’épinglage d’applications, voir [Gérer les stratégies de configuration des applications.](/teams-app-setup-policies)

## <a name="manage-apps-display-order-in-teams-panels"></a>Gérer l’ordre d’affichage des applications dans Teams panneaux 

![Capture d’écran de la section applications dans l’interface utilisateur.](media/appsetup3.png) 

Pour gérer l’ordre d’affichage des applications sur les panneaux Teams, connectez-vous au Centre d’administration Teams pour votre organisation et accédez aux stratégies de configuration des applications **Teams** Sélectionnez les applications épinglées : Déplacer vers le \>  \>  \>  **haut/bas.**

## <a name="assigning-setup-policies-to-a-room-resource-account"></a>Affectation de stratégies d’installation à un compte de ressource de salle

Après avoir créé la stratégie d’installation, l’administrateur doit affecter cette stratégie au compte de ressource de salle qui sera Teams panneaux. Pour plus d’informations, voir [Attribuer des stratégies aux utilisateurs et groupes.](/assign-policies-users-and-groups)

## <a name="faq"></a>FAQ

### <a name="how-long-does-it-take-for-teams-panels-to-get-the-new-or-updated-app-setup-policies"></a>Combien de temps faut-il Teams panneaux pour obtenir les stratégies de configuration d’application nouvelles ou mises à jour ?

Après avoir modifié ou attribué de nouvelles stratégies dans le Teams d’administration, jusqu’à 24 heures peuvent être nécessaires avant que les modifications prennent effet. Les **administrateurs** peuvent essayer de se signer/se connecter à partir du panneau,  d’appuyer sur l’icône Paramètres et de revenir à l’écran d’accueil pour essayer d’actualiser les stratégies.

### <a name="what-is-the-ordering-of-the-apps-on-the-more-screen"></a>Quel est le ordre des applications sur l’écran « Plus » ?

Sur la page **Autres** applications, les applications épinglées apparaissent en premier. Toutes les autres applications installées s’affichent ensuite dans l’ordre alphabétique.

### <a name="why-are-bot-apps-not-showing-up-on-teams-panels"></a>Pourquoi les applications de bot ne s’affichent-elles pas sur Teams panneaux ?

Seuls les onglets statiques du contenu web sont pris en charge pour le moment.

### <a name="why-are-native-teams-apps-such-as-calendar-and-tasks-not-appearing-on-teams-panels"></a>Pourquoi les applications de Teams natives, telles que Calendrier et Tâches, n’apparaissent-elles pas sur Teams panneaux ?

Les Teams natives, telles que Calendrier et Tâches, ne s’Teams panneaux.

### <a name="in-the-teams-admin-center-under-the-setup-policies-section-what-is-the-difference-between-installed-apps-and-pinned-apps"></a>Dans le Teams d’administration, sous la section Stratégies d’installation, quelle est la différence entre les applications installées et épinglées ?

Pour Teams panneaux, Microsoft recommande d’utiliser des applications épinglées, afin que l’administrateur puisse sélectionner l’application souhaitée et réorganiser son ordre.

**Remarque :** Certaines applications ne supportent pas l’épinglage d’application. Contactez le développeur de l’application pour activer la fonctionnalité d’épinglage d’application.

### <a name="why-are-other-apps-appearing-in-the-more-screen-even-though-they-are-not-part-of-the-installed-or-pinned-apps-in-the-teams-app-setup-policy-section"></a>Pourquoi d’autres applications apparaissent-elles sur l’écran « Autres », même si elles ne font pas partie des applications installées ou épinglées dans la section de stratégie de configuration de l’application Teams ?

Si des applications ont été précédemment installées via d’autres stratégies d’application ou manuellement dans les clients de bureau/web Teams pour le compte de ressource de salle utilisé sur des panneaux Teams, l’administrateur devra peut-être se connecter au compte de ressource de la salle dans Teams puis désinstaller manuellement les applications en cliquant avec le bouton droit sur l’application, puis en sélectionnant **Désinstaller.**

### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Pourquoi ne puis-je pas trouver une application dans le volet « Ajouter des applications épinglées » ?

Toutes les applications ne peuvent pas être épinglées Teams via une stratégie de configuration d’application. Certaines applications peuvent ne pas prendre en charge cette fonctionnalité. Pour rechercher des applications qui peuvent être épinglées, recherchez l’application dans le volet Ajouter des applications épinglées.  Pour plus d’informations, consultez la FAQ sur [l’application Working with app setup policies (Fonctionnement des stratégies de configuration d’application).](/teams-app-setup-policies#why-cant-i-find-an-app-in-the-add-pinned-apps-pane)

### <a name="why-am-i-seeing-an-allow-user-pinning-pop-up-in-the-setup-policies-panel-after-i-turn-off-allow-user-pinning"></a>Pourquoi une fenêtre « Autoriser l’épinglage des utilisateurs » apparaît-elle dans le panneau des stratégies d’installation après avoir désactiver l’épinglage d’utilisateurs ?

![Capture d’écran de la section Stratégie de configuration au sein de l’interface utilisateur avec une fenêtre pop-up confirmant que l’épinglage utilisateur est actif.](media/appsetup4.png) 

Ce comportement est prévu pour un appareil dans un espace partagé et permet d’éviter l’épinglage d’application non intentionnelle.
