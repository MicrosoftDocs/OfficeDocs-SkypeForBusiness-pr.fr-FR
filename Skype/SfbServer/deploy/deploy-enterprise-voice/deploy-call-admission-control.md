---
title: Déploiement du contrôle d’admission des appels dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: Le contrôle d’admission des appels (CAC) est une solution qui détermine si une session en temps réel peut être établie en tenant compte de la bande passante disponible pour éviter toute dégradation de la qualité audio/vidéo sur des réseaux saturés. Pour plus d’informations, voir Plan d’appel de contrôle d’admission dans Skype pour Business Server 2015.
ms.openlocfilehash: 0302663546a099e682b5dc405625d4519fe998d9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-call-admission-control-in-skype-for-business-server-2015"></a><span data-ttu-id="8580e-104">Déploiement du contrôle d’admission des appels dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="8580e-104">Deploy call admission control in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8580e-105">Le contrôle d’admission des appels (CAC) est une solution qui détermine si une session en temps réel peut être établie en tenant compte de la bande passante disponible pour éviter toute dégradation de la qualité audio/vidéo sur des réseaux saturés.</span><span class="sxs-lookup"><span data-stu-id="8580e-105">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="8580e-106">Pour plus d’informations, consultez le [Plan d’appel de contrôle d’admission dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="8580e-106">For more information, see [Plan for call admission control in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
### <a name="to-deploy-call-admission-control"></a><span data-ttu-id="8580e-107">Pour déployer le contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="8580e-107">To deploy Call Admission Control</span></span>

1.  <span data-ttu-id="8580e-108">Rassembler toutes les informations requises pour la topologie de votre réseau d’entreprise, comme décrit dans [exemple : collecte des besoins pour un appel de contrôle d’admission dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8580e-108">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
    
2. <span data-ttu-id="8580e-109">Si ce n’est déjà fait, vous devez définir des régions et des sites réseau et associer les sous-réseaux à des sites réseau.</span><span class="sxs-lookup"><span data-stu-id="8580e-109">If you have not done so already, you must define network regions and sites, and associate subnets with network sites.</span></span> <span data-ttu-id="8580e-110">Pour plus d’informations, consultez [zones de réseau de déployer, des sites et des sous-réseaux dans Skype pour entreprise 2015](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="8580e-110">For details, see [Deploy network regions, sites and subnets in Skype for Business 2015](deploy-network.md).</span></span>
    
3. <span data-ttu-id="8580e-111">Créer des profils de stratégie, comme détaillé dans la [création des profils de stratégie de bande passante dans Skype pour Business Server 2015](create-bandwidth-policy-profiles.md) de la bande passante</span><span class="sxs-lookup"><span data-stu-id="8580e-111">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server 2015](create-bandwidth-policy-profiles.md)</span></span>
    
4. <span data-ttu-id="8580e-112">Créer des liens de la région de réseau, comme détaillé dans la [Création de liens de région réseau dans Skype pour Business Server 2015](create-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="8580e-112">Create network region links, as detailed in [Create network region links in Skype for Business Server 2015](create-network-region-links.md).</span></span>
    
5. <span data-ttu-id="8580e-113">Créer des itinéraires inter-REGIONALE réseau, comme détaillé dans les [gammes interrégional de réseau créer dans Skype pour Business Server 2015](create-network-interregional-routes.md).</span><span class="sxs-lookup"><span data-stu-id="8580e-113">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server 2015](create-network-interregional-routes.md).</span></span>
    
6. <span data-ttu-id="8580e-114">Créer des stratégies de réseau intersite, comme détaillé dans [créer les stratégies réseau intersites dans Skype pour Business Server 2015](create-network-intersite-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8580e-114">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server 2015](create-network-intersite-policies.md).</span></span>
    
7. <span data-ttu-id="8580e-115">Activer l’appel de contrôle d’admission, comme détaillé dans le [contrôle d’admission activer appel dans Skype pour Business Server 2015](enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="8580e-115">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server 2015](enable-call-admission-control.md).</span></span>
    
8. <span data-ttu-id="8580e-116">Vérifiez quelques derniers paramètres pour vous assurer que tout est configuré correctement.</span><span class="sxs-lookup"><span data-stu-id="8580e-116">Check a few final settings, to make sure everything is set up correctly.</span></span> <span data-ttu-id="8580e-117">Pour plus d’informations, consultez [appeler le déploiement de contrôle d’admission : liste de vérification finale pour Skype pour Business Server 2015](final-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="8580e-117">For details, see [Call admission control deployment: final checklist for Skype for Business Server 2015](final-checklist.md).</span></span>
    

