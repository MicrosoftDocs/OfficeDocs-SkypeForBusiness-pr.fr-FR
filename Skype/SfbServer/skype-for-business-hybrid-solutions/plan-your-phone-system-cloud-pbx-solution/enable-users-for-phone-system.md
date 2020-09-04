---
title: Activation des utilisateurs pour le système téléphonique avec une connectivité PSTN en local dans Skype Entreprise Server
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
description: Cette rubrique décrit comment activer les utilisateurs pour le système téléphonique avec une connectivité RTC locale. Avant de suivre la procédure décrite dans cette rubrique, vous devez lire les rubriques suivantes :.
ms.openlocfilehash: 7fb1ae9ee013dafbf0de91611bacb68f685daac8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359140"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="7d497-104">Activation des utilisateurs pour le système téléphonique avec une connectivité PSTN en local dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="7d497-104">Enable users for Phone System with on-premises PSTN connectivity in Skype for Business Server</span></span>

<span data-ttu-id="7d497-105">Cette rubrique décrit comment activer les utilisateurs pour le système téléphonique avec une connectivité RTC locale.</span><span class="sxs-lookup"><span data-stu-id="7d497-105">This topic describes how to enable users for Phone System with on-premises PSTN connectivity.</span></span> <span data-ttu-id="7d497-106">Avant de suivre la procédure décrite dans cette rubrique, vous devez lire les rubriques suivantes :.</span><span class="sxs-lookup"><span data-stu-id="7d497-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="7d497-107">Pour en savoir plus sur la configuration de la connectivité hybride, reportez-vous à la rubrique [plan Hybrid Connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) et [déployer une connectivité hybride entre Skype entreprise Server et Skype entreprise Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="7d497-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="7d497-108">Pour en savoir plus sur la planification de votre déploiement, reportez-vous à la rubrique [plan Phone System with on-premises Connectivity Connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="7d497-108">To learn about planning your deployment, see [Plan Phone System with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="7d497-109">Pour en savoir plus sur le système téléphonique, y compris sur les licences et les plans, voir [RTC Calling forfaits for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span><span class="sxs-lookup"><span data-stu-id="7d497-109">To learn more about Phone System, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
> [!Important]
> <span data-ttu-id="7d497-110">Skype entreprise Online sera supprimé le 31 juillet 2021 après lequel le service ne sera plus accessible.</span><span class="sxs-lookup"><span data-stu-id="7d497-110">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="7d497-111">De plus, la connectivité PSTN entre votre environnement local, que ce soit via Skype entreprise Server ou Cloud Connector Edition et Skype entreprise Online, ne sera plus prise en charge.</span><span class="sxs-lookup"><span data-stu-id="7d497-111">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="7d497-112">Découvrez comment connecter votre réseau téléphonique local à teams à l’aide du [routage direct](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="7d497-112">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a><span data-ttu-id="7d497-113">Déplacement des utilisateurs vers le système téléphonique avec une connectivité RTC locale</span><span class="sxs-lookup"><span data-stu-id="7d497-113">Moving users to Phone System with on-premises PSTN connectivity</span></span>

<span data-ttu-id="7d497-114">Avant de déplacer vos utilisateurs vers Skype entreprise Online, il est recommandé d’activer les utilisateurs locaux dans Skype entreprise Server ou Lync Server 2013, puis de les déplacer en ligne.</span><span class="sxs-lookup"><span data-stu-id="7d497-114">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="7d497-115">Pour plus d’informations, reportez-vous à la section planification de la [connectivité hybride entre Skype entreprise Server et Skype entreprise Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) et à la section Considérations spéciales de [activer les utilisateurs pour voix entreprise sur site](enable-the-users-for-enterprise-voice-on-premises.md) (effectué lorsque les utilisateurs sont hébergés en local).</span><span class="sxs-lookup"><span data-stu-id="7d497-115">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span> 
  
<span data-ttu-id="7d497-116">Tous les utilisateurs doivent être créés dans Active Directory en local et synchronisés avec Microsoft 365 ou Office 365 à l’aide de la version prise en charge d’Azure AD Connector.</span><span class="sxs-lookup"><span data-stu-id="7d497-116">All users must be created in Active Directory on premises and synchronized to Microsoft 365 or Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="7d497-117">Vous ne pouvez pas activer les utilisateurs pour le système téléphonique dans Office 365 qui ont été créés directement dans Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7d497-117">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="7d497-118">Si vous souhaitez activer le système téléphonique avec une connectivité RTC locale pour un utilisateur qui a été créé dans Azure AD, vous devez créer un nouveau compte pour cet utilisateur dans votre annuaire Active Directory local, configurer le compte local, puis synchroniser le compte à l’aide d’une version prise en charge de l’outil Azure AD Connector.</span><span class="sxs-lookup"><span data-stu-id="7d497-118">If you want to enable Phone System with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="7d497-119">L’activation d’un utilisateur pour le système téléphonique avec une connectivité RTC locale, puis son déplacement vers Skype entreprise Online nécessite les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="7d497-119">Enabling a user for Phone System with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="7d497-120">[Activer les utilisateurs pour voix entreprise sur site](enable-the-users-for-enterprise-voice-on-premises.md) (effectué lorsque les utilisateurs sont hébergés en local).</span><span class="sxs-lookup"><span data-stu-id="7d497-120">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="7d497-121">[Affecter une stratégie de routage des communications vocales](assign-a-voice-routing-policy.md) (effectuée pendant que les utilisateurs sont hébergés en local).</span><span class="sxs-lookup"><span data-stu-id="7d497-121">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="7d497-122">[Synchroniser les utilisateurs avec le Cloud et attribuer des licences](synchronize-users-to-the-cloud-and-assign-licenses.md) (effectué à l’aide d’Office 365).</span><span class="sxs-lookup"><span data-stu-id="7d497-122">[Synchronize users to the cloud and assign licenses](synchronize-users-to-the-cloud-and-assign-licenses.md) (performed using Office 365).</span></span>
    
- <span data-ttu-id="7d497-123">[Déplacez les utilisateurs locaux vers Skype entreprise Online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (effectué à l’aide de Windows PowerShell en local, mais à l’aide de vos informations d’identification d’administrateur Office 365).</span><span class="sxs-lookup"><span data-stu-id="7d497-123">[Move on-premises users to Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="7d497-124">[Activer les utilisateurs pour voix entreprise Online et messagerie vocale du système téléphonique](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (effectué à l’aide de PowerShell à distance.</span><span class="sxs-lookup"><span data-stu-id="7d497-124">[Enable users for Enterprise Voice online and Phone System Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell.</span></span>
    

