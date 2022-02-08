---
title: Utiliser des conversations surveillées pour les locataires non scolaires
author: SerdarSoysal
ms.author: serdars
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
description: En savoir plus sur les conversations encadrées pour les locataires non scolaires dans Microsoft Teams réunions.
ms.openlocfilehash: 8ba639953485d03e62d7f75f387f9154f65f9599
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394486"
---
# <a name="supervised-chats-for-non-educational-tenants"></a>Conversations supervised for non-educational tenants

La conversation surveillée permet aux responsables désignés d’entamer des conversations avec l’un des membres de son organisation et de bloquer l’accès des utilisateurs restreints au démarrage de nouvelles conversations, sauf si un responsable approprié est présent. Lorsque la surveillance des conversations est activée, les superviseurs ne sont pas autorisés à quitter des conversations et les autres participants ne sont pas autorisés à les supprimer, ce qui garantit que les conversations impliquant des utilisateurs restreints sont correctement encadrées.

Ces limitations s’appliquent uniquement aux nouvelles conversations privées créées une fois la conversation surveillée activée. Elles ne s’appliquent pas aux conversations privées, aux conversations de réunion ou aux canaux existants.

La conversation encadrée est adaptée aux besoins des établissements d’enseignement, mais elle est également accessible aux clients hors enseignement.

> [!NOTE]
> La conversation surveillée protège les nouvelles conversations créées après l’application de la fonctionnalité. Il ne protège pas les conversations existantes.

## <a name="enable-supervised-chat"></a>Activer la conversation surveillée

> [!NOTE]
> Veillez à configurer les rôles d’autorisation de conversation et les stratégies d’autorisation de conversation basées sur les rôles avant d’activer la conversation pour votre établissement afin d’éviter que les utilisateurs ne limitent l’accès indésirable aux conversations non sollicitées.

**Définir des rôles d’autorisation de conversation pour chaque utilisateur de votre environnement**

Pour que la conversation surveillée fonctionne comme prévu, chaque utilisateur au sein de votre environnement doit avoir le rôle d’autorisation de conversation correct. Un utilisateur peut avoir attribué trois rôles :

- Autorisations complètes : ce rôle doit être attribué aux responsables de la conversation au sein de votre environnement. Ils peuvent démarrer des conversations avec n’importe quel utilisateur au sein de votre environnement. Les utilisateurs ayant des autorisations complètes sont censés superviser les conversations dans qui ils participent. Ils ne peuvent pas quitter les conversations qu’ils démarrent ou qui sont en cours de suppression dans des locataires fédérés.

- Autorisations limitées : ce rôle est idéal pour les membres du personnel enseignant qui ne doivent avoir un accès contrôlé qu’à des utilisateurs restreints. Ils peuvent démarrer des conversations avec des utilisateurs complets ou limités, mais ne peuvent pas démarrer des conversations avec des utilisateurs restreints. Si un utilisateur  ayant des autorisations complètes commence une conversation avec un utilisateur dont l’accès est restreint, des utilisateurs limités peuvent y avoir accès. Cet accès se produit parce qu’un utilisateur ayant des autorisations complètes est présent pour superviser la collaboration entre des utilisateurs limités et restreints.

- Autorisations restreintes : ce rôle est idéal pour les utilisateurs qui doivent être encadrés. Ils peuvent uniquement démarrer des conversations avec des utilisateurs  ayant des autorisations complètes. Il peut participer à n’importe quelle conversation à qui l’utilisateur 1er 100 a des autorisations complètes l’invite. Dans les cas de conversations fédérées, les utilisateurs restreints peuvent uniquement être ajoutés aux conversations par un utilisateur ayant des autorisations complètes et provenant du client de l’utilisateur restreint.

Pour définir le rôle d’autorisation de conversation de vos **utilisateurs**, utilisez la stratégie de rôle Autorisations de conversation qui se trouve dans vos options de stratégie de messagerie dans le Teams d’administration. Vous pouvez utiliser PowerShell pour définir des rôles à l’aide de la stratégie ChatPermissionRole avec les valeurs Full, Limited ou Restricted. Cette stratégie se trouve sous [CsTeamsMesspolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).

Des rôles ne peuvent pas être attribués aux invités dans votre client. Un rôle limité est attribué aux invités.

## <a name="allow-supervised-chat"></a>Autoriser la conversation surveillée

La conversation surveillée est désactivée par défaut pour votre client. Une fois que vous avez créé les rôles d’autorisations de conversation pour vos utilisateurs, vous pouvez activer la conversation surveillée au sein de votre client en allant dans les **paramètres** >  à l’échelle de l’organisation **Teams Paramètres** et en définiessant la stratégie des autorisations de conversation basée sur les **rôles** sur **Activé**. Vous pouvez également utiliser PowerShell pour activer la conversation surveillée en  fixant AllowRoleBasedChatPermissions sur True. Cette cmdlet se trouve sous [CsTeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps).

La conversation supervise doit être activée pour tous les utilisateurs du client et ne peut pas l’être pour seulement une partie de vos utilisateurs.

**Activer la conversation**

Activez la conversation pour tous vos utilisateurs à l’aide de la stratégie de conversation existante disponible dans Teams d’administration.

**Tenir des conversations surveillées**

Une fois la conversation surveillée activée, vous devez faire quelques opérations pour vous assurer que les conversations de votre environnement restent sous surveillance :

- Attribuez des rôles appropriés à tous les nouveaux utilisateurs qui rejoignent votre client. Par défaut, un rôle restreint est attribué aux utilisateurs.

- Si un utilisateur avec des autorisations complètes quitte ou est supprimé d’un client, les conversations qu’il a eues sont laissées sans surveillance. Avant de supprimer l’utilisateur d’origine, assurez-vous qu’un autre utilisateur  autorisé est ajouté à ces conversations afin que la conversation puisse rester encadrée. Une fois le superviseur d’origine supprimé, de nouveaux participants ne peuvent pas être ajoutés à la conversation, mais les participants actuels peuvent continuer à communiquer.
