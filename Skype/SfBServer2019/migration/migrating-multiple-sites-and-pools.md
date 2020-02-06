---
title: Migration de plusieurs sites et pools
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
description: 'Skype entreprise Server 2019 prend en charge les déploiements multisites et multi-pool. Le processus de migration de plusieurs regroupements vers Skype entreprise Server 2019 doit prendre en compte les points suivants :'
ms.openlocfilehash: d1257590c431bc15aad4db03908aa6d95fd5fce3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813442"
---
# <a name="migrating-multiple-sites-and-pools"></a>Migration de plusieurs sites et pools

Skype entreprise Server 2019 prend en charge les déploiements multisites et multi-pool. Le processus de migration de plusieurs regroupements vers Skype entreprise Server 2019 doit prendre en compte les points suivants : 
  
1. Après le déploiement d’un pool de pilotes de 2019 Skype entreprise Server, vous devez définir un sous-ensemble d’utilisateurs pilote qui seront déplacés vers le pool Skype entreprise Server 2019 et une méthodologie pour la validation de la fonctionnalité des utilisateurs. Par exemple, après le déplacement d’un utilisateur vers le pool de pilotes, vérifiez que la stratégie de conférence de l’utilisateur a été déplacée vers Skype entreprise Server 2019. 
    
2. Après le déploiement d’un serveur de périphérie dans le pool de pilotes, vous devez vérifier que les utilisateurs externes peuvent communiquer avec le pool Skype entreprise Server 2019.

3. Les fonctionnalités de conversation permanente, de mise en miroir SQL et de fonction XMPP sont déconseillées dans Skype entreprise Server 2019 et ne sont plus disponibles en tant que fonctionnalités de l’API Skype entreprise Server 2019, mais elles peuvent être maintenues dans un environnement de coexistence le cas échéant. environnement hérité. Si vous souhaitez continuer à utiliser ces fonctionnalités, vous devez planifier la poursuite d’un environnement de coexistence pour lequel certains utilisateurs resteront dans les pools hérités.
    
4. Après avoir basculé les serveurs Edge des itinéraires fédérés vers les serveurs de frontière Skype entreprise Server 2019, vous devez vérifier que les utilisateurs fédérés peuvent communiquer avec le pool 2019 du serveur Skype entreprise Server.
    
5. Après avoir déplacé tous les utilisateurs et les objets de contact non-utilisateur, vous devez vérifier que le pool hérité est vide.
    
6. Après avoir vérifié que le pool hérité est vide, vous pouvez désactiver le pool. 
    
    Pour plus d’informations sur la façon de désactiver le pool hérité et les serveurs, voir [phase 8 : déclasser les pools hérités](phase-8-decommission-legacy-pools.md).
    

