---
title: Conditions préalables requises de sécurité et de configuration pour Voix Entreprise dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 'Résumé : Découvrez les conditions de sécurité et de configuration requises pour Voix Entreprise dans Skype pour Business Server 2015.'
ms.openlocfilehash: 400af6d42026007315e30a7706e9730901f90708
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server-2015"></a><span data-ttu-id="2fa48-103">Conditions préalables requises de sécurité et de configuration pour Voix Entreprise dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="2fa48-103">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2fa48-104">**Résumé :** Obtenir des informations sur les conditions de sécurité et de configuration requises pour Voix Entreprise dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2fa48-104">**Summary:** Learn about the security and configuration prerequisites for Enterprise Voice in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="2fa48-105">Avant le déploiement de Voix Entreprise, vérifiez que votre infrastructure répond aux suivante de sécurité, configuration de l’utilisateur et les conditions matérielles spécifiques d’un scénario.</span><span class="sxs-lookup"><span data-stu-id="2fa48-105">Before deploying Enterprise Voice, verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span> 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="2fa48-106">Droits d’administration et infrastructure de certificats</span><span class="sxs-lookup"><span data-stu-id="2fa48-106">Administrative rights and certificate infrastructure</span></span>

<span data-ttu-id="2fa48-107">Avant de procéder au déploiement, vérifiez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="2fa48-107">Before deploying, check the following:</span></span>
  
- <span data-ttu-id="2fa48-108">Les administrateurs de déploiement de Voix Entreprise doivent être membres du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="2fa48-108">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>
    
- <span data-ttu-id="2fa48-109">Les administrateurs doivent disposer des droits appropriés pour effectuer les tâches de configuration :</span><span class="sxs-lookup"><span data-stu-id="2fa48-109">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
  - <span data-ttu-id="2fa48-110">**CsVoiceAdministrator :** ce rôle permet à l’administrateur d’effectuer des tâches de configuration vocale, de gérer les applications vocales et d’affecter des stratégies vocales aux utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="2fa48-110">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
  - <span data-ttu-id="2fa48-p101">**CsUserAdministrator :** ce rôle permet à l’administrateur de gérer les propriétés des utilisateurs, par exemple, pour activer Voix Entreprise pour un utilisateur. Ce rôle permet également à l’administrateur d’affecter des stratégies par utilisateur, à l’exception de la stratégie d’archivage, et de gérer les téléphones de partie commune et les périphériques analogiques.</span><span class="sxs-lookup"><span data-stu-id="2fa48-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
  - <span data-ttu-id="2fa48-113">**CsAdministrator :** ce rôle permet à l’utilisateur d’effectuer toutes les tâches des rôles CsVoiceAdministrator et CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2fa48-113">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
- <span data-ttu-id="2fa48-114">L’infrastructure MKI (Managed Key Infrastructure) est déployée et configurée à l’aide d’une infrastructure d’autorité de certification Microsoft ou tierce.</span><span class="sxs-lookup"><span data-stu-id="2fa48-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2fa48-115">Pour plus d’informations sur la configuration requise des certificats dans Skype pour Business Server, reportez-vous à la section [exigences environnementales pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fa48-115">For details about certificate requirements in Skype for Business Server, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="user-configuration"></a><span data-ttu-id="2fa48-116">Configuration utilisateur</span><span class="sxs-lookup"><span data-stu-id="2fa48-116">User configuration</span></span>

<span data-ttu-id="2fa48-117">Si vous colocalisé avec chaque pool frontal, le serveur de médiation ou le serveur Standard Edition server pendant le déploiement de Front-End, les paramètres utilisateur nécessaires pour les Voix Entreprise ont été configurés automatiquement lors de l’installation des fichiers de ces rôles de serveur.</span><span class="sxs-lookup"><span data-stu-id="2fa48-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>
  
<span data-ttu-id="2fa48-118">Si vous déployez récemment la charge de travail de Voix Entreprise à ce moment, avant de commencer le processus de déploiement, désigner un numéro de téléphone principal pour chaque utilisateur à qui vous souhaitez activer pour les Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="2fa48-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="2fa48-119">En tant qu’administrateur, vous devez vous assurer que ce numéro est unique.</span><span class="sxs-lookup"><span data-stu-id="2fa48-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="2fa48-120">Avant la mise en oeuvre, principal de tous les de téléphone numéros doivent être normalisées (correctement mis en forme) et copiés vers la propriété de **Ligne URI** de chaque utilisateur à l’aide de Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="2fa48-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user's **Line URI** property using Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2fa48-121">Pour obtenir des exemples des numéros de téléphone principaux requis pour le déploiement de Voix Entreprise, reportez-vous à la rubrique [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span><span class="sxs-lookup"><span data-stu-id="2fa48-121">For examples of primary phone numbers required for Enterprise Voice deployment, see [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span></span> 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="2fa48-122">Étapes suivantes : installation des fichiers ou configuration de la connectivité RTC</span><span class="sxs-lookup"><span data-stu-id="2fa48-122">Next Steps: Install files or configure PSTN connectivity</span></span>

<span data-ttu-id="2fa48-123">Après avoir vérifié le logiciel et la configuration requise pour les Voix Entreprise, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="2fa48-123">After verifying software and environmental prerequisites for Enterprise Voice you can either:</span></span>
  
- <span data-ttu-id="2fa48-124">Installer le serveur de médiation, comme décrit dans le [déploiement d’un serveur de médiation dans le Générateur de topologie dans Skype pour Business Server 2015](deploy-a-mediation-server.md), mais uniquement si vous souhaitez déployer un serveur de médiation autonome ou un pool, car les serveurs de médiation sont installés dans le cadre de l’avant Pool de fin ou le processus de déploiement du serveur Standard Edition lorsque colocalisés.</span><span class="sxs-lookup"><span data-stu-id="2fa48-124">Install the Mediation Server, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server 2015](deploy-a-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>
    
- <span data-ttu-id="2fa48-125">Ou bien, commencer à configurer les paramètres à acheminer les appels pour les utilisateurs de Voix Entreprise, comme décrit dans les [puits de configurer dans Skype pour Business Server 2015](configure-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="2fa48-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configure trunks in Skype for Business Server 2015](configure-trunks.md).</span></span>
    

