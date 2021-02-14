---
title: Coexistence avec Microsoft Teams et Skype Entreprise
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Mise à niveau de Skype Entreprise vers Teams - Coexistence
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
# <a name="coexistence-with-teams-and-skype-for-business"></a>Coexistence avec Teams et Skype Entreprise

Cet article résume le comportement qui peut être expérimenté lors de l’exécution des clients Teams et Skype Entreprise dans la même organisation, quel que soit le mode et la méthode de mise à niveau utilisée :

- [Réunions](#meetings)
- [Interopérabilité](#interoperability)
- [Conversations Teams- Interop et threads natifs](#teams-conversations---interop-versus-native-threads)
- [Présence](#presence)
- [Fédération](#federation)
- [Contacts](#contacts)



## <a name="meetings"></a>Réunions

Quel que soit leur mode, les utilisateurs peuvent toujours participer à n’importe quel type de réunion à qui ils sont invités, qu’il s’agit de Skype Entreprise ou Teams.  Toutefois, les utilisateurs doivent participer à la réunion avec un client correspondant au type de réunion :

- S’il s’agit d’une réunion Teams, tous les participants (qu’il s’agit de TeamsOnly, d’îles ou de Skype Entreprise) utilisent le client Teams pour participer à la réunion. Si Teams n’est pas installé, l’utilisateur est dirigé vers le web lors de sa tentative de rejoindre une réunion.

- S’il s’agit d’une réunion Skype Entreprise, tous les participants (qu’il s’agit de TeamsOnly, d’îles ou de Skype Entreprise) utilisent le client Skype Entreprise pour participer à la réunion. Si le client Skype Entreprise n’est pas installé, l’utilisateur sera dirigé vers le Web pour y participer via l’application de réunion Skype.

Lors de l’organisation de réunions, le type de réunion qui est programmé est basé sur le mode de l’organisateur, comme indiqué dans le tableau suivant :

| Mode d’organisateur    |      Comportement |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings |    Toutes les réunions prévues dans Teams. Le module logiciel skype entreprise n’est pas disponible dans Outlook. | 
| SfbWithTeamsCollab, SfbOnly   | Toutes les réunions prévues dans Skype Entreprise. Le add-in Teams n’est pas disponible dans Outlook. | 
| Île | Par défaut, les réunions peuvent être programmées dans Skype Entreprise ou Teams. Les deux modules sont disponibles dans Outlook. Toutefois, vous pouvez demander aux utilisateurs d’îles de toujours planifier des réunions dans Teams en leur attribuant une instance de TeamsMeetingPolicy avec PreferredMeetingProviderForIslandsMode=Teams.| 


## <a name="interoperability"></a>Interopérabilité

Teams prend en charge l’interopérabilité (« interop ») avec Skype Entreprise dans certains scénarios. La communication Interop fait référence à une conversation ou un appel entre un utilisateur Skype Entreprise et un utilisateur de Teams.  La communication Interop n’est possible que entre deux utilisateurs. Les discussions/appels à plusieurs ou l’ajout d’utilisateurs supplémentaires ne sont pas pris en charge.

Une conversation ou un appel interop est créé entre deux utilisateurs lorsque chacun des états suivants est vrai :

- Un utilisateur utilise Teams et l’autre utilise Skype Entreprise.

- Le mode du destinataire de la communication initiale n’est PAS (sinon, la communication se place dans le même client) si les deux utilisateurs font partie de la même organisation. Dans les scénarios fédérés, l’utilisateur d’envoi utilise Teams et le destinataire n’est pas en mode TeamsOnly. 

- L’utilisateur de Teams n’a PAS non plus de compte Skype Entreprise homed sur site. 

Dans la communication interop, la conversation est uniquement en texte intégral. De plus, le partage de fichiers et le partage d’écran ne sont pas possibles *dans la conversation interop elle-même.* Toutefois, les utilisateurs d’une conversation interop peuvent facilement obtenir un partage de fichier et/ou d’écran en créant une réunion à la demande, au sein de la conversation interop, comme décrit ci-dessous :

- Si l’utilisateur de Teams tente de partager son écran, une réunion Teams à la demande est automatiquement créée et un lien d’invitation vers cette réunion est envoyé au client de l’utilisateur Skype Entreprise. Lorsque vous cliquez sur le lien, l’utilisateur de Skype Entreprise ouvre Teams et rejoint la réunion. Les deux utilisateurs sont maintenant dans une réunion Teams et peuvent partager le cas nécessaire.

- Si l’utilisateur de Skype Entreprise utilise un client depuis 2018 ou une date ultérieure et tente de partager du contenu, une réunion Skype Entreprise à la demande est créée automatiquement et un lien d’invitation à cette réunion est envoyé au client de l’utilisateur de Teams. Lorsque vous cliquez sur le lien, l’utilisateur de Teams tente de participer à la réunion Skype Entreprise. Si le client Skype Entreprise est installé sur l’utilisateur Teams, celui-ci s’ouvre et l’utilisateur est invité à se connecter (s’il n’est pas encore connecté).  Si le client Skype Entreprise n’est pas installé pour l’utilisateur Teams, celui-ci est invité à utiliser la version web. Une fois les deux utilisateurs inscrits, ils sont en réunion Skype Entreprise et peuvent les partager au besoin.

## <a name="teams-conversations---interop-versus-native-threads"></a>Conversations Teams - Interop et threads natifs

Étant donné que les communications interop n’offrent pas toutes les fonctionnalités des conversations Teams natives, le client Teams propose des threads de conversation distincts pour les communications Teams-to-Teams et teams-to-Skype Entreprise. Ces conversations sont rendues différemment dans l’interface utilisateur : Les threads Interop peuvent être différenciés d’un thread Teams natif normal par :

- Absence de contrôles pour le texte enrichi, le partage de fichiers/écran, l’impossibilité d’ajouter des utilisateurs.
- Modification de l’icône de l’utilisateur cible affichant un « S » pour Skype Entreprise.

Ces différences sont affichées dans les captures d’écran suivantes :

Conversation Teams-to-Teams native avec Test Utilisateur G3

![Diagramme montrant une conversation Teams-to-Teams native](media/teams-upgrade-native-thread.png)

Conversation interop avec le même test Utilisateur G3

![Diagramme montrant une conversation Interop Teams-to-Teams](media/teams-upgrade-interop-thread.png)

Une fois qu’un fil de conversation est créé, son type ne change jamais. Une fois créée, un thread interop dans Teams routera toujours vers le client Skype Entreprise de l’utilisateur cible. Un fil de discussion natif routera toujours vers le client Teams de l’utilisateur cible.  Si le mode d’un utilisateur du destinataire change, les threads Teams existants à cet utilisateur ne fonctionnent plus et une note s’affiche dans cette conversation avec un lien pour démarrer une nouvelle conversation native, comme illustré dans la capture d’écran suivante.


![Diagramme montrant une conversation avec l’utilisateur Skype Entreprise mis à niveau](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

## <a name="presence"></a>Présence

La présence d’un utilisateur donné est basée sur l’activité de l’utilisateur dans le service via le client. La présence est ensuite publiée pour les autres utilisateurs.  Skype Entreprise et Teams sont des services distincts avec des clients distincts, de sorte que chaque service a son propre état de présence pour un utilisateur.   Il existe également une synchronisation entre les services de présence dans Teams et dans Skype Entreprise Online.  Cela permet à un service de publier éventuellement la présence de l’utilisateur à partir de l’autre service si nécessaire. 

Le comportement de publication de présence est basé sur le mode de l’utilisateur. Il existe trois cas de base :

- Si un utilisateur est en mode TeamsOnly, tous les autres utilisateurs voient la présence Teams pour cet utilisateur, quel que soit le client qu’ils utilisent.

- Si un utilisateur est dans l’un des modes Skype Entreprise, tous les autres utilisateurs voient la présence de Skype Entreprise pour cet utilisateur, quel que soit le client qu’il utilise.

- Si un utilisateur est en mode Îles, la présence publiée dans Skype Entreprise et Teams est indépendante, de sorte que la présence affichée aux utilisateurs au sein de la même organisation dépend du client de l’autre utilisateur. Les utilisateurs d’organisations fédérées peuvent voir s’ils sont présents en fonction de leur activité Skype Entreprise, car le trafic fédéré vers un utilisateur du mode Îles arrive dans Skype Entreprise.

Par exemple, supposons que l’utilisateur A se trouve en mode Îles. Si l’utilisateur A est actif dans Teams, mais n’est pas connecté à Skype Entreprise, d’autres utilisateurs voient l’utilisateur A comme actif à partir de leur client Teams, mais dans leur client Skype Entreprise, ils voient l’utilisateur A comme hors connexion. Cela est tout à fait possible, car l’utilisateur A ne peut pas être joint s’il n’exécute pas le client. 


## <a name="federation"></a>Fédération

La fédération de Teams vers un autre utilisateur utilisant Skype Entreprise nécessite que l’utilisateur de Teams soit homed online dans Skype Entreprise. TeamsUpgradePolicy régit le routage des conversations et appels fédérés entrants. Le comportement de routage fédéré est le même que pour les scénarios au même client, sauf en mode Îles. Lorsque les destinataires sont en mode Îles :

- Les conversations et appels initiés à partir de Teams sont lancés dans Skype Entreprise si le destinataire se trouve dans un client fédéré.
- Les conversations et appels initiés depuis Teams sont lancés dans Teams si le destinataire se trouve dans le même client.
- Les conversations et appels lancés par Skype Entreprise sont toujours lancés dans Skype Entreprise.

Une conversation fédérée peut être un thread natif ou un thread interop. Consultez [Conversations Teams ---interop-versus-native-threads.](#teams-conversations---interop-versus-native-threads)

- Si le récepteur et l’expéditeur sont tous deux en mode de mise à niveau TeamsOnly, la conversation sera une expérience de conversation native qui inclut toutes les fonctionnalités de messagerie et d’appel enrichies. Pour en savoir plus, lisez l’expérience de conversation native pour [les utilisateurs externes (fédérés) dans Teams.](native-chat-for-external-users.md) 

- Si l’un des participants à la conversation n’est PAS en mode de mise à niveau TeamsOnly, la conversation reste une expérience d’échange avec les messages texte uniquement. L’interface utilisateur expose les conversations fédérées de la même manière que les threads interop de même client, sauf qu’une note indique que l’utilisateur est externe.

Pour plus d’informations, voir Gérer l’accès externe dans [Microsoft Teams](manage-external-access.md) et l’expérience de conversation native pour les utilisateurs [externes (fédérés) dans Teams.](native-chat-for-external-users.md)

## <a name="contacts"></a>Contacts

Teams et Skype Entreprise ont des listes de contacts distinctes. Cela signifie que les ajouts, la suppression et les modifications apportées aux contacts dans un système ne sont pas synchronisés avec l’autre système. Toutefois, les contacts de Skype Entreprise sont automatiquement copiés dans Teams lorsque l’un des deux événements spécifiques se produit : 

- Pour les utilisateurs Skype Entreprise Online, lors de leur première connexion à Teams, les contacts de Skype Entreprise sont copiés dans Teams.  Ce comportement n’est pas disponible pour les utilisateurs avec un compte local dans Skype Entreprise Server.  

- Après la mise à niveau d’un utilisateur vers TeamsOnly (via l’affectation de TeamsUpgradePolicy ou via Move-CsUser -MoveToTeams), la prochaine fois qu’un utilisateur se connecte à Teams, les contacts existants dans Skype Entreprise seront fusionnés avec les contacts existants déjà dans Teams. Ce comportement se produit si le compte Skype Entreprise de l’utilisateur est domicile sur site ou en ligne. 

Dans les deux cas, le transfert de contacts de Skype Entreprise vers Teams est asynchrone, de sorte que quelques minutes peuvent être avant que les contacts n’apparaissent dans Teams. Les deux événements ci-dessus déclenchent la copie.  

## <a name="related-links"></a>Liens connexes

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md) 

[Configurer la connectivité hybride entre Skype Entreprise Server et Microsoft 365 ou Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Déplacer des utilisateurs entre l’environnement local et le cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Utilisation du service Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

