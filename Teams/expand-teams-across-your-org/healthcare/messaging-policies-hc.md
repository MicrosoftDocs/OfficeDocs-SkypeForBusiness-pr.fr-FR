---
title: Messagerie sécurisée pour les organisations du secteur des soins de santé utilisant Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Découvrez comment personnaliser une stratégie de messagerie sécurisée pour Microsoft Teams qui peut inclure des notifications de lecture et de priorité.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 77a2024184cb003d5d0ccb0f2b4715b3a3239955
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790626"
---
# <a name="secure-messaging-for-healthcare-organizations"></a>Messagerie sécurisée pour les organismes de santé

Les stratégies de messagerie sont utilisées pour contrôler les fonctionnalités de conversation et de messagerie de canal disponibles pour les utilisateurs dans Microsoft Teams et font partie du déploiement global de la messagerie sécurisée pour les organisations de soins de santé telles que les hôpitals, les associations ou les cabinets de médecin, où la recherche et l’application d’un message dans un délai raisonnable est essentielle, tout comme la connaissance des messages essentiels.

Vous pouvez utiliser la stratégie globale (à l’échelle de l’organisation par défaut) ou créer une ou plusieurs stratégies de messagerie personnalisées pour les membres de votre organisation. Les utilisateurs de votre organisation recevront automatiquement la stratégie globale, sauf si vous créez et leur attribuez une stratégie personnalisée. Après avoir créé une stratégie personnalisée, affectez-la à un utilisateur ou à des groupes d’utilisateurs de votre organisation. Par exemple, vous pouvez choisir d’autoriser uniquement certains rôles à utiliser ces fonctionnalités (par exemple, les médecins et les infirmières uniquement) et d’autres travailleurs (comme l’entité janitorial ou le personnel de cuisine) pour obtenir un ensemble de fonctionnalités plus limité. Décidez par vous-même des besoins de votre organisation. Les conseils qui s’y basent sont tout au plus une suggestion.

Les stratégies peuvent être gérées facilement dans le Centre d’administration [Microsoft Teams](https://admin.teams.microsoft.com) en se connectant avec des informations d’identification d’administrateur et en sélectionnant Stratégies de messagerie dans le volet de navigation gauche. 

 ![Capture d’écran de la page Stratégies de messagerie](../../media/hc-messaging-policy-admin-center.png)

Pour modifier la stratégie de messagerie par défaut existante pour votre organisation, cliquez sur **Global (par** défaut à l’échelle de l’organisation), puis a apporter les modifications nécessaires. Pour créer une stratégie de messagerie personnalisée, **cliquez** sur Ajouter, puis sélectionnez vos paramètres. Sélectionnez **Enregistrer** lorsque vous avez terminé.

![Capture d’écran des paramètres de stratégie de messagerie](../../media/hc-messaging-policy.png)

Les paramètres suivants sont spécifiques aux applications Healthcare et doivent être pris en considération lors de la conception d’une stratégie personnalisée utilisée dans le champ Soins de santé :

## <a name="read-receipts"></a>Read receipts

Les accusés de lecture permettent à l’expéditeur d’un message de conversation de savoir quand son message a été lu par le destinataire dans les conversations de groupe à 1:1 avec au moins 20 personnes. Utilisez ce paramètre pour spécifier si les accusé de lecture sont contrôlés par l’utilisateur, pour tout le monde ou non. Les reçus de lecture de messages sont importants dans les organisations du secteur des soins de santé, car ils suppriment particulièrement l’ôté de l’lisez ou non.

Pour les applications Healthcare, sélectionnez **Utilisateur contrôlé** ou Ouvert pour tout **le monde.** N’ignorez pas  que lorsque vous utilisez le paramètre On pour tout le monde, la seule façon de définir des accusé de réception pour l’ensemble du client consiste soit à n’avoir qu’une stratégie de messagerie pour l’ensemble du client (la stratégie par défaut nommée « Global (par défaut à l’échelle de l’organisation) ») ou que toutes les stratégies de messagerie du client utilisent les mêmes paramètres pour les reçus. La fonctionnalité de lecture/accusé de réception est plus efficace lorsque la fonctionnalité est activée **pour tout le monde.**

*Exemple d’utilisation sans accusé de lecture :* Jakob Jakob, un patient à risque élevé, est admis à l’hôpital.  Sofia Krause est une infirmière travaillant dans l’équipe inter-ins de travailleurs médicaux (IDT), notamment de spécialistes différents, est assignée en tant qu’infirmière principal responsable de ce patient.  Sofia envoie des courriers électroniques et autres messages instantanés à un groupe de infirmières et de médecins qui utilisent plusieurs applications et clients de messagerie, et ne reçoit souvent aucune réponse ou indication si un message a été lu par les membres de l’équipe. En raison de l’enchevêtrement des processus de communication, les médications de Jakob sont malapplées et le reste de son hôpital est étendu.

*Exemple d’utilisation avec les accusé de lecture :* Jakob Jakob, un patient à risque élevé, est admis à l’hôpital.  Sofia Krause est une infirmière travaillant dans l’équipe inter-ins de travailleurs médicaux (IDT), notamment de spécialistes différents, est assignée en tant qu’infirmière principal responsable de ce patient.  Sofia démarre une conversation de groupe avec un groupe de médecins et d’autres infirmières qui travaillent avec le patient pour coordonner les soins et lance un tri d’urgence.  Les infirmières et les médecins communiquent et collaborent sur le plan de soins du patient tout au long du processus de coordination des soins.  Les messages importants et urgents sont envoyés par le biais de conversations à deux ou de groupe. Sofia utilise la fonctionnalité de tickets de lecture pour déterminer si les messages envoyés pour demander un support technique sont remis et lus par le ou les infirmières ciblés. Les cas de patients de Jakob sont quasiment optimaux et il s’en vont plus vite parce que son équipe d’état d’santé communique sans problème.

## <a name="send-urgent-messages-using-priority-notifications"></a>Envoyer des messages urgents à l’aide de notifications de priorité

Un utilisateur peut marquer un message comme *urgent lors* de l’envoi de messages de conversation à d’autres utilisateurs. Cette fonctionnalité permet au personnel de l’hôpital de se prévenir lorsqu’un incident critique nécessite leur attention. Contrairement aux *messages* importants, les notifications de priorité informent les [utilisateurs](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462) toutes les deux minutes pendant jusqu’à 20 minutes ou jusqu’à ce que le message soit choisi et lu par le destinataire, afin de maximiser la probabilité qu’un message soit pris en compte dans un délai raisonnable.

Un administrateur peut activer ou désactiver la possibilité pour les utilisateurs affectés à cette stratégie d’envoyer des notifications de priorité. Cette fonctionnalité est déjà optionnée par défaut. Il est possible que le destinataire du message de priorité n’a pas la même stratégie de messagerie et n’aura pas d’option pour désactiver les messages de priorité de réception. Pour les applications Healthcare, nous vous recommandons d’activer la fonctionnalité pour au moins certains utilisateurs, mais vous devrez déterminer ceux qui le sont.

*Exemple d’utilisation :* Krause de High Risk est en lisez un patient à haut risque, JakobDy. Manuela Carstens, médecin, est le médecin principal pour ce patient.  Sofia envoie un message à Manuela à l’aide d’une notification de priorité demandant de l’aide immédiate sur le tri de Jakob.  Le téléphone de Manuela reçoit le message, mais Manuela n’a pas reçu de vibration du téléphone et ne répond pas. Teams envoie une notification à Manuela et continuera à vous en informer de façon permanente jusqu’à ce qu’elle lise le message. Si les messages de lecture sont également activés, Sofia peut savoir que le message a été lu par Manuela, avant même que Manuela ne décide comment répondre.

## <a name="related-topics"></a>Sujets associés

- [Gérer les stratégies de messagerie dans Teams](../../messaging-policies-in-teams.md)
- [Prise en main de Teams pour les organismes de santé](teams-in-hc.md)
