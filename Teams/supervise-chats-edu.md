---
title: Utiliser les conversations surveillées
author: HowlinWolf-92
ms.author: v-mahoffman
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
description: En savoir plus sur les conversations encadrées dans Microsoft Teams réunions.
ms.openlocfilehash: de22efdf314b03872d3d2c8e9b662b8c688349d5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60848117"
---
# <a name="supervised-chats-in-microsoft-teams"></a>Conversations surveillées dans Microsoft Teams

Les établissements d’enseignement fournissent un espace numérique sécurisé et sain aux étudiants. L’espace numérique inclut les courriers électroniques, les réunions et appels en ligne, et la messagerie Teams. Pour éviter un comportement de messagerie inapproprié, de nombreux établissements scolaires désactivent la conversation privée dans Teams. Malheureusement, la désactivation de la conversation bloque également l’opportunité pour les enseignants de joindre les étudiants en privé pour un apprentissage personnalisé. Une fois la conversation désactivée, les étudiants ne peuvent pas joindre les enseignants lorsqu’ils préfèrent ne pas publier de messages publiquement dans les équipes de classe.

La conversation surveillée permet aux enseignants désignés de lancer des conversations avec les étudiants et de bloquer les étudiants de démarrer de nouvelles conversations, sauf si un enseignant approprié est présent. Lorsque la surveillance des conversations est activée, les superviseurs ne sont pas autorisés à quitter des conversations et les autres participants ne sont pas autorisés à les supprimer, ce qui garantit que les conversations impliquant des étudiants sont correctement encadrées.

Ces limitations s’appliquent uniquement aux nouvelles conversations privées créées une fois la conversation surveillée activée. Elles ne s’appliquent pas aux conversations privées, aux conversations de réunion ou aux canaux existants. Pour en savoir plus sur les meilleures pratiques en matière de conversation de réunion, de sécurité des canaux et de maintien de la sécurité des étudiants, consultez l’affichage Préserver la sécurité des étudiants lors de [l’utilisation Teams.](https://support.microsoft.com/topic/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8?ui=en-us&rs=en-us&ad=us#ID0EBBAAA=For_educators&ID0EDD=For_educators)

> [!Note]
> La conversation surveillée protège les nouvelles conversations créées après l’application de la fonctionnalité.  Il ne protège pas les conversations existantes.

## <a name="review-use-cases-for-supervised-chats"></a>Examiner les cas d’utilisation des conversations surveillées

Les exemples suivants duivent une description de la nécessité d’une conversation surveillée.

- Un suivi 1.1 avec un enseignant lorsque les étudiants ne sont pas à l’aise pour partager ou poser des questions publiquement.

- Enseignants atteignant le 1.1 pour un étudiant sur un devoir, une interaction récente avec la classe (ou absence d') ou un autre sujet.

- Discussions de groupe d’étudiants contrôlées par un enseignant.

- Autorisez les enseignants non enseignants à discuter avec les étudiants dans un environnement encadré.

## <a name="enable-supervised-chat"></a>Activer la conversation surveillée

> [!Note]
> Veillez à configurer les rôles d’autorisation de conversation et les stratégies d’autorisation de conversation basées sur les rôles avant d’activer la conversation pour votre établissement afin d’éviter tout accès indésirable aux conversations non sollicitées par les étudiants.

### <a name="define-chat-permission-roles-for-each-user-in-your-environment"></a>Définir des rôles d’autorisation de conversation pour chaque utilisateur de votre environnement

Pour que la conversation surveillée fonctionne comme prévu, chaque utilisateur au sein de votre environnement doit avoir le rôle d’autorisation de conversation correct. Un utilisateur peut avoir attribué trois rôles :

- *Autorisations complètes* – Ce rôle est idéal pour les enseignants qui doivent avoir un accès total aux étudiants et aux autres membres du personnel. Ils peuvent démarrer des conversations avec n’importe quel utilisateur au sein de votre environnement. Les utilisateurs ayant des autorisations complètes sont censés superviser les conversations dans qui ils participent. Ils ne peuvent pas quitter les conversations qu’ils démarrent ou qui sont en cours de suppression dans des locataires fédérés.

- *Autorisations limitées* – Ce rôle est idéal pour les membres du personnel enseignant qui doivent avoir un accès encadré uniquement aux étudiants et un accès total aux autres membres du personnel et aux enseignants. Ils peuvent démarrer des conversations avec des utilisateurs complets ou limités, mais ne peuvent pas démarrer des conversations avec des utilisateurs restreints. Si un utilisateur ayant des autorisations complètes commence une conversation avec un utilisateur dont l’accès est restreint, des utilisateurs limités peuvent y avoir accès. Cet accès se produit parce qu’un utilisateur ayant des autorisations complètes est présent pour superviser la collaboration entre des utilisateurs limités et restreints.

- *Autorisations restreintes* : ce rôle est idéal pour les étudiants qui doivent être encadrés. Ils peuvent uniquement démarrer des conversations avec des utilisateurs ayant des autorisations complètes. Il peut participer à n’importe quelle conversation à qui l’utilisateur 1er 100 a des autorisations complètes l’invite. Dans les cas de conversations fédérées, les utilisateurs restreints peuvent uniquement être ajoutés aux conversations par un utilisateur ayant des autorisations complètes et provenant du client de l’utilisateur restreint.

Pour définir le rôle d’autorisation de conversation de vos **utilisateurs,**  utilisez la stratégie de rôle Autorisations de conversation qui se trouve dans vos options de stratégie de messagerie dans le Teams d’administration. Vous pouvez utiliser PowerShell pour définir des rôles à l’aide de la stratégie ChatPermissionRole avec les valeurs Full, Limited ou Restricted. Cette stratégie se trouve sous CsTeamsMesspolicy.

Pour en savoir plus sur le paramètre. Teams de stratégies Teams packages de stratégies pour l’Éducation et Attribuer des stratégies à un grand ensemble de guides d’utilisateurs.

Des rôles ne peuvent pas être attribués aux invités dans votre client. Un rôle limité est attribué aux invités.

### <a name="allow-supervised-chat"></a>Autoriser la conversation surveillée

La conversation surveillée est désactivée par défaut pour votre client. Une fois que vous avez créé les rôles d’autorisations de  conversation pour vos utilisateurs, vous pouvez activer la conversation surveillée au sein de votre client en allant dans Teams Teams et en définiessant la stratégie des autorisations de conversation basée sur les &gt; **rôles** *sur Activé.*  Vous pouvez également utiliser PowerShell pour activer la conversation surveillée en fixant AllowRoleBasedChatPermissions sur True. Cette cmdlet se trouve sous CsTeamsClientConfiguration.

La conversation supervise doit être activée pour tous les utilisateurs du client et ne peut pas l’être pour seulement une partie de vos utilisateurs.

### <a name="enable-chat"></a>Activer la conversation

Activez la conversation pour tous vos utilisateurs à l’aide de la stratégie de conversation existante disponible dans Teams d’administration.

## <a name="maintain-supervised-chats"></a>Tenir des conversations surveillées

Une fois la conversation surveillée activée, vous devez faire quelques opérations pour vous assurer que les conversations de votre environnement restent sous surveillance :

- Attribuez des rôles appropriés à tous les nouveaux utilisateurs qui rejoignent votre client. Par défaut, un rôle restreint est attribué aux utilisateurs.

- Si un utilisateur avec des autorisations complètes quitte ou est supprimé d’un client, les conversations qu’il a eues sont laissées sans surveillance. Avant de supprimer l’utilisateur d’origine, assurez-vous qu’un autre utilisateur autorisé est ajouté à ces conversations afin que la conversation puisse rester encadrée. Une fois le superviseur d’origine supprimé, de nouveaux participants ne peuvent pas être ajoutés à la conversation, mais les participants actuels peuvent continuer à communiquer.

## <a name="related-topics"></a>Voir aussi

[Conversations supervised for Teams in education](https://support.microsoft.com/topic/supervised-chats-in-microsoft-teams-for-education-ad3aaafc-c85a-416f-95f9-d691f419cbb8?storagetype=live)
