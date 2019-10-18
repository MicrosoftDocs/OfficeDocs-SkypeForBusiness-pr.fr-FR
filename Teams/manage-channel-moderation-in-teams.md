---
title: Configurer et gérer la modération de canal dans Microsoft teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jotaing
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment configurer des canaux de modération dans Microsoft Teams, y compris comment ajouter des membres à une équipe comme modérateurs de canaux.
ms.openlocfilehash: 52b89f21cd2b622b78f6dbee44d8efe5ce4ce490
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570662"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a>Configurer et gérer la modération de canal dans Microsoft teams

Dans Microsoft Teams, les propriétaires d’équipe peuvent activer le modération d’un canal pour contrôler qui peut démarrer de nouvelles publications et répondre à des publications dans ce canal.

Les propriétaires d’équipe peuvent également ajouter des membres à une équipe comme modérateurs. Il est possible que le propriétaire d’une équipe ne dispose pas de l’expertise du domaine au niveau du canal pour prendre en charge le modérateur du canal. En permettant aux membres d’équipe spécifiques de modérer un canal, la responsabilité de la gestion du contenu et du contexte au sein d’un canal est partagée entre les propriétaires d’équipe et les modérateurs de canaux. Par exemple, un propriétaire d’équipe peut ajouter des propriétaires d’entreprise ou des propriétaires de contenu en tant que modérateurs, ce qui leur permet de contrôler le partage d’information dans ce canal.

## <a name="what-can-a-channel-moderator-do"></a>Que peut faire un modérateur de canal ?

Les modérateurs de canal peuvent :

- Commencez de nouvelles publications dans le canal. Lorsque modération est activée pour un canal, seuls les modérateurs peuvent commencer de nouvelles publications dans ce canal.
- Ajoutez et supprimez des membres d’équipe comme modérateurs d’un canal. Gardez à l’esprit que les propriétaires d’équipe sont les modérateurs de canal et ne peuvent pas être supprimés.
- Déterminez si les membres d’une équipe peuvent répondre à des messages de canal existants et si les robots et connecteurs peuvent envoyer des messages de canal.

## <a name="scenarios"></a>Scénarios

Voici quelques exemples de la manière dont votre organisation peut utiliser le modération des canaux dans Teams.

### <a name="use-a-channel-as-an-announcement-channel"></a>Utiliser un canal comme canal d’annonce

L’équipe marketing utilise un canal spécifique pour partager les annonces principales du projet et les livrables. Parfois, les membres d’équipe publient du contenu sur le canal qui est plus approprié dans d’autres canaux. Le propriétaire de l’équipe veut limiter le partage des informations du canal aux annonces uniquement pour permettre aux membres de l’équipe d’utiliser ce canal pour suivre ce qui est important.

Dans ce scénario, le propriétaire de l’équipe ajoute des leads de marketing comme modérateurs pour qu’ils puissent publier des annonces dans le canal et désactiver la possibilité pour les membres de l’équipe de répondre aux messages dans ce canal.

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a>Utiliser un canal pour les discussions de classe dans teams éducation

Dans teams pour l’éducation, un enseignant souhaite utiliser un canal pour engager des discussions ciblées sur des sujets spécifiques de la classe.

Dans ce scénario, l’enseignant permet aux assistants d’enseignement de modérer le canal. Les assistants d’enseignement peuvent ensuite créer de nouvelles publications pour lancer une discussion avec des étudiants et en créer de nouveaux.

## <a name="manage-channel-moderation"></a>Gérer la modération des canaux

Dans Microsoft Teams, accédez au canal, cliquez sur **autres options.**  >  **Gérer le canal**. Vous pouvez activer et désactiver la modération, ajouter des membres à une équipe comme modérateurs et définir des préférences.

Le modération de canal est un paramètre par canal. Il n’existe aucun paramètre de niveau client pour modération de canal. Si vous souhaitez ajouter un paramètre de modération de canal au niveau du client, demandez-le sur les [équipes UserVoice](https://microsoftteams.uservoice.com/).

![Manage-Channel-Moderation-in-teams-Preferences. png](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a>Activer ou désactiver la modération d’un canal

Par défaut, la modération est désdésactivée, ce qui signifie que les paramètres du canal habituel s’appliquent aux propriétaires d’équipe et aux membres de l’équipe. Par exemple, vous pouvez limiter de nouvelles publications uniquement aux membres de l’équipe ou autoriser tout le monde, y compris les invités, à commencer de nouvelles publications.

Pour activer le modération d’un canal, sous **modération de canal**, cliquez sur **activé**. Lorsque le modération de canal est activé, seuls les modérateurs peuvent commencer de nouvelles publications. 

### <a name="add-or-remove-channel-moderators"></a>Ajouter ou supprimer des modérateurs de canal

Sous **qui est le modérateur ?**, cliquez sur **gérer**, puis ajoutez ou supprimez des membres d’équipe comme modérateurs. Les propriétaires d’équipe et les modérateurs peuvent ajouter et supprimer d’autres modérateurs.  

### <a name="set-team-member-permissions"></a>Définir les autorisations des membres de l’équipe

Sous **autorisations des membres**de l’équipe, activez les cases à cocher en regard des activités que vous voulez autoriser.

## <a name="related-topics"></a>Voir aussi

- [Présentation des équipes et des canaux dans Microsoft Teams](teams-channels-overview.md)
