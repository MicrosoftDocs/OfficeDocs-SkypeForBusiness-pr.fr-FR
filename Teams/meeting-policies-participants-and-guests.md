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
ms.openlocfilehash: 5b489f312dd1fd1fcd9bdb6a301a65e76ab9ed91
ms.sourcegitcommit: 9522d951700d19ab13c60a6452b3a8a4c824ee36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/26/2022
ms.locfileid: "68018090"
---
# <a name="meeting-policy-settings---participants--guests"></a>Paramètres de stratégie de réunion : participants et invités

<a name="bkmeetingparticipants"> </a>

Ces paramètres contrôlent les participants à la réunion qui attendent dans la salle d’attente avant d’être admis à la réunion et le niveau de participation qu’ils sont autorisés à participer à une réunion.

- [Permettre aux personnes anonymes de participer à une réunion](#let-anonymous-people-join-a-meeting)
- [Autoriser les personnes anonymes à démarrer une réunion](#let-anonymous-people-start-a-meeting)
- [Admettre les personnes automatiquement](#automatically-admit-people)
- [Autoriser les utilisateurs entrants à éviter la salle d’attente](#allow-dial-in-users-to-bypass-the-lobby)
- [Légendes en direct](#live-captions)
- [Conversation dans les réunions](#chat-in-meetings)

> [!NOTE]
> Les options permettant de participer à une réunion varient en fonction des paramètres de chaque groupe Teams et de la méthode de connexion. Si votre groupe dispose d’une audioconférence et l’utilise pour se connecter, consultez[Audioconférence](/microsoftteams/audio-conferencing-in-office-365). Si votre équipe n’a pas d’audioconférence, consultez [Participer à une réunion dans Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).

## <a name="let-anonymous-people-join-a-meeting"></a>Permettre aux personnes anonymes de participer à une réunion

Ce paramètre par organisateur permet à quiconque de participer à des réunions en tant qu’utilisateur anonyme en sélectionnant le lien dans l’invitation à la réunion. Pour en savoir plus, voir [Rejoindre une réunion sans disposer de compte Teams](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508). La capacité des utilisateurs anonymes à participer à des réunions est également contrôlée au niveau de votre organisation, le paramètre le plus restrictif sera efficace. Pour plus d’informations, consultez [Utilisation du Centre d’administration Microsoft Teams pour configurer la stratégie à l’échelle de l’organisation](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings).

## <a name="let-anonymous-people-start-a-meeting"></a>Autoriser les personnes anonymes à démarrer une réunion

Ce paramètre est une stratégie par organisateur qui permet des réunions de conférence rendez-vous sans leader. Ce paramètre détermine si les utilisateurs des appels entrants peuvent rejoindre la réunion sans utilisateur authentifié de l’organisation. Par défaut, ce paramètre est désactivé, ce qui signifie que les utilisateurs entrants attendront dans la salle d’attente jusqu’à ce qu’un utilisateur authentifié de l’organisation rejoigne la réunion.

> [!NOTE]
> Si ce paramètre est désactivé et qu’un utilisateur de participation a rejoint la réunion pour la première fois et est placé dans la salle d’attente, l’utilisateur d’une organisation doit participer à la réunion avec un client Teams pour admettre l’utilisateur de la salle d’attente. Il n’y a pas de contrôle de salle d’attente disponible pour les utilisateurs entrants.

## <a name="automatically-admit-people"></a>Admettre les personnes automatiquement

Il s’agit d’une stratégie par organisateur. Ce paramètre détermine si les personnes rejoignent une réunion directement ou attendent dans la salle d’attente jusqu’à ce qu’elles soient admises par un utilisateur authentifié. Ce paramètre ne s’applique pas aux utilisateurs entrants.

![Capture d’écran montrant une réunion avec un utilisateur dans la salle d’attente.](media/meeting-policies-lobby.png)

 Les organisateurs de réunion peuvent cliquer sur **Options de réunion** dans l’invitation à la réunion afin de modifier ce paramètre pour chaque réunion qu’ils planifient.

> [!NOTE]
> In the meeting options the setting is labeled "Who can bypass the lobby". If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.
  
|Valeur du paramètre  |Comportement de jointure |
|---------|---------|
|**Tout le monde**   |Tous les participants à la réunion joignent directement la réunion sans attendre dans la salle d’attente. Cela inclut les utilisateurs authentifiés, les utilisateurs d’organisations approuvées, les invités et les utilisateurs anonymes.     |
|**Membres de mon organisation et invités**     |Les utilisateurs authentifiés au sein de l’organisation, y compris les invités, participent directement à la réunion sans attendre dans la salle d’attente. Les utilisateurs des organisations approuvées et des utilisateurs anonymes attendent dans la salle d’attente. Il s’agit du paramètre par défaut.    |
|**Membres de mon organisation, organisations de confiance et invités**     |Les utilisateurs authentifiés au sein de l’organisation, y compris les invités et les utilisateurs d’organisations approuvées, participent directement à la réunion sans attendre dans la salle d’attente.  Les utilisateurs anonymes attendent dans la salle d’attente.   |
|**Membres de mon organisation**    |Les utilisateurs authentifiés de l’organisation rejoignent directement la réunion sans attendre dans la salle d’attente.  Les utilisateurs d’organisations approuvées, d’invités et d’utilisateurs anonymes attendent dans la salle d’attente.          |
|**Organisateur uniquement**    |Seuls les organisateurs de réunion peuvent rejoindre directement la réunion sans attendre dans la salle d’attente. Tout le monde, y compris les utilisateurs authentifiés au sein de l’organisation, les invités, les utilisateurs d’organisations approuvées et les utilisateurs anonymes doivent attendre dans la salle d’attente. Dans la page Options de réunion du client Teams, elle apparaît comme « Uniquement moi ».          |
|**Utilisateurs invités uniquement**    |Seuls les utilisateurs invités et les organisateurs de réunion peuvent participer directement à la réunion sans attendre dans la salle d’attente. Tout le monde, y compris les utilisateurs authentifiés au sein de l’organisation, les invités, les utilisateurs d’organisations approuvées et les utilisateurs anonymes doivent attendre dans la salle d’attente. Dans la page Options de réunion du client Teams, il apparaît comme « Personnes j’invite ». Les utilisateurs ajoutés dans le cadre d’un groupe de distribution devront passer par la salle d’attente.      |

 > [!NOTE]
> Les organisations approuvées sont des domaines avec lequel vous autorisez les communications fédérées dans Teams. Si vous **activez Autoriser tous les domaines externes** pour l’accès externe dans le Centre d’administration Teams, tout utilisateur authentifié au sein d’une organisation Teams est approuvé. Si vous choisissez de spécifier des domaines externes autorisés et de bloquer tous les autres, les domaines autorisés deviennent des organisations approuvées. Tout domaine bloqué n’est pas considéré comme une organisation approuvée.

## <a name="allow-dial-in-users-to-bypass-the-lobby"></a>Autoriser les utilisateurs entrants à éviter la salle d’attente

Il s’agit d’une stratégie par organisateur. Ce paramètre contrôle si les personnes qui utilisent le téléphone rejoignent directement la réunion ou attendent dans la salle d’attente, quel que soit le paramètre **Autoriser les personnes automatiquement**. Par défaut, ce paramètre est désactivé. Lorsque ce paramètre est désactivé, les utilisateurs appelants patientent dans la salle d’attente jusqu’à ce qu’un utilisateur de l’organisation rejoigne la réunion avec un client Teams et les accepte. Lorsque ce paramètre est activé, les utilisateurs entrants rejoignent automatiquement la réunion lorsqu’un utilisateur de l’organisation rejoint la réunion avec un client Teams.

> [!NOTE]
> Si un utilisateur connecté rejoint une réunion avant qu'un utilisateur de l'organisation ne la rejoigne, il sera placé dans la salle d'attente jusqu'à ce qu'un utilisateur de l'organisation rejoigne la réunion à l'aide d'un client Teams et l'admette. Si vous modifiez le paramètre par défaut pour un utilisateur, celui-ci s’applique à toutes les réunions organisées par cet utilisateur et aux réunions antérieures où l’utilisateur n’a pas modifié les options de la réunion.

## <a name="live-captions"></a>Légendes en direct

Ce paramètre est une stratégie par utilisateur qui s’applique lors d’une réunion. Ce paramètre détermine si l’option **Activer les légendes dynamiques** est disponible pour l’utilisateur, afin d’activer et de désactiver les légendes dynamiques dans les réunions qu’elle attend.  

![Capture d’écran montrant l’option Activer les sous-titres en direct.](media/meeting-policies-live-captions.png)

|Valeur du paramètre |Comportement  |
|---------|---------|
|**Non activé, mais l’utilisateur peut remplacer**     | Les sous-titres en direct ne sont pas activés automatiquement pour l’utilisateur pendant une réunion. L’utilisateur voit l’option **Activer les sous-titres en direct** dans le menu débordement (**...**) pour les activer. Il s’agit du paramètre par défaut. |
|**Non activé**     | Les légendes dynamiques sont désactivées pour l’utilisateur pendant une réunion. L’utilisateur n’a pas la possibilité de les activer.          |

<a name="bkcontentsharing"> </a>

## <a name="chat-in-meetings"></a>Conversation dans les réunions

Il s’agit d’une stratégie par utilisateur et par organisateur. Ce paramètre détermine si la conversation de réunion est autorisée pendant la réunion de l’utilisateur. Ce paramètre ne s’applique pas aux réunions de canal.

|Valeur du paramètre |Comportement  |
|---------|---------|
|**Activer pour tout le monde**     | Tous les participants peuvent écrire et afficher des messages de conversation. |
|**Désactivez-le pour tout le monde**     | La conversation de réunion est désactivée pour tous les participants.  |
|**Activez-le pour tout le monde, sauf les utilisateurs anonymes**     | L’accès en écriture de conversation de réunion est désactivé uniquement pour les participants anonymes.  |

Une fois que cette **stratégie de conversation dans les réunions** est appliquée aux utilisateurs, un organisateur ne peut pas remplacer cette stratégie par le biais des **options de réunion**.

La stratégie appliquée à l’organisateur de la réunion peut affecter d’autres utilisateurs de la réunion. Par exemple :

- Si l’organisateur a défini **chat dans les réunions** pour **l’activer pour tout le monde** ou **l’activer pour tout le monde, mais les utilisateurs anonymes**, la stratégie individuelle d’un utilisateur s’applique et tous les utilisateurs avec **désactiver pour tout le monde** ne sera pas en mesure de discuter dans la réunion.
- Si l’organisateur a défini **chat dans les réunions** pour **la désactiver pour tout le monde**, la stratégie de l’organisateur s’applique et personne ne sera en mesure de discuter dans la réunion.

<a name="bkparticipantsandguests"> </a>

## <a name="qa-in-meetings"></a>Q&A dans les réunions

Il s’agit d’une stratégie par organisateur. Ce paramètre permet aux administrateurs client Microsoft 365 d’activer ou de désactiver l’expérience Questions & Réponses (Q&A).

Le paramètre est appliqué lorsqu’une réunion est créée ou mise à jour par les organisateurs. Par défaut, ce paramètre est désactivé. En savoir plus sur Q&R [ici](/manage-qna-for-meetings).

Le paramètre QnAEngagementMode contrôle cette stratégie dans PowerShell. Q&A peut également être ajusté dans le portail d’administration.

|Valeur du paramètre |Comportement  |
|---------|---------|
|**Activé**     | Les organisateurs peuvent ajouter Q&A lors de la création de réunions. |
|**Désactivé**     | Les organisateurs n’ont pas la possibilité d’ajouter Q&A lors de la création de réunions.  |

## <a name="enable-meeting-policy-settings"></a>Activer les paramètres de stratégie de réunion

Pour activer les paramètres de stratégie de réunion, vous pouvez utiliser le [Centre d’administration Teams](https://admin.teams.microsoft.com/policies/meetings) (Stratégies de **réunion** > **Modifiez une** > **stratégie Participants & invités**) ou l’applet de commande [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) dans Teams PowerShell. 

Dans cet exemple, nous utilisons PowerShell pour modifier la stratégie de réunion globale afin de permettre à quiconque de commencer ou de participer à une réunion.

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AutoAdmittedUsers "Everyone" -AllowAnonymousUsersToStartMeeting $True -AllowPSTNUsersToBypassLobby $True
```

Une fois que vous avez configuré une stratégie, vous devez l’appliquer aux utilisateurs. Si vous avez modifié la stratégie globale (par défaut à l’échelle de l’organisation), elle s’applique automatiquement aux utilisateurs. Vous devez attendre au moins 4 heures pour que les modifications de stratégie prennent effet, mais cela peut prendre jusqu’à 24 heures.


## <a name="related-topics"></a>Sujets associés

- [Présentation de Teams PowerShell](teams-powershell-overview.md)
- [Attribuer des stratégies à vos utilisateurs](policy-assignment-overview.md)
- [Supprimer la stratégie de réunion Teams RestrictedAnonymousAccess des utilisateurs](meeting-policies-restricted-anonymous-access.md)
