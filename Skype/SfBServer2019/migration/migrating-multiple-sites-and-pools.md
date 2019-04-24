---
title: Migration de plusieurs sites et pools
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype pour Business Server 2019 prend en charge les déploiements sur plusieurs sites et multi-pool. Le processus de migration de plusieurs pools à Skype pour Business Server 2019 nécessite les considérations suivantes :'
ms.openlocfilehash: 5e369adb51bf95f4e3c3d12688d1e39611aa5692
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231636"
---
# <a name="migrating-multiple-sites-and-pools"></a>Migration de plusieurs sites et pools

Skype pour Business Server 2019 prend en charge les déploiements sur plusieurs sites et multi-pool. Le processus de migration de plusieurs pools à Skype pour Business Server 2019 nécessite les considérations suivantes : 
  
1. Après avoir déployé un Skype pour Business Server 2019 le pool pilote, vous devez définir un sous-ensemble d’utilisateurs qui seront déplacées vers le Skype pour Business Server 2019 pool et une méthode pour valider le fonctionnement des utilisateurs du pilote. Par exemple, après le déplacement d’un utilisateur vers le pool pilote, vérifiez que la stratégie de conférence de l’utilisateur a déplacé à Skype pour Business Server 2019. 
    
2. Après avoir déployé un serveur de périphérie dans le pool pilote, vous devez vérifier que les utilisateurs externes peuvent communiquer avec le Skype pour Business Server 2019 pool.

3. Conversation permanente, la mise en miroir SQL et la fonctionnalité XMPP sont déconseillées dans Skype pour Business Server 2019 et n’est plus disponible en tant que Skype pour les fonctionnalités de Business Server 2019, mais peut être poursuivis dans un environnement de coexistence si elles ont été précédemment déployés dans un environnement hérité. Si vous souhaitez continuer à utiliser ces fonctionnalités, vous devez planifier poursuivre un environnement de coexistence où certains utilisateurs restent dans les pools hérités.
    
4. Après la transition des serveurs des itinéraires fédérés de périphérie pour le pilote Skype pour les serveurs de périphérie 2019 Business Server, vous devez vérifier que les utilisateurs fédérés peuvent communiquer avec le Skype pour Business Server 2019 pool.
    
5. Après avoir déplacé tous les utilisateurs et les objets contact non-utilisateur, vous devez vérifier que le pool hérité est vide.
    
6. Après avoir vérifié que le pool hérité est vide, vous pouvez le désactiver le pool. 
    
    Pour plus d’informations sur la façon de désactiver le pool hérité et les serveurs, voir [Phase 8 : mettre hors service les pools hérités](phase-8-decommission-legacy-pools.md).
    

