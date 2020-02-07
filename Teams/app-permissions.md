---
title: Autorisations d’applications Microsoft Teams et points à prendre en compte
author: rmw2890
ms.author: rowille
manager: serdars
ms.date: 06/27/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: Cette section explique quelles données et autorisations sont demandées par les applications de votre organisation.
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d7548d4d162310bc239c752e2bce38e725008f9
ms.sourcegitcommit: 8e2fa7b744d0a174b699ae7298d4688b971eeff3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/07/2020
ms.locfileid: "41845225"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Autorisations d’applications Microsoft Teams et points à prendre en compte

Les applications Microsoft Teams permettent de regrouper une ou plusieurs fonctionnalités dans un _package d’applications_ qui peut être installé, mis à niveau et désinstallé. Ces fonctionnalités incluent les éléments suivants :

- Bots
- Extensions de messagerie
- Onglets
- Connecteurs

Les bots sont acceptés par les utilisateurs et gérés par le service informatique de vue stratégique. Toutefois, pour la plupart des cas, les autorisations et le profil de risques d’une application sont définis par les autorisations et les profils de risques des fonctionnalités contenues dans l’application. Cet article est donc axé sur les autorisations et les éléments à prendre en compte au niveau des fonctionnalités.

Les autorisations répertoriées ci-dessous en majuscules, comme par exemple RECEIVE_MESSAGE et REPLYTO_MESSAGE, n’apparaissent pas partout dans la [documentation destinée aux développeurs Microsoft Teams](https://aka.ms/teamsdevdocs) ou les [autorisations de Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference). Il ne s’agit que d’une description aux fins de cet article.


|    |     |
|-----------|------------|
| ![Icône illustrant un point de décision](media/audio_conferencing_image7.png) <br/>Point de décision|<ul><li>Utilisez le tableau ci-dessous pour connaître les autorisations que les applications que vous recherchez demandent.</li></ul> |
| ![Icône montrant l’étape suivante](media/audio_conferencing_image9.png)<br/>Étape suivante|<ul><li>Recherchez l’application ou le service proprement dit pour décider si vous voulez autoriser l’accès au sein de votre organisation. Par exemple, les robots envoient des messages à des utilisateurs et les reçoivent, à l’exception des robots d’entreprise, qui sont situés en dehors de la limite de conformité. Par conséquent, toute application incluant un bot nécessite ces autorisations et possède au moins ce profil de risques. </li></ul>|

## <a name="global-app-permissions-and-considerations"></a>Autorisations et considérations générales pour les applications

### <a name="required-permissions"></a>Autorisations requises

Aucun

### <a name="optional-permissions"></a>Autorisations facultatives

Aucun

### <a name="considerations"></a>Inconvénients

Une application doit divulguer les données qu’elle utilise et quelles sont les données utilisées dans ses conditions générales d’utilisation et de politique de confidentialité.</td>

## <a name="bots-and-messaging-extensions"></a>Robots et extensions de messagerie

### <a name="required-permissions"></a>Autorisations requises

- RECEIVE_MESSAGE, REPLYTO_MESSAGE. Le bot peut recevoir des messages des utilisateurs et leur répondre.<sup>1</sup>

- POST_MESSAGE_USER. Dès qu’un utilisateur a envoyé un message à un bot, le bot peut lui envoyer des messages directs (également appelés *messages proactifs* à tout moment.

- GET_CHANNEL_LIST. Les bots ajoutés à des équipes peuvent obtenir la liste des noms et des ID des canaux d’une équipe.

### <a name="optional-permissions"></a>Autorisations facultatives

- Stockage. Lorsqu’il est utilisé dans un canal, les robots de l’application peuvent accéder aux informations d’identité de base des membres de l’équipe (prénom, nom, nom d’utilisateur principal [UPN], adresse de messagerie). lorsqu’il est utilisé dans une conversation personnelle ou de groupe, le bot peut accéder aux mêmes informations pour ces utilisateurs.

- POST_MESSAGE_TEAM. Permet aux robots d’une application de lui envoyer des messages directs (proactif) à tout moment, même si l’utilisateur n’a jamais parlé au bot auparavant.

- Les éléments suivants ne sont pas des autorisations explicites, mais sont implicites en RECEIVE_MESSAGE et REPLYTO_MESSAGE et les étendues dans lesquelles les robots peuvent être utilisés, déclarées dans le manifeste :
 
    - RECEIVE_MESSAGE_PERSONAL REPLYTO_MESSAGE_PERSONAL
    - RECEIVE_MESSAGE_GROUPCHAT REPLYTO_MESSAGE_GROUPCHAT
    - RECEIVE_MESSAGE_TEAM REPLYTO_MESSAGE_TEAM

- SEND_FILES RECEIVE_FILES. <sup>2</sup> contrôle si un bot peut envoyer et recevoir des fichiers dans la conversation personnelle (pas encore pris en charge pour les conversations ou canaux de groupe).

### <a name="considerations"></a>Inconvénients

- Les robots ont uniquement accès aux équipes auxquelles ils ont été ajoutés ou aux utilisateurs qui les ont installés.

- Les robots reçoivent uniquement les messages dans lesquels ils sont explicitement indiqués par les utilisateurs. Ces données quittent le réseau d’entreprise.

- Les robots peuvent uniquement répondre aux conversations dans lesquelles ils sont mentionnés.

- Après que l’utilisateur a adressé son ID de robot, si ce dernier l’a stocké, il peut lui envoyer un message direct à tout moment.

- Le message bot peut en théorie contenir des liens vers des sites de hameçonnage ou des logiciels malveillants, mais les robots peuvent être bloqués par l’utilisateur, l’administrateur client ou globalement par Microsoft.

- Un bot peut récupérer (et peut stocker) des informations d’identité de base pour les membres de l’équipe auxquelles l’application a été ajoutée ou pour des utilisateurs individuels dans des discussions personnelles ou de groupe. Pour plus d’informations sur ces utilisateurs, le bot doit avoir besoin de se connecter à Azure Active Directory (Azure AD).

- Les robots peuvent récupérer (et peut-être stocker) la liste de canaux dans une équipe ; ces données quittent le réseau d’entreprise.

- Lorsqu’un fichier est envoyé à un bot, le fichier quitte le réseau d’entreprise. Pour envoyer et recevoir des fichiers, l’utilisateur doit approuver chaque fichier. 

- Par défaut, les robots ne peuvent pas agir de la part de l’utilisateur, mais les robots peuvent demander aux utilisateurs de se connecter ; dès que l’utilisateur se connecte, le bot dispose d’un jeton d’accès permettant d’effectuer d’autres actions. Exactement ce que ces éléments supplémentaires dépendent du bot et de l’endroit où l’utilisateur se connecte : un bot est une application Azure https://apps.dev.microsoft.com/ ad inscrite sur et peut avoir son propre jeu d’autorisations.

- Les robots sont informés lorsque les utilisateurs sont ajoutés ou supprimés d’une équipe.

- Les robots ne voient pas les adresses IP des utilisateurs ou d’autres informations de renvoi. Toutes les informations proviennent de Microsoft. (Il existe une seule exception : si un bot implémente son propre utilisateur de connexion, l’interface utilisateur de connexion verra les adresses IP et les informations de renvoi des utilisateurs.)

- En revanche, les extensions de messagerie s’affichent avec les adresses IP des utilisateurs et les informations de renvoi.

- Recommandations en matière d’applications (et notre processus de vérification AppSource) exigez la discrétion lors de l’envoi de messages de discussion personnelles aux utilisateurs (via l’autorisation POST_MESSAGE_TEAM) à des fins valides. En cas d’abus, les utilisateurs peuvent bloquer le bot, les administrateurs de clients peuvent bloquer l’application et Microsoft peut bloquer les robots de manière centralisée, le cas échéant.

<sup>1</sup> certains robots envoient uniquement des messages (POST_MESSAGE_USER). Il s’agit de robots « notifications uniquement », mais le terme ne fait pas référence à ce qu’un bot est autorisé ou qu’il n’est pas autorisé à faire, cela signifie que le bot ne veut pas exposer une conversation. Teams utilise ce champ pour désactiver les fonctionnalités de l’interface utilisateur qui seraient en principe activées ; Ce robot n’est pas limité à ce qu’il est autorisé à faire comparé aux robots qui présentent une connaissance de conversation.

<sup>2</sup> soumis à la propriété booléenne supportsFiles sur l’objet bot dans le fichier manifest. JSON de l’application.

> [!NOTE]
> Si un bot dispose de sa propre connexion, il y a une deuxième fonction de consentement pour la première fois que l’utilisateur se connecte.
>
>Pour l’instant, les autorisations Azure AD associées à toutes les fonctionnalités à l’intérieur d’une application Teams (bot, onglet, connecteur ou extension de messagerie) sont entièrement distinctes des autorisations d’équipe répertoriées ici.

## <a name="tabs"></a>Onglets

Un onglet est un site Web qui s’exécute dans Teams.

### <a name="required-permissions"></a>Autorisations requises

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>Autorisations facultatives

Aucun (actuellement)

### <a name="considerations"></a>Inconvénients

- Le profil de risque d’un onglet est presque identique au même site Web exécuté dans un onglet de navigateur. 

- Un objet Tab obtient également le contexte dans lequel il est en cours d’exécution, y compris le nom de connexion et le nom d’utilisateur principal (UPN) de l’utilisateur actuel, l’ID d’objet Azure AD pour l’utilisateur actuel, l’ID du groupe Office 365 dans lequel il se trouve (s’il s’agit d’une équipe), l’ID de locataire. ainsi que les paramètres régionaux actuels de l’utilisateur. Toutefois, pour mapper ces ID aux informations d’un utilisateur, l’onglet doit permettre à l’utilisateur de se connecter à Azure AD.

## <a name="connectors"></a>Lien

Un connecteur publie des messages vers un canal lorsque des événements dans un système externe se produisent.

### <a name="required-permissions"></a>Autorisations requises

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>Autorisations facultatives

REPLYTO_CONNECTOR_MESSAGE. Certains connecteurs prennent en charge des messages interactifs, ce qui permet aux utilisateurs de publier des réponses ciblées au message du connecteur, par exemple en ajoutant une réponse à un problème de GitHub ou en ajoutant une date à une carte Trello.

### <a name="considerations"></a>Points à prendre en compte

- Le système qui publie des messages de connecteur ne sait pas à qui il envoie des messages ou qui les reçoit : aucune information sur le destinataire n’est divulguée. (Microsoft est le destinataire réel, et non le locataire ; Microsoft effectue le billet réel sur le canal.)

- Aucune donnée ne quitte le réseau d’entreprise lorsque des messages de connecteur sont publiés dans un canal.

- Les connecteurs qui prennent en charge les messages interactifs (autorisation REPLYTO_CONNECTOR_MESSAGE) ne voient pas les informations d’adresse IP et de renvoi. ces informations sont envoyées à Microsoft, puis routées aux points de terminaison HTTP déjà enregistrés auprès de Microsoft dans le portail de connecteurs.

- Chaque fois qu’un connecteur est configuré pour un canal, une URL unique est créée pour cette instance de connecteur. Si cette instance de connecteur est supprimée, l’URL ne peut plus être utilisée.

- Les messages de connexion ne peuvent pas contenir de pièces jointes.

- L’URL d’instance du connecteur doit être considérée comme secrète/confidentiel : toute personne disposant de cette URL peut la publier dans celle-ci, comme une adresse de messagerie. Par conséquent, il existe du courrier indésirable ou des liens vers des sites de hameçonnage ou de Malware. Si tel est le cas, les propriétaires d’équipe peuvent supprimer l’instance de connecteur.

- Si le service qui envoie des messages de connecteur a été compromis et qu’ils commencent à envoyer des courriers indésirables/de hameçonnage/malveillants, un administrateur client peut empêcher la création d’instances de connecteur et Microsoft peut les bloquer de manière centralisée.

> [!NOTE]
> Il n’est pas possible actuellement de savoir quels connecteurs prennent en charge les messages exploitables (autorisation REPLYTO_CONNECTOR_MESSAGE).

## <a name="outgoing-webhooks"></a>Raccordements Web sortants

Les *webhook sortants* sont créés à la volée par les propriétaires d’équipe ou les membres de l’équipe. Elles ne sont pas des fonctionnalités des applications Teams. ces informations sont disponibles à des fins d’exhaustivité.

### <a name="required-permissions"></a>Autorisations requises

RECEIVE_MESSAGE REPLYTO_MESSAGE. Peut recevoir des messages des utilisateurs et y répondre.

### <a name="optional-permissions"></a>Autorisations facultatives

Aucun

### <a name="considerations"></a>Points à prendre en compte

- Les raccordements Web sortants sont similaires aux robots, mais ils ont moins de privilèges. Elles doivent être mentionnées explicitement, comme les robots.

- Lors de l’enregistrement d’un webhook sortant, une clé secrète est générée, ce qui permet au webhook sortant de vérifier que l’expéditeur est Microsoft teams plutôt qu’à un attaquant malveillant. Ce secret doit rester secret ; toute personne qui y a accès peut emprunter l’identité de Microsoft Teams. Si la clé secrète est compromise, le webhook sortant peut être supprimé, recréé et un nouveau secret est généré.

- Même s’il est possible de créer un webhook sortant qui ne valide pas le secret, nous vous recommandons de le faire contre.

- Hormis le fait de recevoir et de répondre à des messages, les Cross Hook sortantes ne peuvent pas faire beaucoup : les utilisateurs ne peuvent pas envoyer de messages de manière proactive, ils ne peuvent pas envoyer ou recevoir des fichiers, ils ne peuvent pas effectuer d’autres opérations que les robots peuvent effectuer, sauf recevoir des messages et y répondre.
