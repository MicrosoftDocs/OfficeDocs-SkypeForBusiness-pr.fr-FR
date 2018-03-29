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
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a><span data-ttu-id="66fcf-103">Configurer la fédération pour un fournisseur de conférence audio dans votre déploiement hybride</span><span class="sxs-lookup"><span data-stu-id="66fcf-103">Configure federation for an audio conferencing provider in your hybrid deployment</span></span>
 
<span data-ttu-id="66fcf-104">**Résumé :** Apprenez à configurer la fédération pour un fournisseur de conférence audio dans Skype Business Online.</span><span class="sxs-lookup"><span data-stu-id="66fcf-104">**Summary:** Learn how to configure federation for an audio conferencing provider in Skype for Business Online.</span></span>
  
<span data-ttu-id="66fcf-105">Si vous souhaitez utiliser un fournisseur de conférence Audio (ACP) dans votre déploiement hybride (local avec en ligne), vous devez configurer la fédération entre votre déploiement sur site et le partenaire ACP sous la forme d’un serveur partenaire autorisé.</span><span class="sxs-lookup"><span data-stu-id="66fcf-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (on-premises with online), you need to configure federation between your on-premises deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="66fcf-106">Vous pouvez configurer la fédération en ajoutant le domaine de partenaire ACP et un serveur de transport Edge (Cela peut également être appelé le Proxy d’accès) à la liste des domaines de fédéré pour votre déploiement sur site.</span><span class="sxs-lookup"><span data-stu-id="66fcf-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="66fcf-107">Votre partenaire ACP, doit ajouter le nom de domaine complet de votre pool de serveur de transport Edge sur site à la liste de domaines fédérés autorisés.</span><span class="sxs-lookup"><span data-stu-id="66fcf-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="66fcf-108">Pour plus d’informations, contactez votre fournisseur ACP.</span><span class="sxs-lookup"><span data-stu-id="66fcf-108">Contact your ACP provider for additional details.</span></span> <span data-ttu-id="66fcf-109">Votre partenaire ACP, doit ajouter le nom de domaine complet de votre pool de serveur de transport Edge sur site à la liste de domaines fédérés autorisés.</span><span class="sxs-lookup"><span data-stu-id="66fcf-109">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>
  
- <span data-ttu-id="66fcf-110">**Ajout du domaine ACP et du serveur Edge en tant que domaine fédéré autorisé**</span><span class="sxs-lookup"><span data-stu-id="66fcf-110">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>
    
    <span data-ttu-id="66fcf-111">Pour ajouter le domaine ACP comme un serveur de partenaire autorisé (autorisés domaine fédéré), suivez les étapes de [Prise en charge de configuration pour les domaines externes autorisés](http://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span><span class="sxs-lookup"><span data-stu-id="66fcf-111">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure Support for Allowed External Domains](http://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span></span> <span data-ttu-id="66fcf-112">Pour le serveur Edge, ajoutez le nom de domaine complet de serveur de transport Edge du partenaire ACP.</span><span class="sxs-lookup"><span data-stu-id="66fcf-112">For the Edge Server, add the FQDN of the ACP partner's Edge Server.</span></span> <span data-ttu-id="66fcf-113">Vous devrez peut-être contacter votre partenaire ACP pour obtenir le nom de domaine complet (FQDN) de son serveur Edge, que votre ACP peut également appelé « serveur proxy d’accès ».</span><span class="sxs-lookup"><span data-stu-id="66fcf-113">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>
    
- <span data-ttu-id="66fcf-114">**Transmission du nom de domaine complet (FQDN) de votre pool de serveurs Edge au partenaire ACP**</span><span class="sxs-lookup"><span data-stu-id="66fcf-114">**Provide the FQDN of your Edge Server Pool to the ACP partner**</span></span>
    
    <span data-ttu-id="66fcf-115">Le partenaire ACP doit configurer la fédération pour ajouter votre domaine local en tant que serveur partenaire autorisé en ajoutant le nom de domaine complet (FQDN) de votre pool de serveurs Edge en tant que domaine fédéré autorisé.</span><span class="sxs-lookup"><span data-stu-id="66fcf-115">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>
    

