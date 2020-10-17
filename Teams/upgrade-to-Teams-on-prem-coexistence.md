---
title: Coexistence avec Microsoft teams et Skype entreprise
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Mise à niveau de Skype entreprise vers équipes-coexistence
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0690af8226f3f992dcc12f68c6135c953eb043f5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533611"
---
# <a name="coexistence-with-teams-and-skype-for-business"></a>Coexistence avec teams et Skype entreprise

Cet article présente un résumé du comportement susceptible d’être rencontré lors de l’exécution d’équipes et de clients Skype entreprise au sein d’une même organisation, indépendamment du mode et de la méthode de mise à niveau utilisée :

- [Réunions](#meetings)
- [Interopérabilité](#interoperability)
- [Conversations teams-interopérabilité et threads natifs](#teams-conversations---interop-versus-native-threads)
- [Présence](#presence)
- [Fédération](#federation)
- [Contacts](#contacts)



## <a name="meetings"></a>Réunions

Quels que soient leur mode, les utilisateurs peuvent toujours participer à n’importe quel type de réunion auxquelles ils sont invités, qu’il s’agisse de Skype entreprise ou d’équipes.  Toutefois, les utilisateurs doivent rejoindre la réunion avec un client correspondant qui correspond au type de la réunion :

- S’il s’agit d’une réunion en équipe, tous les participants (qu’il s’agisse de TeamsOnly, d’îlots ou d’utilisateurs Skype entreprise) utilisent le client teams pour rejoindre la réunion. Si teams n’est pas installé, l’utilisateur sera dirigé vers le Web lors d’une tentative de participation à une réunion.

- S’il s’agit d’une réunion Skype entreprise, tous les participants (qu’il s’agisse d’TeamsOnly, d’îlots ou d’utilisateurs Skype entreprise) utilisent le client Skype entreprise pour rejoindre la réunion. Si le client Skype entreprise n’est pas installé, l’utilisateur est dirigé vers le Web pour s’y joindre par le biais de l’application de réunion Skype.

Lors de l’organisation de réunions, le type de réunion qui est planifié est basé sur le mode de l’organisateur, comme indiqué dans le tableau suivant :

| Mode de l’organisateur    |      Comportement |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings |    Toutes les réunions planifiées dans Teams. Le complément Skype entreprise n’est pas disponible dans Outlook. | 
| SfbWithTeamsCollab, SfbOnly   | Toutes les réunions planifiées dans Skype entreprise. Le complément teams n’est pas disponible dans Outlook. | 
| Île | Par défaut, il est possible de planifier des réunions dans Skype entreprise ou Teams. Les deux compléments sont disponibles dans Outlook. Toutefois, vous pouvez éventuellement exiger que les utilisateurs dans les îlots planifient toujours des réunions en équipe en leur attribuant une instance de TeamsMeetingPolicy avec PreferredMeetingProviderForIslandsMode = Teams.| 


## <a name="interoperability"></a>Interopérabilité

Teams prend en charge l’interopérabilité (« interopérabilité ») avec Skype entreprise dans certains cas. La communication d’interopérabilité fait référence à une discussion ou un appel entre un utilisateur de Skype entreprise et un utilisateur de teams.  La communication interopérabilité est possible uniquement entre deux utilisateurs. la discussion ou l’ajout d’utilisateurs supplémentaires n’est pas pris en charge.

Une discussion ou un appel d’interopérabilité entre deux utilisateurs est créé lorsque les conditions suivantes sont remplies :

- Un utilisateur travaille en équipe et l’autre utilise Skype entreprise.

- Le mode du destinataire de la communication initiale n’est pas un îlot (sinon la communication ne serait pas disponible sur le même client) si les deux utilisateurs appartiennent à la même organisation. Dans les scénarios fédérés, l’utilisateur expéditeur utilise équipes, et le destinataire n’est pas en mode TeamsOnly. 

- L’utilisateur d’équipes n’a pas de compte Skype entreprise local hébergé sur site. 

Dans le cadre de la communication d’interopérabilité, les discussions sont en texte brut uniquement. Par ailleurs, le partage de fichiers et le partage d’écran ne sont pas possibles *dans la discussion d’interopérabilité*. Toutefois, les utilisateurs d’une conversation d’interopérabilité peuvent facilement atteindre le partage de fichiers et/ou d’écran en créant une réunion à la demande à partir de la discussion d’interopérabilité, comme décrit ci-dessous :

- Si l’utilisateur teams tente de partager son écran, une réunion teams à la demande est créée automatiquement et un lien d’invitation à cette réunion est envoyé au client de l’utilisateur Skype entreprise. Lorsque vous cliquez sur le lien, l’utilisateur de Skype entreprise ouvre teams et joint la réunion. Les deux utilisateurs travaillent désormais à une réunion teams et peuvent partager selon les besoins.

- Si l’utilisateur Skype entreprise utilise un client à partir de 2018 ou une version ultérieure et tente de partager du contenu, une réunion Skype entreprise à la demande est créée automatiquement et un lien d’invitation à cette réunion est envoyé au client de l’utilisateur Teams. Lorsque vous cliquez sur le lien, l’utilisateur teams tente de participer à la réunion Skype entreprise. Si l’utilisateur de teams a installé le client Skype entreprise, il s’ouvre et l’utilisateur est invité à se connecter (s’il n’y a pas encore de connexion).  Si le client Skype entreprise n’est pas installé sur l’utilisateur Teams, l’utilisateur est invité à utiliser la version Web. Lorsque les deux utilisateurs sont connectés, ils sont dans une réunion Skype entreprise et peuvent partager selon les besoins.

## <a name="teams-conversations---interop-versus-native-threads"></a>Conversations teams-interopérabilité et threads natifs

Étant donné que les communications d’interopérabilité ne prennent pas en charge toutes les fonctionnalités de conversation d’équipe native, le client teams gère des threads de conversation distinctes pour la communication équipes-à-équipes et équipes-Skype entreprise. Ces conversations sont rendues différemment dans l’interface utilisateur : les threads d’interopérabilité peuvent être différenciés d’un thread d’équipe natif ordinaire, en procédant comme suit :

- Absence de contrôles pour la mise en forme de texte enrichi, de partage de fichiers ou d’écrans, incapacité à ajouter des utilisateurs.
- Modification de l’icône de l’utilisateur cible, avec le « S » pour Skype entreprise.

Ces différences apparaissent dans les captures d’écran suivantes :

Conversation d’équipes en équipes native avec test de l’utilisateur G3

![Diagramme illustrant une conversation d’équipes en équipes Native](media/teams-upgrade-native-thread.png)

Conversation d’interopérabilité avec le même test de l’utilisateur G3

![Diagramme illustrant une conversation d’équipe à teams](media/teams-upgrade-interop-thread.png)

Une fois qu’un fil de discussion est créé, son type n’est jamais modifié. Une fois créé, un thread d’interopérabilité dans teams sera toujours acheminé vers le client Skype entreprise de l’utilisateur cible. Un thread natif sera toujours acheminé vers le client teams de l’utilisateur cible.  Si le mode de l’utilisateur d’un destinataire change, il est possible que les threads teams existants vers cet utilisateur ne fonctionnent plus et qu’une remarque s’affiche dans la conversation avec un lien pour démarrer une nouvelle conversation native, comme illustré dans la capture d’écran suivante.


![Diagramme montrant une discussion avec un utilisateur de Skype entreprise mis à niveau](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

## <a name="presence"></a>Présence

La présence d’un utilisateur donné est basée sur l’activité de l’utilisateur dans le service via le client. La présence est alors publiée pour que d’autres utilisateurs puissent la voir.  Skype entreprise et équipes étant des services distincts avec des clients distincts, chaque service dispose de son propre état de présence pour un utilisateur.   Il existe également une synchronisation entre les services de présence dans équipes et dans Skype entreprise online.  Cela permet à un service de publier la présence de l’utilisateur à partir de l’autre service, si nécessaire. 

Le comportement de publication de présence repose sur le mode de l’utilisateur. Il existe trois cas de base :

- Si un utilisateur est en mode TeamsOnly, tous les autres utilisateurs voient la présence d’équipes pour cet utilisateur, quel que soit le client utilisé.

- Si un utilisateur se trouve dans l’un des modes Skype entreprise, tous les autres utilisateurs voient la présence Skype entreprise pour cet utilisateur, quel que soit le client utilisé.

- Si un utilisateur est en mode d’îlot, le statut de présence publié dans Skype entreprise et équipes est indépendant, de sorte que les présences des utilisateurs au sein de la même organisation varient selon le client de l’autre utilisateur. Les utilisateurs des organisations fédérées verront la présence de cet utilisateur en fonction de son activité Skype entreprise, car le trafic fédéré vers le mode d’utilisation des classeurs dans Skype entreprise.

Par exemple, supposons que l’utilisateur A est en mode îlot. Si l’utilisateur A est actif dans Teams, mais n’est pas connecté à Skype entreprise, les autres utilisateurs verront que l’utilisateur A est actif à partir du client de leur équipe, mais dans leur client Skype entreprise, ils verront l’utilisateur A déconnectée. C’est par conception, car l’utilisateur A ne peut pas être contacté s’il n’exécute pas le client. 


## <a name="federation"></a>Fédération

La Fédération entre teams et un autre utilisateur de Skype entreprise nécessite que l’utilisateur de teams soit à domicile en ligne dans Skype entreprise. TeamsUpgradePolicy gère le routage des conversations et appels fédérés entrants. Le comportement de routage fédéré est le même que pour les mêmes scénarios de client, sauf dans le mode îlot. Lorsque les destinataires sont en mode îlot :

- Discussions et appels passés à partir de teams dans Skype entreprise si le destinataire est dans un client fédéré.
- Les conversations et les appels passés à partir de teams dans teams si le destinataire est dans le même client.
- Les conversations et les appels passés à partir de Skype entreprise sont toujours terrains dans Skype entreprise.

Une discussion fédérée peut être un thread natif ou un thread d’interopérabilité. Voir [les conversations d’équipe---interopérabilité par rapport aux threads natifs](#teams-conversations---interop-versus-native-threads).

- S’il s’agit du destinataire et de l’expéditeur dans le mode de mise à niveau de TeamsOnly, la conversation sera une expérience de chat native qui inclut l’ensemble des fonctionnalités d’appel et de messagerie complètes. Pour en savoir plus, consultez [l’interface de conversation native pour les utilisateurs externes dans teams](native-chat-for-external-users.md). 

- Si l’un des participants à la conversation n’est pas en mode de mise à niveau TeamsOnly, la conversation reste une interface d’interopérabilité avec les messages texte uniquement. Dans l’interface utilisateur, les discussions fédérées sont similaires aux threads d’interopérabilité des locataires, sauf qu’il existe une remarque indiquant que l’utilisateur est externe.

Pour plus d’informations, reportez-vous à [gérer l’accès externe dans Microsoft teams](manage-external-access.md) et à l' [interface de conversation native pour les utilisateurs externes dans teams](native-chat-for-external-users.md).

## <a name="contacts"></a>Contacts

Les équipes et Skype entreprise disposent de listes de contacts distinctes. Cela signifie que les ajouts de contacts, la suppression et les modifications apportées dans un système ne sont pas synchronisés avec l’autre système. En revanche, lorsque l’un ou l’autre des deux événements suivants se produit, vos contacts Skype entreprise sont automatiquement copiés dans teams : 

- Pour tout utilisateur de Skype entreprise Online, lors de la première connexion à Teams, les contacts de Skype entreprise seront copiés dans Teams.  Ce comportement n’est pas disponible pour les utilisateurs disposant d’un compte local dans Skype entreprise Server.  

- Une fois qu’un utilisateur a procédé à la mise à niveau vers TeamsOnly (en attribuant TeamsUpgradePolicy ou par le biais de Move-CsUser-MoveToTeams), la prochaine fois qu’un utilisateur se connecte à Teams, les contacts existants dans Skype entreprise sont fusionnés avec les contacts existants déjà dans Teams. Ce comportement se produit si le compte Skype entreprise de l’utilisateur est hébergé sur site ou en ligne. 

Dans les deux cas, le transfert de contacts de Skype entreprise à teams est asynchrone et peut donc être de quelques minutes avant l’affichage des contacts dans Teams. Les deux événements ci-dessus sont le déclencheur de la copie.  

## <a name="related-links"></a>Liens connexes

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md) 

[Configurer une connectivité hybride entre Skype entreprise Server et Microsoft 365 ou Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Déplacer des utilisateurs entre l’environnement local et le cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Utiliser le service de migration de réunion (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

