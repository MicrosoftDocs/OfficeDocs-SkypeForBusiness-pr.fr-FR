---
title: Processus de migration
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: La procédure de migration recommandée et prise en charge pour Skype Entreprise Server 2019 est la migration côte à côte. Cette rubrique décrit pourquoi vous devez utiliser la migration côte à côte et inclut également des informations sur les tests de coexistence.
ms.openlocfilehash: 2343e3d6dd7eadbcfbf2b900d51594253e22f933
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752636"
---
# <a name="migration-process"></a>Processus de migration

La procédure de migration recommandée et prise en charge pour Skype Entreprise Server 2019 est la migration côte à côte. Cette rubrique décrit pourquoi vous devez utiliser la migration côte à côte et inclut également des informations sur les tests de coexistence.
  
## <a name="side-by-side-migration"></a>Migration côte à côte

Il est recommandé d’appliquer la migration côte à côte dans pratiquement toutes les migrations. Lors d’une migration côte à côte, vous déployez un nouveau serveur avec Skype Entreprise Server 2019 avec un serveur correspondant exécutant une version précédente, puis transférez les opérations vers le nouveau serveur. S’il devient nécessaire de revenir à la version précédente, vous devez uniquement revenir aux opérations sur les serveurs d’origine. Sachez que dans cette situation, toute nouvelle réunion planifiée avec les clients mis à niveau ne fonctionnera pas, et que les clients devront également être rétrogradés.
  
## <a name="coexistence-testing"></a>Test de coexistence

Après avoir déployé Skype Entreprise Server 2019 en parallèle avec la version précédente, le déploiement représente un état de test de coexistence de Skype Entreprise Server 2019 et de la version précédente. Dans cet état, il est important de tester et de s’assurer que les services sont démarrés, que chaque site peut être administré et que les clients peuvent communiquer avec les utilisateurs actuels et hérités. Avant la migration de tous les utilisateurs, il est très important de comprendre l’état de chaque déploiement et de veiller à ce que chaque déploiement soit opérationnel et fonctionne correctement. En règle générale, la phase de test de coexistence existe tout au long du test pilote de Skype Entreprise Server 2019. Les utilisateurs hérités sont déplacés vers Skype Entreprise Server 2019 pendant un certain temps pour s’assurer que la compatibilité des applications, ainsi que les fonctionnalités et fonctions fonctionnent correctement. Après le test pilote, les utilisateurs et les applications sont déplacés vers la version de production de Skype Entreprise Server 2019, et les pools et applications hérités de la version précédente sont retirés.
  
