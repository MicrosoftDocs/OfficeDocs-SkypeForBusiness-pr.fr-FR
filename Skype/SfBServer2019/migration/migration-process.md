---
title: Processus de migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: La procédure de migration pris en charge et recommandé de Skype pour Business Server 2019 est migration côte à côte. Cette rubrique explique pourquoi vous devez utiliser migration côte à côte et contient également des informations sur le test de coexistence.
ms.openlocfilehash: e14226721cbc09bd1f0ac66b47dbd1710712eb17
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876291"
---
# <a name="migration-process"></a>Processus de migration

La procédure de migration pris en charge et recommandé de Skype pour Business Server 2019 est migration côte à côte. Cette rubrique explique pourquoi vous devez utiliser migration côte à côte et contient également des informations sur le test de coexistence.
  
## <a name="side-by-side-migration"></a>Migration côte à côte

Dans pratiquement tous migration, vous devez utiliser le chemin d’accès de la migration côte à côte. Dans une migration côte à côte, vous déployez un nouveau serveur avec Skype pour Business Server 2019 parallèlement à un serveur qui exécute une version précédente correspondant et opérations transférez vers le nouveau serveur. Si vous devez revenir à la version précédente, vous devez uniquement retransférer les opérations vers les serveurs d’origine. N’oubliez pas que les nouvelles réunions planifiées avec des clients mis à niveau ne fonctionnent pas dans ce cas, et les clients doivent également être mis à niveau.
  
## <a name="coexistence-testing"></a>Test de coexistence

Une fois que vous avez déployé Skype pour Business Server 2019 parallèlement à la version précédente, le déploiement représente une coexistence test état de Skype pour Business Server 2019 et la version précédente. Dans cet état, il est important de tester et vérifier que les services sont démarrés et chaque site peut être administré, et les clients peuvent communiquer avec des utilisateurs actuels et hérités. Avant la migration de tous les utilisateurs, il est très important de connaître l’état de chaque déploiement et assurez-vous que chaque déploiement est fonctionnel et qu’elle fonctionne correctement. En règle générale, la phase de test de coexistence existe dans le test pilote du Skype pour Business Server 2019. Les utilisateurs hérités sont déplacés vers Skype pour Business Server 2019 pour une période de temps pour assurer la compatibilité des applications et les fonctions et fonctionnalités fonctionnent correctement. Après le test pilote, les utilisateurs et les applications sont déplacées vers la version de production de Skype pour Business Server 2019 et les pools hérités et les applications de la version précédente sont supprimées.
  
