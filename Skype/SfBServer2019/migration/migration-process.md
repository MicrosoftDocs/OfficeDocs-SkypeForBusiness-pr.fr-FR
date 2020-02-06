---
title: Processus de migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: La procédure de migration recommandée et prise en charge pour Skype entreprise Server 2019 est une migration côte à côte. Cette rubrique décrit les raisons pour lesquelles vous devez utiliser la migration côte à côte et inclut des informations sur les tests de coexistence.
ms.openlocfilehash: 7d8ce6513535871939894092850ad0526b1b6a63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813412"
---
# <a name="migration-process"></a>Processus de migration

La procédure de migration recommandée et prise en charge pour Skype entreprise Server 2019 est une migration côte à côte. Cette rubrique décrit les raisons pour lesquelles vous devez utiliser la migration côte à côte et inclut des informations sur les tests de coexistence.
  
## <a name="side-by-side-migration"></a>Migration côte à côte

Dans presque chaque migration, utilisez le chemin de migration côte à côte. Dans le cas d’une migration côte à côte, vous déployez un nouveau serveur avec Skype entreprise Server 2019, parallèlement à un serveur correspondant exécutant une version antérieure, puis transférez les opérations vers le nouveau serveur. S’il est nécessaire de revenir à la version précédente, il est nécessaire de basculer vers les serveurs d’origine. Notez que dans ce cas, toutes les réunions planifiées avec des clients mis à niveau ne fonctionneront pas et les clients devront également être mis à niveau vers une version antérieure.
  
## <a name="coexistence-testing"></a>Tests de coexistence

Après avoir déployé Skype entreprise Server 2019 parallèlement à la version précédente, le déploiement représente un état de test de coexistence de Skype entreprise Server 2019 et la version précédente. Dans cet État, il est important de tester et de veiller à ce que les services soient démarrés, chaque site peut être administré et les clients peuvent communiquer avec leurs utilisateurs actuels et propriétaires. Avant de procéder à la migration de tous les utilisateurs, il est très important de comprendre l’état de chacun d’eux et de garantir le fonctionnement correct de chaque déploiement. En règle générale, la phase de test de coexistence existe tout au long des tests pilotes de Skype entreprise Server 2019. Les anciens utilisateurs sont déplacés vers Skype entreprise Server 2019 pendant un certain temps pour garantir la compatibilité et les fonctionnalités de l’application. Après le test pilote, les utilisateurs et les applications sont déplacés vers la version de production de Skype entreprise Server 2019, et les applications et les pools hérités de la version précédente sont obsolètes.
  
