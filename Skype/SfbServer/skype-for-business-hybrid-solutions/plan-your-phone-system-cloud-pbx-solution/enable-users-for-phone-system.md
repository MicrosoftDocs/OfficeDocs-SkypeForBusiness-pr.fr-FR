---
title: Permettre aux utilisateurs de système téléphonique dans Office 365 avec la connectivité RTPC local dans Skype pour Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: Cette rubrique décrit comment permettre aux utilisateurs de système téléphonique dans Office 365 avec la connectivité RTPC sur site. Avant de suivre les étapes décrites dans cette rubrique, vous devez lire ce qui suit :.
ms.openlocfilehash: e4b76074f26cbfafc248bfe9787f5886f4a70063
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="8ce70-104">Permettre aux utilisateurs de système téléphonique dans Office 365 avec la connectivité RTPC local dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="8ce70-104">Enable users for Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="8ce70-105">Cette rubrique décrit comment permettre aux utilisateurs de système téléphonique dans Office 365 avec la connectivité RTPC sur site.</span><span class="sxs-lookup"><span data-stu-id="8ce70-105">This topic describes how to enable users for Phone System in Office 365 with on-premises PSTN connectivity.</span></span> <span data-ttu-id="8ce70-106">Avant de suivre les étapes décrites dans cette rubrique, vous devez lire ce qui suit :.</span><span class="sxs-lookup"><span data-stu-id="8ce70-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="8ce70-107">Pour savoir comment configurer la connectivité de hybride, voir [planification de la connectivité d’hybride entre Skype pour Business Server et Skype pour Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) et [déployer une connectivité hybride entre Skype pour Business Server et Skype pour l’activité en ligne](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="8ce70-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="8ce70-108">Pour en savoir plus sur la planification de votre déploiement, reportez-vous à la section [Planifier le système téléphonique dans Office 365 avec la connectivité RTPC dans Skype pour Business Server local](plan-phone-system-with-on-premises-pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="8ce70-108">To learn about planning your deployment, see [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="8ce70-109">Pour en savoir plus sur le système téléphonique dans Office 365, y compris le Gestionnaire de licences et les plans, consultez [plans PSTN appel Skype pour les entreprises](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span><span class="sxs-lookup"><span data-stu-id="8ce70-109">To learn more about Phone System in Office 365, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a><span data-ttu-id="8ce70-110">Déplacement des utilisateurs au système téléphonique dans Office 365 avec la connectivité RTPC sur site</span><span class="sxs-lookup"><span data-stu-id="8ce70-110">Moving users to Phone System in Office 365 with on-premises PSTN connectivity</span></span>

<span data-ttu-id="8ce70-111">Avant de déplacer vos utilisateurs à Skype pour professionnels en ligne, il est recommandé de permettre à vos utilisateurs sur site dans Skype pour Business Server ou de Microsoft Lync Server 2013 et de les déplacer en ligne.</span><span class="sxs-lookup"><span data-stu-id="8ce70-111">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="8ce70-112">Pour plus d’informations, reportez-vous à la section [planification de la connectivité d’hybride entre Skype pour Business Server et Skype pour entreprise en ligne](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) et à la section Considérations spéciales de [permettre aux utilisateurs de Voix Entreprise dans les locaux](enable-the-users-for-enterprise-voice-on-premises.md).</span><span class="sxs-lookup"><span data-stu-id="8ce70-112">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md).</span></span> 
  
<span data-ttu-id="8ce70-113">Tous les utilisateurs doivent être créés dans Active Directory dans les locaux et synchronisés avec Office 365 à l’aide de la version prise en charge d’Azure le connecteur Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8ce70-113">All users must be created in Active Directory on premises and synchronized to Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="8ce70-114">Impossible d’activer les utilisateurs pour le système téléphonique dans Office 365, qui ont été créés directement dans Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8ce70-114">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="8ce70-115">Si vous souhaitez activer le système téléphonique dans Office 365 avec la connectivité RTPC local pour un utilisateur qui a été créé dans Active Directory Azure, vous devez créer un nouveau compte pour cet utilisateur dans vos locaux AD, configurer le compte local et synchronisent ensuite le compte à l’aide une version prise en charge de l’outil Azure le connecteur Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8ce70-115">If you want to enable Phone System in Office 365 with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="8ce70-116">Permettant à un utilisateur de système téléphonique dans Office 365 avec la connectivité RTPC sur site et les déplacer à Skype pour entreprise en ligne nécessitent les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="8ce70-116">Enabling a user for Phone System in Office 365 with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="8ce70-117">[Permettre aux utilisateurs de Voix Entreprise dans les locaux](enable-the-users-for-enterprise-voice-on-premises.md) (opération effectuée alors que les utilisateurs sont hébergées sur site).</span><span class="sxs-lookup"><span data-stu-id="8ce70-117">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="8ce70-118">[Affecter une stratégie de routage de voix](assign-a-voice-routing-policy.md) (opération effectuée alors que les utilisateurs sont hébergées sur site).</span><span class="sxs-lookup"><span data-stu-id="8ce70-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="8ce70-119">[Synchroniser les licences de cloud et affecter les utilisateurs](synchronize-users-to-the-cloud-and-assign-licenses.md) (opération effectuée à l’aide d’Office 365).</span><span class="sxs-lookup"><span data-stu-id="8ce70-119">[Synchronize users to the cloud and assign licenses](synchronize-users-to-the-cloud-and-assign-licenses.md) (performed using Office 365).</span></span>
    
- <span data-ttu-id="8ce70-120">[Déplacer les utilisateurs locaux à Skype pour professionnels en ligne](move-on-premises-users-to-skype-for-business-online.md) (opération effectuée à l’aide de Windows PowerShell sur site, mais à l’aide de vos références d’administrateur Office 365).</span><span class="sxs-lookup"><span data-stu-id="8ce70-120">[Move on-premises users to Skype for Business Online](move-on-premises-users-to-skype-for-business-online.md) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="8ce70-121">[Permettre aux utilisateurs de Voix Entreprise en ligne et un système téléphonique de messagerie vocale de Office 365](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (opération effectuée à l’aide du PowerShell distant).</span><span class="sxs-lookup"><span data-stu-id="8ce70-121">[Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell).</span></span>
    

