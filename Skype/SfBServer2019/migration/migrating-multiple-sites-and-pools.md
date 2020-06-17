---
title: Migration de plusieurs sites et pools
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
description: 'Skype entreprise Server 2019 prend en charge les déploiements multisites et à plusieurs pools. Le processus de migration de plusieurs pools vers Skype entreprise Server 2019 requiert les considérations suivantes :'
ms.openlocfilehash: 4906b05138d546e685a06acecc4f7adc4e88516e
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752656"
---
# <a name="migrating-multiple-sites-and-pools"></a>Migration de plusieurs sites et pools

Skype entreprise Server 2019 prend en charge les déploiements multisites et à plusieurs pools. Le processus de migration de plusieurs pools vers Skype entreprise Server 2019 requiert les considérations suivantes : 
  
1. Après avoir déployé un pool pilote Skype entreprise Server 2019, vous devez définir un sous-ensemble d’utilisateurs pilotes qui seront déplacés vers le pool de Skype entreprise Server 2019, ainsi qu’une méthodologie pour la validation de la fonctionnalité des utilisateurs. Par exemple, après avoir déplacé un utilisateur vers le pool pilote, vérifiez que la stratégie de conférence de l’utilisateur a été déplacée vers Skype entreprise Server 2019. 
    
2. Après avoir déployé un serveur Edge dans le pool pilote, vous devez vérifier que les utilisateurs externes peuvent communiquer avec le pool Skype entreprise Server 2019.

3. Les fonctionnalités de conversation permanente, de mise en miroir SQL et XMPP sont déconseillées dans Skype entreprise Server 2019 et ne sont plus disponibles en tant que fonctionnalités de Skype entreprise Server 2019, mais elles peuvent être poursuivies dans un environnement de coexistence si elles ont été précédemment déployées dans un environnement hérité. Si vous souhaitez continuer à utiliser ces fonctionnalités, vous devez planifier le maintien d’un environnement de coexistence dans lequel certains utilisateurs seront conservés dans les pools hérités.
    
4. Après avoir transféré les serveurs Edge des itinéraires fédérés vers les serveurs Edge de Skype entreprise Server 2019, vous devez vérifier que les utilisateurs fédérés peuvent communiquer avec le pool de Skype entreprise Server 2019.
    
5. Après avoir déplacé tous les utilisateurs et les objets contact non-utilisateur, vous devez vérifier que le pool hérité est vide.
    
6. Après avoir vérifié que le pool hérité est vide, vous pouvez désactiver le pool. 
    
    Pour plus d’informations sur la façon de désactiver le pool hérité et les serveurs, reportez-vous à la section [phase 8 : déclassement des pools hérités](phase-8-decommission-legacy-pools.md).
    

