---
title: Déployer le contrôle d’admission des appels dans Skype Entreprise Server
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
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: Le contrôle d’admission des appels (CAC) est une solution qui détermine si une session en temps réel peut être établie en tenant compte de la bande passante disponible pour éviter toute dégradation de la qualité audio/vidéo sur des réseaux saturés.
ms.openlocfilehash: af08afe02b1dc138aa38ded654d567aed6a09247
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836884"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="d0483-103">Déployer le contrôle d’admission des appels dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="d0483-103">Deploy call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="d0483-104">Le contrôle d’admission des appels (CAC) est une solution qui détermine si une session en temps réel peut être établie en tenant compte de la bande passante disponible pour éviter toute dégradation de la qualité audio/vidéo sur des réseaux saturés.</span><span class="sxs-lookup"><span data-stu-id="d0483-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="d0483-105">Pour plus d’informations, voir Planifier le contrôle [d’admission des appels dans Skype Entreprise Server.](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)</span><span class="sxs-lookup"><span data-stu-id="d0483-105">For more information, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
### <a name="to-deploy-call-admission-control"></a><span data-ttu-id="d0483-106">Pour déployer le contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="d0483-106">To deploy Call Admission Control</span></span>

1.  <span data-ttu-id="d0483-107">Rassemblez toutes les informations requises pour votre topologie de réseau d’entreprise, comme décrit dans l’exemple : Collecte des conditions requises pour le contrôle d’admission des appels [dans Skype Entreprise Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0483-107">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
    
2. <span data-ttu-id="d0483-108">Si vous ne l’avez pas déjà fait, vous devez définir des régions et des sites réseau et associer des sous-réseaux à des sites réseau.</span><span class="sxs-lookup"><span data-stu-id="d0483-108">If you have not done so already, you must define network regions and sites, and associate subnets with network sites.</span></span> <span data-ttu-id="d0483-109">Pour plus d’informations, voir Déployer des régions réseau, des sites et [des sous-réseaux dans Skype Entreprise.](deploy-network.md)</span><span class="sxs-lookup"><span data-stu-id="d0483-109">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
3. <span data-ttu-id="d0483-110">Créer des profils de stratégie de bande passante, comme détaillé dans Créer des profils de stratégie [de bande passante dans Skype Entreprise Server](create-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="d0483-110">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md)</span></span>
    
4. <span data-ttu-id="d0483-111">Créez des liens de région réseau, comme détaillé dans Créer des liens de région [réseau dans Skype Entreprise Server.](create-network-region-links.md)</span><span class="sxs-lookup"><span data-stu-id="d0483-111">Create network region links, as detailed in [Create network region links in Skype for Business Server](create-network-region-links.md).</span></span>
    
5. <span data-ttu-id="d0483-112">Créez des itinéraires inter-régions réseau, comme détaillé dans Créer des [itinéraires interrégion réseau dans Skype Entreprise Server.](create-network-interregional-routes.md)</span><span class="sxs-lookup"><span data-stu-id="d0483-112">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server](create-network-interregional-routes.md).</span></span>
    
6. <span data-ttu-id="d0483-113">Créez des stratégies intersite réseau, comme détaillé dans Créer des [stratégies intersite](create-network-intersite-policies.md)réseau dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d0483-113">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server](create-network-intersite-policies.md).</span></span>
    
7. <span data-ttu-id="d0483-114">Activez le contrôle d’admission des appels, comme détaillé dans Activer le contrôle [d’admission des appels dans Skype Entreprise Server.](enable-call-admission-control.md)</span><span class="sxs-lookup"><span data-stu-id="d0483-114">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
8. <span data-ttu-id="d0483-115">Vérifiez quelques paramètres finaux pour vous assurer que tout est correctement installé.</span><span class="sxs-lookup"><span data-stu-id="d0483-115">Check a few final settings, to make sure everything is set up correctly.</span></span> <span data-ttu-id="d0483-116">Pour plus d’informations, [voir Déploiement du contrôle d’admission des appels : liste de contrôle finale pour Skype Entreprise Server.](final-checklist.md)</span><span class="sxs-lookup"><span data-stu-id="d0483-116">For details, see [Call admission control deployment: final checklist for Skype for Business Server](final-checklist.md).</span></span>
    

