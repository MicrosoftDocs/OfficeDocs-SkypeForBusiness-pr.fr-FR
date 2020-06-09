---
title: Gérer les stratégies de messagerie dans Teams
ms.author: lolaj
author: lolajacobsen
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.messagingpolicies.overview
- seo-marvel-apr2020
description: Dans cet article, vous allez découvrir les stratégies de messagerie et savoir comment les utiliser pour contrôler la messagerie vocale dans Teams.
ms.openlocfilehash: d435296f26c76017218af6120bcae5a4b90a0b36
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44637923"
---
# <a name="manage-messaging-policies-in-teams"></a>Gérer les stratégies de messagerie dans Teams

<!--- Add zone marker here--->

Les stratégies de messagerie permettent de contrôler la disponibilité des fonctionnalités de conversation et de messagerie de canal pour les utilisateurs de Microsoft Teams. Vous pouvez utiliser la stratégie par défaut qui est créée automatiquement ou créer une ou plusieurs stratégies de messagerie personnalisées pour les membres de votre organisation. Après avoir créé une stratégie, vous pouvez l’affecter à un utilisateur ou à un groupe d’utilisateurs de votre organisation.

Par défaut, la création d’une stratégie nommée global (au niveau de l’organisation par défaut) est créée. Par défaut, tous les utilisateurs de votre organisation reçoivent cette stratégie de messagerie. Vous pouvez modifier cette stratégie ou en créer une ou plusieurs, et leur affecter des utilisateurs. Lorsque vous créez une stratégie personnalisée, vous pouvez autoriser ou empêcher l’accès à certaines fonctionnalités à vos utilisateurs, puis les affecter à un ou plusieurs utilisateurs qui auront besoin des paramètres appliqués.

## <a name="change-or-create-a-messaging-policy"></a>Modification ou création d’une stratégie de messagerie

Vous pouvez facilement gérer les stratégies de messagerie dans le centre d’administration de Microsoft Teams ( https://admin.teams.microsoft.com) en vous connectant avec des informations d’identification d’administrateur et en choisissant **stratégies de messagerie** dans le volet de navigation gauche. Pour modifier la stratégie de messagerie par défaut existante pour votre organisation, sélectionnez la ligne **global (par défaut de l’organisation)** , puis apportez les modifications souhaitées. Pour créer une stratégie de messagerie personnalisée, sélectionnez **nouvelle stratégie**, attribuez un nom à la nouvelle stratégie, puis sélectionnez vos paramètres. Lorsque vous avez fin, cliquez sur **Enregistrer** .

Par exemple, imaginons que vous vouliez vérifier que les messages envoyés ne sont pas supprimés ou modifiés. Vous pouvez créer une stratégie personnalisée nommée « conserver les messages envoyés » et désactiver les paramètres suivants :

- Les propriétaires peuvent supprimer des messages envoyés
- Les utilisateurs peuvent supprimer des messages envoyés
- Les utilisateurs peuvent modifier les messages envoyés

Vous pouvez ensuite attribuer la stratégie aux utilisateurs.

> [!NOTE]
> Un utilisateur ne peut avoir qu’une stratégie de messagerie à la fois.

## <a name="assign-a-messaging-policy-to-a-user"></a>Attribuer une stratégie de messagerie à un utilisateur

Si vous créez une stratégie de messagerie personnalisée, celle-ci est activée uniquement pour un utilisateur si celle-ci est affectée à l’utilisateur. Pour attribuer une stratégie personnalisée à un utilisateur, accédez au centre d’administration Microsoft Teams, sélectionnez **utilisateurs** dans le volet de navigation gauche, puis sélectionnez l’utilisateur auquel vous voulez affecter la stratégie. Dans la page de l’utilisateur, choisissez **modifier** en regard de **stratégies affectées**. Ensuite, dans le volet **modifier les stratégies d’utilisateur** , sous stratégie de **messagerie**, sélectionnez la stratégie de messagerie dans la liste déroulante, puis sélectionnez **Enregistrer**. Vous pouvez également modifier les paramètres dans la liste des utilisateurs. Pour cela, sélectionnez l’utilisateur en cliquant à gauche du nom complet de l’utilisateur. Sélectionnez **modifier les paramètres**. Dans le volet **modifier les paramètres** , sous **stratégie de messagerie**, sélectionnez la stratégie dans la liste déroulante, puis sélectionnez **Enregistrer**.

Si vous appliquez une stratégie à plusieurs utilisateurs, sélectionnez chacun d’eux en cliquant à gauche du nom de l’utilisateur, puis sélectionnez **modifier les paramètres**. Dans le volet **modifier les paramètres** , sous stratégie de **messagerie**, sélectionnez la stratégie dans la liste déroulante, puis sélectionnez **Enregistrer**.

Vous pouvez également affecter une stratégie de messagerie à un ou plusieurs utilisateurs comme suit :

1. Accédez au **Centre d’administration Microsoft teams**  >  **Messaging policies**.
2. Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci.
3. Sélectionnez **Gérer les utilisateurs**.
4. Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
5. Lorsque vous avez terminé d’ajouter des utilisateurs, sélectionnez **Enregistrer**.

> [!NOTE]
> Vous ne pouvez pas supprimer une stratégie s’il est affecté à des utilisateurs. Vous devez d’abord affecter une stratégie différente à tous les utilisateurs concernés, puis supprimer la stratégie d’origine.

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>Paramètres de la stratégie de messagerie

Utilisez les paramètres suivants pour modifier la stratégie de messagerie générale ou créer une nouvelle stratégie personnalisée :

- **Les propriétaires peuvent supprimer des messages envoyés**  Utilisez ce paramètre pour permettre aux propriétaires de supprimer les messages que les utilisateurs ont envoyés dans une conversation.
- **Les utilisateurs peuvent supprimer des messages envoyés** Utilisez ce paramètre pour permettre aux utilisateurs de supprimer les messages qu’ils ont envoyés dans une conversation.
- **Les utilisateurs peuvent modifier les messages envoyés** Utilisez ce paramètre pour permettre aux utilisateurs de modifier les messages qu’ils ont envoyés dans une conversation.
- **Confirmations de lecture** Les confirmations de lecture permettent à l’expéditeur d’un message de recevoir une notification lors de la lecture du message par le destinataire dans 1:1 et les discussions de groupe de 20 personnes ou moins. Les confirmations de lecture des messages ne s’importent pas incertainement quant à la lecture des messages et à l’amélioration de la communication d’équipe. Veuillez noter que les confirmations de lecture ne sont pas capturées dans les rapports eDiscovery.  
    - **Contrôle utilisateur** Cela signifie que les utilisateurs décident d’activer ou de désactiver les confirmations de lecture. Le paramètre par défaut de l’application est activé. Les utilisateurs peuvent alors le désactiver.
    - **Activé pour tout le monde** Cela signifie que tout le monde au sein du client dispose de la fonctionnalité, sans option pour le désactiver. Sachez que lors de l’utilisation du paramètre **activé pour tout le monde** , la seule façon de définir les accusés de réception pour l’ensemble du client est d’avoir une seule stratégie de messagerie pour l’ensemble du client (la stratégie par défaut nommée « global (organisation par défaut) ») ou de faire en sorte que toutes les stratégies de messagerie du client utilisent les mêmes paramètres pour les reçus. La fonctionnalité accusés de lecture est particulièrement efficace lorsque la fonctionnalité est activée **pour tout le monde**.
    - **Désactivé pour tous** Cela signifie que la fonctionnalité est désactivée et que personne ne dispose d’une confirmation de lecture dans le client.
<a name="bkchat"> </a>

- **Discussions**  Activez ce paramètre si vous souhaitez que les utilisateurs de votre organisation puissent utiliser l’application équipes pour discuter avec d’autres personnes.
- **Utiliser Giphys dans les conversations**  Si vous activez cette fonction, les utilisateurs peuvent inclure des Giphys dans les conversations par messagerie instantanée avec d’autres personnes. Giphy est une base de données en ligne et moteur de recherche qui permet aux utilisateurs de rechercher et partager des fichiers GIF animés. Chaque Giphy est affecté à une évaluation du contenu.
- **Évaluation du contenu Giphy**
    - **Aucune restriction** Cela signifie que vos utilisateurs seront en mesure d’insérer des Giphy dans les discussions indépendamment de l’évaluation du contenu.
    - **Modérer**  Cela signifie que vos utilisateurs seront en mesure d’insérer des Giphys dans les discussions, mais qu’ils seront modérément limités à des contenus adultes.
    - **Strictement**  Cela signifie que vos utilisateurs seront en mesure d’insérer des Giphys dans les discussions, mais qu’ils seront strictement limités aux contenus adultes.
- **Utiliser mèmes dans les conversations** Si vous activez cette fonction, les utilisateurs peuvent inclure des mèmes dans les conversations par messagerie instantanée avec d’autres personnes.
- **Utiliser les autocollants dans les conversations** Si vous activez cette fonction, les utilisateurs peuvent inclure des autocollants dans les conversations par messagerie instantanée avec d’autres personnes.
- **Autoriser les aperçus d’URL** Utilisez ce paramètre pour activer ou désactiver l’aperçu d’URL automatique dans les messages.
- **Permettre aux utilisateurs de traduire des messages** Activez ce paramètre pour permettre aux utilisateurs de traduire automatiquement des messages dans la langue spécifiée par leurs paramètres de langue personnels pour Microsoft 365 ou Office 365.
- **Autoriser le lecteur immersif à afficher les messages** Activez ce paramètre pour permettre aux utilisateurs d’afficher des messages dans le lecteur immersif Microsoft. Le lecteur immersif est un outil d’apprentissage qui offre une interface de lecture plein écran pour améliorer la lisibilité du texte.
- **Envoyer des messages urgents à l’aide de notifications de priorité** Si vous activez cette fonction, les utilisateurs peuvent envoyer des messages à l’aide de [notifications de priorité](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462). Les notifications de priorité indiquent aux utilisateurs toutes les 2 minutes pour une période de 20 minutes ou jusqu’à ce que les messages marqués comme *urgents* soient sélectionnés et lus par le destinataire, ce qui maximise la probabilité que le message soit agi en temps opportun.   [!INCLUDE [pri-message-offer](includes/pri-message-offer.md)]
- **Création de messages audio**
  > [!Important]
  > Les messages audio ne sont pas capturés dans la création de rapports eDiscovery.
    - **Autorisé dans les conversations et les canaux** Cela signifie que les utilisateurs peuvent laisser des messages audio dans les conversations et les canaux.
    - **Accordé uniquement aux conversations** Cela signifie que les utilisateurs peuvent laisser des messages audio dans les discussions, mais pas dans les canaux.
    - **Désactivé** Cela signifie que les utilisateurs ne peuvent pas créer de messages audio dans des conversations ou des canaux.  
- **Sur les appareils mobiles, afficher les canaux préférés au-dessus des discussions récentes** Activez ce paramètre pour déplacer les canaux favoris vers le haut de l’écran de l’appareil mobile de sorte qu’il ne soit pas nécessaire de faire défiler les canaux pour les retrouver.
- **Autoriser un utilisateur à supprimer des utilisateurs d’une conversation de groupe** Activez ce paramètre pour permettre à un utilisateur de supprimer d’autres utilisateurs d’une discussion de groupe. Cette fonctionnalité vous permet de poursuivre une conversation avec un groupe de personnes plus petit sans perdre l’historique de vos conversations.
- **Activer les réponses suggérées**  Activez ce paramètre pour activer les réponses suggérées pour les messages de discussion.

> [!NOTE]
> Certains de ces paramètres, tels que l’utilisation de Giphys, peuvent également être configurés au niveau de l’équipe par les propriétaires d’équipe et au niveau du canal privé par les propriétaires de canaux privés.

### <a name="related-topics"></a>Rubriques connexes

[Stratégies de réunion dans teams](meeting-policies-in-teams.md)
