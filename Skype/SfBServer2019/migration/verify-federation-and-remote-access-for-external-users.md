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
ms.openlocfilehash: 80a7e5042fb9473e3bbd07438c1f0a57026b1bc5454784973870a695946c0cd7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303328"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>Vérifier la fédération et l’accès à distance pour les utilisateurs externes

Après avoir effectué la transition de l’itinéraire de fédération vers le serveur Edge Skype Entreprise Server 2019, vous devez effectuer des tests fonctionnels pour vérifier que la fédération fonctionne comme prévu. Les tests relatifs à l’accès des utilisateurs externes doivent inclure chaque type d’utilisateur externe pris en charge par votre organisation, notamment une partie ou l’ensemble de ce qui suit.
  
### <a name="test-connectivity-of-external-users-and-external-access"></a>Tester la connectivité des utilisateurs externes et de l’accès externe

- Utilisateurs d’au moins un domaine fédéré, un utilisateur interne Skype Entreprise Server 2019 et un utilisateur sur l’installation héritée. Testez la messagerie instantanée, la présence, l’audio/vidéo (A/V) et le partage de Bureau.
    
- Utilisateurs de chaque fournisseur de services de messagerie instantanée public pris en charge par votre organisation (et pour lequel l’approvisionnement a été effectué) communiquant avec un utilisateur sur Skype Entreprise Server 2019 et un utilisateur sur l’installation héritée. 
    
- Vérifiez que les utilisateurs anonymes peuvent participer à des conférences.
    
- Utilisateur hébergé sur l’installation héritée à l’aide de l’accès des utilisateurs distants (enregistrement i nto Lync Server/Skype Entreprise en dehors de l’intranet mais sans VPN) avec un utilisateur sur Skype Entreprise Server 2019 et un utilisateur sur l’installation héritée. Testez la messagerie instantanée, la présence, l’audio/vidéo et le partage de Bureau.
    
- Utilisateur hébergé sur Skype Entreprise Server 2019 utilisant l’accès des utilisateurs distants (connexion à Skype Entreprise Server 2019 en dehors de l’intranet mais sans VPN) avec un utilisateur sur Skype Entreprise Server 2019 et un utilisateur sur l’installation héritée. Testez la messagerie instantanée, la présence, l’audio/vidéo et le partage de Bureau.
    

