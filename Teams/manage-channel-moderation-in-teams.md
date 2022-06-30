---
title: Configurer et gérer la modération des canaux
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Découvrez comment configurer des canaux pour la modération dans Microsoft Teams, notamment comment ajouter des membres d’équipe en tant que modérateurs de canal.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 52fb88d6371c033713c5b14d96ecf2a9211420b0
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562363"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a>Configurer et gérer la modération des canaux dans Microsoft Teams

Dans Microsoft Teams, les propriétaires d’équipe peuvent activer la modération pour un canal standard afin de contrôler qui peut démarrer de nouvelles publications et répondre aux publications de ce canal.

Les propriétaires d’équipe peuvent également ajouter des membres d’équipe en tant que modérateurs. Un propriétaire d’équipe n’a peut-être pas l’expertise en la matière au niveau du canal pour mieux prendre en charge la modération des canaux. En permettant à des membres d’équipe spécifiques de modérer un canal, la responsabilité de la gestion du contenu et du contexte au sein d’un canal est partagée entre les propriétaires d’équipe et les modérateurs de canal. Par exemple, un propriétaire d’équipe peut ajouter des propriétaires d’entreprise ou des propriétaires de contenu en tant que modérateurs, ce qui leur permet de contrôler le partage d’informations dans ce canal.

> [!NOTE]
> La modération de canal est disponible pour les canaux standard. Il n’est pas disponible pour le canal Général ou pour les canaux privés ou partagés.

## <a name="what-can-a-channel-moderator-do"></a>Que peut faire un modérateur de canal ?

Les modérateurs de canal peuvent :

- Démarrez de nouvelles publications dans le canal. Lorsque la modération est activée pour un canal, seuls les modérateurs peuvent démarrer de nouvelles publications dans ce canal.
- Ajoutez et supprimez des membres d’équipe en tant que modérateurs dans un canal. Gardez à l’esprit que, par défaut, les propriétaires d’équipe sont des modérateurs de canal et ne peuvent pas être supprimés.
- Déterminez si les membres de l’équipe peuvent répondre aux messages de canal existants et si les bots et les connecteurs peuvent envoyer des messages de canal.

## <a name="scenarios"></a>Scénarios

Voici quelques exemples de la façon dont votre organisation peut utiliser la modération de canal dans Teams.

### <a name="use-a-channel-as-an-announcement-channel"></a>Utiliser un canal comme canal d’annonce

L’équipe marketing utilise un canal spécifique pour partager des annonces de projet clés et des livrables. Parfois, les membres de l’équipe publient du contenu sur le canal qui appartient de manière plus appropriée à d’autres canaux. Le propriétaire de l’équipe souhaite limiter le partage d’informations dans le canal aux seules annonces afin que les membres de l’équipe puissent utiliser ce canal pour rester informés de ce qui est important.

Dans ce scénario, le propriétaire de l’équipe ajoute des prospects marketing en tant que modérateurs afin qu’ils puissent publier des annonces dans le canal et désactiver la possibilité pour les membres de l’équipe de répondre aux messages de ce canal.

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a>Utiliser un canal pour les discussions de classe dans Teams pour l'éducation

Dans Teams pour l'éducation, un enseignant de sciences souhaite utiliser un canal pour impliquer les étudiants dans des discussions ciblées sur des sujets spécifiques de classe.

Dans ce scénario, l’enseignant permet à ses assistants d’enseignement de modérer le canal. Les assistants d’enseignement peuvent ensuite créer de nouveaux postes pour lancer et mener des discussions avec les étudiants.

## <a name="manage-channel-moderation"></a>Gérer la modération des canaux

Dans Teams, accédez au canal, cliquez sur **Autres options...** >  **Gérer le canal**. À partir de là, vous pouvez activer et désactiver la modération, ajouter des membres d’équipe en tant que modérateurs et définir des préférences.

La modération de canal est un paramètre par canal. Il n’existe aucun paramètre au niveau du locataire pour la modération de canal. Si vous souhaitez que nous ajoutions un paramètre de modération de canal au niveau du locataire, demandez-le sur le [portail de commentaires Teams](https://feedbackportal.microsoft.com/feedback/forum/ad198462-1c1c-ec11-b6e7-0022481f8472).

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

![préférences pour la gestion de canal-modération dans les équipes.](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a>Activer ou désactiver la modération pour un canal

Par défaut, la modération est désactivée, ce qui signifie que les paramètres de canal habituels s’appliquent aux propriétaires d’équipe et aux membres de l’équipe. Par exemple, vous pouvez limiter les nouvelles publications aux membres de l’équipe uniquement ou autoriser tout le monde, y compris les invités, à démarrer de nouveaux billets.

Pour activer la modération d’un canal, sous **Modération du canal**, cliquez **sur Activé**. Lorsque la modération de canal est activée, seuls les modérateurs peuvent démarrer de nouvelles publications. 

### <a name="add-or-remove-channel-moderators"></a>Ajouter ou supprimer des modérateurs de canal

Sous **Qui sont les modérateurs ?**, cliquez sur **Gérer**, puis ajoutez ou supprimez des membres de l’équipe en tant que modérateurs. Les propriétaires et modérateurs d’équipe peuvent ajouter et supprimer d’autres modérateurs.  

### <a name="set-team-member-permissions"></a>Définir les autorisations des membres de l’équipe

Sous **Autorisations des membres de l’équipe**, activez les cases à cocher en regard des activités que vous souhaitez autoriser.

## <a name="related-topics"></a>Sujets associés

- [Présentation des équipes et des canaux dans Teams](teams-channels-overview.md)
