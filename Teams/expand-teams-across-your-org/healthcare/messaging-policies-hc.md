---
title: Démarrage avec la messagerie sécurisée pour les organismes de santé
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Démarrage avec la messagerie sécurisée pour les organismes de santé
ms.openlocfilehash: 167021c475edd760bf9b56d550616ebb199f2fb5
ms.sourcegitcommit: 55da03c85237b43b848e7ff9b427304c2d9e568f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2019
ms.locfileid: "34681904"
---
# <a name="get-started-with-secure-messaging-for-healthcare-organizations"></a>Démarrage avec la messagerie sécurisée pour les organismes de santé

Les stratégies de messagerie sont utilisées pour contrôler les fonctionnalités de messagerie et de messagerie de canal qui sont accessibles aux utilisateurs de Microsoft Teams, et qui font partie du déploiement global de la messagerie sécurisée pour les établissements de santé tels que les hôpitaux, les cliniques ou les bureaux de médecins, où le fait de faire en sorte qu’un message est pris en compte et est essentiel, car il est essentiel de lire les messages cruciaux.

Vous pouvez utiliser la stratégie par défaut ou créer une ou plusieurs stratégies de messagerie personnalisées pour les membres de votre organisation. Lorsque vous créez une stratégie, vous lui attribuez un utilisateur ou des groupes d’utilisateurs de votre organisation. Par exemple, vous pouvez choisir d’autoriser uniquement certains rôles de poste pour utiliser ces fonctions (par exemple, les médecins et les infirmières uniquement) et d’autres travailleurs (comme le JANITORIAL ou le personnel de cuisine) pour obtenir un ensemble de fonctionnalités plus limité. Déterminez pour vous-même les besoins de votre organisation, et voici une suggestion.

Vous pouvez facilement gérer les stratégies dans le [Centre d’administration Microsoft teams](http://admin.teams.microsoft.com) en vous connectant avec les informations d’identification d’administrateur et en choisissant stratégies de **messagerie** dans le volet de navigation gauche.

 ![Capture d’écran de la page stratégies de messagerie](../../media/messaging-policies-image1.png)

Pour modifier la stratégie de messagerie par défaut existante pour votre organisation, cliquez sur la ligne **global (par défaut de l’organisation)** , puis apportez les modifications souhaitées. Pour créer une stratégie de messagerie personnalisée, cliquez sur **nouvelle stratégie** et sélectionnez vos paramètres. Lorsque vous avez fin, cliquez sur **Enregistrer** .

![Capture d’écran des paramètres de stratégie de messagerie](../../media/hc-message-policy.png)

Les paramètres suivants sont particulièrement intéressants pour les applications de santé et doivent être pris en compte lors de la conception d’une stratégie personnalisée utilisée dans le champ santé:

## <a name="read-receipts"></a>Confirmations de lecture

- ![Icône du numéro 1, qui fait référence à une légende dans la](../../media/sfbcallout1.png) **** capture d’écran précédente confirmation de lecture des confirmations de lecture permet à l’expéditeur d’un message de savoir lorsque le message a été lu par le destinataire. Utilisez ce paramètre pour spécifier si les confirmations de lecture sont contrôlées par l’utilisateur, activées pour tout le monde, ou désactivées pour tout le monde. Les confirmations de lecture de messages sont importantes dans les organisations de soins de santé, car elles suppriment de façon incertaine l’existence ou non de la lecture d’un message.

  Dans le cas d’applications de santé, sélectionnez géré par l' **utilisateur** ou **activé pour tout le monde**. Sachez que lors de l’utilisation du paramètre **activé pour tout le monde** , la seule façon de définir les accusés de réception pour l’ensemble du client est de n’avoir qu’une seule stratégie de messagerie pour l’ensemble du client (par défaut, la stratégie par défaut nommée «global (org, par défaut)») ou avoir tous les messages les stratégies du client utilisent les mêmes paramètres pour les accusés de réception.

  > [!NOTE]
  > Lors de l’utilisation de confirmations de lecture dans une discussion de groupe importante (par exemple, pour les utilisateurs de plus de 100, par exemple), les messages de bon de réception risquent de submerger les messages et de susciter la frustration de l’utilisateur. Il s’agit d’une information dont les utilisateurs doivent tenir compte. Une discussion de groupe de plus petite taille (peut-être 20 utilisateurs ou moins) utilise une meilleure utilisation de cette fonctionnalité.

    *Exemple d’utilisation sans confirmation de lecture:* Jakob Roth, un patient à haut risque, est admis aux hôpitaux.Le Sofia Krause est une infirmier qui travaille dans le cadre de l’équipe interdisciplinaire (IDT) des travailleurs médicaux, y compris des spécialistes, est désigné comme le coordinateur principal responsable du patient.  Le champ Sofia envoie des messages électroniques et d’autres messages instantanés à un groupe d’infirmières et de médecins utilisant divers clients et applications de messagerie, et n’obtient généralement aucune réponse ou indication qu’un message a été lu par les membres de l’équipe. En raison de processus de communication Tangled, le médicament de Jakob est appliqué de façon incertaine et le reste de l’hôpital est prolongé.

    *Exemple d’utilisation avec confirmations de lecture:* Jakob Roth, un patient à haut risque, est admis aux hôpitaux.Le Sofia Krause est une infirmier qui travaille dans le cadre de l’équipe interdisciplinaire (IDT) des travailleurs médicaux, y compris des spécialistes, est désigné comme le coordinateur principal responsable du patient.  Sofia démarre une discussion de groupe avec un ensemble de médecins et d’autres infirmières qui travaillent avec le patient pour coordonner les soins et commencer un triage d’urgence.Les infirmières et les médecins communiquent et collaborent au plan de soins du patient tout au long du processus de coordination des soins.  Les messages importants et urgents sont envoyés via 1:1 et les conversations de groupe. Sofia utilise la fonctionnalité de confirmation de lecture pour déterminer si les messages envoyés demandant une assistance sont remis et lus par les médecins ou les infirmières ciblés. Les résultats du patient de Jakob sont les plus proches et qu’ils s’ouvrent plus rapidement, car l’équipe de soins communiquera en toute transparence.

## <a name="priority-notifications"></a>Notifications de priorité

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

[!INCLUDE [pri-message-offer](../../includes/pri-message-offer.md)]

- ![Icône du numéro 2, qui référence une légende dans la capture d'](../../media/sfbcallout2.png) écran précédente **les utilisateurs peuvent envoyer des notifications de priorité** utilisez ce paramètre pour autoriser les utilisateurs à envoyer des messages de discussion prioritaire à d’autres utilisateurs. Cette fonctionnalité permet au personnel de l’hôpital de s’avertir lorsque l’un d’eux nécessite son attention. À la différence des messages de type «important» normaux, les notifications de priorité avertissent les utilisateurs de manière répétée sur une période de 20 minutes ou jusqu’à ce que les messages soient sélectionnés et lus par le destinataire, ce qui maximise la probabilité que le message soit reçu et agi en temps opportun.

  Un administrateur peut activer ou désactiver la possibilité pour les utilisateurs ayant affecté cette stratégie d’envoyer des notifications de priorité. Cette fonctionnalité est activée par défaut. Le destinataire du message prioritaire peut ne pas avoir la même stratégie de messagerie et ne peut pas désactiver la réception de messages de priorité. Dans le cas des applications de santé, nous vous recommandons d’activer la fonctionnalité pour au moins quelques utilisateurs, mais vous devez en déterminer les.

  *Exemple d’utilisation:* Sofia Krause est en plus d’admettre un patient à haut risque, Jakob Roth. Manuela Carsten est le médecin principal du patient pour ce patient.  Sofia envoie un message à Manuela à l’aide d’une notification de priorité demandant une assistance immédiate au triage de Jakob.  Le numéro de téléphone de Manuela reçoit le message mais Manuela n’a pas trouvé la vibration du téléphone et ne répond pas. Teams réactive le Manuela et continue d’avertir de nouveau jusqu’à ce qu’il Lise le message. Si les confirmations de lecture sont également activées, vous savez que le message a été lu par Manuela, même avant que Manuela ne décide du mode de réponse.

## <a name="related-topics"></a>Voir aussi

- [Gérer les stratégies de messagerie dans Teams](../../messaging-policies-in-teams.md)
- [Prise en main de Teams pour les organismes de santé](teams-in-hc.md)
