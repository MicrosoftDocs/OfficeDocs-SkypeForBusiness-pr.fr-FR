---
title: Utiliser des conversations supervisées pour les locataires non éducatifs
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Découvrez les conversations supervisées pour les locataires non éducatifs dans les réunions Microsoft Teams.
ms.openlocfilehash: a06aa7b9ae24e29a70b3c1a4fc74fae134616b6b
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564182"
---
# <a name="supervised-chats-for-non-educational-tenants"></a>Conversations supervisées pour les locataires non éducatifs

La conversation supervisée permet aux superviseurs désignés de lancer des conversations avec toute personne de leur organisation et empêche les utilisateurs de démarrer de nouvelles conversations, sauf si un superviseur approprié est présent. Lorsque la supervision des conversations est activée, les superviseurs ne sont pas autorisés à quitter les conversations et les autres participants ne sont pas autorisés à les supprimer, ce qui garantit que les conversations impliquant des utilisateurs restreints sont correctement supervisées.

Ces limitations sont appliquées uniquement aux nouvelles conversations privées créées après que la conversation supervisée a été entièrement activée. Elles ne s’appliquent pas aux conversations privées, aux conversations de réunion ou aux canaux existants.

La conversation supervisée est adaptée aux besoins des établissements d’enseignement, mais elle est également disponible pour les locataires non-éducatifs.

> [!NOTE]
> La conversation supervisée protège les nouvelles conversations créées après l’application de la fonctionnalité. Il ne protège pas les conversations existantes.

## <a name="enable-supervised-chat"></a>Activer la conversation supervisée

> [!NOTE]
> Veillez à configurer les rôles d’autorisation de conversation et les stratégies d’autorisation de conversation en fonction du rôle avant d’activer la conversation pour votre établissement afin d’éviter les accès utilisateur restreints indésirables aux conversations non supervisées.

**Définissez des rôles d’autorisation de conversation pour chaque utilisateur de votre environnement** :

Pour que la conversation supervisée fonctionne comme prévu, le rôle d’autorisation de conversation approprié doit être attribué à chaque utilisateur de votre environnement. Un utilisateur peut avoir affecté trois rôles :

- Autorisations complètes : ce rôle doit être attribué aux superviseurs de conversation dans votre environnement. Ils peuvent démarrer des conversations avec n’importe quel utilisateur de votre environnement. Les utilisateurs disposant d’autorisations complètes sont censés superviser les conversations aux laquelle ils participent. Ils ne peuvent pas quitter ou être supprimés des conversations qu’ils démarrent ou des conversations qu’ils supervisent dans des locataires fédérés.

- Autorisations limitées : ce rôle est idéal pour les membres du personnel qui doivent uniquement avoir un accès supervisé aux utilisateurs restreints. Ils peuvent démarrer des conversations avec des utilisateurs complets ou limités, mais ils ne peuvent pas démarrer des conversations avec des utilisateurs restreints. Si un utilisateur disposant d’autorisations complètes commence une conversation avec un utilisateur restreint, des utilisateurs limités peuvent être introduits dans la conversation. Cet accès se produit parce qu’un utilisateur disposant d’autorisations complètes est présent pour superviser la collaboration entre les utilisateurs limités et restreints.

- Autorisations restreintes : ce rôle est idéal pour les utilisateurs qui doivent être supervisés. Ils peuvent uniquement démarrer des conversations avec des utilisateurs disposant d’autorisations complètes. Ils peuvent participer à n’importe quelle conversation à laquelle un utilisateur disposant d’autorisations complètes les invite à participer. Dans les cas de conversation fédérée, les utilisateurs restreints peuvent uniquement être ajoutés aux conversations par un utilisateur disposant d’autorisations complètes provenant du locataire de l’utilisateur restreint.

Pour définir le rôle d’autorisation de conversation de vos utilisateurs, utilisez la stratégie de **rôle Autorisations** de conversation disponible dans les options de votre stratégie de messagerie dans le portail d’administration Teams. Vous pouvez utiliser PowerShell pour définir des rôles à l’aide de la stratégie ChatPermissionRole avec les valeurs Full, Limited ou Restricted. Cette stratégie est sous [CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy).

Les rôles ne peuvent pas être attribués aux invités de votre locataire. Le rôle limité est attribué aux invités.

## <a name="allow-supervised-chat"></a>Autoriser la conversation supervisée

La conversation supervisée est désactivée par défaut pour votre locataire. Une fois que vous avez défini des rôles d’autorisation de conversation pour vos utilisateurs, vous pouvez activer la conversation supervisée au sein de votre locataire en accédant aux **paramètres à l’échelle de l’organisation paramètres** \> **Teams** et en définissant la stratégie **d’autorisations de conversation basée sur le rôle** **sur Activé**. Vous pouvez également utiliser PowerShell pour activer la conversation supervisée en définissant AllowRoleBasedChatPermissions sur True. Cette applet de commande se trouve sous [CsTeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration).

La conversation supervisée doit être activée pour tous les utilisateurs du locataire et ne peut pas être activée uniquement pour une partie de vos utilisateurs.

**Activer la conversation** :

Activez la conversation pour tous vos utilisateurs à l’aide de la stratégie de conversation existante disponible dans le Centre d’administration Teams.

**Gérer les conversations supervisées** :

Une fois la conversation supervisée activée initialement, vous devez effectuer quelques opérations pour vous assurer que les conversations dans votre environnement restent supervisées :

- Attribuez les rôles appropriés à tous les nouveaux utilisateurs qui rejoignent votre locataire. Par défaut, un rôle restreint est attribué aux utilisateurs.

- Si un utilisateur disposant d’autorisations complètes quitte ou est supprimé d’un locataire, les conversations qu’il supervisait sont laissées sans assistance. Avant de supprimer l’utilisateur d’origine, assurez-vous qu’un autre utilisateur disposant des autorisations complètes est ajouté à ces conversations afin que la conversation puisse rester supervisée. Une fois le superviseur d’origine supprimé, les nouveaux participants ne peuvent pas être ajoutés à la conversation, mais les participants actuels peuvent continuer à communiquer.
