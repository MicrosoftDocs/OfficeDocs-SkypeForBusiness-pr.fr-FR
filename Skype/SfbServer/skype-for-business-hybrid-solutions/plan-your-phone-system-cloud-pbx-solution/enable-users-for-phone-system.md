---
title: Permettre aux utilisateurs pour le système téléphonique dans Office 365 avec une connectivité PSTN local dans Skype pour Business Server
ms.reviewer: ''
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
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: Cette rubrique décrit comment permettre aux utilisateurs pour le système téléphonique dans Office 365 avec une connectivité PSTN sur site. Avant de suivre les étapes décrites dans cette rubrique, vous devez voir les articles suivants :.
ms.openlocfilehash: a3eec7adbd4897889cbc2ef8c7e985231c53bc99
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234069"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="1de47-104">Permettre aux utilisateurs pour le système téléphonique dans Office 365 avec une connectivité PSTN local dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="1de47-104">Enable users for Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="1de47-105">Cette rubrique décrit comment permettre aux utilisateurs pour le système téléphonique dans Office 365 avec une connectivité PSTN sur site.</span><span class="sxs-lookup"><span data-stu-id="1de47-105">This topic describes how to enable users for Phone System in Office 365 with on-premises PSTN connectivity.</span></span> <span data-ttu-id="1de47-106">Avant de suivre les étapes décrites dans cette rubrique, vous devez voir les articles suivants :.</span><span class="sxs-lookup"><span data-stu-id="1de47-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="1de47-107">Pour savoir comment configurer la connectivité hybride, consultez [planification de la connectivité hybride entre Skype pour Business Server et Skype pour Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) et [déployer la connectivité hybride entre Skype pour Business Server et Skype pour Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="1de47-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="1de47-108">Pour plus d’informations sur la planification de votre déploiement, voir [Planifier le système téléphonique dans Office 365 avec une connectivité PSTN dans Skype pour Business Server local](plan-phone-system-with-on-premises-pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="1de47-108">To learn about planning your deployment, see [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="1de47-109">Pour en savoir plus sur le système téléphonique dans Office 365, notamment la gestion des licences et plans, voir [appel PSTN de plans de Skype pour les entreprises](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span><span class="sxs-lookup"><span data-stu-id="1de47-109">To learn more about Phone System in Office 365, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a><span data-ttu-id="1de47-110">Déplacement d’utilisateurs au système téléphonique dans Office 365 avec une connectivité PSTN sur site</span><span class="sxs-lookup"><span data-stu-id="1de47-110">Moving users to Phone System in Office 365 with on-premises PSTN connectivity</span></span>

<span data-ttu-id="1de47-111">Avant de déplacer vos utilisateurs à Skype pour Business Online, il est recommandé que vous activez vos utilisateurs sur site dans Skype pour Business Server ou Microsoft Lync Server 2013 et les déplacez en ligne.</span><span class="sxs-lookup"><span data-stu-id="1de47-111">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="1de47-112">Pour plus d’informations, voir [planification de la connectivité hybride entre Skype pour Business Server et Skype pour Business en ligne](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) et à la section Considérations spéciales d' [Activer les utilisateurs pour Enterprise Voice sur site](enable-the-users-for-enterprise-voice-on-premises.md) (opération réalisée alors que les utilisateurs sont hébergés sur site).</span><span class="sxs-lookup"><span data-stu-id="1de47-112">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span> 
  
<span data-ttu-id="1de47-113">Tous les utilisateurs doivent être créés dans Active Directory sur site et synchronisés avec Office 365 à l’aide de la version prise en charge d’Azure AD connecteur.</span><span class="sxs-lookup"><span data-stu-id="1de47-113">All users must be created in Active Directory on premises and synchronized to Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="1de47-114">Vous ne pouvez pas activer les utilisateurs pour système téléphonique dans Office 365 qui ont été créées directement dans Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1de47-114">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="1de47-115">Si vous souhaitez activer le système téléphonique dans Office 365 avec une connectivité PSTN pour un utilisateur qui a été créé dans Azure AD sur site, vous devez créer un nouveau compte de cet utilisateur dans votre environnement local AD, configurer le compte local, puis synchroniser le compte à l’aide une version prise en charge de l’outil Azure AD connecteur.</span><span class="sxs-lookup"><span data-stu-id="1de47-115">If you want to enable Phone System in Office 365 with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="1de47-116">Permettre à un utilisateur pour le système téléphonique dans Office 365 avec une connectivité PSTN sur site et les déplacer vers Skype pour Business Online nécessitent les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="1de47-116">Enabling a user for Phone System in Office 365 with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="1de47-117">[Activez les utilisateurs pour Enterprise Voice sur site](enable-the-users-for-enterprise-voice-on-premises.md) (opération réalisée alors que les utilisateurs sont hébergés sur un système local).</span><span class="sxs-lookup"><span data-stu-id="1de47-117">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="1de47-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (lorsque les utilisateurs sont hébergés en local).</span><span class="sxs-lookup"><span data-stu-id="1de47-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="1de47-119">[Synchroniser les utilisateurs pour les nuage et attribuer des licences](synchronize-users-to-the-cloud-and-assign-licenses.md) (opération réalisée à l’aide d’Office 365).</span><span class="sxs-lookup"><span data-stu-id="1de47-119">[Synchronize users to the cloud and assign licenses](synchronize-users-to-the-cloud-and-assign-licenses.md) (performed using Office 365).</span></span>
    
- <span data-ttu-id="1de47-120">[Déplacer des utilisateurs sur site à Skype pour Business Online](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (opération réalisée à l’aide de Windows PowerShell local, mais à l’aide de vos informations d’identification d’administrateur Office 365).</span><span class="sxs-lookup"><span data-stu-id="1de47-120">[Move on-premises users to Skype for Business Online](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="1de47-121">[Activer les utilisateurs pour Enterprise Voice en ligne et le système téléphonique dans la messagerie Office 365](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (opération réalisée à l’aide de PowerShell à distance.</span><span class="sxs-lookup"><span data-stu-id="1de47-121">[Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell.</span></span>
    

