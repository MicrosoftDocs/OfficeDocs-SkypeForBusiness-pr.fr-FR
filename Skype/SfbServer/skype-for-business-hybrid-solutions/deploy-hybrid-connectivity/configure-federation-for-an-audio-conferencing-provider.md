---
title: Configurer la fédération pour un fournisseur de services d’audioconférence dans votre déploiement hybride
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 08dedcce-0d3f-45da-8282-cf2634a41665
description: 'Résumé : Découvrez comment configurer la fédération pour un fournisseur de services d’audioconférence dans Skype pour Business Online.'
ms.openlocfilehash: 95ca4e369e42bf265d243842067f531907e26531
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>Configurer la fédération pour un fournisseur de services d’audioconférence dans votre déploiement hybride
 
**Résumé :** Découvrez comment configurer la fédération pour un fournisseur de services d’audioconférence dans Skype pour Business en ligne.
  
Si vous souhaitez utiliser un fournisseur d’audioconférence (ACP) dans votre déploiement hybride (local avec en ligne), vous devez configurer la fédération entre votre déploiement sur site et le partenaire ACP en tant qu’un serveur partenaire autorisé. Vous pouvez configurer la fédération en ajoutant le domaine du partenaire ACP et le serveur de périphérie (il peut également être appelé le Proxy d’accès) à la liste des domaines fédérés pour votre déploiement sur site. Votre partenaire ACP doit ensuite ajouter le nom de domaine complet de votre pool de serveur de transport Edge local à sa liste des domaines fédérés autorisés. Pour plus d’informations, contactez votre fournisseur ACP. Votre partenaire ACP doit ensuite ajouter le nom de domaine complet de votre pool de serveur de transport Edge local à sa liste des domaines fédérés autorisés.
  
- **Ajout du domaine ACP et du serveur Edge en tant que domaine fédéré autorisé**
    
    Pour ajouter le domaine ACP comme un serveur partenaire autorisé (autorisé domaine fédéré), suivez les étapes de [Configurer la prise en charge pour les domaines externes autorisés](http://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx). Pour le serveur Edge, ajoutez le nom de domaine complet du serveur de périphérie du partenaire ACP. Vous devrez peut-être contacter votre partenaire ACP pour obtenir le nom de domaine complet (FQDN) de son serveur Edge, que votre ACP peut également appelé « serveur proxy d’accès ».
    
- **Transmission du nom de domaine complet (FQDN) de votre pool de serveurs Edge au partenaire ACP**
    
    Le partenaire ACP doit configurer la fédération pour ajouter votre domaine local en tant que serveur partenaire autorisé en ajoutant le nom de domaine complet (FQDN) de votre pool de serveurs Edge en tant que domaine fédéré autorisé.
    

