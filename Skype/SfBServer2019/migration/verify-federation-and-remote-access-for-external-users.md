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
description: Après avoir effectué la transition de l’itinéraire de fédération vers le serveur Edge Skype Entreprise Server 2019, vous devez effectuer des tests fonctionnels pour vérifier que la fédération fonctionne comme prévu. Les tests relatifs à l’accès des utilisateurs externes doivent inclure chaque type d’utilisateur externe pris en charge par votre organisation, notamment une partie ou l’ensemble de ce qui suit.
ms.openlocfilehash: b2567f4e46bd39d2748e3a4a3ba6cc5d6c197b11
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751666"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>Vérifier la fédération et l’accès à distance pour les utilisateurs externes

Après avoir effectué la transition de l’itinéraire de fédération vers le serveur Edge Skype Entreprise Server 2019, vous devez effectuer des tests fonctionnels pour vérifier que la fédération fonctionne comme prévu. Les tests relatifs à l’accès des utilisateurs externes doivent inclure chaque type d’utilisateur externe pris en charge par votre organisation, notamment une partie ou l’ensemble de ce qui suit.
  
### <a name="test-connectivity-of-external-users-and-external-access"></a>Tester la connectivité des utilisateurs externes et de l’accès externe

- Utilisateurs d’au moins un domaine fédéré, d’un utilisateur interne sur Skype Entreprise Server 2019 et d’un utilisateur sur l’installation héritée. Testez la messagerie instantanée, la présence, l’audio/vidéo (A/V) et le partage de Bureau.
    
- Utilisateurs de chaque fournisseur de services de messagerie instantanée public pris en charge par votre organisation (et pour lequel la mise en service a été terminée) communiquant avec un utilisateur sur Skype Entreprise Server 2019 et un utilisateur sur l’installation héritée. 
    
- Vérifiez que les utilisateurs anonymes peuvent participer à des conférences.
    
- Utilisateur hébergé sur l’installation héritée à l’aide de l’accès des utilisateurs distants (enregistrement i nto Lync Server/Skype Entreprise en dehors de l’intranet mais sans VPN) avec un utilisateur sur Skype Entreprise Server 2019 et un utilisateur sur l’installation héritée. Testez la messagerie instantanée, la présence, l’audio/vidéo et le partage de Bureau.
    
- Utilisateur hébergé sur Skype Entreprise Server 2019 à l’aide de l’accès des utilisateurs distants (connexion à Skype Entreprise Server 2019 en dehors de l’intranet mais sans VPN) avec un utilisateur sur Skype Entreprise Server 2019 et un utilisateur sur l’installation héritée. Testez la messagerie instantanée, la présence, l’audio/vidéo et le partage de Bureau.
    

