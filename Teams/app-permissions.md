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
description: L’administrateur peut savoir quelles données et autorisations Microsoft Teams applications demandent à leur organisation.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 59d8303943b8912f7ed0578bd911b633b618f113
ms.sourcegitcommit: de6eb0478a79e178c5d02cdab8cca44a88beb853
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2022
ms.locfileid: "63070553"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Autorisations d’applications Microsoft Teams et points à prendre en compte

Microsoft Teams d’applications vous permettent d’agréger une ou plusieurs fonctionnalités dans un _package_ d’application qui peut être installé, mis à niveau et désinstallé. Les fonctionnalités sont les suivantes :

- Bots
- Extensions de messagerie
- Onglets
- Connecteurs

Les applications sont y consentées par les utilisateurs et gérées par les professionnels de l’it dans une perspective de stratégie. Toutefois, pour la plupart, les autorisations et le profil de risque d’une application sont définis par les autorisations et les profils de risque des fonctionnalités que contient l’application. Par conséquent, cet article se concentre sur les autorisations et les considérations au niveau de la fonctionnalité.

Les autorisations ci-dessous en majuscules, par exemple RECEIVE_MESSAGE et REPLYTO_MESSAGE, n’apparaissent pas dans la documentation du développeur [Microsoft Teams](/microsoftteams/platform/overview) ou dans les [autorisations de Microsoft Graph](/graph/permissions-reference). Il s’agit simplement d’une a bref descriptif des objectifs de cet article.


| Titre   | Description    |
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/>Point de décision|<ul><li>Utilisez les tableaux ci-dessous comme guide pour comprendre les autorisations que les applications que vous examinez demandent.</li></ul> |
| ![Icône montrant l’étape suivante.](media/audio_conferencing_image9.png)<br/>Étape suivante|<ul><li>Recherchez l’application ou le service lui-même pour décider si vous voulez autoriser ou non l’accès à l’application au sein de votre organisation. Par exemple, les robots envoient et reçoivent des messages des utilisateurs et, à l’exception des robots personnalisés d’entreprise, ils se trouvent en dehors de la limite de conformité. Par conséquent, toute application qui inclut un bot requiert ces autorisations et possède au minimum ce profil de risque. </li></ul>|

Voir aussi [Demander des autorisations d’appareil pour votre Microsoft Teams onglet.](/microsoftteams/platform/concepts/device-capabilities/native-device-permissions)

## <a name="global-app-permissions-and-considerations"></a>Considérations et autorisations pour les applications globales

### <a name="required-permissions"></a>Autorisations requises

Aucun

### <a name="optional-permissions"></a>Autorisations facultatives

Aucun

### <a name="considerations"></a>Considérations

- Une application doit divulguer les données qu’elle utilise et ce à quoi elles sont utilisées dans ses liens d’utilisation et de politique de confidentialité.

- [Le consentement spécifique à une](resource-specific-consent.md) ressource fournit un ensemble d’autorisations que les applications peuvent demander, qui apparaît sur l’écran d’installation de l’application. Pour en savoir plus sur les autorisations de consentement spécifiques aux ressources, voir [Graph référence des autorisations](/graph/permissions-reference#teams-resource-specific-consent-permissions).

- Les applications peuvent également avoir besoin d’autorisations autres que des autorisations de consentement spécifiques aux ressources. Une fois qu’une application est installée, elle peut demander Graph autorisations d’autorisation par le biais d’une invite de consentement. Pour en savoir plus, voir [Comprendre Azure AD expériences de consentement d’application](/azure/active-directory/develop/application-consent-experience). Vous pouvez configurer les autorisations et le consentement de l’API dans le portail Azure. Pour plus d’informations, voir [Azure Active Directory infrastructure de consentement.](/azure/active-directory/develop/consent-framework)

## <a name="bots-and-messaging-extensions"></a>Bots et extensions de messagerie

### <a name="required-permissions"></a>Autorisations requises

- RECEIVE_MESSAGE, REPLYTO_MESSAGE. Le robot peut recevoir des messages d’utilisateurs et y répondre. <sup>1</sup>

- POST_MESSAGE_USER. Une fois qu’un utilisateur a envoyé un message à un bot, il peut envoyer des messages directs à l’utilisateur (également *appelés messages proactifs* à tout moment).

- GET_CHANNEL_LIST. Les bots ajoutés aux équipes peuvent obtenir une liste des noms et des ID des canaux d’une équipe.

### <a name="optional-permissions"></a>Autorisations facultatives

- IDENTITY. Lorsqu’il est utilisé dans un canal, les robots de l’application peuvent accéder aux informations d’identité de base des membres de l’équipe (prénom, nom, nom d’utilisateur principal [UPN], adresse de messagerie) ; lorsqu’il est utilisé dans une conversation personnelle ou de groupe, le robot peut accéder aux mêmes informations pour ces utilisateurs.

- POST_MESSAGE_TEAM. Permet aux robots d’une application d’envoyer des messages directs (proactifs) à tout membre de l’équipe à tout moment, même si l’utilisateur n’a jamais parlé au robot auparavant.

- Les autorisations suivantes ne sont pas explicites, mais sont implicites par RECEIVE_MESSAGE et REPLYTO_MESSAGE ainsi que les étendues dans lesquelles les robots peuvent être utilisés, déclarés dans le manifeste :
 
    - RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL
    - RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT
    - RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM

- SEND_FILES, RECEIVE_FILES. <sup>2 Contrôle</sup> si un bot peut envoyer et recevoir des fichiers dans une conversation personnelle (pas encore pris en charge pour les discussions de groupe ou les canaux).

### <a name="considerations"></a>Considérations

- Les robots ont uniquement accès aux équipes à lesquelles elles ont été ajoutées ou aux utilisateurs qui les ont installées.

- Les robots reçoivent uniquement les messages dans lesquels ils sont explicitement mentionnés par les utilisateurs. Ces données quittent le réseau d’entreprise.

- Les robots peuvent uniquement répondre aux conversations dans lesquelles ils sont mentionnés.

- Lorsqu’un utilisateur a converser avec un bot, si celui-ci stocke son ID, il peut envoyer des messages directs à cet utilisateur à tout moment.

- Il est très souvent possible pour les messages de bots de contenir des liens vers des sites de phishing ou de programmes malveillants, mais les robots peuvent être bloqués par l’utilisateur, l’administrateur du client ou, globalement, par Microsoft.

- Un bot peut récupérer (et stocker) des informations d’identité très basiques pour les membres de l’équipe à qui l’application a été ajoutée ou pour les utilisateurs individuels dans les conversations personnelles ou de groupe. Pour obtenir des informations supplémentaires sur ces utilisateurs, le bot doit les obliger à se Azure Active Directory (Azure AD).

- Les robots peuvent récupérer (et stocker) la liste des canaux dans une équipe . ces données quittent le réseau d’entreprise.

- Lorsqu’un fichier est envoyé à un bot, il quitte le réseau d’entreprise. L’envoi et la réception de fichiers nécessitent l’approbation de l’utilisateur pour chaque fichier. 

- Par défaut, les robots ne peuvent pas agir pour le compte de l’utilisateur, mais ils peuvent demander aux utilisateurs de se connecter. dès que l’utilisateur se signe, le bot a un jeton d’accès avec lequel il peut faire des choses supplémentaires. Les informations supplémentaires dépendent du robot et de l’endroit où l’utilisateur se trouve : un robot est une application Azure AD https://apps.dev.microsoft.com/ inscrite à et qui peut avoir son propre ensemble d’autorisations.

- Les robots sont informés chaque fois que des utilisateurs sont ajoutés ou supprimés d’une équipe.

- Les robots ne voient pas les adresses IP des utilisateurs ou d’autres informations de référence. Toutes les informations proviennent de Microsoft. (Il existe une exception : si un bot implémente sa propre expérience de inscription, l’interface utilisateur de sign-in affiche les adresses IP des utilisateurs et les informations de référence.)

- En revanche, les extensions de messagerie voient les adresses IP des utilisateurs et les informations des références.

- Les directives de l’application (et notre processus de révision AppSource) requièrent la discrétion de publier des messages de conversation personnelle à l’adresse des utilisateurs (via l’autorisation POST_MESSAGE_TEAM) à des fins valides. En cas d’abus, les utilisateurs peuvent bloquer le robot, les administrateurs des clients peuvent bloquer l’application et Microsoft peut bloquer les bots de façon centralisée si nécessaire.

<sup>1 Certains</sup> robots envoient uniquement des messages (POST_MESSAGE_USER). Ces robots sont appelés « notification uniquement », mais ce terme ne fait pas référence à ce qu’un robot est autorisé ou non à faire, cela signifie que le robot ne souhaite pas exposer une expérience de conversation. Teams utilise ce champ pour désactiver la fonctionnalité dans l’interface utilisateur qui serait normalement activée. Le robot n’est pas limité par ce qu’il est autorisé à faire par rapport aux robots qui exposent une expérience de conversation.

<sup>2</sup> Régi par la propriété booléens Supports dans le fichier manifest.json de l’application.

> [!NOTE]
> Si un robot dispose de sa propre inscription, il existe une deuxième expérience de consentement différente la première fois que l’utilisateur se connecte.
>
>Actuellement, les autorisations Azure AD associées à l’une des fonctionnalités d’une application Teams (bot, onglet, connecteur ou extension de messagerie) sont totalement distinctes des autorisations Teams répertoriées ici.

## <a name="tabs"></a>Onglets

Un onglet est un site web s’exécutant dans Teams.

### <a name="required-permissions"></a>Autorisations requises

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>Autorisations facultatives

Aucun (actuellement)

### <a name="considerations"></a>Considérations

- Le profil de risque d’un onglet est presque identique à celui du site web en cours d’exécution dans un onglet de navigateur. 

- Un onglet obtient également le contexte dans lequel il est en cours d’exécution, y compris le nom d’utilisateur général et le nom d’utilisateur général de l’utilisateur actuel, l’ID d’objet Azure AD de l’utilisateur actuel, l’ID du groupe Microsoft 365 dans lequel il réside (s’il s’agit d’une équipe), l’ID de client et les paramètres régionaux actuels de l’utilisateur. Toutefois, pour ma carte ces ID et les informations d’un utilisateur, l’onglet doit le faire se Azure AD.

## <a name="connectors"></a>Connecteurs

Un connecteur publie des messages sur un canal lorsque des événements dans un système externe se produisent.

### <a name="required-permissions"></a>Autorisations requises

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>Autorisations facultatives

REPLYTO_CONNECTOR_MESSAGE. Certains connecteurs supportent des messages actionnables, qui permettent aux utilisateurs de publier des réponses ciblées au message de connecteur, par exemple en ajoutant une réponse à un problème GitHub ou en ajoutant une date à une carte Trello.

### <a name="considerations"></a>Considérations

- Le système qui publie des messages connecteur ne sait pas vers qui il publie ou qui les reçoit : aucune information sur le destinataire n’est divulguer. (Microsoft est le destinataire réel, pas le client ; Microsoft publie réellement sur le canal.)

- Aucune donnée ne quitte le réseau d’entreprise lorsque des messages de connecteur sont publiés sur un canal.

- Les connecteurs qui supportent les messages actionnables (REPLYTO_CONNECTOR_MESSAGE autorisation) ne voient pas non plus les informations d’adresse IP et de référence ; Ces informations sont envoyées à Microsoft, puis acheminées vers des points de terminaison HTTP préalablement inscrits auprès de Microsoft dans le portail Connecteurs.

- Chaque fois qu’un connecteur est configuré pour un canal, une URL unique est créée pour cette instance de connecteur. Si cette instance de connecteur est supprimée, l’URL ne peut plus être utilisée.

- Les messages de connecteur ne peuvent pas contenir de pièces jointes.

- L’URL de l’instance du connecteur doit être traitée comme secrète/confidentielle : toute personne ayant cette URL peut y publier, comme une adresse e-mail. Par conséquent, il existe un risque lié au courrier indésirable ou aux liens vers des sites de phishing ou de programmes malveillants. Dans ce cas, les propriétaires d’équipe peuvent supprimer l’instance du connecteur.

- Si le service qui envoie des messages de connecteur deviendrait compromis et commencer à envoyer des liens de courrier indésirable, d’hameçonnage ou de programmes malveillants, un administrateur client peut empêcher la création de nouvelles instances de connecteur et Microsoft peut les bloquer de manière centralisée.

> [!NOTE]
> Il n’est actuellement pas possible de savoir quels connecteurs peuvent prendre en charge les messages actionnables (REPLYTO_CONNECTOR_MESSAGE autorisation).

## <a name="outgoing-webhooks"></a>Sites web sortants

*Les sites web sortants sont créés* à la volée par les propriétaires d’équipe ou les membres de l’équipe. Il ne s’agit pas de fonctionnalités Teams d’applications ; ces informations sont incluses pour l’intégralité.

### <a name="required-permissions"></a>Autorisations requises

RECEIVE_MESSAGE, REPLYTO_MESSAGE. Peut recevoir des messages des utilisateurs et y répondre.

### <a name="optional-permissions"></a>Autorisations facultatives

Aucun

### <a name="considerations"></a>Considérations

- Les sites web sortants sont similaires aux bots, mais ont moins de privilèges. Ils doivent être explicitement mentionnés, tout comme les bots.

- Lorsqu’un site web sortant est enregistré, un secret est généré, ce qui permet à l’équipe web sortante de vérifier que l’expéditeur est Microsoft Teams par opposition à un pirate malveillant. Ce secret doit rester un secret . toute personne qui y a accès peut prendre l’identité d’Microsoft Teams. Si le secret est compromis, l’accès web sortant peut être supprimé et recréé, et un nouveau secret est généré.

- Bien qu’il soit possible de créer un site web sortant qui ne valide pas le secret, nous vous recommandons de vous y baser.

- En plus de recevoir et de répondre à des messages, les sites Web sortants ne peuvent pas faire grand chose : ils ne peuvent pas envoyer des messages de manière proactive, ils ne peuvent pas envoyer ou recevoir de fichiers, ils ne peuvent rien faire d’autre que recevoir et répondre à des messages.