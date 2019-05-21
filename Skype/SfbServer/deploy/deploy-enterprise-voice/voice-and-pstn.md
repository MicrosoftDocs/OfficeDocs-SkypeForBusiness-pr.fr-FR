---
title: Configuration des stratégies de voix, des enregistrements d’utilisation RTC et des itinéraires vocaux dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: 'Résumé: Découvrez comment configurer les stratégies vocales, les enregistrements d’utilisation RTC et les itinéraires vocaux dans Skype entreprise Server.'
ms.openlocfilehash: 5ce6b6b3e93804f648529043b9189110d25cbb08
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300908"
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business"></a><span data-ttu-id="16e51-103">Configuration des stratégies de voix, des enregistrements d’utilisation RTC et des itinéraires vocaux dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="16e51-103">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>
 
<span data-ttu-id="16e51-104">**Résumé:** Apprenez à configurer les stratégies vocales, les enregistrements d’utilisation RTC et les itinéraires vocaux dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="16e51-104">**Summary:** Learn how to configure voice policies, PSTN usage records, and voice routes in Skype for Business Server.</span></span>
  
<span data-ttu-id="16e51-p101">Les stratégies de voix, les enregistrements d’utilisation RTC et les itinéraires des communications vocales sont étroitement liés. Pour configurer une stratégie de voix vous devez sélectionner des fonctionnalités d’appel, puis affecter à la stratégie des enregistrements d’utilisation RTC, qui spécifient les droits accordés aux utilisateurs et aux groupes auxquels la stratégie de voix est affectée. Les itinéraires des communications vocales reçoivent également des enregistrements d’utilisation RTC, qui permettent d’associer les itinéraires aux utilisateurs autorisés à les utiliser. En d’autres termes, les utilisateurs ne peuvent effectuer que des appels utilisant des itinéraires pour lesquels ils disposent d’enregistrements d’utilisation RTC correspondants.</span><span class="sxs-lookup"><span data-stu-id="16e51-p101">Voice policies, PSTN usage records, and voice routes are integrally related. You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy. Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them. That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>
  
<span data-ttu-id="16e51-109">La procédure recommandée pour un nouveau déploiement de Voix Entreprise est de commencer par configurer une stratégie de voix qui comprend les enregistrements d’utilisation RTC appropriés, puis d’associer les itinéraires appropriés à chaque enregistrement d’utilisation RTC.</span><span class="sxs-lookup"><span data-stu-id="16e51-109">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="16e51-110">Vous pouvez également créer des politiques vocales avec l’étendue des *utilisateurs* et les affecter à des utilisateurs ou groupes individuels.</span><span class="sxs-lookup"><span data-stu-id="16e51-110">You can also create voice policies with  *user*  scope and assign them to individual users or groups.</span></span>
  
<span data-ttu-id="16e51-111">Pour connaître en détail la marche à suivre pour effectuer chacune de ces tâches, reportez-vous aux procédures de cette section.</span><span class="sxs-lookup"><span data-stu-id="16e51-111">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="16e51-112">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="16e51-112">In this section</span></span>

- [<span data-ttu-id="16e51-113">Création ou modification d’une stratégie de voix et configuration des enregistrements d’utilisation RTC dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="16e51-113">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)
    
- [<span data-ttu-id="16e51-114">Configurer l’échappement de la messagerie vocale dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="16e51-114">Configure voice mail escape in Skype for Business</span></span>](configure-voice-mail-escape.md)
    
- [<span data-ttu-id="16e51-115">Afficher les enregistrements d’utilisation RTC dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="16e51-115">View PSTN usage records in Skype for Business</span></span>](view-pstn-usage-records.md)
    
- [<span data-ttu-id="16e51-116">Création ou modification d’un itinéraire vocal dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="16e51-116">Create or modify a voice route in Skype for Business</span></span>](create-or-modify-a-voice-route.md)
    
- [<span data-ttu-id="16e51-117">Exporter ou importer un fichier de configuration de l’itinéraire vocal dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="16e51-117">Export or import a voice route configuration file in Skype for Business</span></span>](voice-route-configuration-import-export.md)
    
- [<span data-ttu-id="16e51-118">Les modifications en attente apportées à la configuration de l’acheminement vocal dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="16e51-118">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)
    

