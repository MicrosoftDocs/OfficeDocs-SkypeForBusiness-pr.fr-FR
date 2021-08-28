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
ms.localizationpriority: medium
description: 'Skype Entreprise Server 2019 prend en charge les déploiements sur plusieurs sites et plusieurs pool. Le processus de migration de plusieurs pools vers Skype Entreprise Server 2019 nécessite les considérations suivantes :'
ms.openlocfilehash: 514c606b580f0602ebf8ce6b1a41e553445aa4f2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613374"
---
# <a name="migrating-multiple-sites-and-pools"></a>Migration de plusieurs sites et pools

Skype Entreprise Server 2019 prend en charge les déploiements sur plusieurs sites et plusieurs pool. Le processus de migration de plusieurs pools vers Skype Entreprise Server 2019 nécessite les considérations suivantes : 
  
1. Après avoir déployé un pool pilote Skype Entreprise Server 2019, vous devez définir un sous-ensemble d’utilisateurs pilotes qui seront déplacés vers le pool Skype Entreprise Server 2019 et une méthodologie pour valider les fonctionnalités des utilisateurs. Par exemple, après avoir déplacé un utilisateur vers le pool pilote, vérifiez que la stratégie de conférence de l’utilisateur a été déplacée vers Skype Entreprise Server 2019. 
    
2. Après avoir déployé un serveur Edge dans le pool pilote, vous devez vérifier que les utilisateurs externes peuvent communiquer avec le pool Skype Entreprise Server 2019.

3. Les fonctionnalités de conversation permanente, de mise en miroir SQL et de XMPP sont dépréciées dans Skype Entreprise Server 2019 et ne sont plus disponibles en tant que fonctionnalités Skype Entreprise Server 2019, mais elles peuvent être poursuivies dans un environnement de coexistence si elles ont été précédemment déployées dans un environnement hérité. Si vous souhaitez continuer à utiliser ces fonctionnalités, vous devez planifier de continuer avec un environnement de coexistence dans lequel certains utilisateurs resteront dans des pools hérités.
    
4. Après avoir fait passer les serveurs Edge des itinéraires fédérés vers les serveurs Edge Skype Entreprise Server 2019 pilotes, vous devez vérifier que les utilisateurs fédérés peuvent communiquer avec le pool Skype Entreprise Server 2019.
    
5. Après le déplacement de tous les utilisateurs et des objets contact non-utilisateur, vous devez vérifier que le pool hérité est vide.
    
6. Après avoir vérifié que le pool hérité est vide, vous pouvez le désactiver. 
    
    Pour plus d’informations sur la désactivation du pool et des serveurs hérités, voir Phase 8 : Désaffecter les [pools hérités.](phase-8-decommission-legacy-pools.md)
    

