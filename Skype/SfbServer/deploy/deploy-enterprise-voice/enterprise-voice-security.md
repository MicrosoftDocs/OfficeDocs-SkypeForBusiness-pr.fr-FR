---
title: Sécurité et configuration requises pour Enterprise Voice sur Skype pour Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 'Résumé : Découvrez les composants de sécurité et configuration requis pour Enterprise Voice sur Skype pour Business Server.'
ms.openlocfilehash: 2738f1b39500673bd68b6c4f0c5cfdfb5b8b45d5
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21017389"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="0678a-103">Sécurité et configuration requises pour Enterprise Voice sur Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="0678a-103">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="0678a-104">**Résumé :** Découvrez les composants de sécurité et configuration requis pour Enterprise Voice sur Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="0678a-104">**Summary:** Learn about the security and configuration prerequisites for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="0678a-105">Avant de déployer Enterprise Voice, vérifiez que votre infrastructure réunit la sécurité suivante, configuration de l’utilisateur et conditions préalables matérielles des scénarios spécifiques.</span><span class="sxs-lookup"><span data-stu-id="0678a-105">Before deploying Enterprise Voice, verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span> 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="0678a-106">Droits d’administration et infrastructure de certificats</span><span class="sxs-lookup"><span data-stu-id="0678a-106">Administrative rights and certificate infrastructure</span></span>

<span data-ttu-id="0678a-107">Avant de procéder au déploiement, vérifiez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="0678a-107">Before deploying, check the following:</span></span>
  
- <span data-ttu-id="0678a-108">Les administrateurs déployant Enterprise Voice doivent être membres du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="0678a-108">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>
    
- <span data-ttu-id="0678a-109">Les administrateurs doivent disposer des droits appropriés pour effectuer les tâches de configuration :</span><span class="sxs-lookup"><span data-stu-id="0678a-109">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
  - <span data-ttu-id="0678a-110">**CsVoiceAdministrator :** ce rôle permet à l’administrateur d’effectuer des tâches de configuration vocale, de gérer les applications vocales et d’affecter des stratégies vocales aux utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="0678a-110">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
  - <span data-ttu-id="0678a-p101">**CsUserAdministrator :** ce rôle permet à l’administrateur de gérer les propriétés des utilisateurs, par exemple, pour activer Voix Entreprise pour un utilisateur. Ce rôle permet également à l’administrateur d’affecter des stratégies par utilisateur, à l’exception de la stratégie d’archivage, et de gérer les téléphones de partie commune et les périphériques analogiques.</span><span class="sxs-lookup"><span data-stu-id="0678a-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
  - <span data-ttu-id="0678a-113">**CsAdministrator :** ce rôle permet à l’utilisateur d’effectuer toutes les tâches des rôles CsVoiceAdministrator et CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0678a-113">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
- <span data-ttu-id="0678a-114">L’infrastructure MKI (Managed Key Infrastructure) est déployée et configurée à l’aide d’une infrastructure d’autorité de certification Microsoft ou tierce.</span><span class="sxs-lookup"><span data-stu-id="0678a-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0678a-115">Pour plus d’informations sur les certificats requis dans Skype pour Business Server, consultez [exigences pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou [configuration serveur requise pour Skype pour Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0678a-115">For details about certificate requirements in Skype for Business Server, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
## <a name="user-configuration"></a><span data-ttu-id="0678a-116">Configuration utilisateur</span><span class="sxs-lookup"><span data-stu-id="0678a-116">User configuration</span></span>

<span data-ttu-id="0678a-117">Si vous colocalisé le serveur de médiation à chaque pool frontal ou Standard Edition server au cours du déploiement frontal, les paramètres utilisateur nécessaires pour Enterprise Voice ont été configurés automatiquement lors de l’installation des fichiers de ces rôles de serveur.</span><span class="sxs-lookup"><span data-stu-id="0678a-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>
  
<span data-ttu-id="0678a-118">Si vous déployez nouvellement la charge de travail Enterprise Voice à ce stade, avant de commencer le processus de déploiement, désigner un numéro de téléphone principal pour chaque utilisateur qui vous envisagez d’activer pour Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="0678a-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="0678a-119">En tant qu’administrateur, vous devez vous assurer que ce numéro est unique.</span><span class="sxs-lookup"><span data-stu-id="0678a-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="0678a-120">Avant l’implémentation, principal tous les téléphone numéros doivent être normalisées (correctement mis en forme) et copié dans la propriété **URI de ligne** de chaque utilisateur à l’aide de Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="0678a-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user's **Line URI** property using Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0678a-121">Pour obtenir des exemples des numéros de téléphone principaux requis pour le déploiement de Voix Entreprise, reportez-vous à la rubrique [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span><span class="sxs-lookup"><span data-stu-id="0678a-121">For examples of primary phone numbers required for Enterprise Voice deployment, see [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span></span> 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="0678a-122">Étapes suivantes : installation des fichiers ou configuration de la connectivité RTC</span><span class="sxs-lookup"><span data-stu-id="0678a-122">Next Steps: Install files or configure PSTN connectivity</span></span>

<span data-ttu-id="0678a-123">Après avoir vérifié les logiciels et les conditions préalables pour Enterprise Voice, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="0678a-123">After verifying software and environmental prerequisites for Enterprise Voice you can either:</span></span>
  
- <span data-ttu-id="0678a-124">Installer le serveur de médiation, comme décrit dans [déployer un serveur de médiation dans le Générateur de topologie dans Skype pour Business Server](deploy-a-mediation-server.md), mais uniquement si vous souhaitez déployer un serveur de médiation autonome ou un pool, car les serveurs de médiation sont installés dans le cadre du serveur frontal pool ou le processus de déploiement de Standard Edition server lorsque colocalisés.</span><span class="sxs-lookup"><span data-stu-id="0678a-124">Install the Mediation Server, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>
    
- <span data-ttu-id="0678a-125">Ou, commencer à configurer les paramètres pour acheminer les appels pour les utilisateurs d’Enterprise Voice, comme décrit dans [configurer les jonctions dans Skype pour Business Server](configure-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="0678a-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configure trunks in Skype for Business Server](configure-trunks.md).</span></span>
    

