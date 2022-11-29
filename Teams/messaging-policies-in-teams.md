---
title: Gérer les stratégies de messagerie dans Teams
ms.author: mabond
author: mkbond007
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
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.messagingpolicies.overview
- seo-marvel-apr2020
description: Découvrez les stratégies de messagerie et comment elles peuvent être utilisées pour contrôler la messagerie de conversation dans Teams.
ms.openlocfilehash: 83ee815651a0e08dc01d25639570c69f03edc588
ms.sourcegitcommit: e9718ad7e23317d490b238b3801267cb2e6b26e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/28/2022
ms.locfileid: "69176681"
---
# <a name="manage-messaging-policies-in-teams"></a>Gérer les stratégies de messagerie dans Teams

<!--- Add zone marker here--->

Les stratégies de messagerie sont utilisées pour contrôler les fonctionnalités de messagerie de conversation et de canal disponibles pour [les utilisateurs (propriétaires et membres)](assign-roles-permissions.md) dans Microsoft Teams. Vous pouvez utiliser la stratégie globale (par défaut à l’échelle de l’organisation) créée automatiquement ou créer et affecter des stratégies de messagerie personnalisées.

Les utilisateurs de votre organisation obtiennent automatiquement la stratégie globale, sauf si vous créez et affectez une stratégie personnalisée. Modifiez les paramètres de la stratégie globale ou créez et affectez une ou plusieurs stratégies personnalisées pour activer ou désactiver les fonctionnalités souhaitées.

> [!NOTE]
> Pour garantir la synchronisation après un changement de stratégie, un redémarrage peut être nécessaire pour certaines instances. 

## <a name="create-a-custom-messaging-policy"></a>Créer une stratégie de messagerie personnalisée

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **Stratégies de messagerie**.
2. Sélectionnez **Ajouter**.
3. Entrez un nom pour votre stratégie, ainsi qu’une description.
4. Sélectionnez les paramètres de votre choix.
5. Sélectionnez **Enregistrer**.

Par exemple, vous souhaitez vous assurer que les messages envoyés ne sont pas supprimés ou modifiés. Créez une stratégie personnalisée nommée « Conserver les messages envoyés » et désactivez les paramètres suivants :

- Les propriétaires peuvent supprimer les messages envoyés
- Les utilisateurs peuvent supprimer les messages envoyés
- Les utilisateurs peuvent modifier les messages envoyés

Affectez ensuite la stratégie aux utilisateurs.

## <a name="edit-a-messaging-policy"></a>Modifier une stratégie de messagerie

Vous pouvez modifier la stratégie globale et les stratégies personnalisées que vous créez.

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **Stratégies de messagerie**.
2. Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci, puis sélectionnez **Modifier**.
3. À partir de là, apportez les modifications souhaitées.
4. Sélectionnez **Enregistrer**.

## <a name="assign-a-custom-messaging-policy-to-users"></a>Affecter une stratégie de messagerie personnalisée aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Un utilisateur ne peut se voir affecter qu’une seule stratégie de messagerie à la fois.

> [!NOTE]
> Vous ne pouvez pas supprimer une stratégie qui est attribuée à des utilisateurs. Vous devez d'abord attribuer une autre stratégie à tous les utilisateurs concernés, puis supprimer la stratégie d’origine.

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>Paramètres de stratégie de messagerie

Voici les paramètres de stratégie de messagerie que vous pouvez configurer.

- **Les propriétaires peuvent supprimer les messages envoyés**  Utilisez ce paramètre pour permettre aux propriétaires de supprimer les messages de canal ou les publications envoyés par les utilisateurs.
- **Supprimer les messages envoyés** Utilisez ce paramètre pour permettre aux utilisateurs de supprimer les messages qu’ils ont envoyés dans la conversation.
- **Modifier les messages envoyés** Utilisez ce paramètre pour permettre aux utilisateurs de modifier les messages qu’ils ont envoyés dans la conversation.
- **Confirmations de lecture** Les confirmations de lecture permettent à l’expéditeur d’un message de conversation d’être averti lorsque son message a été lu par le destinataire dans 1:1 et les conversations de groupe de 20 personnes ou moins. Les accusés de lecture de message suppriment l’incertitude quant à la lecture d’un message et améliorent la communication de l’équipe. Les confirmations de lecture ne sont pas capturées dans les rapports eDiscovery.  
    - **Contrôlé par l’utilisateur** Cela signifie que les utilisateurs peuvent décider s’ils souhaitent activer ou désactiver les confirmations de lecture. Le paramètre par défaut dans l’application est ON. Les utilisateurs peuvent ensuite la désactiver.
    - **Activé pour tout le monde** Cela signifie que tous les membres du locataire auront la fonctionnalité ON sans possibilité de la désactiver. Lorsque vous utilisez le paramètre **Activé pour tout le monde** , la seule façon de définir des reçus pour l’ensemble du locataire consiste à n’avoir qu’une seule stratégie de messagerie pour l’ensemble du locataire (stratégie par défaut nommée « Globale (par défaut à l’échelle de l’organisation) ») ou à faire en sorte que toutes les stratégies de messagerie du locataire utilisent les mêmes paramètres pour les reçus. La fonctionnalité d’accusés de lecture est plus efficace lorsque la fonctionnalité est activée **Activé pour tout le monde**.
    - **Désactivé pour tout le monde** Cela signifie que la fonctionnalité est désactivée et que personne dans le locataire n’a de confirmation de lecture ni ne peut l’activer.
<a name="bkchat"> </a>

- **Bavarder**  Activez ce paramètre si vous souhaitez que les utilisateurs de votre organisation puissent utiliser l’application Teams pour discuter avec d’autres personnes.
- **Discuter avec des groupes** Les utilisateurs peuvent démarrer une conversation avec des groupes de distribution, des groupes de sécurité à extension messagerie et Microsoft 365 groupes.
- *Utiliser Giphy dans les conversations** Si vous activez Giphys, les utilisateurs peuvent inclure Giphys dans les conversations avec d’autres personnes. Giphy est une base de données en ligne et moteur de recherche qui permet aux utilisateurs de rechercher et partager des fichiers GIF animés. Chaque Giphy est affecté à une évaluation du contenu. En plus d’activer ce paramètre, vous devez activer les [expériences connectées facultatives](/deployoffice/privacy/manage-privacy-controls#policy-setting-for-optional-connected-experiences) pour autoriser Giphys dans les conversations.
- **Évaluation du contenu Giphy**
  - **Aucune restriction** Cela signifie que vos utilisateurs pourront insérer n’importe quel Giphy dans les conversations, quelle que soit la classification du contenu.
  - **Modérée**  Cela signifie que vos utilisateurs seront en mesure d’insérer Giphys dans les conversations, mais seront modérément limités au contenu pour adultes.
  - **Stricte**  Cela signifie que vos utilisateurs seront en mesure d’insérer Giphys dans les conversations, mais seront strictement limités à partir du contenu pour adultes.
- **Mèmes dans les conversations** Si vous activez les mèmes, les utilisateurs peuvent inclure des mèmes dans les conversations de conversation avec d’autres personnes.
- **Autocollants dans les conversations** Si vous activez cette option, les utilisateurs peuvent inclure des autocollants dans les conversations de conversation avec d’autres personnes.
- **Aperçus d’URL** Utilisez ce paramètre pour activer ou désactiver l’aperçu automatique des URL dans les messages.
- **Traduire des messages** Activez ce paramètre pour permettre aux utilisateurs de traduire automatiquement les messages Teams dans la langue spécifiée par leurs paramètres de langue personnels pour Microsoft 365 ou Office 365.
- **Lecteur immersif pour les messages** Activez ce paramètre pour permettre aux utilisateurs d’afficher les messages dans Microsoft Lecteur immersif. Lecteur immersif est un outil d’apprentissage qui offre une expérience de lecture en plein écran pour améliorer la lisibilité du texte.
- **Envoyer des messages urgents à l’aide de notifications de priorité** Si vous activez cette option, les utilisateurs peuvent envoyer des messages à l’aide de [notifications de priorité](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462). Les notifications de priorité informent les utilisateurs toutes les 2 minutes pendant 20 minutes ou jusqu’à ce que les messages marqués comme *urgents* soient récupérés et lus par le destinataire. Cette fonctionnalité augmente la probabilité que le message soit traité en temps voulu. Vous ne pouvez pas modifier un message urgent après l’avoir envoyé.
- **Créer des messages vocaux**
  > [!Important]
  > Les messages audio ne sont pas capturés dans les rapports eDiscovery.
  - **Autorisé dans les conversations et les canaux** Cela signifie que les utilisateurs peuvent laisser des messages audio dans les conversations et les canaux.
  - **Autorisé dans les conversations uniquement** Cela signifie que les utilisateurs peuvent laisser des messages audio dans les conversations, mais pas dans les canaux.
  - **Non activé** Cela signifie que les utilisateurs ne peuvent pas créer de messages audio dans des conversations ou des canaux.  
- **Sur les appareils mobiles, affichez les canaux favoris au-dessus des conversations récentes** Activez ce paramètre pour déplacer les canaux favoris vers le haut de l’écran de l’appareil mobile afin qu’un utilisateur n’ait pas besoin de faire défiler pour les trouver.
- **Supprimer des utilisateurs des conversations de groupe** Activez ce paramètre pour permettre à un utilisateur de supprimer d’autres utilisateurs d’une conversation de groupe. Cette fonctionnalité vous permet de poursuivre une conversation avec un plus petit groupe de personnes sans perdre l’historique des conversations.
- **Prédictions de texte** Activez ce paramètre pour permettre à un utilisateur d’obtenir des prédictions de texte pour les messages de conversation.
- **Réponses suggérées**  Activez ce paramètre pour activer les réponses suggérées pour les messages de conversation.
- **Rôle d’autorisation de conversation** Utilisez ce paramètre pour définir le rôle de conversation supervisée de l’utilisateur. En savoir plus sur [surveillance de conversation](supervise-chats-edu.md).
- **Les utilisateurs disposant d’autorisations de conversation complètes peuvent supprimer n’importe quel message** Utilisez ce paramètre pour permettre aux utilisateurs disposant d’autorisations complètes de supprimer tout message de conversation de groupe ou de réunion.
- **Messages vidéo** Activez ce paramètre si vous souhaitez que les utilisateurs de votre organisation puissent utiliser l’application Teams pour envoyer des messages vidéo à d’autres personnes dans Chat.

> [!NOTE]
> Certains de ces paramètres, tels que l’utilisation de Giphys, peuvent également être configurés au niveau de l’équipe par les propriétaires d’équipe et au niveau du canal privé ou partagé par les propriétaires de canaux.

### <a name="related-topics"></a>Rubriques connexes

- [Affecter des stratégies à des utilisateurs et des groupes dans Teams](assign-policies-users-and-groups.md)
- [Affecter des propriétaires d’équipe et des membres dans Microsoft Teams](assign-roles-permissions.md)
