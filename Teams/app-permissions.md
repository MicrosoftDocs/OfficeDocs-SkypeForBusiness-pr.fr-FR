---
title: Autorisations d’applications Microsoft Teams et points à prendre en compte
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.date: 06/27/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: Administration pouvez savoir quelles données et autorisations Microsoft Teams applications demandent à leur organisation.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 925136660ef6adda6374fab1acccf10a2b9f1722
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190284"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Autorisations d’applications Microsoft Teams et points à prendre en compte

Microsoft Teams applications sont un moyen d’agréger une ou plusieurs fonctionnalités dans des applications qui peuvent être installées, mises à niveau et désinstallées. Les fonctionnalités des applications sont les suivantes :

* Bots
* Extensions de messagerie
* Onglets
* Connecteurs

En tant qu’administrateur, vous gérez uniquement les applications. Toutefois, l’article se concentre sur les autorisations et les considérations au niveau des fonctionnalités, car les fonctionnalités d’une application affectent les autorisations requises et les profils de risque de l’application. Pour l’utilisation, les applications sont approuvées par les utilisateurs et gérées par des professionnels de l’informatique du point de vue de la stratégie.

Les autorisations répertoriées ci-dessous en majuscules, par exemple `RECEIVE_MESSAGE` `REPLYTO_MESSAGE` , sont uniquement à des fins d’illustration et d’explication. Ces chaînes ou autorisations n’apparaissent nulle part dans la [documentation Microsoft Teams développeur](/microsoftteams/platform/overview) ou [les autorisations pour Microsoft Graph](/graph/permissions-reference).

## <a name="global-app-permissions-and-considerations"></a>Considérations et autorisations d’application globales

### <a name="required-permissions"></a>Autorisations requises

Aucun

### <a name="optional-permissions"></a>Autorisations facultatives

Aucun

### <a name="considerations"></a>Considérations

* Une application doit divulguer les données qu’elle utilise et les données utilisées dans ses conditions d’utilisation et ses liens de politique de confidentialité.

* [Le consentement spécifique à la ressource](resource-specific-consent.md) fournit un ensemble d’autorisations que les applications peuvent demander, qui s’affiche sur l’écran d’installation de l’application. Pour en savoir plus sur les autorisations de consentement spécifiques aux ressources, consultez [Graph référence sur les autorisations](/graph/permissions-reference#teams-resource-specific-consent-permissions).

* Les applications peuvent également avoir besoin d’autorisations autres que des autorisations de consentement spécifiques aux ressources. Une fois qu’une application est installée, elle peut demander Graph autorisations via une invite de consentement. Pour plus d’informations, consultez [Présentation des expériences de consentement d’application Azure AD](/azure/active-directory/develop/application-consent-experience). Vous pouvez configurer les autorisations d’API et le consentement dans le Portail Azure. Pour en savoir plus, consultez [Azure Active Directory framework de consentement](/azure/active-directory/develop/consent-framework).

## <a name="bots-and-messaging-extensions"></a>Bots et extensions de messagerie

### <a name="required-permissions"></a>Autorisations requises

* RECEIVE_MESSAGE, REPLYTO_MESSAGE : le bot peut recevoir des messages des utilisateurs et y répondre. <sup>1</sup>

* POST_MESSAGE_USER : une fois qu’un utilisateur a envoyé un message à un bot, il peut envoyer des messages directs à l’utilisateur (également *appelés messages proactifs* à tout moment.

* GET_CHANNEL_LIST : les bots ajoutés aux équipes peuvent obtenir une liste de noms et d’ID des canaux d’une équipe.

### <a name="optional-permissions"></a>Autorisations facultatives

* IDENTITÉ : lorsqu’il est utilisé dans un canal, les bots de l’application peuvent accéder aux informations d’identité de base des membres de l’équipe (prénom, nom, nom d’utilisateur principal [UPN], adresse e-mail). Lorsqu’il est utilisé dans une conversation personnelle ou de groupe, le bot peut accéder aux mêmes informations pour ces utilisateurs.

* POST_MESSAGE_TEAM : permet aux bots d’une application d’envoyer des messages directs (proactifs) au membre de l’équipe à tout moment, même si l’utilisateur n’a jamais interagi avec le bot.

* Les autorisations suivantes ne sont pas explicites, mais sont implicites par RECEIVE_MESSAGE et REPLYTO_MESSAGE et les étendues dans lesquelles les bots peuvent être utilisés, déclarées dans le manifeste :

  * RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL
  * RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT
  * RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM

* Les autorisations suivantes ne sont pas explicites, mais sont implicites par RECEIVE_MESSAGE et REPLYTO_MESSAGE et les étendues dans lesquelles les bots peuvent être utilisés, déclarées dans le manifeste :

  * RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL
  * RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT
  * RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM

* SEND_FILES, RECEIVE_FILES:<sup>2</sup> détermine si un bot peut envoyer et recevoir des fichiers dans une conversation personnelle (pas encore pris en charge pour les conversations de groupe ou les canaux).

### <a name="considerations"></a>Considérations

* Les bots ont uniquement accès aux équipes auxquelles ils ont été ajoutés ou aux utilisateurs qui les ont installés.

* Les bots reçoivent uniquement les messages dans lesquels ils sont explicitement mentionnés par les utilisateurs. Ces données quittent le réseau d’entreprise.

* Les bots peuvent uniquement répondre aux conversations dans lesquelles ils sont mentionnés.

* Lorsqu’un utilisateur converse avec un bot, s’il stocke l’ID de l’utilisateur, il peut envoyer des messages directs à tout moment.

* Théoriquement, il est possible que les messages bot contiennent des liens vers des sites de hameçonnage ou de programmes malveillants. Toutefois, les bots peuvent être bloqués par l’utilisateur, l’administrateur client ou globalement par Microsoft. [Les vérifications de vérification et de validation des](overview-of-app-validation.md) applications garantissent que toutes les applications fausses ne sont pas disponibles dans Teams magasin.

* Un bot peut récupérer (et stocker) des informations d’identité de base pour les membres de l’équipe auxquels l’application a été ajoutée, ou pour des utilisateurs individuels dans des conversations personnelles ou de groupe. Pour obtenir des informations supplémentaires sur ces utilisateurs, le bot doit les obliger à se connecter à Azure Active Directory (Azure AD).

* Les bots peuvent récupérer (et stocker) la liste des canaux dans une équipe ; ces données quittent le réseau d’entreprise.

* Par défaut, les bots n’ont pas la possibilité d’agir pour le compte de l’utilisateur, mais les bots peuvent demander aux utilisateurs de se connecter ; Dès que l’utilisateur se connecte, le bot dispose d’un jeton d’accès avec lequel il peut effectuer des opérations supplémentaires. Exactement ce que ces autres choses sont dépend du bot et de l’endroit où l’utilisateur se connecte : un bot est une application Azure AD inscrite auprès https://apps.dev.microsoft.com/ de laquelle il peut avoir son propre jeu d’autorisations.

* Lorsqu’un fichier est envoyé à un bot, il quitte le réseau d’entreprise. L’envoi et la réception de fichiers nécessitent l’approbation de l’utilisateur pour chaque fichier.

* Par défaut, les bots n’ont pas la possibilité d’agir pour le compte de l’utilisateur, mais les bots peuvent demander aux utilisateurs de se connecter ; Dès que l’utilisateur se connecte, le bot dispose d’un jeton d’accès avec lequel il peut effectuer des opérations supplémentaires. Exactement ce que ces éléments supplémentaires sont dépend du bot et de l’endroit où l’utilisateur se connecte : un bot est une application Azure AD inscrite sur le [portail d’inscription d’application](https://apps.dev.microsoft.com/?referrer=https:%2f%2fdocs.microsoft.com%2f#/appList) et peut avoir son propre ensemble d’autorisations.

* Les bots sont informés chaque fois que des utilisateurs sont ajoutés ou supprimés d’une équipe.

* Les bots ne voient pas les adresses IP des utilisateurs ni d’autres informations de référence. Toutes les informations proviennent de Microsoft. (Il existe une exception : si un bot implémente sa propre expérience de connexion, l’interface utilisateur de connexion voit les adresses IP et les informations du référent des utilisateurs.)

* En revanche, les extensions de messagerie voient les adresses IP et les informations de référence des utilisateurs.

* Les instructions d’application (et notre processus de révision AppSource) nécessitent une discrétion dans la publication de messages de conversation personnels aux utilisateurs (via l’autorisation POST_MESSAGE_TEAM) à des fins valides. En cas d’abus, les utilisateurs peuvent bloquer le bot, les administrateurs de locataires peuvent bloquer l’application et Microsoft peut bloquer les bots de manière centralisée si nécessaire.

<sup>1</sup> Certains bots envoient uniquement des messages (POST_MESSAGE_USER). Ils sont appelés bots de notification uniquement, mais le terme ne fait pas référence à ce qu’un bot est autorisé ou non autorisé à faire, cela signifie que le bot ne veut pas exposer une expérience conversationnelle. Teams utilise ce champ pour désactiver les fonctionnalités de l’interface utilisateur qui seraient normalement activées ; le bot n’est pas limité dans ce qu’il est autorisé à faire par rapport aux bots qui exposent une expérience conversationnelle.

<sup>2</sup> Régi par la propriété booléen supportsFiles sur l’objet bot dans le `manifest.json` fichier de l’application.

> [!NOTE]
> Si un bot a sa propre connexion, il existe une deuxième expérience de consentement (différente) la première fois que l’utilisateur se connecte.
>
>Actuellement, les autorisations Azure AD associées à l’une des fonctionnalités d’une application Teams (bot, onglet, connecteur ou extension de messagerie) sont complètement distinctes des autorisations Teams répertoriées ici.

## <a name="tabs"></a>Onglets

Un onglet est un site web s’exécutant dans Teams.

### <a name="required-permissions"></a>Autorisations requises

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>Autorisations facultatives

Aucun (actuellement)

### <a name="considerations"></a>Considérations

* Le profil de risque d’un onglet est presque identique à celui du même site web exécuté dans un onglet de navigateur.

* Un onglet obtient également le contexte dans lequel il s’exécute, y compris le nom de connexion et l’UPN de l’utilisateur actuel, l’ID d’objet Azure AD pour l’utilisateur actuel, l’ID du groupe Microsoft 365 dans lequel il réside (s’il s’agit d’une équipe), l’ID de locataire et les paramètres régionaux actuels de l’utilisateur. Toutefois, pour mapper ces ID aux informations d’un utilisateur, l’onglet doit faire en sorte que l’utilisateur se connecte à Azure AD.

## <a name="connectors"></a>Connecteurs

Un connecteur publie des messages sur un canal lorsque des événements se produisent dans un système externe.

### <a name="required-permissions"></a>Autorisations requises

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>Autorisations facultatives

REPLYTO_CONNECTOR_MESSAGE. Certains connecteurs prennent en charge les messages actionnables, qui permettent aux utilisateurs de publier des réponses ciblées au message du connecteur, par exemple en ajoutant une réponse à un problème de GitHub ou en ajoutant une date à une carte Trello.

### <a name="considerations"></a>Considérations

* Le système qui publie des messages de connecteur ne sait pas qui il publie ou qui reçoit les messages : aucune information sur le destinataire n’est divulguée. (Microsoft est le destinataire réel, pas le locataire ; Microsoft effectue le post réel sur le canal.)

* Aucune donnée ne quitte le réseau d’entreprise lorsque les messages du connecteur sont publiés sur un canal.

* Les connecteurs qui prennent en charge les messages actionnables (REPLYTO_CONNECTOR_MESSAGE autorisation) ne voient pas non plus l’adresse IP et les informations de référence ; ces informations sont envoyées à Microsoft, puis routées vers des points de terminaison HTTP précédemment inscrits auprès de Microsoft dans le portail connecteurs.

* Chaque fois qu’un connecteur est configuré pour un canal, une URL unique pour cette instance de connecteur est créée. Si cette instance de connecteur est supprimée, l’URL ne peut plus être utilisée.

* Les messages du connecteur ne peuvent pas contenir de pièces jointes de fichier.

* L’URL de l’instance de connecteur doit être traitée comme secrète/confidentielle : toute personne disposant de cette URL peut la publier, comme une adresse e-mail. Par conséquent, il existe un risque de courrier indésirable ou de liens vers des sites de hameçonnage ou de programmes malveillants. Si cela se produit, les propriétaires d’équipe peuvent supprimer l’instance de connecteur.

* Si le service qui envoie des messages de connecteur est compromis et commence à envoyer des liens de courrier indésirable/hameçonnage/programmes malveillants, un administrateur client peut empêcher la création de nouvelles instances de connecteur et Microsoft peut les bloquer de manière centralisée.

> [!NOTE]
> Il n’est actuellement pas possible de savoir quels connecteurs prennent en charge les messages actionnables (REPLYTO_CONNECTOR_MESSAGE autorisation).

## <a name="outgoing-webhooks"></a>Webhooks sortants

_Les webhooks sortants sont créés_ par les propriétaires d’équipe ou les membres de l’équipe. Il ne s’agit pas de fonctionnalités d’applications Teams ; ces informations sont incluses pour l’exhaustivité.

### <a name="required-permissions"></a>Autorisations requises

RECEIVE_MESSAGE, REPLYTO_MESSAGE. Peut recevoir des messages des utilisateurs et y répondre.

### <a name="optional-permissions"></a>Autorisations facultatives

Aucun

### <a name="considerations"></a>Considérations

* Les webhooks sortants sont similaires aux bots, mais ont moins de privilèges. Ils doivent être mentionnés explicitement, tout comme les bots.

* Lorsqu’un webhook sortant est inscrit, un secret est généré, ce qui permet au webhook sortant de vérifier que l’expéditeur est Microsoft Teams par opposition à un attaquant malveillant. Ce secret doit rester un secret; toute personne qui y a accès peut emprunter l’identité de Microsoft Teams. Si le secret est compromis, le webhook sortant peut être supprimé et recréé, et un nouveau secret est généré.

* Bien qu’il soit possible de créer un webhook sortant qui ne valide pas le secret, nous vous recommandons de le faire.

* Outre la réception et la réponse aux messages, les webhooks sortants ne peuvent pas faire grand chose : ils ne peuvent pas envoyer de messages de manière proactive, ils ne peuvent pas envoyer ou recevoir des fichiers, ils ne peuvent rien faire d’autre que recevoir et répondre aux messages.
