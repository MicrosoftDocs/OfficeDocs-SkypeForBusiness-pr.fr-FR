---
title: Vérifier la fédération et l’accès à distance pour les utilisateurs externes
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Après la transition de l’itinéraire de Fédération au serveur Edge 2019 de Skype entreprise Server, vous devez effectuer certains tests fonctionnels pour vérifier que la Fédération s’exécute comme prévu. Les tests pour l’accès utilisateur externe doivent inclure chaque type d’utilisateur externe pris en charge par votre organisation, y compris tout ou partie des éléments suivants.
ms.openlocfilehash: ea17cbc8643d864f464da8e8a582191504970059
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243767"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>Vérifier la fédération et l’accès à distance pour les utilisateurs externes

Après la transition de l’itinéraire de Fédération au serveur Edge 2019 de Skype entreprise Server, vous devez effectuer certains tests fonctionnels pour vérifier que la Fédération s’exécute comme prévu. Les tests pour l’accès utilisateur externe doivent inclure chaque type d’utilisateur externe pris en charge par votre organisation, y compris tout ou partie des éléments suivants.
  
### <a name="test-connectivity-of-external-users-and-external-access"></a>Tester la connectivité des utilisateurs externes et des accès externes

- Utilisateurs d’au moins un domaine fédéré, d’un utilisateur interne sur Skype entreprise Server 2019 et un utilisateur sur l’installation héritée. Testez la messagerie instantanée, la présence, les appels audio/vidéo (A/V) et le partage de bureau.
    
- Utilisateurs de chaque fournisseur de services de messagerie instantanée publique pris en charge par votre organisation (et pour lequel la mise en service a été effectuée) communique avec un utilisateur sur Skype entreprise Server 2019 et un utilisateur sur l’installation héritée. 
    
- Vérifiez que les utilisateurs anonymes peuvent participer à des conférences.
    
- Un utilisateur A hébergé une installation héritée à l’aide de l’accès distant aux utilisateurs (journalisation i nPour Lync Server/Skype entreprise hors de l’intranet, mais sans VPN) avec un utilisateur sur Skype entreprise Server 2019 et un utilisateur sur l’installation héritée. Testez la messagerie instantanée, la présence, A/V et le partage du bureau.
    
- Un utilisateur hébergé sur Skype entreprise Server 2019 à l’aide de l’accès des utilisateurs distants (connexion à Skype entreprise Server 2019 hors de l’intranet mais sans VPN) avec un utilisateur sur Skype entreprise Server 2019, et un utilisateur sur l’installation héritée. Testez la messagerie instantanée, la présence, A/V et le partage du bureau.
    

