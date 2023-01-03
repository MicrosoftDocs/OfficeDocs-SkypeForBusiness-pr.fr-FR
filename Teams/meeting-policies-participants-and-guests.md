---
title: Gérer les stratégies de réunion pour les participants et les invités
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.participantandguests
- seo-marvel-apr2020
description: Découvrez comment gérer les paramètres de stratégie de réunion dans Teams pour les participants et les invités.
ms.openlocfilehash: 26d2fd24d8b241b8f79276148ed27abd3e5412b1
ms.sourcegitcommit: 84a832330c0a9f9fb818bbfb22e534fe035c1837
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/03/2023
ms.locfileid: "69693387"
---
# <a name="meeting-policy-settings---participants--guests"></a>Paramètres de stratégie de réunion : participants et invités

<a name="bkmeetingparticipants"> </a>

Ces paramètres contrôlent les participants à la réunion qui attendent dans la salle d’attente avant d’être admis à la réunion et le niveau de participation qu’ils sont autorisés à participer à une réunion.

- [Permettre à des personnes anonymes de rejoindre une réunion](#let-anonymous-people-join-a-meeting)
- [Autoriser les personnes anonymes à démarrer une réunion](#let-anonymous-people-start-a-meeting)
- [Qui peut présenter dans les réunions](#who-can-present-in-meetings)
- [Admettre les personnes automatiquement](#automatically-admit-people)
- [Les utilisateurs rendez-vous peuvent contourner la salle d’attente](#dial-in-users-can-bypass-the-lobby)
- [Se réunir maintenant dans des réunions privées](#meet-now-in-private-meetings)
- [Sous-titres en direct](#live-captions)
- [Conversation dans les réunions](#chat-in-meetings)
- [Q&R Teams](#teams-qa)
- [Réactions aux réunions](#meeting-reactions)

Ces paramètres se trouvent dans le Centre d’administration Teams sous **Stratégies de** > **réunion** dans la section **Participants & invités** .

> [!NOTE]
> Les options permettant de participer à une réunion varient en fonction des paramètres de chaque groupe Teams et de la méthode de connexion. Si votre groupe dispose d’une audioconférence et l’utilise pour se connecter, consultez[Audioconférence](/microsoftteams/audio-conferencing-in-office-365). Si votre équipe n’a pas d’audioconférence, consultez [Participer à une réunion dans Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).

## <a name="let-anonymous-people-join-a-meeting"></a>Permettre à des personnes anonymes de rejoindre une réunion

Ce paramètre par organisateur permet à n’importe qui de rejoindre des réunions en tant qu’utilisateur anonyme en sélectionnant le lien dans l’invitation à la réunion. Pour en savoir plus, voir [Rejoindre une réunion sans disposer de compte Teams](https://support.microsoft.com/office/c6efc38f-4e03-4e79-b28f-e65a4c039508). La capacité des utilisateurs anonymes à participer aux réunions est également contrôlée au niveau de votre organisation. Le paramètre le plus restrictif sera efficace. Pour en savoir plus, consultez [Utilisation du Centre d’administration Microsoft Teams pour configurer la stratégie à l’échelle de l’organisation](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings).

## <a name="let-anonymous-people-start-a-meeting"></a>Autoriser les personnes anonymes à démarrer une réunion

Ce paramètre est une stratégie par organisateur qui autorise les réunions de conférence rendez-vous sans leader. Ce paramètre contrôle si les utilisateurs anonymes et les appelants rendez-vous peuvent rejoindre la réunion sans qu’un utilisateur authentifié de l’organisation ne soit présent. Par défaut, ce paramètre est désactivé, ce qui signifie que les utilisateurs anonymes et les appelants rendez-vous attendent dans la salle d’attente jusqu’à ce qu’un utilisateur authentifié de l’organisation rejoigne la réunion.

> [!NOTE]
> Si ce paramètre est désactivé et qu’un utilisateur de participation a rejoint la réunion pour la première fois et est placé dans la salle d’attente, l’utilisateur d’une organisation doit participer à la réunion avec un client Teams pour admettre l’utilisateur de la salle d’attente. Il n’y a pas de contrôle de salle d’attente disponible pour les utilisateurs entrants.

## <a name="who-can-present-in-meetings"></a>Qui peut présenter dans les réunions

Ce paramètre est une stratégie par utilisateur qui vous permet de modifier la valeur par défaut du paramètre **Qui peut présenter ?** dans **Options de réunion** dans le client Teams. Le paramètre **de stratégie Qui peut être présent dans les réunions** affecte toutes les réunions, y compris les réunions Meet Now.

Le paramètre **Qui peut présenter ?** permet aux organisateurs de réunions de choisir qui peuvent être présentateurs pendant une réunion. Pour plus d’informations, consulte [Modifier les paramètres des participants pour une réunion Teams](https://support.microsoft.com/office/53261366-dbd5-45f9-aae9-a70e6354f88e) et [Rôles dans une réunion Teams](https://support.microsoft.com/office/c16fa7d0-1666-4dde-8686-0a0bfe16e019).

Pour spécifier la valeur par défaut du paramètre **Qui peut présenter ?** dans Teams, définissez l’un des paramètres suivants dans la stratégie **Qui peut être présent dans les réunions** :

- **Organisateurs, mais les utilisateurs peuvent remplacer** : seul l’organisateur de la réunion peut être un présentateur et tous les participants à la réunion sont désignés comme participants. Ce paramètre correspond au paramètre **Uniquement moi** dans Teams.
- **Tout le monde dans l’organisation, mais l’utilisateur peut remplacer** : les utilisateurs authentifiés de l’organisation, y compris les invités, peuvent être présentateurs. Ce paramètre correspond au **paramètre Personnes dans mon organisation** dans Teams.
- **Tout le monde, sauf l’utilisateur peut remplacer** : tous les participants à la réunion peuvent être présentateurs. Ceci est la valeur par défaut. Ce paramètre correspond au paramètre **Tout le monde** dans Teams.

Gardez à l’esprit qu’une fois que vous avez défini la valeur par défaut, les organisateurs de réunion peuvent toujours modifier ce paramètre dans Teams et choisir les personnes pouvant présenter les réunions qu’ils planifient.

## <a name="automatically-admit-people"></a>Admettre les personnes automatiquement

Il s’agit d’une stratégie par organisateur. Ce paramètre contrôle si les personnes rejoignent une réunion directement ou attendent dans la salle d’attente jusqu’à ce qu’elles soient admises par un utilisateur authentifié. Ce paramètre ne s’applique pas aux utilisateurs rendez-vous.

![Capture d’écran montrant une réunion avec un utilisateur dans la salle d’attente.](media/meeting-policies-lobby.png)

 Les organisateurs de réunion peuvent cliquer sur **Options de réunion** dans l’invitation à la réunion afin de modifier ce paramètre pour chaque réunion qu’ils planifient.

> [!NOTE]
> In the meeting options the setting is labeled "Who can bypass the lobby". If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.
  
|Valeur du paramètre  |Comportement de jointure |
|---------|---------|
|**Tout le monde**   |Tous les participants à la réunion joignent directement la réunion sans attendre dans la salle d’attente. Cela inclut les utilisateurs authentifiés, les utilisateurs d’organisations approuvées, les invités et les utilisateurs anonymes.     |
|**Membres de mon organisation et invités**     |Les utilisateurs authentifiés au sein de l’organisation, y compris les invités, rejoignent la réunion directement sans attendre dans la salle d’attente. Les utilisateurs des organisations approuvées et des utilisateurs anonymes attendent dans la salle d’attente. Il s’agit du paramètre par défaut.    |
|**Membres de mon organisation, organisations de confiance et invités**     |Les utilisateurs authentifiés au sein de l’organisation, y compris les invités et les utilisateurs d’organisations approuvées, rejoignent la réunion directement sans attendre dans la salle d’attente.  Les utilisateurs anonymes attendent dans la salle d’attente.   |
|**Membres de mon organisation**    |Les utilisateurs authentifiés de l’organisation rejoignent la réunion directement sans attendre dans la salle d’attente.  Les utilisateurs d’organisations approuvées, d’invités et d’utilisateurs anonymes attendent dans la salle d’attente.          |
|**Organisateur uniquement**    |Seuls les organisateurs de réunion peuvent rejoindre directement la réunion sans attendre dans la salle d’attente. Tout le monde, y compris les utilisateurs authentifiés au sein de l’organisation, les invités, les utilisateurs d’organisations approuvées et les utilisateurs anonymes doivent attendre dans la salle d’attente. Dans la page des options de réunion du client Teams, elle apparaît sous la forme « Moi seul ».          |
|**Utilisateurs invités uniquement**    |Seuls les utilisateurs invités et les organisateurs de la réunion peuvent participer directement à la réunion sans attendre dans la salle d’attente. Tout le monde, y compris les utilisateurs authentifiés au sein de l’organisation, les invités, les utilisateurs d’organisations approuvées et les utilisateurs anonymes doivent attendre dans la salle d’attente. Dans la page d’options de réunion du client Teams, le message s’affiche sous la forme « Personnes j’invite ». Les utilisateurs ajoutés dans le cadre d’un groupe de distribution devront passer par la salle d’attente.      |

 > [!NOTE]
> Les organisations approuvées sont des domaines avec lesquels vous autorisez les communications fédérées dans Teams. Si vous activez **Autoriser tous les domaines externes** pour l’accès externe dans le Centre d’administration Teams, tout utilisateur authentifié au sein d’une organisation Teams sera approuvé. Si vous choisissez de spécifier des domaines externes autorisés et de bloquer tous les autres domaines, les domaines autorisés deviennent des organisations approuvées. Tout domaine bloqué est considéré comme n’étant pas une organisation approuvée.

## <a name="dial-in-users-can-bypass-the-lobby"></a>Les utilisateurs rendez-vous peuvent contourner la salle d’attente

Il s’agit d’une stratégie par organisateur. Ce paramètre contrôle si les personnes qui utilisent le téléphone rejoignent directement la réunion ou attendent dans la salle d’attente, quel que soit le paramètre **Autoriser les personnes automatiquement**. Par défaut, ce paramètre est désactivé. Lorsque ce paramètre est désactivé, les utilisateurs appelants patientent dans la salle d’attente jusqu’à ce qu’un utilisateur de l’organisation rejoigne la réunion avec un client Teams et les accepte. Lorsque ce paramètre est activé, les utilisateurs rendez-vous rejoignent automatiquement la réunion lorsqu’un utilisateur de l’organisation rejoint la réunion avec un client Teams.

> [!NOTE]
> Si un utilisateur connecté rejoint une réunion avant qu'un utilisateur de l'organisation ne la rejoigne, il sera placé dans la salle d'attente jusqu'à ce qu'un utilisateur de l'organisation rejoigne la réunion à l'aide d'un client Teams et l'admette. Si vous modifiez le paramètre par défaut pour un utilisateur, celui-ci s’applique à toutes les réunions organisées par cet utilisateur et aux réunions antérieures où l’utilisateur n’a pas modifié les options de la réunion.

## <a name="meet-now-in-private-meetings"></a>Se réunir maintenant dans des réunions privées

Il s’agit d’une stratégie par utilisateur qui s’applique avant le début d’une réunion. Ce paramètre détermine si un utilisateur peut démarrer une réunion privée non planifiée. Par défaut, ce paramètre est activé.

## <a name="live-captions"></a>Sous-titres en direct

Ce paramètre est une stratégie par utilisateur qui s’applique pendant une réunion. Ce paramètre détermine si l’option **Activer les légendes dynamiques** est disponible pour l’utilisateur, afin d’activer et de désactiver les légendes dynamiques dans les réunions qu’elle attend.  

![Capture d’écran montrant l’option Activer les sous-titres en direct.](media/meeting-policies-live-captions.png)

|Valeur du paramètre |Comportement  |
|---------|---------|
|**Non activé, mais l’utilisateur peut remplacer**     | Les sous-titres en direct ne sont pas activés automatiquement pour l’utilisateur pendant une réunion. L’utilisateur voit l’option **Activer les sous-titres en direct** dans le menu débordement (**...**) pour les activer. Il s’agit du paramètre par défaut. |
|**Non activé**     | Les légendes dynamiques sont désactivées pour l’utilisateur pendant une réunion. L’utilisateur n’a pas la possibilité de les activer.          |

Pour plus d’informations sur la façon dont vos utilisateurs finaux peuvent activer **les sous-titres en direct**, consultez [Utiliser des sous-titres en direct dans une réunion Teams](https://support.microsoft.com/office/4be2d304-f675-4b57-8347-cbd000a21260).

### <a name="live-translated-captions"></a>Sous-titres traduits en direct

> [!NOTE]
> Cette fonctionnalité est temporairement disponible en préversion publique. Après la préversion, l’organisateur de la réunion doit disposer d’une licence Teams Premium pour permettre aux participants d’utiliser des sous-titres traduits en direct.

Par défaut, **les sous-titres en direct sont affichés** dans la langue parlée pendant une réunion. **Les sous-titres traduits en direct** permettent à vos utilisateurs de voir les légendes traduites dans la langue avec laquelle ils sont le plus à l’aise.

Pour activer **les sous-titres traduits en direct**, **les sous-titres en direct** doivent être définis sur **Non activé, mais l’utilisateur peut remplacer** dans le centre d’administration Teams. Pour désactiver **les sous-titres traduits en direct**, définissez cette option sur **Non activé**.

<a name="bkcontentsharing"> </a>

## <a name="chat-in-meetings"></a>Conversation dans les réunions

Il s’agit d’une stratégie par utilisateur et par organisateur. Ce paramètre détermine si la conversation de réunion est autorisée pendant la réunion de l’utilisateur. Ce paramètre ne s’applique pas aux réunions de canal.

|Valeur du paramètre |Comportement  |
|---------|---------|
|**Activez-la pour tout le monde**     | Tous les participants peuvent écrire et afficher des messages de conversation. |
|**Désactivez-le pour tout le monde**     | La conversation de réunion est désactivée pour tous les participants.  |
|**Activez-la pour tout le monde sauf pour les utilisateurs anonymes**     | L’accès en écriture aux conversations de réunion est désactivé uniquement pour les participants anonymes.  |

Une fois que cette stratégie **De conversation dans les réunions** est appliquée aux utilisateurs, un organisateur ne peut pas remplacer cette stratégie par le biais des **options de réunion**.

La stratégie appliquée à l’organisateur de la réunion peut affecter d’autres utilisateurs de la réunion. Par exemple :

- Si l’organisateur a **défini La conversation dans les réunions** sur **Activer pour tout le monde** ou **l’Activer pour tout le monde sauf les utilisateurs anonymes**, la stratégie individuelle d’un utilisateur s’applique et tous les utilisateurs avec **l’option Désactiver pour tout le monde** défini ne pourront pas discuter dans la réunion.
- Si l’organisateur a **l’option Conversation dans les réunions** définie **sur Désactiver pour tout le monde**, la stratégie de l’organisateur s’applique et personne ne pourra discuter dans la réunion.

<a name="bkparticipantsandguests"> </a>

## <a name="teams-qa"></a>Q&R Teams

Il s’agit d’une stratégie par organisateur. Ce paramètre active ou désactive l’expérience Questions & Réponses (Q&R).

Le paramètre est appliqué lorsqu’une réunion est créée ou mise à jour par les organisateurs. Par défaut, ce paramètre est désactivé. En savoir plus sur [Q&R dans Réunions Teams](/manage-qna-for-teams).

Les questions&R teams peuvent être ajustées dans le Centre d’administration Teams sous **Stratégies de** > **réunion** de réunions dans la section **Participants & invités** . Le paramètre `-QnAEngagementMode` contrôle cette stratégie dans PowerShell.

|Valeur du paramètre |Comportement  |
|---------|---------|
|**Activé**     | Les organisateurs peuvent ajouter des Q&R lors de la création de réunions. |
|**Désactivé**     | Les organisateurs n’auront pas la possibilité d’ajouter Q&R lors de la création de réunions.  |

## <a name="meeting-reactions"></a>Réactions aux réunions

Les réactions aux réunions sont activées par défaut. La désactivation des réactions pour un utilisateur ne signifie pas qu’il ne peut pas utiliser les réactions dans les réunions qu’il planifie. L’organisateur de la réunion peut toujours activer les réactions à partir de la page des options de réunion, quel que soit le paramètre par défaut.

## <a name="enable-meeting-policy-settings"></a>Activer les paramètres de stratégie de réunion

Pour activer les paramètres de stratégie de réunion, vous pouvez utiliser le [Centre d’administration Teams](https://admin.teams.microsoft.com/policies/meetings) (**Stratégies** >  de réunion **Modifier une stratégie** > **Participants & invités**) ou l’applet de commande [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) dans Teams PowerShell.

Dans cet exemple, nous utilisons PowerShell pour modifier la stratégie de réunion globale afin d’autoriser tout le monde à démarrer ou à rejoindre une réunion.

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AutoAdmittedUsers "Everyone" -AllowAnonymousUsersToStartMeeting $True -AllowPSTNUsersToBypassLobby $True
```

Une fois que vous avez configuré une stratégie, vous devez l’appliquer aux utilisateurs. Si vous avez modifié la stratégie globale (par défaut à l’échelle de l’organisation), elle s’applique automatiquement aux utilisateurs. Vous devez attendre au moins 4 heures avant que les modifications de stratégie prennent effet, mais cela peut prendre jusqu’à 24 heures.

## <a name="related-topics"></a>Sujets associés

- [Présentation de Teams PowerShell](teams-powershell-overview.md)
- [Attribuer des stratégies à vos utilisateurs](policy-assignment-overview.md)
- [Supprimer la stratégie de réunion Teams RestrictedAnonymousAccess des utilisateurs](meeting-policies-restricted-anonymous-access.md)
