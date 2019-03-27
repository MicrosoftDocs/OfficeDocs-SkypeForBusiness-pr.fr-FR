---
title: Configurer les stratégies de voix, les enregistrements d’utilisation PSTN et les itinéraires de communications vocales dans Skype pour les entreprises
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: 'Résumé : Découvrez comment configurer des stratégies de voix, les enregistrements d’utilisation PSTN et les itinéraires de communications vocales dans Skype pour Business Server.'
ms.openlocfilehash: 37cc90e76a4ebf93ebd1ab1d61595b7fb8f6db38
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30872765"
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business"></a><span data-ttu-id="e1953-103">Configurer les stratégies de voix, les enregistrements d’utilisation PSTN et les itinéraires de communications vocales dans Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="e1953-103">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>
 
<span data-ttu-id="e1953-104">**Résumé :** Découvrez comment configurer des stratégies de voix, les enregistrements d’utilisation PSTN et les itinéraires de communications vocales dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="e1953-104">**Summary:** Learn how to configure voice policies, PSTN usage records, and voice routes in Skype for Business Server.</span></span>
  
<span data-ttu-id="e1953-p101">Les stratégies de voix, les enregistrements d’utilisation RTC et les itinéraires des communications vocales sont étroitement liés. Pour configurer une stratégie de voix vous devez sélectionner des fonctionnalités d’appel, puis affecter à la stratégie des enregistrements d’utilisation RTC, qui spécifient les droits accordés aux utilisateurs et aux groupes auxquels la stratégie de voix est affectée. Les itinéraires des communications vocales reçoivent également des enregistrements d’utilisation RTC, qui permettent d’associer les itinéraires aux utilisateurs autorisés à les utiliser. En d’autres termes, les utilisateurs ne peuvent effectuer que des appels utilisant des itinéraires pour lesquels ils disposent d’enregistrements d’utilisation RTC correspondants.</span><span class="sxs-lookup"><span data-stu-id="e1953-p101">Voice policies, PSTN usage records, and voice routes are integrally related. You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy. Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them. That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>
  
<span data-ttu-id="e1953-109">La procédure recommandée pour un nouveau déploiement de Voix Entreprise est de commencer par configurer une stratégie de voix qui comprend les enregistrements d’utilisation RTC appropriés, puis d’associer les itinéraires appropriés à chaque enregistrement d’utilisation RTC.</span><span class="sxs-lookup"><span data-stu-id="e1953-109">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e1953-110">Vous pouvez également créer des stratégies de voix avec l’étendue *utilisateur* et les affecter à des utilisateurs individuels ou des groupes.</span><span class="sxs-lookup"><span data-stu-id="e1953-110">You can also create voice policies with  *user*  scope and assign them to individual users or groups.</span></span>
  
<span data-ttu-id="e1953-111">Pour connaître en détail la marche à suivre pour effectuer chacune de ces tâches, reportez-vous aux procédures de cette section.</span><span class="sxs-lookup"><span data-stu-id="e1953-111">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="e1953-112">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="e1953-112">In this section</span></span>

- [<span data-ttu-id="e1953-113">Créer ou modifier une stratégie de voix et configurer les enregistrements d’utilisation PSTN dans Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="e1953-113">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)
    
- [<span data-ttu-id="e1953-114">Configurer la redirection vers la messagerie vocale dans Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="e1953-114">Configure voice mail escape in Skype for Business</span></span>](configure-voice-mail-escape.md)
    
- [<span data-ttu-id="e1953-115">Afficher les enregistrements d’utilisation PSTN dans Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="e1953-115">View PSTN usage records in Skype for Business</span></span>](view-pstn-usage-records.md)
    
- [<span data-ttu-id="e1953-116">Créer ou modifier un itinéraire de communications vocales dans Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="e1953-116">Create or modify a voice route in Skype for Business</span></span>](create-or-modify-a-voice-route.md)
    
- [<span data-ttu-id="e1953-117">Exporter ou importer un fichier de configuration d’itinéraire de voix dans Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="e1953-117">Export or import a voice route configuration file in Skype for Business</span></span>](voice-route-configuration-import-export.md)
    
- [<span data-ttu-id="e1953-118">Publier des modifications en attente de la configuration de routage voix dans Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="e1953-118">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)
    

