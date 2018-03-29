---
title: Configurer la fédération pour un fournisseur de conférence audio dans votre déploiement hybride
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 08dedcce-0d3f-45da-8282-cf2634a41665
description: 'Résumé : Apprenez à configurer la fédération pour un fournisseur de conférence audio dans Skype Business Online.'
ms.openlocfilehash: 8ac7e8d365b2a46ac37091510c6909ea996d8ada
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>Configurer la fédération pour un fournisseur de conférence audio dans votre déploiement hybride
 
**Résumé :** Apprenez à configurer la fédération pour un fournisseur de conférence audio dans Skype Business Online.
  
Si vous souhaitez utiliser un fournisseur de conférence Audio (ACP) dans votre déploiement hybride (local avec en ligne), vous devez configurer la fédération entre votre déploiement sur site et le partenaire ACP sous la forme d’un serveur partenaire autorisé. Vous pouvez configurer la fédération en ajoutant le domaine de partenaire ACP et un serveur de transport Edge (Cela peut également être appelé le Proxy d’accès) à la liste des domaines de fédéré pour votre déploiement sur site. Votre partenaire ACP, doit ajouter le nom de domaine complet de votre pool de serveur de transport Edge sur site à la liste de domaines fédérés autorisés. Pour plus d’informations, contactez votre fournisseur ACP. Votre partenaire ACP, doit ajouter le nom de domaine complet de votre pool de serveur de transport Edge sur site à la liste de domaines fédérés autorisés.
  
- **Ajout du domaine ACP et du serveur Edge en tant que domaine fédéré autorisé**
    
    Pour ajouter le domaine ACP comme un serveur de partenaire autorisé (autorisés domaine fédéré), suivez les étapes de [Prise en charge de configuration pour les domaines externes autorisés](http://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx). Pour le serveur Edge, ajoutez le nom de domaine complet de serveur de transport Edge du partenaire ACP. Vous devrez peut-être contacter votre partenaire ACP pour obtenir le nom de domaine complet (FQDN) de son serveur Edge, que votre ACP peut également appelé « serveur proxy d’accès ».
    
- **Transmission du nom de domaine complet (FQDN) de votre pool de serveurs Edge au partenaire ACP**
    
    Le partenaire ACP doit configurer la fédération pour ajouter votre domaine local en tant que serveur partenaire autorisé en ajoutant le nom de domaine complet (FQDN) de votre pool de serveurs Edge en tant que domaine fédéré autorisé.
    

