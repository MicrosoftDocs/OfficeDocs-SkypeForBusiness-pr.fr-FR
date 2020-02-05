---
title: Conditions préalables à la sécurité et à la configuration d’Enterprise voix dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 'Résumé : Obtenez des informations sur la sécurité et la configuration requise pour Enterprise Voice dans Skype entreprise Server.'
ms.openlocfilehash: 314c25429dbf346a5f62705afa4f19a5b518452a
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767237"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="e7158-103">Conditions préalables à la sécurité et à la configuration d’Enterprise voix dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="e7158-103">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="e7158-104">**Résumé :** En savoir plus sur la sécurité et la configuration requise pour Enterprise Voice dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="e7158-104">**Summary:** Learn about the security and configuration prerequisites for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="e7158-105">Avant de déployer Enterprise Voice, assurez-vous que votre infrastructure répond à la configuration requise en matière de sécurité, de configuration utilisateur et de matériel spécifique.</span><span class="sxs-lookup"><span data-stu-id="e7158-105">Before deploying Enterprise Voice, verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span> 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="e7158-106">Droits d’administration et infrastructure de certificats</span><span class="sxs-lookup"><span data-stu-id="e7158-106">Administrative rights and certificate infrastructure</span></span>

<span data-ttu-id="e7158-107">Avant de procéder au déploiement, vérifiez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="e7158-107">Before deploying, check the following:</span></span>
  
- <span data-ttu-id="e7158-108">Le déploiement d’Enterprise Voice par les administrateurs doit être membre du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e7158-108">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>
    
- <span data-ttu-id="e7158-109">Les administrateurs doivent disposer des droits appropriés pour effectuer les tâches de configuration :</span><span class="sxs-lookup"><span data-stu-id="e7158-109">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
  - <span data-ttu-id="e7158-110">**CsVoiceAdministrator :** ce rôle permet à l’administrateur d’effectuer des tâches de configuration vocale, de gérer les applications vocales et d’affecter des stratégies vocales aux utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="e7158-110">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
  - <span data-ttu-id="e7158-p101">**CsUserAdministrator :** ce rôle permet à l’administrateur de gérer les propriétés des utilisateurs, par exemple, pour activer Voix Entreprise pour un utilisateur. Ce rôle permet également à l’administrateur d’affecter des stratégies par utilisateur, à l’exception de la stratégie d’archivage, et de gérer les téléphones de partie commune et les périphériques analogiques.</span><span class="sxs-lookup"><span data-stu-id="e7158-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
  - <span data-ttu-id="e7158-113">**CsAdministrator :** ce rôle permet à l’utilisateur d’effectuer toutes les tâches des rôles CsVoiceAdministrator et CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e7158-113">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
- <span data-ttu-id="e7158-114">L’infrastructure MKI (Managed Key Infrastructure) est déployée et configurée à l’aide d’une infrastructure d’autorité de certification Microsoft ou tierce.</span><span class="sxs-lookup"><span data-stu-id="e7158-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e7158-115">Pour plus d’informations sur les exigences relatives aux certificats dans Skype entreprise Server, voir [configuration environnementale requise pour Skype entreprise server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou [configuration serveur requise pour skype entreprise Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7158-115">For details about certificate requirements in Skype for Business Server, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
## <a name="user-configuration"></a><span data-ttu-id="e7158-116">Configuration utilisateur</span><span class="sxs-lookup"><span data-stu-id="e7158-116">User configuration</span></span>

<span data-ttu-id="e7158-117">Si vous avez localisé le serveur de médiation avec chaque pool frontal ou serveur Standard Edition au cours du déploiement frontal, les paramètres utilisateur nécessaires à l’utilisation d’Enterprise Voice étaient configurés automatiquement lors de l’installation des fichiers pour ces rôles de serveur.</span><span class="sxs-lookup"><span data-stu-id="e7158-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>
  
<span data-ttu-id="e7158-118">Si vous venez de déployer la charge de travail voix entreprise pour le moment, avant de commencer le processus de déploiement, spécifiez le numéro de téléphone principal de chaque utilisateur que vous envisagez d’activer pour voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="e7158-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="e7158-119">En tant qu’administrateur, vous devez vous assurer que ce numéro est unique.</span><span class="sxs-lookup"><span data-stu-id="e7158-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="e7158-120">Avant l’implémentation, tous les numéros de téléphone principal doivent être normalisés (correctement mis en forme) et copiés sur les propriétés d' **URI de ligne** de chaque utilisateur à l’aide de Skype entreprise Server Control Panel.</span><span class="sxs-lookup"><span data-stu-id="e7158-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user's **Line URI** property using Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e7158-121">Pour obtenir des exemples des numéros de téléphone principaux requis pour le déploiement de Voix Entreprise, reportez-vous à la rubrique [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span><span class="sxs-lookup"><span data-stu-id="e7158-121">For examples of primary phone numbers required for Enterprise Voice deployment, see [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span></span> 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="e7158-122">Étapes suivantes : installation des fichiers ou configuration de la connectivité RTC</span><span class="sxs-lookup"><span data-stu-id="e7158-122">Next Steps: Install files or configure PSTN connectivity</span></span>

<span data-ttu-id="e7158-123">Après vérification de la configuration logicielle et environnementale requise pour Enterprise Voice, vous pouvez effectuer l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7158-123">After verifying software and environmental prerequisites for Enterprise Voice you can either:</span></span>
  
- <span data-ttu-id="e7158-124">Installez le serveur de médiation, comme décrit dans la rubrique [déploiement d’un serveur de médiation dans le générateur de topologie de Skype entreprise Server](deploy-a-mediation-server.md), mais uniquement si vous voulez déployer un serveur de médiation autonome ou un pool, car les serveurs de médiation sont installés dans le cadre du processus de déploiement de la liste frontale ou du serveur Standard Edition lorsqu’il est localisé.</span><span class="sxs-lookup"><span data-stu-id="e7158-124">Install the Mediation Server, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>
    
- <span data-ttu-id="e7158-125">Vous pouvez aussi commencer à configurer des paramètres pour acheminer les appels pour les utilisateurs d’Enterprise Voice, comme décrit dans la rubrique [configurer des Trunks dans Skype entreprise Server](configure-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="e7158-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configure trunks in Skype for Business Server](configure-trunks.md).</span></span>
    

