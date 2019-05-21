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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.messagingpolicies.overview
description: Apprenez-en davantage sur les stratégies de messagerie et leur utilisation pour contrôler la messagerie vocale dans Teams.
ms.openlocfilehash: 74baed2a51f1a03ee29238da1795c67601e30ae0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298057"
---
# <a name="manage-messaging-policies-in-teams"></a>Gérer les stratégies de messagerie dans Teams

<!--- Add zone marker here--->

Les stratégies de messagerie sont utilisées pour contrôler les fonctionnalités de messagerie et de messagerie de canal disponibles pour les utilisateurs de Microsoft Teams. Vous pouvez utiliser la stratégie par défaut qui est créée automatiquement ou créer une ou plusieurs stratégies de messagerie personnalisées pour les membres de votre organisation. Après avoir créé une stratégie, vous pouvez l’affecter à un utilisateur ou à un groupe d’utilisateurs de votre organisation.

Par défaut, la création d’une stratégie nommée global (au niveau de l’organisation par défaut) est créée. Par défaut, tous les utilisateurs de votre organisation reçoivent cette stratégie de messagerie. Vous pouvez modifier cette stratégie ou en créer une ou plusieurs, et leur affecter des utilisateurs. Lorsque vous créez une stratégie personnalisée, vous pouvez autoriser ou empêcher l’accès à certaines fonctionnalités à vos utilisateurs, puis les affecter à un ou plusieurs utilisateurs qui auront besoin des paramètres appliqués. 

## <a name="change-or-create-a-messaging-policy"></a>Modification ou création d’une stratégie de messagerie

Vous pouvez facilement gérer les stratégies de messagerie dans le centre d’administrationhttp://admin.teams.microsoft.com) de Microsoft Teams (en vous connectant avec des informations d’identification d’administrateur et en choisissant **stratégies de messagerie** dans le volet de navigation gauche. Pour modifier la stratégie de messagerie par défaut existante pour votre organisation, sélectionnez la ligne **global (par défaut de l’organisation)** , puis apportez les modifications souhaitées. Pour créer une stratégie de messagerie personnalisée, sélectionnez **nouvelle stratégie**, attribuez un nom à la nouvelle stratégie, puis sélectionnez vos paramètres. Lorsque vous avez fin, cliquez sur **Enregistrer** .

Par exemple, imaginons que vous vouliez vérifier que les messages envoyés ne sont pas supprimés ou modifiés. Vous pouvez créer une stratégie personnalisée nommée «conserver les messages envoyés» et désactiver les paramètres suivants:

- Les propriétaires peuvent supprimer des messages envoyés
- Les utilisateurs peuvent supprimer des messages envoyés
- Les utilisateurs peuvent modifier les messages envoyés

Affectez ensuite la stratégie aux utilisateurs.

> [!NOTE] 
> Un utilisateur ne peut avoir qu’une stratégie de messagerie à la fois.
 
## <a name="assign-a-messaging-policy-to-a-user"></a>Attribuer une stratégie de messagerie à un utilisateur

Si vous créez une stratégie de messagerie personnalisée, celle-ci est activée uniquement pour un utilisateur si celle-ci est affectée à l’utilisateur. Pour attribuer une stratégie personnalisée à un utilisateur, accédez au centre d’administration Microsoft Teams, sélectionnez **utilisateurs** dans le volet de navigation gauche, puis sélectionnez l’utilisateur auquel vous voulez affecter la stratégie. Dans la page de l’utilisateur, choisissez **modifier** en regard de **stratégies affectées**. Ensuite, dans le volet **modifier les stratégies d’utilisateur** , sous stratégie de **messagerie**, sélectionnez la stratégie de messagerie dans la liste déroulante, puis sélectionnez **Enregistrer**. Vous pouvez également modifier les paramètres dans la liste des utilisateurs. Pour cela, sélectionnez l’utilisateur en cliquant à gauche du nom complet de l’utilisateur. Sélectionnez **modifier les paramètres**. Dans le volet **modifier les paramètres** , sous **stratégie de messagerie**, sélectionnez la stratégie dans la liste déroulante, puis sélectionnez **Enregistrer**.

Si vous appliquez une stratégie à plusieurs utilisateurs, sélectionnez chacun d’eux en cliquant à gauche du nom de l’utilisateur, puis sélectionnez **modifier les paramètres**. Dans le volet **modifier les paramètres** , sous stratégie de **messagerie**, sélectionnez la stratégie dans la liste déroulante, puis sélectionnez **Enregistrer**.

Vous pouvez également affecter une stratégie de messagerie à un ou plusieurs utilisateurs comme suit:

1. Accédez**** au **Centre** > d’administration Microsoft Teams.
2. Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie.
3. Sélectionnez **gérer les utilisateurs**.
4. Dans le volet **gérer les utilisateurs** , recherchez l’utilisateur par nom complet ou par nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
5. Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.

> [!NOTE]
> Vous ne pouvez pas supprimer une stratégie s’il est affecté à des utilisateurs. Vous devez d’abord affecter une stratégie différente à tous les utilisateurs concernés, puis supprimer la stratégie d’origine.

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>Paramètres de la stratégie de messagerie

Utilisez les paramètres suivants pour modifier la stratégie de messagerie générale ou créer une nouvelle stratégie personnalisée:

- **Les propriétaires peuvent supprimer des messages envoyés**  Utilisez ce paramètre pour permettre aux propriétaires de supprimer les messages que les utilisateurs ont envoyés dans une conversation.
- **Les utilisateurs peuvent supprimer des messages envoyés** Utilisez ce paramètre pour permettre aux utilisateurs de supprimer les messages qu’ils ont envoyés dans une conversation.
- **Les utilisateurs peuvent modifier les messages envoyés** Utilisez ce paramètre pour permettre aux utilisateurs de modifier les messages qu’ils ont envoyés dans une conversation.
- **Confirmations de lecture** Utilisez ce paramètre pour spécifier si les confirmations de lecture sont contrôlées par l’utilisateur, activées pour tout le monde, ou désactivé.
<a name="bkchat"> </a>

- **Discussions**  Activez ce paramètre si vous souhaitez que les utilisateurs de votre organisation puissent utiliser l’application équipes pour discuter avec d’autres personnes.
- **Utiliser Giphys dans les conversations**  Si vous activez cette fonction, les utilisateurs peuvent inclure des Giphys dans les conversations par messagerie instantanée avec d’autres personnes. Giphy est une base de données en ligne et moteur de recherche qui permet aux utilisateurs de rechercher et partager des fichiers GIF animés. Chaque Giphy est affecté à une évaluation du contenu.
- **Évaluation du contenu Giphy** 
    - **Aucune restriction** Cela signifie que vos utilisateurs seront en mesure d’insérer des Giphy dans les discussions indépendamment de l’évaluation du contenu.
    - **Modérer**  Cela signifie que vos utilisateurs seront en mesure d’insérer des Giphys dans les discussions, mais qu’ils seront modérément limités à des contenus adultes.
    - **Strictement**  Cela signifie que vos utilisateurs seront en mesure d’insérer des Giphys dans les discussions, mais qu’ils seront strictement limités aux contenus adultes.
- **Utiliser mèmes dans les conversations** Si vous activez cette fonction, les utilisateurs peuvent inclure des mèmes dans les conversations par messagerie instantanée avec d’autres personnes. 
- **Utiliser les autocollants dans les conversations** Si vous activez cette fonction, les utilisateurs peuvent inclure des autocollants dans les conversations par messagerie instantanée avec d’autres personnes.
- **Autoriser** les aperçus d’URL Utilisez ce paramètre pour activer ou désactiver l’aperçu d’URL automatique dans les messages.
- **Permettre aux utilisateurs de traduire des messages** Activez ce paramètre pour permettre aux utilisateurs de traduire automatiquement des messages de teams dans la langue spécifiée par leurs paramètres de langue personnels pour Office 365.
- **Autoriser le lecteur immersif à afficher les messages** Activez ce paramètre pour permettre aux utilisateurs d’afficher des messages dans le lecteur immersif Microsoft. Le lecteur immersif est un outil d’apprentissage qui offre une interface de lecture plein écran pour améliorer la lisibilité du texte.
- **Les utilisateurs peuvent envoyer des notifications de priorité** Si vous activez cette fonction, les utilisateurs peuvent envoyer un message qui utilise les notifications de priorité. Les notifications de priorité avertissent les utilisateurs de manière répétée sur une période de 20 minutes, ou jusqu’à ce que les messages soient sélectionnés et lus par le destinataire, ce qui permet d’optimiser la probabilité que le message soit reçu et agi en temps opportun.
- **Creation de messages vocaux** 
    - **Autorisé dans les conversations et les canaux** Cela signifie que les utilisateurs peuvent laisser des messages vocaux dans les conversations et les canaux.
    - **Accordé uniquement aux conversations** Cela signifie que les utilisateurs peuvent laisser des messages vocaux dans les conversations, mais pas dans les canaux.
    - **Désactivé** Cela signifie que les utilisateurs ne peuvent pas créer de messages vocaux dans des conversations ou des canaux.  
- **Sur les appareils mobiles, afficher les canaux préférés au-dessus des discussions récentes** Activez ce paramètre pour déplacer les canaux favoris vers le haut de l’écran de l’appareil mobile de sorte qu’il ne soit pas nécessaire de faire défiler les canaux pour les retrouver. 
- **Autoriser un utilisateur à supprimer des utilisateurs d’une conversation de groupe** Activez ce paramètre pour permettre à un utilisateur de supprimer d’autres utilisateurs d’une discussion de groupe. Cette fonctionnalité vous permet de poursuivre une conversation avec un groupe de personnes plus petit sans perdre l’historique de vos conversations.

### <a name="related-topics"></a>Voir aussi
[Stratégies de réunion dans teams](meeting-policies-in-teams.md)
