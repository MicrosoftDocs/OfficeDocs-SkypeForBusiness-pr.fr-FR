---
title: Configurer la fédération pour un fournisseur de services d’audioconférence dans votre déploiement hybride
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Résumé : Découvrez comment configurer la fédération pour un fournisseur de services d’audioconférence dans Skype pour Business Online.'
ms.openlocfilehash: 2f89045e7d2ee3e51a6526344d2dcf2f07c0d98d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "25030755"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>Configurer la fédération pour un fournisseur de services d’audioconférence dans votre déploiement hybride

**Résumé :** Découvrez comment configurer la fédération pour un fournisseur de services d’audioconférence dans Skype pour Business en ligne.

Si vous souhaitez utiliser un fournisseur d’audioconférence (ACP) dans votre déploiement hybride (local avec en ligne), vous devez configurer la fédération entre votre déploiement sur site et le partenaire ACP en tant qu’un serveur partenaire autorisé. Vous pouvez configurer la fédération en ajoutant le domaine du partenaire ACP et le serveur de périphérie (il peut également être appelé le Proxy d’accès) à la liste des domaines fédérés pour votre déploiement sur site. Votre partenaire ACP doit ensuite ajouter le nom de domaine complet de votre pool de serveur de transport Edge local à sa liste des domaines fédérés autorisés. Pour plus d’informations, contactez votre fournisseur ACP. Votre partenaire ACP doit ensuite ajouter le nom de domaine complet de votre pool de serveur de transport Edge local à sa liste des domaines fédérés autorisés.

- **Ajout du domaine ACP et du serveur Edge en tant que domaine fédéré autorisé**

    Pour ajouter le domaine ACP comme un serveur partenaire autorisé (autorisé domaine fédéré), suivez les étapes de [Configurer la prise en charge pour les domaines externes autorisés](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx). Pour le serveur Edge, ajoutez le nom de domaine complet du serveur de périphérie du partenaire ACP. Vous devrez peut-être contacter votre partenaire ACP pour obtenir le nom de domaine complet (FQDN) de son serveur Edge, que votre ACP peut également appelé « serveur proxy d’accès ».

- **Fournir le nom de domaine complet de votre Pool de serveurs Edge pour le partenaire ACP**

    Le partenaire ACP doit configurer la fédération pour ajouter votre domaine local en tant que serveur partenaire autorisé en ajoutant le nom de domaine complet (FQDN) de votre pool de serveurs Edge en tant que domaine fédéré autorisé.


