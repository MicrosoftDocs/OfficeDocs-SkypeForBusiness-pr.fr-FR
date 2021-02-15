---
title: Conditions préalables de sécurité et de configuration pour Voix Entreprise dans Skype Entreprise Server
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
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 'Résumé : Découvrez les conditions préalables de sécurité et de configuration requises pour Voix Entreprise dans Skype Entreprise Server.'
ms.openlocfilehash: 77efbf231f83c6d3c31254c9ab742de7e2b226e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830844"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="bb3ec-103">Conditions préalables de sécurité et de configuration pour Voix Entreprise dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="bb3ec-103">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="bb3ec-104">**Résumé :** Découvrez les conditions préalables de sécurité et de configuration requises pour Voix Entreprise dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="bb3ec-104">**Summary:** Learn about the security and configuration prerequisites for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="bb3ec-105">Avant de déployer Voix Entreprise, vérifiez que votre infrastructure répond aux conditions préalables suivantes en matière de sécurité, de configuration utilisateur et de matériel spécifique au scénario.</span><span class="sxs-lookup"><span data-stu-id="bb3ec-105">Before deploying Enterprise Voice, verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span> 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="bb3ec-106">Droits d’administration et infrastructure de certificats</span><span class="sxs-lookup"><span data-stu-id="bb3ec-106">Administrative rights and certificate infrastructure</span></span>

<span data-ttu-id="bb3ec-107">Avant de déployer, vérifiez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="bb3ec-107">Before deploying, check the following:</span></span>
  
- <span data-ttu-id="bb3ec-108">Les administrateurs déployant Voix Entreprise doivent être membres du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="bb3ec-108">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>
    
- <span data-ttu-id="bb3ec-109">Les administrateurs doivent disposer des droits appropriés pour effectuer les tâches de configuration :</span><span class="sxs-lookup"><span data-stu-id="bb3ec-109">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
  - <span data-ttu-id="bb3ec-110">**CsVoiceAdministrator :** Ce rôle permet à l’administrateur d’effectuer des tâches de configuration vocale, de gérer les applications vocales et d’affecter des stratégies vocales aux utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="bb3ec-110">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
  - <span data-ttu-id="bb3ec-p101">**CsUserAdministrator :** Ce rôle permet à l’administrateur de gérer les propriétés des utilisateurs, par exemple, pour activer Voix Entreprise pour un utilisateur. Ce rôle permet également à l’administrateur d’affecter des stratégies par utilisateur, à l’exception de la stratégie d’archivage, et de gérer les téléphones de partie commune et les périphériques analogues.</span><span class="sxs-lookup"><span data-stu-id="bb3ec-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
  - <span data-ttu-id="bb3ec-113">**CsAdministrator :** Ce rôle permet à l’utilisateur d’effectuer toutes les tâches des rôles CsVoiceAdministrator et CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="bb3ec-113">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
- <span data-ttu-id="bb3ec-114">L’infrastructure MKI (Managed Key Infrastructure) est déployée et configurée, à l’aide d’une infrastructure d’autorité de certification Microsoft ou tierce.</span><span class="sxs-lookup"><span data-stu-id="bb3ec-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bb3ec-115">Pour plus d’informations sur les certificats requis dans Skype Entreprise Server, voir [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or Server requirements for Skype for Business Server [2019](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb3ec-115">For details about certificate requirements in Skype for Business Server, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
## <a name="user-configuration"></a><span data-ttu-id="bb3ec-116">Configuration utilisateur</span><span class="sxs-lookup"><span data-stu-id="bb3ec-116">User configuration</span></span>

<span data-ttu-id="bb3ec-117">Si vous avez coqueté le serveur de médiation avec chaque pool frontal ou serveur Standard Edition Server lors du déploiement frontal, les paramètres utilisateur nécessaires pour Voix Entreprise ont été configurés automatiquement lors de l’installation des fichiers pour ces rôles serveur.</span><span class="sxs-lookup"><span data-stu-id="bb3ec-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>
  
<span data-ttu-id="bb3ec-118">Si vous procédez à un nouveau déploiement de la charge de travail de Voix Entreprise, avant de commencer le processus de déploiement, désignez un numéro de téléphone principal pour chaque utilisateur pour lequel vous envisagez d’activer Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="bb3ec-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="bb3ec-119">En tant qu’administrateur, vous devez vous assurer que ce numéro est unique.</span><span class="sxs-lookup"><span data-stu-id="bb3ec-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="bb3ec-120">Avant l’implémentation, tous les numéros de téléphone principaux doivent être normalisés (correctement formatés) et copiés dans la propriété **d’URI** de ligne de chaque utilisateur à l’aide du Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="bb3ec-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user's **Line URI** property using Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bb3ec-121">Pour obtenir des exemples de numéros de téléphone principaux requis pour Voix Entreprise déploiement, voir [exemples de règles de normalisation.](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules)</span><span class="sxs-lookup"><span data-stu-id="bb3ec-121">For examples of primary phone numbers required for Enterprise Voice deployment, see [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span></span> 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="bb3ec-122">Étapes suivantes : installer des fichiers ou configurer la connectivité PSTN</span><span class="sxs-lookup"><span data-stu-id="bb3ec-122">Next Steps: Install files or configure PSTN connectivity</span></span>

<span data-ttu-id="bb3ec-123">Après avoir vérifié les conditions préalables logicielles et environnementales pour Voix Entreprise vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="bb3ec-123">After verifying software and environmental prerequisites for Enterprise Voice you can either:</span></span>
  
- <span data-ttu-id="bb3ec-124">Installez le serveur de médiation, comme décrit dans Déployer un serveur de médiation dans le Générateur de topologies dans Skype Entreprise [Server,](deploy-a-mediation-server.md)mais uniquement si vous souhaitez déployer un serveur de médiation ou un pool autonome, car les serveurs de médiation sont installés dans le cadre du processus de déploiement du pool frontal ou du serveur Standard Edition lors de la cocation.</span><span class="sxs-lookup"><span data-stu-id="bb3ec-124">Install the Mediation Server, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>
    
- <span data-ttu-id="bb3ec-125">Vous pouvez également commencer à configurer les paramètres pour router les appels pour Voix Entreprise utilisateurs, comme décrit dans La configuration des [trunks dans Skype Entreprise Server.](configure-trunks.md)</span><span class="sxs-lookup"><span data-stu-id="bb3ec-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configure trunks in Skype for Business Server](configure-trunks.md).</span></span>
    

