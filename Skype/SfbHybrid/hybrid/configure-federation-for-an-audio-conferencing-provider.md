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
ms.openlocfilehash: 3e01615c65777508c2adead26dd15ca85afbb102e04d8ba57492826942f86672
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54301820"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>Configurer la fédération pour un fournisseur de services d’audioconférence dans votre déploiement hybride

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


**Résumé :** Découvrez comment configurer la fédération pour un fournisseur de services d’audioconférence dans Skype Entreprise Online.

Si vous souhaitez utiliser un fournisseur de services d’audioconférence (ACP) dans votre déploiement hybride (en local avec online), vous devez configurer la fédération entre votre déploiement local et le partenaire ACP en tant que serveur partenaire autorisé. Vous pouvez configurer la fédération en ajoutant le domaine partenaire ACP et le serveur Edge (également appelé proxy d’accès) à la liste des domaines fédérés pour votre déploiement local. Votre partenaire ACP doit ensuite ajouter le nom de domaine général (FQDN) de votre pool de serveurs Edge local à la liste des domaines fédérés autorisés. Pour plus d’informations, contactez votre fournisseur ACP. Votre partenaire ACP doit ensuite ajouter le nom de domaine général (FQDN) de votre pool de serveurs Edge local à la liste des domaines fédérés autorisés.

- **Ajout du domaine ACP et du serveur Edge en tant que domaine fédéré autorisé**

    Pour ajouter le domaine ACP en tant que serveur partenaire autorisé (domaine fédéré autorisé), suivez les étapes de la procédure de configuration de la prise en charge des [domaines externes autorisés.](/previous-versions/office/lync-server-2013/lync-server-2013-configure-support-for-allowed-external-domains) Pour le serveur Edge, ajoutez le nom de groupe du serveur Edge du partenaire ACP. Vous devrez peut-être contacter votre partenaire ACP pour obtenir le nom deqdn de son serveur Edge, qui peut également être appelé proxy d’accès par votre ACP.

- **Fourniture du nom deqdn de votre pool de serveurs Edge au partenaire ACP**

    Le partenaire ACP doit configurer la fédération pour ajouter votre domaine local en tant que serveur partenaire autorisé en ajoutant le nom de domaine de votre pool de serveurs Edge en tant que domaine fédéré autorisé.