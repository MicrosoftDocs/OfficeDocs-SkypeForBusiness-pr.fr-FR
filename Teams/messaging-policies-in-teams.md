---
title: Que sont les stratégies de messagerie dans Teams ?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.messagingpolicies.overview
description: Découvrez les stratégies de messagerie et comment ils peuvent être utilisés pour contrôler la conversation de messagerie dans les équipes.
ms.openlocfilehash: 5292d88c148e2bd23242f96a3593d98178b9a923
ms.sourcegitcommit: d400c8f83a2325c4a8bbb963ddad685a346bc4d8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/07/2019
ms.locfileid: "29760582"
---
# <a name="what-are-messaging-policies-in-teams"></a>Que sont les stratégies de messagerie dans Teams ?
::: zone target="docs"
Les stratégies de messagerie sont utilisés pour contrôler les conversation et le canal des fonctionnalités de messagerie sont disponibles pour les utilisateurs de Microsoft Teams. Vous pouvez utiliser la stratégie par défaut qui est créée ou créer une ou plusieurs stratégies de messagerie personnalisés des personnes de votre organisation. Après avoir créé une stratégie, vous allez l’attribuer un utilisateur ou groupes d’utilisateurs dans votre organisation.

Les stratégies peuvent être facilement gérés dans le centre d’administration équipes (http://admin.teams.microsoft.com) en vous connectant avec les informations d’identification d’administrateur et en cliquant sur les **Stratégies de messagerie** dans le volet de navigation gauche. Pour modifier la stratégie par défaut existant pour votre organisation, sélectionnez la ligne **Global (à l’échelle de l’organisation par défaut)** , cliquez sur **Modifier**. Pour créer une nouvelle stratégie de messagerie, cliquez sur **nouvelle stratégie**.

![Stratégies de messagerie dans les équipes](media/messaging-policies.png)
::: zone-end

::: zone target="chromeless"
Les paramètres disponibles pour la stratégie sont décrits ci-dessous : 

- **Les propriétaires peuvent supprimer des messages envoyés**  Utilisez ce paramètre pour permettre aux propriétaires de supprimer des messages que les utilisateurs envoient dans la conversation.
- **Les utilisateurs peuvent supprimer des messages envoyés** Utilisez ce paramètre pour permettre aux utilisateurs de supprimer les messages qu’ils envoient dans la conversation.
- **Les utilisateurs peuvent modifier les messages envoyés** Utilisez ce paramètre pour permettre aux utilisateurs de modifier les messages qu’ils envoient dans la conversation.
- **Confirmations de lecture** Utilisez ce paramètre pour spécifier si des confirmations de lecture utilisateur contrôlé, activé pour tout le monde ou désactivé.
<a name="bkchat"> </a>

- **Conversation**  Activez ce paramètre si vous souhaitez que les utilisateurs de votre organisation à être en mesure d’utiliser l’application équipes pour converser avec d’autres personnes.
- **Utiliser Giphys dans des conversations**  Si vous activez ce, les utilisateurs peuvent inclure Giphys dans des conversations avec d’autres personnes. Giphy est une base de données en ligne et le moteur de recherche qui permet aux utilisateurs de rechercher et partager les fichiers GIF animés. Chaque Giphy est affecté à une classification de contenu.
- **Évaluation du contenu Giphy** 
    - **Aucune restriction** Cela signifie que vos utilisateurs seront en mesure d’insérer tous les Giphys à des conversations, quelle que soit la classification du contenu.
    - **Modéré**  Cela signifie que vos utilisateurs seront en mesure d’insérer Giphys dans les salles de conversation, mais seront limitées moyennement du contenu pour adultes.
    - **Strict**  Cela signifie que vos utilisateurs seront en mesure d’insérer Giphys dans les salles de conversation, mais seront limitées strictement du contenu pour adultes.
- **Utilisez Memes dans des conversations** Si vous activez ce, les utilisateurs peuvent inclure les Memes conversation avec d’autres personnes. 
- **Autocollants d’utilisation dans des conversations** Si vous activez ce, les utilisateurs peuvent inclure des autocollants conversation avec d’autres personnes.
- **Autoriser les URL aperçus** Utilisez ce paramètre pour activer automatique URL aperçu activé ou désactivé dans les messages.
- **Autoriser les utilisateurs à convertir des messages** Activez ce paramètre pour permettre aux utilisateurs de traduire automatiquement des messages d’équipes dans la langue spécifiée par leurs paramètres personnels de langue pour Office 365.
::: zone-end

::: zone target="docs"
Si vous avez créé une stratégie de messagerie personnalisée, il ne sera active pour un utilisateur si cette stratégie est affectée à un utilisateur.  Pour affecter une stratégie personnalisée à un utilisateur dans le centre d’administration d’équipes, cliquez sur **utilisateurs** dans le volet de navigation gauche, sélectionnez l’utilisateur que vous voulez attribuer la stratégie à, puis cliquez sur **Modifier** sous **Stratégies affectées**.


### <a name="related-topics"></a>Rubriques connexes
[Stratégies de réunion dans Teams](meeting-policies-in-teams.md)
::: zone-end