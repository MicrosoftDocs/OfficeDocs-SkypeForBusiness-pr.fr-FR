---
title: Définir les conditions requises pour les appels d’urgence dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d891a212-8ad9-4bfa-9ca7-04921c46fb45
description: Récapitule les étapes nécessaires à l’activation d’E9-1-1 dans Skype Entreprise Server Voix Entreprise, selon que vous avez un fournisseur de services E9-1-1 de la branche SIP ou une passerelle ELIN.
ms.openlocfilehash: 8efd38657a80bee1ecd979e8730feacfb980053e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825814"
---
# <a name="define-your-requirements-for-emergency-calls-in-skype-for-business-server"></a><span data-ttu-id="31e29-103">Définir les conditions requises pour les appels d’urgence dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="31e29-103">Define your requirements for emergency calls in Skype for Business Server</span></span>
 
<span data-ttu-id="31e29-104">Récapitule les étapes nécessaires à l’activation d’E9-1-1 dans Skype Entreprise Server Voix Entreprise, selon que vous avez un fournisseur de services E9-1-1 de la branche SIP ou une passerelle ELIN.</span><span class="sxs-lookup"><span data-stu-id="31e29-104">Summarizes the steps necessary for enabling E9-1-1 in Skype for Business Server Enterprise Voice, depending on whether you have a SIP trunk E9-1-1 service provider or an ELIN gateway.</span></span>
  
<span data-ttu-id="31e29-105">Avant de commencer un déploiement Skype Entreprise Server E9-1-1, vous devez d’abord être en mesure de répondre aux questions détaillées dans les sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="31e29-105">Before you begin a Skype for Business Server E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="31e29-106">La planification dont vous avez besoin dépend du type de solution E9-1-1 que vous choisissez de déployer : fournisseur de services E9-1-1 de jonction SIP ou numéro ELIN (Emergency Location Identification Number).</span><span class="sxs-lookup"><span data-stu-id="31e29-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="31e29-107">Le tableau suivant identifie les sections de ce manuel de planification que vous devrez consulter pour chacune de ces solutions.</span><span class="sxs-lookup"><span data-stu-id="31e29-107">The following table identifies the sections in this planning workbook that you'll need to review for each of those solutions.</span></span>
  
<span data-ttu-id="31e29-108">**Étapes de planification par type de solution E9-1-1**</span><span class="sxs-lookup"><span data-stu-id="31e29-108">**Planning Steps by Type of E9-1-1 Solution**</span></span>

|<span data-ttu-id="31e29-109">**Fournisseur de services de jonction SIP**</span><span class="sxs-lookup"><span data-stu-id="31e29-109">**SIP trunk service provider**</span></span>|<span data-ttu-id="31e29-110">**Passerelle ELIN**</span><span class="sxs-lookup"><span data-stu-id="31e29-110">**ELIN gateway**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="31e29-111">Définir l’étendue du déploiement E9-1-1 dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="31e29-111">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |[<span data-ttu-id="31e29-112">Définir l’étendue du déploiement E9-1-1 dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="31e29-112">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |
|[<span data-ttu-id="31e29-113">Définir les éléments réseau utilisés pour déterminer l’emplacement dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="31e29-113">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |[<span data-ttu-id="31e29-114">Définir les éléments réseau utilisés pour déterminer l’emplacement dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="31e29-114">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |
|[<span data-ttu-id="31e29-115">Activer les utilisateurs pour E9-1-1 dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="31e29-115">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |[<span data-ttu-id="31e29-116">Activer les utilisateurs pour E9-1-1 dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="31e29-116">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |
|[<span data-ttu-id="31e29-117">Gérer les emplacements pour les fournisseurs de services de ligne de transport SIP dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="31e29-117">Manage locations for SIP trunk service providers in Skype for Business Server</span></span>](manage-locations.md) <br/> |[<span data-ttu-id="31e29-118">Gérer les emplacements des passerelles ELIN dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="31e29-118">Manage locations for ELIN gateways in Skype for Business Server</span></span>](elin-gateways.md) <br/> |
|[<span data-ttu-id="31e29-119">Définir l’expérience utilisateur pour l’acquisition manuelle d’un emplacement dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="31e29-119">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |[<span data-ttu-id="31e29-120">Définir l’expérience utilisateur pour l’acquisition manuelle d’un emplacement dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="31e29-120">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |
|[<span data-ttu-id="31e29-121">Conception de la trunk SIP pour E9-1-1 dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="31e29-121">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>](design-the-sip-trunk.md) <br/> |[<span data-ttu-id="31e29-122">Inclure le service de sécurité dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="31e29-122">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |
|[<span data-ttu-id="31e29-123">Inclure le service de sécurité dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="31e29-123">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |[<span data-ttu-id="31e29-124">Planifier des stratégies d’emplacement pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="31e29-124">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> |
|[<span data-ttu-id="31e29-125">Choisir un fournisseur de services E9-1-1 pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="31e29-125">Choose an E9-1-1 service provider for Skype for Business Server</span></span>](choose-a-service-provider.md) <br/> |[<span data-ttu-id="31e29-126">Attribution d’une étendue de stratégie d’emplacement dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="31e29-126">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> |
|[<span data-ttu-id="31e29-127">Planifier des stratégies d’emplacement pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="31e29-127">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> ||
|[<span data-ttu-id="31e29-128">Attribution d’une étendue de stratégie d’emplacement dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="31e29-128">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> ||
   

