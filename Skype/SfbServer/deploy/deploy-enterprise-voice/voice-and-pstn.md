---
title: Configurer des stratégies de voix, des enregistrements d’utilisation PSTN et des itinéraires de voix dans Skype Entreprise
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: 'Résumé : Découvrez comment configurer des stratégies de voix, des enregistrements d’utilisation PSTN et des itinéraires de voix dans Skype Entreprise Server.'
ms.openlocfilehash: f8c9f75f24a06b210a1c17ed11a1485ab5158f3d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830444"
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business"></a><span data-ttu-id="c5842-103">Configurer des stratégies de voix, des enregistrements d’utilisation PSTN et des itinéraires de voix dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="c5842-103">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>
 
<span data-ttu-id="c5842-104">**Résumé :** Découvrez comment configurer des stratégies de voix, des enregistrements d’utilisation PSTN et des itinéraires de voix dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c5842-104">**Summary:** Learn how to configure voice policies, PSTN usage records, and voice routes in Skype for Business Server.</span></span>
  
<span data-ttu-id="c5842-p101">Les stratégies de voix, les enregistrements d’utilisation PSTN et les itinéraires des communications vocales sont étroitement liés. Pour configurer une stratégie de voix vous devez sélectionner des fonctionnalités d’appel, puis affecter des enregistrements d’utilisation PSTN à la stratégie, qui spécifient les droits qui sont accordés aux utilisateurs et aux groupes auxquels la stratégie de voix est affectée. Les itinéraires des communications vocales reçoivent également des enregistrements d’utilisation PSTN, qui permettent d’associer les itinéraires aux utilisateurs autorisés à les utiliser. En d’autres termes, les utilisateurs peuvent uniquement effectuer des appels qui utilisent des itinéraires pour lesquels ils disposent d’enregistrements d’utilisation PSTN correspondants.</span><span class="sxs-lookup"><span data-stu-id="c5842-p101">Voice policies, PSTN usage records, and voice routes are integrally related. You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy. Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them. That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>
  
<span data-ttu-id="c5842-109">La procédure recommandée pour un nouveau déploiement de Voix Entreprise est de commencer à configurer une stratégie de voix qui comprend les enregistrements d’utilisation PSTN appropriés, puis d’associer les itinéraires appropriés à chaque enregistrement d’utilisation PSTN.</span><span class="sxs-lookup"><span data-stu-id="c5842-109">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c5842-110">Vous pouvez également créer des stratégies de voix avec  *une étendue*  utilisateur et les affecter à des utilisateurs ou des groupes individuels.</span><span class="sxs-lookup"><span data-stu-id="c5842-110">You can also create voice policies with  *user*  scope and assign them to individual users or groups.</span></span>
  
<span data-ttu-id="c5842-111">Pour connaître en détail la marche à suivre pour effectuer chacune de ces tâches, voir les procédures dans cette section.</span><span class="sxs-lookup"><span data-stu-id="c5842-111">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="c5842-112">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="c5842-112">In this section</span></span>

- [<span data-ttu-id="c5842-113">Créer ou modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="c5842-113">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)
    
- [<span data-ttu-id="c5842-114">Configurer l’échappatoire de messagerie vocale dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="c5842-114">Configure voice mail escape in Skype for Business</span></span>](configure-voice-mail-escape.md)
    
- [<span data-ttu-id="c5842-115">Afficher les enregistrements d’utilisation PSTN dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="c5842-115">View PSTN usage records in Skype for Business</span></span>](view-pstn-usage-records.md)
    
- [<span data-ttu-id="c5842-116">Créer ou modifier un itinéraire de voix dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="c5842-116">Create or modify a voice route in Skype for Business</span></span>](create-or-modify-a-voice-route.md)
    
- [<span data-ttu-id="c5842-117">Exporter ou importer un fichier de configuration d’itinéraire de voix dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="c5842-117">Export or import a voice route configuration file in Skype for Business</span></span>](voice-route-configuration-import-export.md)
    
- [<span data-ttu-id="c5842-118">Publication des modifications en attente de la configuration du routage des voix dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="c5842-118">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)
    

