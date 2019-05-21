---
title: Déployer le contrôle d’admission des appels dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: Le contrôle d’admission des appels (CAC) est une solution qui détermine si une session en temps réel peut être établie en tenant compte de la bande passante disponible pour éviter toute dégradation de la qualité audio/vidéo sur des réseaux saturés.
ms.openlocfilehash: 7f7f8dee4e25061533564ce517f797281bef042e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280438"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="cc12b-103">Déployer le contrôle d’admission des appels dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="cc12b-103">Deploy call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="cc12b-104">Le contrôle d’admission des appels (CAC) est une solution qui détermine si une session en temps réel peut être établie en tenant compte de la bande passante disponible pour éviter toute dégradation de la qualité audio/vidéo sur des réseaux saturés.</span><span class="sxs-lookup"><span data-stu-id="cc12b-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="cc12b-105">Pour plus d’informations, reportez-vous à la section [planifier le contrôle d’admission des appels dans Skype entreprise Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="cc12b-105">For more information, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
### <a name="to-deploy-call-admission-control"></a><span data-ttu-id="cc12b-106">Pour déployer le contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="cc12b-106">To deploy Call Admission Control</span></span>

1.  <span data-ttu-id="cc12b-107">Collectez toutes les informations requises pour la topologie de votre réseau d’entreprise, comme décrit dans l' [exemple ci-dessous: rassemblement des exigences de contrôle d’admission des appels dans Skype entreprise Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc12b-107">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
    
2. <span data-ttu-id="cc12b-108">Si ce n’est déjà fait, vous devez définir des régions et des sites réseau et associer les sous-réseaux à des sites réseau.</span><span class="sxs-lookup"><span data-stu-id="cc12b-108">If you have not done so already, you must define network regions and sites, and associate subnets with network sites.</span></span> <span data-ttu-id="cc12b-109">Pour plus d’informations, reportez-vous à la rubrique [déploiement de régions, de sites et de sous-réseaux dans Skype entreprise](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="cc12b-109">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
3. <span data-ttu-id="cc12b-110">Créer des profils de stratégie de bande passante, comme détaillé dans [créer des profils de stratégie de bande passante dans Skype entreprise Server](create-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="cc12b-110">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md)</span></span>
    
4. <span data-ttu-id="cc12b-111">Créez des liens vers les régions de réseau, comme détaillé dans [créer des liens de région réseau dans Skype entreprise Server](create-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="cc12b-111">Create network region links, as detailed in [Create network region links in Skype for Business Server](create-network-region-links.md).</span></span>
    
5. <span data-ttu-id="cc12b-112">Créez des itinéraires réseau inter-régions, comme détaillé dans [créer des itinéraires réseau interrégionals dans Skype entreprise Server](create-network-interregional-routes.md).</span><span class="sxs-lookup"><span data-stu-id="cc12b-112">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server](create-network-interregional-routes.md).</span></span>
    
6. <span data-ttu-id="cc12b-113">Créez des stratégies d’intersite réseau, comme décrit dans la [création de stratégies d’intersite réseau dans Skype entreprise Server](create-network-intersite-policies.md).</span><span class="sxs-lookup"><span data-stu-id="cc12b-113">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server](create-network-intersite-policies.md).</span></span>
    
7. <span data-ttu-id="cc12b-114">Activez le contrôle d’admission des appels, comme indiqué dans la procédure [activer le contrôle d’admission des appels de Skype entreprise Server](enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="cc12b-114">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
8. <span data-ttu-id="cc12b-115">Vérifiez quelques derniers paramètres pour vous assurer que tout est configuré correctement.</span><span class="sxs-lookup"><span data-stu-id="cc12b-115">Check a few final settings, to make sure everything is set up correctly.</span></span> <span data-ttu-id="cc12b-116">Pour plus d’informations, reportez-vous à la rubrique [déploiement de contrôle d’admission des appels: liste de vérification finale pour Skype entreprise Server](final-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="cc12b-116">For details, see [Call admission control deployment: final checklist for Skype for Business Server](final-checklist.md).</span></span>
    

