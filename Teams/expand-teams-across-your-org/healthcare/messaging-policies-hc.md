---
title: Démarrage avec la messagerie sécurisée pour les organismes de santé
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Démarrage avec la messagerie sécurisée pour les organismes de santé
ms.openlocfilehash: ff4f9089d7fba87678345d37f8c9d85949fb478e
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827732"
---
# <a name="get-started-with-secure-messaging-for-healthcare-organizations"></a>Démarrage avec la messagerie sécurisée pour les organismes de santé

Les stratégies de messagerie sont utilisées pour contrôler les fonctionnalités de messagerie et de messagerie de canal qui sont accessibles aux utilisateurs de Microsoft Teams, et qui font partie du déploiement global de la messagerie sécurisée pour les établissements de santé tels que les hôpitaux, les cliniques ou les bureaux de médecins, où le fait de faire en sorte qu’un message est pris en compte et est essentiel, car il est essentiel de lire les messages cruciaux.

Vous pouvez utiliser la stratégie par défaut ou créer une ou plusieurs stratégies de messagerie personnalisées pour les membres de votre organisation. Lorsque vous créez une stratégie, vous lui attribuez un utilisateur ou des groupes d’utilisateurs de votre organisation. Par exemple, vous pouvez choisir d’autoriser uniquement certains rôles de poste pour utiliser ces fonctions (par exemple, les médecins et les infirmières uniquement) et d’autres travailleurs (comme le JANITORIAL ou le personnel de cuisine) pour obtenir un ensemble de fonctionnalités plus limité. Déterminez pour vous-même les besoins de votre organisation, et voici une suggestion.

Vous pouvez facilement gérer les stratégies dans le [Centre d’administration Microsoft teams](https://admin.teams.microsoft.com) en vous connectant avec les informations d’identification d’administrateur et en choisissant **stratégies de messagerie** dans le volet de navigation gauche.

 ![Capture d’écran de la page stratégies de messagerie](../../media/messaging-policies-image1.png)

Pour modifier la stratégie de messagerie par défaut existante pour votre organisation, cliquez sur la ligne **global (par défaut de l’organisation)** , puis apportez les modifications souhaitées. Pour créer une stratégie de messagerie personnalisée, cliquez sur **nouvelle stratégie** et sélectionnez vos paramètres. Lorsque vous avez fin, cliquez sur **Enregistrer** .

![Capture d’écran des paramètres de stratégie de messagerie](../../media/hc-message-policy.png)

Les paramètres suivants sont particulièrement intéressants pour les applications de santé et doivent être pris en compte lors de la conception d’une stratégie personnalisée utilisée dans le champ santé :

## <a name="read-receipts"></a>Confirmations de lecture

- ![Icône du numéro 1, faisant référence à une légende dans](../../media/sfbcallout1.png) **la capture d’écran précédente confirmations** de lecture pour permettre à l’expéditeur d’un message de savoir lorsque le message a été lu par le destinataire dans 1:1 et les discussions de groupe de 20 personnes ou moins. Utilisez ce paramètre pour spécifier si les confirmations de lecture sont contrôlées par l’utilisateur, pour tout le monde ou désactivé pour tout le monde. Les confirmations de lecture de messages sont importantes dans les organisations de soins de santé, car elles suppriment de façon incertaine l’existence ou non de la lecture d’un message.

  Pour les applications de santé, sélectionnez **contrôle utilisateur** ou **activé pour tout le monde**. Sachez que lors de l’utilisation du paramètre **activé pour tout le monde** , la seule façon de définir les accusés de réception pour l’ensemble du client est d’avoir une seule stratégie de messagerie pour l’ensemble du client (la stratégie par défaut nommée « global (organisation par défaut) ») ou de faire en sorte que toutes les stratégies de messagerie du client utilisent les mêmes paramètres pour les reçus. La fonctionnalité accusés de lecture est particulièrement efficace lorsque la fonctionnalité est activée **pour tout le monde**.

    *Exemple d’utilisation sans confirmation de lecture :* Jakob Roth, un patient à haut risque, est admis aux hôpitaux.Le Sofia Krause est une infirmier qui travaille dans le cadre de l’équipe interdisciplinaire (IDT) des travailleurs médicaux, y compris des spécialistes, est désigné comme le coordinateur principal responsable du patient.  Le champ Sofia envoie des messages électroniques et d’autres messages instantanés à un groupe d’infirmières et de médecins utilisant divers clients et applications de messagerie, et n’obtient généralement aucune réponse ou indication qu’un message a été lu par les membres de l’équipe. En raison de processus de communication Tangled, le médicament de Jakob est appliqué de façon incertaine et le reste de l’hôpital est prolongé.

    *Exemple d’utilisation avec confirmations de lecture :* Jakob Roth, un patient à haut risque, est admis aux hôpitaux.Le Sofia Krause est une infirmier qui travaille dans le cadre de l’équipe interdisciplinaire (IDT) des travailleurs médicaux, y compris des spécialistes, est désigné comme le coordinateur principal responsable du patient.  Sofia démarre une discussion de groupe avec un ensemble de médecins et d’autres infirmières qui travaillent avec le patient pour coordonner les soins et commencer un triage d’urgence.Les infirmières et les médecins communiquent et collaborent au plan de soins du patient tout au long du processus de coordination des soins.  Les messages importants et urgents sont envoyés via 1:1 et les conversations de groupe. Sofia utilise la fonctionnalité de confirmation de lecture pour déterminer si les messages envoyés demandant une assistance sont remis et lus par les médecins ou les infirmières ciblés. Les résultats du patient de Jakob sont les plus proches et qu’ils s’ouvrent plus rapidement, car l’équipe de soins communiquera en toute transparence.

## <a name="priority-notifications"></a>Notifications de priorité

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

[!INCLUDE [pri-message-offer](../../includes/pri-message-offer.md)]

- ![Icône du numéro 2, qui référence une légende dans la capture d'](../../media/sfbcallout2.png) écran précédente **les utilisateurs peuvent envoyer des notifications de priorité** un utilisateur peut marquer un message comme « urgent » lors de l’envoi de messages instantanés à d’autres utilisateurs. Cette fonctionnalité permet au personnel de l’hôpital de s’avertir lorsque l’un d’eux nécessite son attention. À la différence des messages « importants » normaux, les notifications de priorité avertissent les utilisateurs toutes les deux minutes pour une période de 20 minutes maximum ou jusqu’à ce que le message soit reçu et lu par le destinataire, ce qui maximise la probabilité d’action du message en temps opportun.

  Un administrateur peut activer ou désactiver la possibilité pour les utilisateurs ayant affecté cette stratégie d’envoyer des notifications de priorité. Cette fonctionnalité est activée par défaut. Le destinataire du message prioritaire peut ne pas avoir la même stratégie de messagerie et ne peut pas désactiver la réception de messages de priorité. Dans le cas des applications de santé, nous vous recommandons d’activer la fonctionnalité pour au moins quelques utilisateurs, mais vous devez en déterminer les.

  *Exemple d’utilisation :* Sofia Krause est en plus d’admettre un patient à haut risque, Jakob Roth. Manuela Carsten est le médecin principal du patient pour ce patient.  Sofia envoie un message à Manuela à l’aide d’une notification de priorité demandant une assistance immédiate au triage de Jakob.  Le numéro de téléphone de Manuela reçoit le message mais Manuela n’a pas trouvé la vibration du téléphone et ne répond pas. Teams réactive le Manuela et continue d’avertir de nouveau jusqu’à ce qu’il Lise le message. Si les confirmations de lecture sont également activées, vous savez que le message a été lu par Manuela, même avant que Manuela ne décide du mode de réponse.

## <a name="related-topics"></a>Rubriques connexes

- [Gérer les stratégies de messagerie dans Teams](../../messaging-policies-in-teams.md)
- [Prise en main de Teams pour les organismes de santé](teams-in-hc.md)
