---
title: Gérer les stratégies de messagerie dans Teams
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
ms.openlocfilehash: 20c1354f168b5476733c95b49d3344364b8a6008
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231782"
---
# <a name="manage-messaging-policies-in-teams"></a>Gérer les stratégies de messagerie dans Teams

<!--- Add zone marker here--->

Les stratégies de messagerie sont utilisés pour contrôler les conversation et le canal des fonctionnalités de messagerie sont disponibles pour les utilisateurs de Microsoft Teams. Vous pouvez utiliser la stratégie par défaut qui est créée automatiquement ou en créer une ou plusieurs stratégies de messagerie personnalisés des personnes de votre organisation. Après avoir créé une stratégie, vous pouvez l’affecter à un utilisateur ou un groupe d’utilisateurs dans votre organisation.

Par défaut, une stratégie nommée Global (valeur par défaut à l’échelle de l’organisation) est créée. Tous les utilisateurs de votre organisation recevront cette stratégie de messagerie par défaut. Apporter des modifications à cette stratégie ou créer un ou plusieurs des stratégies personnalisées et leur affecter des utilisateurs. Lorsque vous créez une stratégie personnalisée, autoriser ou empêcher certaines fonctionnalités disponibles pour vos utilisateurs et puis l’affecter à un ou plusieurs utilisateurs qui auront besoin les paramètres qui leur sont appliquées. 

## <a name="change-or-create-a-messaging-policy"></a>Modifier ou créer une stratégie de messagerie

Vous pouvez facilement gérer les stratégies de messagerie dans le centre d’administration Microsoft Teams (http://admin.teams.microsoft.com) en connexion avec les informations d’identification d’administrateur et **stratégies de messagerie** dans le volet de navigation de gauche. Pour modifier la stratégie de votre organisation de messagerie par défaut existant, sélectionnez la ligne **Global (à l’échelle de l’organisation par défaut)** , puis apportez vos modifications. Pour créer une nouvelle stratégie de messagerie personnalisée, sélectionnez **nouvelle stratégie**, nommez la nouvelle stratégie, puis sélectionnez vos paramètres. Lorsque vous avez terminé, cliquez sur **Enregistrer** .

Par exemple, que vous voulez vous assurer qui a envoyé les messages ne sont pas supprimés, ou a été modifiés. Vous créez une nouvelle stratégie personnalisée nommée « Conserver les messages envoyé » et désactiver les paramètres suivants :

- Les propriétaires peuvent supprimer des messages envoyés
- Les utilisateurs peuvent supprimer des messages envoyés
- Les utilisateurs peuvent modifier les messages envoyés

Ensuite, attribuez la stratégie aux utilisateurs.

> [!NOTE] 
> Un utilisateur peut uniquement être affecté une stratégie de messagerie à la fois.
 
## <a name="assign-a-messaging-policy-to-a-user"></a>Affecter une stratégie de messagerie à un utilisateur

Si vous créez une stratégie de messagerie personnalisée, il ne sera active pour un utilisateur si la stratégie est affectée à l’utilisateur. Pour affecter une stratégie personnalisée à un utilisateur, accédez au centre d’administration Microsoft Teams, choisissez **utilisateurs** dans le volet de navigation de gauche, puis sélectionnez l’utilisateur que vous voulez attribuer la stratégie. Sur la page de l’utilisateur, cliquez sur **Modifier** en regard de **stratégies attribuées**. Ensuite, dans le volet **Modifier les stratégies d’utilisateur** , sous **stratégie de messagerie**, sélectionnez la stratégie de messagerie dans la liste déroulante et sélectionnez **Enregistrer**. Vous pouvez également modifier les paramètres de la liste des utilisateurs. Pour ce faire, sélectionnez l’utilisateur en cliquant à gauche du nom complet de l’utilisateur. Sélectionnez **Modifier les paramètres**. Puis, dans le volet **Modifier les paramètres** , sous **stratégie de messagerie**, sélectionnez la stratégie dans la liste déroulante, puis sélectionnez **Enregistrer**.

Si vous appliquez une stratégie à plusieurs utilisateurs, sélectionnez chacune des utilisateurs en cliquant sur à gauche du nom d’utilisateur, puis sélectionnez **Modifier les paramètres**. Dans le volet **Modifier les paramètres** , sous **stratégie de messagerie**, sélectionnez la stratégie dans la liste déroulante, puis sélectionnez **Enregistrer**.

Vous pouvez également assigner une stratégie de messagerie comme suit pour un ou plusieurs utilisateurs :

1. Accédez au **Centre d’administration de Microsoft équipes** > **stratégies de messagerie**.
2. Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie.
3. Sélectionnez **Gérer les utilisateurs**.
4. Dans le volet **Gérer les utilisateurs** , recherchez l’utilisateur par nom complet ou par un nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
5. Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.

> [!NOTE]
> Impossible de supprimer une stratégie si les utilisateurs sont qui lui est affectés. Vous devez d’abord attribuer une stratégie différente à tous les utilisateurs concernés, et vous pouvez supprimer la stratégie d’origine.

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>Paramètres de stratégie de messagerie

Pour modifier la stratégie globale de messagerie ou de créer une nouvelle stratégie personnalisée, utilisez les paramètres suivants :

- **Les propriétaires peuvent supprimer des messages envoyés**  Utilisez ce paramètre pour permettre aux propriétaires de supprimer des messages que les utilisateurs envoyés dans la conversation.
- **Les utilisateurs peuvent supprimer des messages envoyés** Utilisez ce paramètre pour permettre aux utilisateurs de supprimer des messages qui leur a envoyé dans la conversation.
- **Les utilisateurs peuvent modifier les messages envoyés** Utilisez ce paramètre pour permettre aux utilisateurs de modifier les messages qu’ils envoyés dans la conversation.
- **Confirmations de lecture** Utilisez ce paramètre pour spécifier si des confirmations de lecture utilisateur contrôlé, activé pour tout le monde ou désactivé.
<a name="bkchat"> </a>

- **Conversation**  Activez ce paramètre si vous souhaitez que les utilisateurs de votre organisation à être en mesure d’utiliser l’application équipes pour converser avec d’autres personnes.
- **Utiliser Giphys dans des conversations**  Si vous activez ce, les utilisateurs peuvent inclure Giphys dans des conversations avec d’autres personnes. Giphy est une base de données en ligne et moteur de recherche qui permet aux utilisateurs de rechercher et partager des fichiers GIF animés. Chaque Giphy est affecté à une évaluation du contenu.
- **Évaluation du contenu Giphy** 
    - **Aucune restriction** Cela signifie que vos utilisateurs seront en mesure d’insérer n’importe quel Giphy à des conversations, quelle que soit la classification du contenu.
    - **Modéré**  Cela signifie que vos utilisateurs seront en mesure d’insérer Giphys dans les salles de conversation, mais seront limitées moyennement du contenu pour adultes.
    - **Strict**  Cela signifie que vos utilisateurs seront en mesure d’insérer Giphys dans les salles de conversation, mais seront limitées strictement du contenu pour adultes.
- **Utilisez Memes dans des conversations** Si vous activez ce, les utilisateurs peuvent inclure les Memes conversation avec d’autres personnes. 
- **Autocollants d’utilisation dans des conversations** Si vous activez ce, les utilisateurs peuvent inclure des autocollants conversation avec d’autres personnes.
- **Autoriser les URL aperçus** Utilisez ce paramètre pour activer automatique URL aperçu activé ou désactivé dans les messages.
- **Autoriser les utilisateurs à convertir des messages** Activez ce paramètre pour permettre aux utilisateurs de traduire automatiquement des messages d’équipes dans la langue spécifiée par leurs paramètres personnels de langue pour Office 365.
- **Autoriser la lecture immersive pour l’affichage des messages** Désactiver ce paramètre à permettre aux utilisateurs affichage des messages dans Microsoft Reader immersif. Lecteur immersif est un outil de formation qui fournit un expérience pour améliorer la lisibilité du texte de lecture en plein écran.
- **Les utilisateurs peuvent envoyer des notifications de priorité** Si vous activez ce, les utilisateurs peuvent indiquer la priorité du message.
- **Création de message vocal** 
    - **Autorisés dans les salles de conversation et de canaux** Cela signifie que les utilisateurs peuvent laisser des messages vocaux dans les salles de conversation et de canaux.
    - **Autorisé dans conversations uniquement** Cela signifie que les utilisateurs peuvent laisser des messages vocaux dans les salles de conversation, mais pas dans les canaux.
    - **Désactivé** Cela signifie que les utilisateurs ne peuvent pas créer des messages vocaux dans les salles de conversation ou de canaux.  
- **Sur les appareils mobiles, afficher les canaux favoris au-dessus de conversations récentes** Activez ce paramètre pour déplacer des canaux favoris en haut de l’écran de l’appareil mobile afin qu’un utilisateur n’a pas besoin de faire défiler pour rechercher les. 
- **Autoriser un utilisateur de supprimer des utilisateurs d’une conversation de groupe** Activez ce paramètre pour permettre à un utilisateur de supprimer d’autres utilisateurs à partir d’une conversation de groupe. Cette fonctionnalité vous permet de continuer une conversation avec un plus petit groupe de personnes sans perdre l’historique de conversation.

### <a name="related-topics"></a>Voir aussi
[Stratégies de la réunion dans les équipes](meeting-policies-in-teams.md)
