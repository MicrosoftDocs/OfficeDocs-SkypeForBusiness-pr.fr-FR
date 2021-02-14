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
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a><span data-ttu-id="c3ca2-103">Configurer la fédération pour un fournisseur de services d’audioconférence dans votre déploiement hybride</span><span class="sxs-lookup"><span data-stu-id="c3ca2-103">Configure federation for an audio conferencing provider in your hybrid deployment</span></span>

<span data-ttu-id="c3ca2-104">**Résumé :** Découvrez comment configurer la fédération pour un fournisseur de services d’audioconférence dans Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="c3ca2-104">**Summary:** Learn how to configure federation for an audio conferencing provider in Skype for Business Online.</span></span>

<span data-ttu-id="c3ca2-105">Si vous souhaitez utiliser un fournisseur de services d’audioconférence (ACP) dans votre déploiement hybride (en local avec online), vous devez configurer la fédération entre votre déploiement local et le partenaire ACP en tant que serveur partenaire autorisé.</span><span class="sxs-lookup"><span data-stu-id="c3ca2-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (on-premises with online), you need to configure federation between your on-premises deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="c3ca2-106">Vous pouvez configurer la fédération en ajoutant le domaine partenaire ACP et le serveur Edge (également appelé proxy d’accès) à la liste des domaines fédérés pour votre déploiement local.</span><span class="sxs-lookup"><span data-stu-id="c3ca2-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="c3ca2-107">Votre partenaire ACP doit ensuite ajouter le nom de domaine général (FQDN) de votre pool de serveurs Edge local à la liste des domaines fédérés autorisés.</span><span class="sxs-lookup"><span data-stu-id="c3ca2-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="c3ca2-108">Pour plus d’informations, contactez votre fournisseur ACP.</span><span class="sxs-lookup"><span data-stu-id="c3ca2-108">Contact your ACP provider for additional details.</span></span> <span data-ttu-id="c3ca2-109">Votre partenaire ACP doit ensuite ajouter le nom de domaine général (FQDN) de votre pool de serveurs Edge local à la liste des domaines fédérés autorisés.</span><span class="sxs-lookup"><span data-stu-id="c3ca2-109">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

- <span data-ttu-id="c3ca2-110">**Ajout du domaine ACP et du serveur Edge en tant que domaine fédéré autorisé**</span><span class="sxs-lookup"><span data-stu-id="c3ca2-110">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>

    <span data-ttu-id="c3ca2-111">Pour ajouter le domaine ACP en tant que serveur partenaire autorisé (domaine fédéré autorisé), suivez les étapes de la procédure de configuration de la prise en charge des [domaines externes autorisés.](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx)</span><span class="sxs-lookup"><span data-stu-id="c3ca2-111">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure Support for Allowed External Domains](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span></span> <span data-ttu-id="c3ca2-112">Pour le serveur Edge, ajoutez le nom de groupe du serveur Edge du partenaire ACP.</span><span class="sxs-lookup"><span data-stu-id="c3ca2-112">For the Edge Server, add the FQDN of the ACP partner's Edge Server.</span></span> <span data-ttu-id="c3ca2-113">Vous devrez peut-être contacter votre partenaire ACP pour obtenir le nom deqdn de son serveur Edge, qui peut également être appelé proxy d’accès par votre ACP.</span><span class="sxs-lookup"><span data-stu-id="c3ca2-113">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

- <span data-ttu-id="c3ca2-114">**Fourniture du nom deqdn de votre pool de serveurs Edge au partenaire ACP**</span><span class="sxs-lookup"><span data-stu-id="c3ca2-114">**Providing the FQDN of your Edge Server Pool to the ACP partner**</span></span>

    <span data-ttu-id="c3ca2-115">Le partenaire ACP doit configurer la fédération pour ajouter votre domaine local en tant que serveur partenaire autorisé en ajoutant le nom de domaine de votre pool de serveurs Edge en tant que domaine fédéré autorisé.</span><span class="sxs-lookup"><span data-stu-id="c3ca2-115">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>


