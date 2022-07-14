---
title: Utiliser des conversations supervisées
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: angch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez les conversations supervisées dans les réunions Microsoft Teams.
ms.openlocfilehash: c355730424ec164c2853d4f4dc55956fb7554ce2
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789979"
---
# <a name="supervised-chats-in-microsoft-teams"></a>Conversations supervisées dans Microsoft Teams

Les établissements d’enseignement offrent aux étudiants un espace numérique sûr et sain. L’espace numérique inclut les e-mails, les réunions et les appels en ligne, ainsi que la messagerie dans Teams. Pour éviter un comportement de messagerie inapproprié, de nombreuses écoles désactivent la conversation privée dans Teams. Malheureusement, la désactivation de la conversation bloque également la possibilité pour les enseignants de contacter les étudiants en privé pour un apprentissage personnalisé. Lorsque la conversation est désactivée, les étudiants ne peuvent pas contacter les enseignants lorsqu’ils préfèrent ne pas publier les messages publiquement dans les équipes de classe.

La conversation supervisée permet aux enseignants désignés de lancer des conversations avec les étudiants et empêche les étudiants de commencer de nouvelles conversations, sauf si un enseignant approprié est présent. Lorsque la supervision des conversations est activée, les superviseurs ne sont pas autorisés à quitter les conversations et les autres participants ne sont pas autorisés à les supprimer, ce qui garantit que les conversations impliquant des étudiants sont correctement supervisées.

Ces limitations sont appliquées uniquement aux nouvelles conversations privées créées après que la conversation supervisée a été entièrement activée. Elles ne s’appliquent pas aux conversations privées, aux conversations de réunion ou aux canaux existants. Pour en savoir plus sur les meilleures pratiques pour la conversation de réunion, la sécurité des canaux et la sécurité des étudiants, consultez [La sécurité des étudiants lors de l’utilisation de Teams](https://support.microsoft.com/topic/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8?ui=en-us&rs=en-us&ad=us#ID0EBBAAA=For_educators&ID0EDD=For_educators).

> [!Note]
> La conversation supervisée protège les nouvelles conversations créées après l’application de la fonctionnalité.  Il ne protège pas les conversations existantes.

## <a name="review-use-cases-for-supervised-chats"></a>Examiner les cas d’usage pour les conversations supervisées

Les exemples suivants sont des descriptions du moment où une conversation supervisée est nécessaire.

- Suivi 1.1 avec un enseignant lorsque les étudiants ne sont pas à l’aise de partager ou de poser des questions publiquement.

- Les enseignants communiquent 1.1 avec un étudiant au sujet d’un devoir, d’une interaction récente en classe (ou d’un manque de) ou d’une autre rubrique.

- Discussions de groupe d’étudiants surveillées par un enseignant.

- Autoriser le personnel non enseignant à discuter avec un étudiant dans un environnement supervisé.

## <a name="enable-supervised-chat"></a>Activer la conversation supervisée

> [!Note]
> Veillez à configurer les rôles d’autorisation de conversation et les stratégies d’autorisation de conversation en fonction du rôle avant d’activer la conversation pour votre établissement afin d’éviter l’accès non souhaité des étudiants aux conversations non supervisées.

### <a name="define-chat-permission-roles-for-each-user-in-your-environment"></a>Définir des rôles d’autorisation de conversation pour chaque utilisateur de votre environnement

Pour que la conversation supervisée fonctionne comme prévu, le rôle d’autorisation de conversation approprié doit être attribué à chaque utilisateur de votre environnement. Un utilisateur peut avoir affecté trois rôles :

- *Autorisations complètes* : ce rôle est idéal pour les enseignants qui doivent avoir un accès complet aux étudiants et aux autres membres du personnel. Ils peuvent démarrer des conversations avec n’importe quel utilisateur de votre environnement. Les utilisateurs disposant d’autorisations complètes sont censés superviser les conversations aux laquelle ils participent. Ils ne peuvent pas quitter ou être supprimés des conversations qu’ils démarrent ou des conversations qu’ils supervisent dans des locataires fédérés.

- *Autorisations limitées* : ce rôle est idéal pour les membres du personnel qui doivent uniquement avoir un accès supervisé aux étudiants et avoir un accès complet à d’autres membres du personnel et des enseignants. Ils peuvent démarrer des conversations avec des utilisateurs complets ou limités, mais ils ne peuvent pas démarrer des conversations avec des utilisateurs restreints. Si un utilisateur disposant d’autorisations complètes commence une conversation avec un utilisateur restreint, des utilisateurs limités peuvent être introduits dans la conversation. Cet accès se produit parce qu’un utilisateur disposant d’autorisations complètes est présent pour superviser la collaboration entre les utilisateurs limités et restreints.

- *Autorisations restreintes* : ce rôle est idéal pour les étudiants qui doivent être supervisés. Ils peuvent uniquement démarrer des conversations avec des utilisateurs disposant d’autorisations complètes. Ils peuvent participer à n’importe quelle conversation à laquelle un utilisateur disposant d’autorisations complètes démarre, puis l’invite à le faire. Dans les cas de conversation fédérée, les utilisateurs restreints peuvent uniquement être ajoutés aux conversations par un utilisateur disposant d’autorisations complètes provenant du locataire de l’utilisateur restreint.

Pour définir le rôle d’autorisation de conversation de vos **utilisateurs**, utilisez la stratégie de **rôle** Autorisations de conversation disponible dans les options de votre stratégie de messagerie dans le portail d’administration Teams. Vous pouvez utiliser PowerShell pour définir des rôles à l’aide de la stratégie ChatPermissionRole avec les valeurs Full, Limited ou Restricted. Cette stratégie est sous CsTeamsMessagingPolicy.

Pour en savoir plus sur les paramètres. Les stratégies Teams voient les stratégies et les packages de stratégie Teams pour l’éducation et attribuent des stratégies à de grands ensembles de guides d’utilisateurs.

Les rôles ne peuvent pas être attribués aux invités de votre locataire. Le rôle limité est attribué aux invités.

### <a name="allow-supervised-chat"></a>Autoriser la conversation supervisée

La conversation supervisée est désactivée par défaut pour votre locataire. Une fois que vous avez défini des rôles d’autorisation de conversation pour vos utilisateurs, vous pouvez activer la conversation supervisée au sein de votre locataire en accédant aux **paramètres** **Teams** &gt; et en définissant la stratégie **d’autorisations de conversation basée sur les rôles** *sur Activé.* Vous pouvez également utiliser PowerShell pour activer la conversation supervisée en définissant AllowRoleBasedChatPermissions sur True. Cette applet de commande se trouve sous CsTeamsClientConfiguration.

La conversation supervisée doit être activée pour tous les utilisateurs du locataire et ne peut pas être activée uniquement pour une partie de vos utilisateurs.

### <a name="enable-chat"></a>Activer la conversation

Activez la conversation pour tous vos utilisateurs à l’aide de la stratégie de conversation existante disponible dans le Centre d’administration Teams.

## <a name="maintain-supervised-chats"></a>Gérer les conversations supervisées

Une fois la conversation supervisée activée initialement, vous devez effectuer quelques opérations pour vous assurer que les conversations dans votre environnement restent supervisées :

- Attribuez les rôles appropriés à tous les nouveaux utilisateurs qui rejoignent votre locataire. Par défaut, un rôle restreint est attribué aux utilisateurs.

- Si un utilisateur disposant d’autorisations complètes quitte ou est supprimé d’un locataire, les conversations qu’il supervisait sont laissées sans assistance. Avant de supprimer l’utilisateur d’origine, assurez-vous qu’un autre utilisateur disposant des autorisations complètes est ajouté à ces conversations afin que la conversation puisse rester supervisée. Une fois le superviseur d’origine supprimé, les nouveaux participants ne peuvent pas être ajoutés à la conversation, mais les participants actuels peuvent continuer à communiquer.

## <a name="related-topics"></a>Sujets associés

[Conversations supervisées pour Teams dans l’éducation](https://support.microsoft.com/topic/supervised-chats-in-microsoft-teams-for-education-ad3aaafc-c85a-416f-95f9-d691f419cbb8?storagetype=live)
