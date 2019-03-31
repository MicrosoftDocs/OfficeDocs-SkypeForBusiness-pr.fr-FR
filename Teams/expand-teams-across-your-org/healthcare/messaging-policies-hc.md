---
title: Prendre en main messagerie sécurisée pour les organisations de santé
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
description: Prendre en main messagerie sécurisée pour les organisations de santé
ms.openlocfilehash: 58e19cd5f8e39e05b2b2178bcf4062260546e509
ms.sourcegitcommit: 355bcdafa58b6349bb6bc771054f4c9c91387a81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013768"
---
# <a name="get-started-with-secure-messaging-for-healthcare-organizations"></a>Prendre en main messagerie sécurisée pour les organisations de santé

Stratégies de messagerie sont utilisés pour contrôler les conversation et le canal des fonctionnalités de messagerie sont disponibles pour les utilisateurs de Microsoft Teams et font partie du déploiement global de messagerie sécurisée pour les organisations de santé hôpitaux, stages ou bureaux médecin, où recevoir un message choisie et traités en temps voulu est primordial, comme est de savoir lorsque des messages indispensables sont lus.

Vous pouvez utiliser la stratégie par défaut ou créer un ou plusieurs stratégies de messagerie personnalisées pour les personnes dans votre organisation. Après avoir créé une stratégie, vous allez l’attribuer un utilisateur ou groupes d’utilisateurs dans votre organisation. Par exemple, vous pouvez choisir d’autoriser uniquement certains rôles de travail à utiliser ces fonctionnalités (par exemple les docteurs et personnel uniquement) et autres travailleurs (par exemple, le personnel d’entretien ou de graisse) pour obtenir un ensemble plus limité de fonctionnalités. Les besoins de votre organisation dispose de décider, les instructions ici sont au maximum une suggestion de.

Les stratégies peuvent être facilement gérés dans le [Centre d’administration de Microsoft équipes](http://admin.teams.microsoft.com) en vous connectant avec les informations d’identification d’administrateur et le choix des **Stratégies de messagerie** dans le volet de navigation de gauche.

 ![stratégies de messagerie dans les équipes](../../media/messaging-policies-image1.png)

Pour modifier la stratégie de messagerie par défaut existante pour votre organisation, cliquez sur la ligne **Global (à l’échelle de l’organisation par défaut)** , puis apportez vos modifications. Pour créer une nouvelle stratégie de messagerie personnalisée, cliquez sur **nouvelle stratégie** et sélectionnez vos paramètres. Lorsque vous avez terminé, cliquez sur **Enregistrer** .

![Prestataires de paramètres de stratégie de messagerie](../../media/hc-message-policy.png)

Les paramètres suivants sont particulièrement intéressant pour les applications de santé et doivent être considérés lors de la conception d’une stratégie personnalisée utilisée dans le domaine de la santé :

- ![un numéro](../../media/sfbcallout1.png) confirmations de lecture des **confirmations de lecture** permet à l’expéditeur d’un message de conversation à connaître lorsque le message a été lu par le destinataire. Utilisez ce paramètre pour spécifier si des confirmations de lecture utilisateur contrôlée, activée pour tout le monde ou désactivée pour tout le monde. Message lu confirmations sont importantes dans les organisations de santé car elles suppriment sans certitude sur indique si un message a été lu.

  Pour les applications de santé, choisissez **utilisateur contrôlé** ou **activé pour tout le monde**. Gardez à l’esprit que lorsque vous utilisez le paramètre **activé pour tout le monde** , le seul moyen pour définir les confirmations du client entière est de n'avoir qu’une seule stratégie de messagerie pour le client entière (la stratégie par défaut nommé « Global (valeur par défaut à l’échelle de l’organisation) ») ou pour que tous les échanges stratégies dans le client utilisent les mêmes paramètres pour les reçus.

  > [!NOTE]
  > Lorsque lecture confirmations sont utilisées dans un grand groupe de conversation (avec plus de 100 utilisateurs, par exemple), la réception de messages peuvent saturer les messages réels et entraîner confort de conversation. Il s’agit de quelque chose que vous devrez informer les utilisateurs de. Une conversation de groupe plus petite (par exemple 20 utilisateurs ou moins) permet une meilleure utilisation de cette fonctionnalité.

 *Exemple d’utilisation sans confirmations de lecture :* Jakob Roth, un patient risque élevé, est admis à l’hôpital.Sofia Krause est infirmier fonctionne dans le cadre de l’équipe interdisciplinaires (IDT) des travailleurs médicales, y compris les spécialistes différents, est affecté comme coordinateur de soins primaires responsable de ce dernier.  Sofia envoie les messages électroniques et autres messages instantanés à des groupes de personnel et les médecins qui utilisent des clients de messagerie et les applications et souvent n’obtient aucune réponse ou une indication si un message a été lu par les membres de l’équipe. En raison du processus de communication compliquée, médication Jakob est mal appliquée et son restent hôpital est étendue.

  *Exemple d’utilisation avec des confirmations de lecture :* Jakob Roth, un patient risque élevé, est admis à l’hôpital.Sofia Krause est infirmier fonctionne dans le cadre de l’équipe interdisciplinaires (IDT) des travailleurs médicales, y compris les spécialistes différents, est affecté comme coordinateur de soins primaires responsable de ce dernier.  Sofia commence une conversation de groupe avec un ensemble de médecins et autres personnel qui contactera le patient pour coordonner des soins et démarre un triage d’urgence.Le personnel et les médecins communiquent et collaborent sur le plan de soins tout au long du processus de coordination de soins.  Important et d’urgent messages sont transmis par le biais de 1:1 et des conversations de groupe. Sofia utilise la fonctionnalité confirmations de lecture pour déterminer si les messages envoyés demande de prise en charge sont remis et lus par les médecins ciblés ou personnel. Des patients Jakob sont presque optimale et il accède personnel plus tôt, car son équipe de soins communique comme prévu.

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

- ![chiffre deux](../../media/sfbcallout2.png) **les utilisateurs peuvent envoyer des notifications de priorité** d’utiliser ce paramètre pour permettre aux utilisateurs d’envoyer des messages de conversation de priorité à d’autres utilisateurs. Cette fonctionnalité permet de personnel hospitalier eux d’alerte lorsqu’un incident grave requiert une attention particulière. Contrairement aux messages « importants » régulières, les notifications de priorité avertir les utilisateurs à plusieurs reprises pour une période de 20 minutes ou jusqu'à ce que les messages sont récupérés et lu par le destinataire, optimisation de la probabilité que le message est choisie et traité en temps voulu.

  Un administrateur peut activer ou désactiver la possibilité pour les utilisateurs affectés cette stratégie pour envoyer des notifications de priorité. Le paramètre par défaut est désactivé. Le destinataire du message de priorité peuvent ne pas avoir la même stratégie de messagerie et n’auront pas une option pour désactiver la réception de messages de priorité. Pour les applications de santé, il est recommandé d’activer la fonctionnalité pour au moins certains utilisateurs, mais vous devez déterminer ceux.

  *Exemple d’utilisation :* Sofia Krause est pourraitent un patient à haut risque, Jakob Roth. Manuela Carstens, un médecin, est le médecin soins primaires de ce dernier.  Sofia envoie qu'un message à Manuela marqué comme « Haute priorité » et nécessitant une exécution de l’aide avec triage de Jakob.  Téléphone de Manuela reçoit le message, mais Manuela sentiment vibrations téléphone et ne répond pas. Les équipes nouveau avertit Manuela et continuera à persistant avertir de nouveau jusqu'à ce qu’elle lit le message. Si la lecture confirmations sont également activées, Sofia peut être conscient que le message a été lu par Manuela, même avant Manuela décide comment répondre.

## <a name="related-topics"></a>Rubriques connexes

- [Gérer les stratégies de messagerie dans Teams](../../messaging-policies-in-teams.md)
- [Prendre en main équipes pour les organisations de santé](teams-in-hc.md)
