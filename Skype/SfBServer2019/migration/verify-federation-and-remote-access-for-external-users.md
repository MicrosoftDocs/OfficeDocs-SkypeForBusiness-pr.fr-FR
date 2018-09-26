---
title: Vérifier la fédération et l’accès à distance pour les utilisateurs externes
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Après la transition de l’itinéraire de fédération pour le Skype pour le serveur de périphérie 2019 Business Server, vous devez effectuer des tests fonctionnels pour vérifier que la fédération fonctionne comme prévu. Tests pour l’accès des utilisateurs externes doivent inclure chaque type d’utilisateur externe prenant en charge votre organisation, dont un ou plusieurs des options suivantes.
ms.openlocfilehash: ce0e2dd6ee7d4fb605f844d7dfb26b3f9d13bf14
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027234"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>Vérifier la fédération et l’accès à distance pour les utilisateurs externes

Après la transition de l’itinéraire de fédération pour le Skype pour le serveur de périphérie 2019 Business Server, vous devez effectuer des tests fonctionnels pour vérifier que la fédération fonctionne comme prévu. Tests pour l’accès des utilisateurs externes doivent inclure chaque type d’utilisateur externe prenant en charge votre organisation, dont un ou plusieurs des options suivantes.
  
### <a name="test-connectivity-of-external-users-and-external-access"></a>Tester la connectivité des utilisateurs externes et l’accès externe

- Les utilisateurs d’au moins un domaine fédéré, un utilisateur interne sur Skype pour Business Server 2019 et un utilisateur hérité installent. Tester la messagerie instantanée, présence, audio/vidéo (A / V) et le partage du bureau.
    
- Les utilisateurs de chaque fournisseur de services de messagerie instantanée publique qui prend en charge de votre organisation (et pour lequel le provisionnement a été effectué) communiquant avec un utilisateur sur Skype pour Business Server 2019 et un utilisateur sur l’installation héritée. 
    
- Vérifier que les utilisateurs anonymes peuvent participer à des conférences.
    
- Un utilisateur hébergé sur hérité installer à l’aide de l’accès des utilisateurs distants (journalisation i /nPour Lync Server/Skype pour les entreprises à partir de l’extérieur de l’intranet, mais sans VPN) à un utilisateur sur Skype pour Business Server 2019 et un utilisateur sur l’installation héritée. Test de messagerie instantanée, présence, A / V et du bureau de partage.
    
- Un utilisateur hébergé sur Skype pour Business Server 2019 à l’aide de l’accès des utilisateurs distants (connexion à Skype pour Business Server 2019 à partir de l’extérieur de l’intranet, mais sans VPN) avec un utilisateur sur Skype pour Business Server 2019 et un utilisateur sur l’installation héritée. Test de messagerie instantanée, présence, A / V et du bureau de partage.
    

