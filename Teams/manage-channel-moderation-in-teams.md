---
title: Configurer et gérer la modération de canal
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.reviewer: jotaing
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez comment configurer des canaux pour la modération dans Microsoft Teams, y compris comment ajouter des membres de l’équipe comme modérateurs de canaux.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: dbfdec9af83bda6c0b14a6371e0694d68e25d1d1
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829558"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a>Configurer et gérer la modération de canal dans Microsoft Teams

Dans Microsoft Teams, les propriétaires d’équipe peuvent activer la modération pour un canal standard afin de contrôler qui peut commencer de nouvelles publications et y répondre.

Les propriétaires d’équipe peuvent également ajouter des membres de l’équipe en tant que modérateurs. Un propriétaire d’équipe peut ne pas avoir au niveau du canal l’expertise en la matière pour prendre en charge au mieux la modération du canal. En permettant à des membres spécifiques d’une équipe de modérer un canal, la responsabilité de la gestion du contenu et du contexte au sein d’un canal est partagée entre les propriétaires d’équipe et les modérateurs des canaux. Par exemple, un propriétaire d’équipe peut ajouter des propriétaires d’entreprise ou de contenu comme modérateurs, ce qui leur permet de contrôler le partage d’informations dans ce canal.

> [!NOTE]
> La modération de canal est disponible pour les canaux standard. Elle n’est pas disponible pour le canal Général ou les canaux privés.

## <a name="what-can-a-channel-moderator-do"></a>Que peut faire un modérateur de canal ?

Les modérateurs de canaux peuvent :

- Commencez de nouvelles publications dans le canal. Lorsque la modération est désactivée pour un canal, seuls les modérateurs peuvent commencer de nouvelles publications dans ce canal.
- Ajoutez et supprimez des membres de l’équipe comme modérateurs d’un canal. Gardez à l’esprit que, par défaut, les propriétaires d’équipe sont des modérateurs de canaux et ne peuvent pas être supprimés.
- Contrôler si les membres de l’équipe peuvent répondre aux messages de canal existants et si les bots et connecteurs peuvent envoyer des messages de canal.

## <a name="scenarios"></a>Scénarios

Voici quelques exemples de la façon dont votre organisation peut utiliser la modération de canal dans Teams.

### <a name="use-a-channel-as-an-announcement-channel"></a>Utiliser un canal comme canal d’annonce

L’équipe marketing utilise un canal spécifique pour partager les annonces et livrables clés du projet. Parfois, les membres d’une équipe publient du contenu sur le canal appartenant le mieux à d’autres canaux. Le propriétaire de l’équipe souhaite limiter le partage d’informations dans le canal aux annonces uniquement afin que les membres de l’équipe utilisent ce canal pour rester au fait de ce qui est important.

Dans ce scénario, le propriétaire de l’équipe ajoute des prospects marketing en tant que modérateurs afin qu’ils peuvent publier des annonces dans le canal et les membres de l’équipe ne peuvent plus répondre aux messages dans ce canal.

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a>Utiliser un canal pour les discussions de classe dans Teams pour l'éducation

Dans Teams pour l'éducation, un enseignant de science souhaite utiliser un canal pour impliquer les étudiants dans des discussions axées sur des sujets de classe spécifiques.

Dans ce scénario, l’enseignant autorise ses assistants d’enseignement à modérer le canal. Les assistants enseignants peuvent ensuite créer des billets pour lancer et conduire des discussions avec les étudiants.

## <a name="manage-channel-moderation"></a>Gérer la modération de canal

Dans Teams, sur le canal, cliquez **sur Autres options...**  >  **Gérer le canal.** À partir de là, vous pouvez activer et désactiver la modération, ajouter des membres de l’équipe comme modérateurs et définir des préférences.

La modération de canal est un paramètre par canal. Il n’existe aucun paramètre de modération au niveau du client. Si vous souhaitez que nous ajoutons un paramètre de modération de canal au niveau du client, demandez-le [sur Teams UserVoice.](https://microsoftteams.uservoice.com/)

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

![préférences pour la gestion-canal-modération-dans les équipes.](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a>Activer ou désactiver la modération pour un canal

Par défaut, la modération est off, ce qui signifie que les paramètres habituels du canal s’appliquent aux propriétaires d’équipe et aux membres d’équipe. Par exemple, vous pouvez limiter les nouvelles publications aux seuls membres de l’équipe ou autoriser tout le monde, y compris les invités, à commencer de nouvelles publications.

Pour activer la modération pour un canal, sous **Modération du** canal, cliquez **sur Activer.** Lorsque la modération de canal est en cours, seuls les modérateurs peuvent commencer de nouvelles publications. 

### <a name="add-or-remove-channel-moderators"></a>Ajouter ou supprimer des modérateurs de canal

Sous **Qui sont les modérateurs ?** Cliquez sur Gérer, puis ajoutez ou supprimez des membres de l’équipe comme modérateurs.  Les propriétaires d’équipe et les modérateurs peuvent ajouter et supprimer d’autres modérateurs.  

### <a name="set-team-member-permissions"></a>Définir les autorisations des membres d’une équipe

Sous **Autorisations des membres de l’équipe,** cochez les cases en regard des activités que vous voulez autoriser.

## <a name="related-topics"></a>Voir aussi

- [Présentation des équipes et des canaux dans Teams](teams-channels-overview.md)
