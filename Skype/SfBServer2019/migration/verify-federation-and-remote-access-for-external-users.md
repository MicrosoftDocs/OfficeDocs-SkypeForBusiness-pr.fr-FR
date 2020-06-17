---
title: Vérifier la fédération et l’accès à distance pour les utilisateurs externes
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
description: Après avoir effectué la transition de l’itinéraire de Fédération vers le serveur Edge Skype entreprise Server 2019, vous devez effectuer certains tests fonctionnels pour vérifier que la Fédération se comporte comme prévu. Les tests relatifs à l’accès des utilisateurs externes doivent inclure chaque type d’utilisateur externe pris en charge par votre organisation, notamment une partie ou l’ensemble de ce qui suit.
ms.openlocfilehash: b2567f4e46bd39d2748e3a4a3ba6cc5d6c197b11
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751666"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>Vérifier la fédération et l’accès à distance pour les utilisateurs externes

Après avoir effectué la transition de l’itinéraire de Fédération vers le serveur Edge Skype entreprise Server 2019, vous devez effectuer certains tests fonctionnels pour vérifier que la Fédération se comporte comme prévu. Les tests relatifs à l’accès des utilisateurs externes doivent inclure chaque type d’utilisateur externe pris en charge par votre organisation, notamment une partie ou l’ensemble de ce qui suit.
  
### <a name="test-connectivity-of-external-users-and-external-access"></a>Tester la connectivité des utilisateurs externes et de l’accès externe

- Les utilisateurs d’au moins un domaine fédéré, un utilisateur interne sur Skype entreprise Server 2019 et un utilisateur sur l’installation héritée. Testez la messagerie instantanée, la présence, l’audio/vidéo (A/V) et le partage de Bureau.
    
- Les utilisateurs de chaque fournisseur de services de messagerie instantanée public pris en charge par votre organisation (et pour lequel le provisionnement a été effectué) communiquant avec un utilisateur sur Skype entreprise Server 2019 et un utilisateur sur l’installation héritée. 
    
- Vérifiez que les utilisateurs anonymes peuvent participer à des conférences.
    
- Un utilisateur hébergé sur l’installation héritée à l’aide de l’accès des utilisateurs distants (connexion i nPour Lync Server/Skype entreprise depuis l’extérieur de l’intranet mais sans VPN) avec un utilisateur sur Skype entreprise Server 2019 et un utilisateur sur l’installation héritée. Testez la messagerie instantanée, la présence, l’audio/vidéo et le partage de Bureau.
    
- Un utilisateur hébergé sur Skype entreprise Server 2019 à l’aide de l’accès des utilisateurs distants (connexion à Skype entreprise Server 2019 depuis l’extérieur de l’intranet mais sans VPN) avec un utilisateur sur Skype entreprise Server 2019 et un utilisateur sur l’installation héritée. Testez la messagerie instantanée, la présence, l’audio/vidéo et le partage de Bureau.
    

