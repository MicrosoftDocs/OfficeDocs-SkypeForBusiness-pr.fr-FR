---
title: Activer les utilisateurs pour le système téléphonique dans Office 365 avec une connectivité RTC locale dans Skype entreprise Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: Cette rubrique décrit comment activer les utilisateurs pour le système téléphonique dans Office 365 avec une connectivité RTC locale. Avant de suivre la procédure décrite dans cette rubrique, vous devez lire les rubriques suivantes :.
ms.openlocfilehash: 87dcafcfe0c5ce69bcdbcd9809d23cea80c234ba
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050186"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="7fe7a-104">Activer les utilisateurs pour le système téléphonique dans Office 365 avec une connectivité RTC locale dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="7fe7a-104">Enable users for Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="7fe7a-105">Cette rubrique décrit comment activer les utilisateurs pour le système téléphonique dans Office 365 avec une connectivité RTC locale.</span><span class="sxs-lookup"><span data-stu-id="7fe7a-105">This topic describes how to enable users for Phone System in Office 365 with on-premises PSTN connectivity.</span></span> <span data-ttu-id="7fe7a-106">Avant de suivre la procédure décrite dans cette rubrique, vous devez lire les rubriques suivantes :.</span><span class="sxs-lookup"><span data-stu-id="7fe7a-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="7fe7a-107">Pour en savoir plus sur la configuration de la connectivité hybride, reportez-vous à la rubrique [plan Hybrid Connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) et [déployer une connectivité hybride entre Skype entreprise Server et Skype entreprise Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="7fe7a-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="7fe7a-108">Pour en savoir plus sur la planification de votre déploiement, reportez-vous à [plan Phone System in Office 365 with local RTC Connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="7fe7a-108">To learn about planning your deployment, see [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="7fe7a-109">Pour en savoir plus sur le système téléphonique dans Office 365, y compris les licences et les plans, voir [RTC Calling forfaits for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span><span class="sxs-lookup"><span data-stu-id="7fe7a-109">To learn more about Phone System in Office 365, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a><span data-ttu-id="7fe7a-110">Déplacement d’utilisateurs vers le système téléphonique dans Office 365 avec une connectivité RTC locale</span><span class="sxs-lookup"><span data-stu-id="7fe7a-110">Moving users to Phone System in Office 365 with on-premises PSTN connectivity</span></span>

<span data-ttu-id="7fe7a-111">Avant de déplacer vos utilisateurs vers Skype entreprise Online, il est recommandé d’activer les utilisateurs locaux dans Skype entreprise Server ou Lync Server 2013, puis de les déplacer en ligne.</span><span class="sxs-lookup"><span data-stu-id="7fe7a-111">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="7fe7a-112">Pour plus d’informations, reportez-vous à la section planification de la [connectivité hybride entre Skype entreprise Server et Skype entreprise Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) et à la section Considérations spéciales de [activer les utilisateurs pour voix entreprise sur site](enable-the-users-for-enterprise-voice-on-premises.md) (effectué lorsque les utilisateurs sont hébergés en local).</span><span class="sxs-lookup"><span data-stu-id="7fe7a-112">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span> 
  
<span data-ttu-id="7fe7a-113">Tous les utilisateurs doivent être créés dans Active Directory en local et synchronisés avec Office 365 à l’aide de la version prise en charge d’Azure AD Connector.</span><span class="sxs-lookup"><span data-stu-id="7fe7a-113">All users must be created in Active Directory on premises and synchronized to Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="7fe7a-114">Vous ne pouvez pas activer les utilisateurs pour le système téléphonique dans Office 365 qui ont été créés directement dans Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7fe7a-114">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="7fe7a-115">Si vous souhaitez activer le système téléphonique dans Office 365 avec une connectivité RTC locale pour un utilisateur qui a été créé dans Azure AD, vous devez créer un nouveau compte pour cet utilisateur dans votre annuaire Active Directory local, configurer le compte en local, puis synchroniser le compte à l’aide de une version prise en charge de l’outil Azure AD Connector.</span><span class="sxs-lookup"><span data-stu-id="7fe7a-115">If you want to enable Phone System in Office 365 with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="7fe7a-116">L’activation d’un utilisateur pour le système téléphonique dans Office 365 avec une connectivité RTC locale, puis son déplacement vers Skype entreprise Online nécessite les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="7fe7a-116">Enabling a user for Phone System in Office 365 with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="7fe7a-117">[Activer les utilisateurs pour voix entreprise sur site](enable-the-users-for-enterprise-voice-on-premises.md) (effectué lorsque les utilisateurs sont hébergés en local).</span><span class="sxs-lookup"><span data-stu-id="7fe7a-117">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="7fe7a-118">[Affecter une stratégie de routage des communications vocales](assign-a-voice-routing-policy.md) (effectuée pendant que les utilisateurs sont hébergés en local).</span><span class="sxs-lookup"><span data-stu-id="7fe7a-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="7fe7a-119">[Synchroniser les utilisateurs avec le Cloud et attribuer des licences](synchronize-users-to-the-cloud-and-assign-licenses.md) (effectué à l’aide d’Office 365).</span><span class="sxs-lookup"><span data-stu-id="7fe7a-119">[Synchronize users to the cloud and assign licenses](synchronize-users-to-the-cloud-and-assign-licenses.md) (performed using Office 365).</span></span>
    
- <span data-ttu-id="7fe7a-120">[Déplacez les utilisateurs locaux vers Skype entreprise Online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (effectué à l’aide de Windows PowerShell en local, mais à l’aide de vos informations d’identification d’administrateur Office 365).</span><span class="sxs-lookup"><span data-stu-id="7fe7a-120">[Move on-premises users to Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="7fe7a-121">[Activer les utilisateurs pour voix entreprise Online et le système téléphonique dans Office 365 la messagerie vocale](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (effectuée à l’aide de PowerShell à distance.</span><span class="sxs-lookup"><span data-stu-id="7fe7a-121">[Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell.</span></span>
    

