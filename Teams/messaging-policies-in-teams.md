---
title: Gérer les stratégies de messagerie dans Teams
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: 050f072a2148be909dbaabd4ac8ab53c1e5bb298
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611658"
---
# <a name="manage-messaging-policies-in-teams"></a>Gérer les stratégies de messagerie dans Teams

<!--- Add zone marker here--->

Les stratégies de messagerie sont utilisées pour contrôler les fonctionnalités de messagerie et de messagerie de canal disponibles pour les utilisateurs de Microsoft teams [(propriétaires et membres)](assign-roles-permissions.md) . Vous pouvez utiliser la stratégie globale par défaut de l’organisation qui est créée automatiquement ou crée et attribue des stratégies de messagerie personnalisées.

Les utilisateurs de votre organisation recevront automatiquement la stratégie globale, sauf si vous créez et leur attribuez une stratégie personnalisée. Vous pouvez modifier les paramètres de la stratégie globale ou créer et affecter une ou plusieurs stratégies personnalisées pour activer ou désactiver les fonctionnalités de votre choix.

## <a name="create-a-custom-messaging-policy"></a>Créer une stratégie de messagerie personnalisée

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **stratégies de messagerie**.
2. Cliquez sur **Ajouter**.
3. Entrez un nom pour votre stratégie, ainsi qu’une description.
4. Choisissez les paramètres souhaités.
5. Cliquez sur **Enregistrer**.

Par exemple, imaginons que vous vouliez vérifier que les messages envoyés ne sont pas supprimés ou modifiés. Créez une stratégie personnalisée nommée « conserver les messages envoyés » et désactivez les paramètres suivants :

- Les propriétaires peuvent supprimer des messages envoyés
- Les utilisateurs peuvent supprimer des messages envoyés
- Les utilisateurs peuvent modifier les messages envoyés

Affectez ensuite la stratégie aux utilisateurs.

## <a name="edit-a-messaging-policy"></a>Modifier une stratégie de messagerie

Vous pouvez modifier la stratégie globale et les stratégies personnalisées que vous créez. 

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **stratégies de messagerie**.
2. Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie, puis cliquez sur **modifier**.
3. À partir de cet emplacement, apportez les modifications souhaitées.
4. Cliquez sur **Enregistrer**.

## <a name="assign-a-custom-messaging-policy-to-users"></a>Assigner une stratégie de messagerie personnalisée aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Un utilisateur ne peut avoir qu’une stratégie de messagerie à la fois.

> [!NOTE]
> Vous ne pouvez pas supprimer une stratégie s’il est affecté à des utilisateurs. Vous devez d’abord affecter une stratégie différente à tous les utilisateurs concernés, puis supprimer la stratégie d’origine.

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>Paramètres de la stratégie de messagerie

Voici les paramètres de stratégie de messagerie que vous pouvez configurer.

- **Les propriétaires peuvent supprimer des messages envoyés**  Utilisez ce paramètre pour permettre aux propriétaires de supprimer les messages que les utilisateurs ont envoyés dans une conversation.
- **Les utilisateurs peuvent supprimer des messages envoyés** Utilisez ce paramètre pour permettre aux utilisateurs de supprimer les messages qu’ils ont envoyés dans une conversation.
- **Les utilisateurs peuvent modifier les messages envoyés** Utilisez ce paramètre pour permettre aux utilisateurs de modifier les messages qu’ils ont envoyés dans une conversation.
- **Confirmations de lecture** Les confirmations de lecture permettent à l’expéditeur d’un message de recevoir une notification lors de la lecture du message par le destinataire dans 1:1 et les discussions de groupe de 20 personnes ou moins. Les confirmations de lecture des messages ne s’importent pas incertainement quant à la lecture des messages et à l’amélioration de la communication d’équipe. Veuillez noter que les confirmations de lecture ne sont pas capturées dans les rapports eDiscovery.  
    - **Contrôle utilisateur** Cela signifie que les utilisateurs décident d’activer ou de désactiver les confirmations de lecture. Le paramètre par défaut de l’application est activé. Les utilisateurs peuvent alors le désactiver.
    - **Activé pour tout le monde** Cela signifie que tout le monde au sein du client dispose de la fonctionnalité, sans option pour le désactiver. Sachez que lors de l’utilisation du paramètre **activé pour tout le monde** , la seule façon de définir les accusés de réception pour l’ensemble du client est d’avoir une seule stratégie de messagerie pour l’ensemble du client (la stratégie par défaut nommée « global (organisation par défaut) ») ou de faire en sorte que toutes les stratégies de messagerie du client utilisent les mêmes paramètres pour les reçus. La fonctionnalité accusés de lecture est particulièrement efficace lorsque la fonctionnalité est activée **pour tout le monde**.
    - **Désactivé pour tous** Cela signifie que la fonctionnalité est désactivée et que personne ne dispose d’une confirmation de lecture dans le client.
<a name="bkchat"> </a>

- **Discussions**  Activez ce paramètre si vous souhaitez que les utilisateurs de votre organisation puissent utiliser l’application équipes pour discuter avec d’autres personnes.
- **Utiliser Giphys dans les conversations**  Si vous activez cette fonction, les utilisateurs peuvent inclure des Giphys dans les conversations par messagerie instantanée avec d’autres personnes. Giphy est une base de données en ligne et moteur de recherche qui permet aux utilisateurs de rechercher et partager des fichiers GIF animés. Chaque Giphy est affecté à une évaluation du contenu. Notez que, en plus de activer ce paramètre, vous devez également activer les [expériences connectées facultatives](https://docs.microsoft.com/deployoffice/privacy/manage-privacy-controls#policy-setting-for-optional-connected-experiences) pour autoriser Giphys dans les conversations.
- **Évaluation du contenu Giphy**
    - **Aucune restriction** Cela signifie que vos utilisateurs seront en mesure d’insérer des Giphy dans les discussions indépendamment de l’évaluation du contenu.
    - **Modérer**  Cela signifie que vos utilisateurs seront en mesure d’insérer des Giphys dans les discussions, mais qu’ils seront modérément limités à des contenus adultes.
    - **Strictement**  Cela signifie que vos utilisateurs seront en mesure d’insérer des Giphys dans les discussions, mais qu’ils seront strictement limités aux contenus adultes.
- **Utiliser mèmes dans les conversations** Si vous activez cette fonction, les utilisateurs peuvent inclure des mèmes dans les conversations par messagerie instantanée avec d’autres personnes.
- **Utiliser les autocollants dans les conversations** Si vous activez cette fonction, les utilisateurs peuvent inclure des autocollants dans les conversations par messagerie instantanée avec d’autres personnes.
- **Autoriser les aperçus d’URL** Utilisez ce paramètre pour activer ou désactiver l’aperçu d’URL automatique dans les messages.
- **Permettre aux utilisateurs de traduire des messages** Activez ce paramètre pour permettre aux utilisateurs de traduire automatiquement des messages dans la langue spécifiée par leurs paramètres de langue personnels pour Microsoft 365 ou Office 365.
- **Autoriser le lecteur immersif à afficher les messages** Activez ce paramètre pour permettre aux utilisateurs d’afficher des messages dans le lecteur immersif Microsoft. Le lecteur immersif est un outil d’apprentissage qui offre une interface de lecture plein écran pour améliorer la lisibilité du texte.
- **Envoyer des messages urgents à l’aide de notifications de priorité** Si vous activez cette fonction, les utilisateurs peuvent envoyer des messages à l’aide de [notifications de priorité](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462). Les notifications de priorité indiquent aux utilisateurs toutes les 2 minutes pour une période de 20 minutes ou jusqu’à ce que les messages marqués comme *urgents* soient sélectionnés et lus par le destinataire, ce qui maximise la probabilité que le message soit agi en temps opportun.
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

### <a name="related-topics"></a>Voir aussi

- [Attribuer des stratégies à vos utilisateurs dans teams](assign-policies.md)
- [Affecter des propriétaires d’équipe et des membres dans Microsoft Teams](assign-roles-permissions.md)
