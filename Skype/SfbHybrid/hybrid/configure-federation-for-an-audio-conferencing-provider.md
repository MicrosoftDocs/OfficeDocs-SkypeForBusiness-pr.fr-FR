---
title: Configurer la Fédération pour un fournisseur de services d’audioconférence dans votre déploiement hybride
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 'Résumé: Découvrez comment configurer la Fédération pour un fournisseur de services d’audioconférence dans Skype entreprise online.'
ms.openlocfilehash: faeae07c0662bc252e07bbf66ec463355e439461
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160506"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>Configurer la Fédération pour un fournisseur de services d’audioconférence dans votre déploiement hybride

**Résumé:** Découvrez comment configurer la Fédération pour un fournisseur de services d’audioconférence dans Skype entreprise online.

Si vous souhaitez utiliser un fournisseur de services d’audioconférence (ACP) dans votre déploiement hybride (local avec Online), vous devez configurer la Fédération entre votre déploiement local et le partenaire ACP en tant que serveur partenaire autorisé. Vous pouvez configurer la Fédération en ajoutant le domaine du partenaire ACP et le serveur Edge (il peut également s’agir du proxy d’accès) à la liste des domaines fédérés pour votre déploiement local. Votre partenaire ACP doit ensuite ajouter le nom de domaine complet de votre pool de serveurs Edge sur site à la liste des domaines fédérés autorisés. Pour plus d’informations, contactez votre fournisseur ACP. Votre partenaire ACP doit ensuite ajouter le nom de domaine complet de votre pool de serveurs Edge sur site à la liste des domaines fédérés autorisés.

- **Ajout du domaine ACP et du serveur Edge en tant que domaine fédéré autorisé**

    Pour ajouter le domaine ACP en tant que serveur partenaire autorisé (domaine fédéré autorisé), suivez les étapes décrites dans [configurer la prise en charge des domaines externes autorisés](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx). Pour le serveur Edge, ajoutez le nom de domaine complet (FQDN) du serveur Edge du partenaire ACP. Vous devrez peut-être contacter votre partenaire ACP pour obtenir le nom de domaine complet (FQDN) de son serveur Edge, qui peut également être désigné par votre partenaire ACP en tant que proxy d’accès.

- **Fourniture du nom de domaine complet (FQDN) de votre pool de serveurs Edge au partenaire ACP**

    Le partenaire ACP doit configurer la Fédération pour ajouter votre domaine local en tant que serveur partenaire autorisé en ajoutant le nom de domaine complet (FQDN) de votre pool de serveurs Edge en tant que domaine fédéré autorisé.


