---
title: Gérer les stratégies de messagerie
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.messagingpolicies.overview
- ms.teamsadmincenter.messagingpolicies.settings.chat
description: Découvrez les stratégies de messagerie et comment ils peuvent être utilisés pour contrôler la conversation de messagerie dans les équipes.
ms.openlocfilehash: 69097888038699b8d30084598fcf411fe0f97dc2
ms.sourcegitcommit: f3b41e7abafc84571bd9e8267d41decc0fe78e4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/08/2019
ms.locfileid: "30494100"
---
# <a name="what-are-messaging-policies-in-teams"></a>Que sont les stratégies de messagerie dans Teams ?  

::: zone target="docs"
Les stratégies de messagerie sont utilisés pour contrôler les conversation et le canal des fonctionnalités de messagerie sont disponibles pour les utilisateurs de Microsoft Teams. Vous pouvez utiliser la stratégie par défaut qui est créée ou créer une ou plusieurs stratégies de messagerie personnalisés des personnes de votre organisation. Après avoir créé une stratégie, vous allez l’attribuer un utilisateur ou groupes d’utilisateurs dans votre organisation.

Les stratégies peuvent être facilement gérés dans le centre d’administration Microsoft Teams (http://admin.teams.microsoft.com) en vous connectant avec les informations d’identification d’administrateur et le choix des **Stratégies de messagerie** dans le volet de navigation de gauche. 

![Stratégies de messagerie dans les équipes](media/messaging-policies-image1.png)

Pour modifier la stratégie de messagerie par défaut existante pour votre organisation, cliquez sur la ligne **Global (à l’échelle de l’organisation par défaut)** , puis apportez vos modifications. Pour créer une nouvelle stratégie de messagerie personnalisée, cliquez sur **nouvelle stratégie** et sélectionnez vos paramètres. Lorsque vous avez terminé, cliquez sur **Enregistrer** .

![Paramètres de stratégie de messagerie dans les équipes](media/messaging-policies-image2.png)
::: zone-end  
::: zone target="chromeless"
Pour modifier la stratégie globale de messagerie ou de créer une nouvelle stratégie personnalisée, utilisez les paramètres suivants :

- **Les propriétaires peuvent supprimer des messages envoyés**  Utilisez ce paramètre pour permettre aux propriétaires de supprimer des messages que les utilisateurs envoyés dans la conversation.
- **Les utilisateurs peuvent supprimer des messages envoyés** Utilisez ce paramètre pour permettre aux utilisateurs de supprimer des messages qui leur a envoyé dans la conversation.
- **Les utilisateurs peuvent modifier les messages envoyés** Utilisez ce paramètre pour permettre aux utilisateurs de modifier les messages qu’ils envoyés dans la conversation.
- **Confirmations de lecture** Utilisez ce paramètre pour spécifier si des confirmations de lecture utilisateur contrôlé, activé pour tout le monde ou désactivé.

<a name="bkchat"> </a>

- **Conversation**  Activez ce paramètre si vous souhaitez que les utilisateurs de votre organisation à être en mesure d’utiliser l’application équipes pour converser avec d’autres personnes.
- **Utiliser Giphys dans des conversations**  Si vous activez ce, les utilisateurs peuvent inclure Giphys dans des conversations avec d’autres personnes. Giphy est une base de données en ligne et le moteur de recherche qui permet aux utilisateurs de rechercher et partager les fichiers GIF animés. Chaque Giphy est affecté à une classification de contenu.
- **Évaluation du contenu Giphy** 
    - **Aucune restriction** Cela signifie que vos utilisateurs seront en mesure d’insérer n’importe quel Giphy à des conversations, quelle que soit la classification du contenu.
    - **Modéré**  Cela signifie que vos utilisateurs seront en mesure d’insérer Giphys dans les salles de conversation, mais seront limitées moyennement du contenu pour adultes.
    - **Strict**  Cela signifie que vos utilisateurs seront en mesure d’insérer Giphys dans les salles de conversation, mais seront limitées strictement du contenu pour adultes.
- **Utilisez Memes dans des conversations** Si vous activez ce, les utilisateurs peuvent inclure les Memes conversation avec d’autres personnes. 
- **Autocollants d’utilisation dans des conversations** Si vous activez ce, les utilisateurs peuvent inclure des autocollants conversation avec d’autres personnes.
- **Autoriser les URL aperçus** Utilisez ce paramètre pour activer automatique URL aperçu activé ou désactivé dans les messages.
- **Autoriser les utilisateurs à convertir des messages** Activez ce paramètre pour permettre aux utilisateurs de traduire automatiquement des messages d’équipes dans la langue spécifiée par leurs paramètres personnels de langue pour Office 365. 

[Article complet](messaging-policies-in-teams.md)
::: zone-end

::: zone target="docs"
Si vous avez créé une stratégie de messagerie personnalisée, il ne sera active pour un utilisateur si cette stratégie est affectée à un utilisateur. Pour affecter une stratégie personnalisée à un utilisateur dans le centre d’administration Microsoft Teams, choisissez **utilisateurs** dans le volet de navigation gauche, puis sélectionnez l’utilisateur que vous voulez attribuer la stratégie. Sur la page de l’utilisateur, cliquez sur **Modifier** en regard de **Stratégies attribuées**.
::: zone-end

### <a name="related-topics"></a>Rubriques connexes
[Stratégies de réunion dans Teams](meeting-policies-in-teams.md)



