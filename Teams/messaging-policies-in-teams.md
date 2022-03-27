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
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.messagingpolicies.overview
- seo-marvel-apr2020
description: Découvrez les stratégies de messagerie et comment elles peuvent être utilisées pour contrôler la messagerie instantanée dans Teams.
ms.openlocfilehash: 0f4001fc2a646b83f005d9cc48948fbbb314f042
ms.sourcegitcommit: 867e8b4120e81c93c029c0c1b9cb69c161fc87a4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/26/2022
ms.locfileid: "64480666"
---
# <a name="manage-messaging-policies-in-teams"></a>Gérer les stratégies de messagerie dans Teams

<!--- Add zone marker here--->

Les stratégies de messagerie servent à contrôler les fonctionnalités de conversation et de messagerie de canal disponibles pour les utilisateurs [(propriétaires](assign-roles-permissions.md) et membres) Microsoft Teams. Vous pouvez utiliser la stratégie globale (à l’échelle de l’organisation par défaut) créée automatiquement ou créer et attribuer des stratégies de messagerie personnalisées.

Les utilisateurs de votre organisation obtiennent automatiquement la stratégie globale, sauf si vous créez et attribuez une stratégie personnalisée. Modifiez les paramètres de la stratégie globale ou créez et affectez une ou plusieurs stratégies personnalisées pour activer ou désactiver les fonctionnalités que vous souhaitez.

> [!NOTE]
> Pour garantir la synchronisation après un changement de stratégie, un redémarrage peut être nécessaire pour certaines instances. 

## <a name="create-a-custom-messaging-policy"></a>Créer une stratégie de messagerie personnalisée

1. Dans le panneau de navigation gauche du Microsoft Teams d’administration, allez dans **Stratégies de messagerie**.
2. Sélectionnez **Ajouter**.
3. Entrez un nom pour votre stratégie, ainsi qu’une description.
4. Sélectionnez les paramètres de votre choix.
5. Sélectionnez **Enregistrer**.

Par exemple, vous voulez vous assurer que les messages envoyés ne sont pas supprimés ou modifiés. Créez une stratégie personnalisée nommée « Conserver les messages envoyés », puis désactiver les paramètres suivants :

- Les propriétaires peuvent supprimer les messages envoyés
- Les utilisateurs peuvent supprimer les messages envoyés
- Les utilisateurs peuvent modifier les messages envoyés

Affectez ensuite la stratégie aux utilisateurs.

## <a name="edit-a-messaging-policy"></a>Modifier une stratégie de messagerie

Vous pouvez modifier la stratégie globale et les stratégies personnalisées que vous créez.

1. Dans le panneau de navigation gauche du Microsoft Teams d’administration, allez dans **Stratégies de messagerie**.
2. Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci, puis sélectionnez **Modifier**.
3. À partir de là, apportez les modifications souhaitées.
4. Sélectionnez **Enregistrer**.

## <a name="assign-a-custom-messaging-policy-to-users"></a>Affecter une stratégie de messagerie personnalisée aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Un utilisateur ne peut avoir qu’une stratégie de messagerie à la fois.

> [!NOTE]
> Vous ne pouvez pas supprimer une stratégie qui est attribuée à des utilisateurs. Vous devez d'abord attribuer une autre stratégie à tous les utilisateurs concernés, puis supprimer la stratégie d’origine.

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a>Paramètres de stratégie de messagerie

Voici les paramètres de stratégie de messagerie que vous pouvez configurer.

- **Les propriétaires peuvent supprimer les messages envoyés**  Utilisez ce paramètre pour que les propriétaires suppriment des messages de canal ou des publications que les utilisateurs ont envoyés.
- **Supprimer les messages envoyés** Ce paramètre permet aux utilisateurs de supprimer les messages qu’ils ont envoyés dans une conversation.
- **Modifier les messages envoyés** Ce paramètre permet aux utilisateurs de modifier les messages qu’ils ont envoyés dans une conversation.
- **Read receipts** Les receipts de lecture permettent à l’expéditeur d’un message de conversation d’être informé lorsque son message a été lu par le destinataire dans les conversations de groupe de 1:1 et de 20 personnes au moins. Les messages de lecture sont supprimés de manière visuelle pour déterminer si un message a été lu ou non et améliorer la communication au niveau de l’équipe. Les reçus de lecture ne sont pas capturés dans les rapports eDiscovery.  
    - **Utilisateur contrôlé** Cela signifie que les utilisateurs peuvent décider s’ils souhaitent recevoir des reçus de lecture comme ils le souhaitent. Le paramètre par défaut dans l’application est sous l’option. Les utilisateurs peuvent ensuite le désactiver.
    - **Désactivé pour tout le monde** Cela signifie que tous les personnes du client disposent de la fonctionnalité sans option pour la désactiver. Lorsque vous utilisez le paramètre **On** pour tout le monde, la seule façon de définir des accusé de réception pour l’ensemble du client consiste à n’avoir qu’une seule stratégie de messagerie pour l’ensemble du client (la stratégie par défaut nommée « Global (par défaut à l’échelle de l’organisation) ») ou de faire en sorte que toutes les stratégies de messagerie du client utilisent les mêmes paramètres pour les reçus. La fonctionnalité d’accusés de lecture est plus efficace lorsque la fonctionnalité est activée **Activé pour tout le monde**.
    - **Désactivé pour tout le monde** Cela signifie que la fonctionnalité est désactivée et que personne au client n’a de reçu de lecture, ni ne peut l’activer.
<a name="bkchat"> </a>

- **Bavarder**  Activer ce paramètre si vous voulez que les utilisateurs de votre organisation puissent utiliser l’application Teams pour discuter avec d’autres personnes.
- *Utilisez Giphy dans les conversations** Si vous allumez Giphys, les utilisateurs peuvent inclure Des Giphys dans les conversations avec d’autres personnes. Giphy est une base de données en ligne et moteur de recherche qui permet aux utilisateurs de rechercher et partager des fichiers GIF animés. Chaque Giphy est affecté à une évaluation du contenu. En plus d’activer ce paramètre, vous devez activer les [](/deployoffice/privacy/manage-privacy-controls#policy-setting-for-optional-connected-experiences) expériences connectées facultatives pour autoriser les Giphys dans les conversations.
- **Évaluation du contenu Giphy**
  - **Aucune restriction** Cela signifie que vos utilisateurs pourront insérer des Giphy dans les conversations, quel que soit l’évaluation du contenu.
  - **Modéré**  Cela signifie que vos utilisateurs pourront insérer des Giphys dans les conversations, mais que le contenu pour adultes sera modérément restreint.
  - **Strict**  Cela signifie que vos utilisateurs pourront insérer des Giphys dans les conversations, mais sont strictement limitées au contenu adulte.
- **Mèmes dans les conversations** Si vous activer les mèmes, les utilisateurs peuvent inclure des mèmes dans les conversations avec d’autres personnes.
- **Autocollants dans les conversations** Si vous l’allumez, les utilisateurs peuvent inclure des autocollants dans les conversations avec d’autres personnes.
- **Aperçus d’URL** Utilisez ce paramètre pour activer ou désactiver la prévisualisation automatique des URL dans les messages.
- **Traduire des messages** Activer ce paramètre pour que les utilisateurs traduisent automatiquement Teams messages dans la langue spécifiée par leurs paramètres de langue personnels pour Microsoft 365 ou Office 365.
- **Lecteur immersif des messages** Activer ce paramètre pour que les utilisateurs visualisent les messages dans Microsoft Lecteur immersif. Lecteur immersif est un outil d’apprentissage qui offre une expérience de lecture plein écran pour améliorer la lisibilité du texte.
- **Envoyer des messages urgents à l’aide de notifications de priorité** Si vous l’activer, les utilisateurs peuvent envoyer des messages à l’aide de [notifications de priorité](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462). Les notifications de priorité informent les utilisateurs toutes les 2 minutes pendant 20 minutes ou jusqu’à ce que les messages marqués comme urgents soient choisis et lus par le destinataire. Cette fonctionnalité augmente la probabilité que le message soit envoyé dans un délai raisonnable.
- **Créer des messages vocaux**
  > [!Important]
  > Les messages audio ne sont pas capturés dans les rapports eDiscovery.
  - **Autorisé dans les conversations et les canaux** Cela signifie que les utilisateurs peuvent laisser des messages audio dans les conversations et les canaux.
  - **Autorisé dans les conversations uniquement** Cela signifie que les utilisateurs peuvent laisser des messages audio dans les conversations, mais pas dans les canaux.
  - **Non activé** Cela signifie que les utilisateurs ne peuvent pas créer de messages audio dans les conversations ou les canaux.  
- **Sur les appareils mobiles, afficher les canaux favoris au-dessus des conversations récentes** Activez ce paramètre pour déplacer les canaux favoris vers le haut de l’écran de l’appareil mobile afin qu’un utilisateur n’a pas besoin de faire défiler la page pour les trouver.
- **Supprimer des utilisateurs des conversations de groupe** Activer ce paramètre pour qu’un utilisateur supprime d’autres utilisateurs d’une conversation de groupe. Cette fonctionnalité vous permet de poursuivre une conversation avec un groupe de personnes plus petit sans perdre l’historique des discussions.
- **Prédictions de texte** Activer ce paramètre pour qu’un utilisateur reçoie des prédictions de texte pour les messages de conversation.
- **Réponses suggérées**  Activez ce paramètre pour activer les réponses suggérées pour les messages de conversation.
- **Rôle d’autorisation de conversation** Utilisez ce paramètre pour définir le rôle de conversation surveillée de l’utilisateur. En savoir plus sur [surveillance de conversation](supervise-chats-edu.md).
- **Les utilisateurs autorisés à utiliser les autorisations de conversation peuvent supprimer n’importe quel message** Utilisez ce paramètre pour autoriser les utilisateurs  autorisés à supprimer n’importe quel message de conversation de groupe ou de réunion.

> [!NOTE]
> Certains de ces paramètres, tels que l’utilisation de Giphys, peuvent également être configurés au niveau de l’équipe par les propriétaires d’équipe et au niveau du canal privé ou partagé par les propriétaires de canal.

### <a name="related-topics"></a>Sujets associés

- [Attribuer des stratégies aux utilisateurs et groupes dans Teams](assign-policies-users-and-groups.md)
- [Affecter des propriétaires d’équipe et des membres dans Microsoft Teams](assign-roles-permissions.md)
