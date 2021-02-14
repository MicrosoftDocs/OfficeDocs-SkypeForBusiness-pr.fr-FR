---
title: Configurer la fédération pour un fournisseur de services d’audioconférence dans votre déploiement hybride
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
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
description: 'Résumé : Découvrez comment configurer la fédération pour un fournisseur de services d’audioconférence dans Skype Entreprise Online.'
ms.openlocfilehash: a19704327d1cf5591a1ebb3f62aa23f46fe09d10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726884"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>Configurer la fédération pour un fournisseur de services d’audioconférence dans votre déploiement hybride

**Résumé :** Découvrez comment configurer la fédération pour un fournisseur de services d’audioconférence dans Skype Entreprise Online.

Si vous souhaitez utiliser un fournisseur de services d’audioconférence (ACP) dans votre déploiement hybride (en local avec online), vous devez configurer la fédération entre votre déploiement local et le partenaire ACP en tant que serveur partenaire autorisé. Vous pouvez configurer la fédération en ajoutant le domaine partenaire ACP et le serveur Edge (également appelé proxy d’accès) à la liste des domaines fédérés pour votre déploiement local. Votre partenaire ACP doit ensuite ajouter le nom de domaine général (FQDN) de votre pool de serveurs Edge local à la liste des domaines fédérés autorisés. Pour plus d’informations, contactez votre fournisseur ACP. Votre partenaire ACP doit ensuite ajouter le nom de domaine général (FQDN) de votre pool de serveurs Edge local à la liste des domaines fédérés autorisés.

- **Ajout du domaine ACP et du serveur Edge en tant que domaine fédéré autorisé**

    Pour ajouter le domaine ACP en tant que serveur partenaire autorisé (domaine fédéré autorisé), suivez les étapes de la procédure de configuration de la prise en charge des [domaines externes autorisés.](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx) Pour le serveur Edge, ajoutez le nom de groupe du serveur Edge du partenaire ACP. Vous devrez peut-être contacter votre partenaire ACP pour obtenir le nom deqdn de son serveur Edge, qui peut également être appelé proxy d’accès par votre ACP.

- **Fourniture du nom deqdn de votre pool de serveurs Edge au partenaire ACP**

    Le partenaire ACP doit configurer la fédération pour ajouter votre domaine local en tant que serveur partenaire autorisé en ajoutant le nom de domaine de votre pool de serveurs Edge en tant que domaine fédéré autorisé.


