---
title: Plan for Shared Line Appearance in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/21/2016
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
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: Lisez cette rubrique pour découvrir comment planifier l’apparence de ligne partagée (SLA) dans Skype Entreprise Server 2015, mise à jour cumulative de novembre 2015.
ms.openlocfilehash: d7fa13b36c232e37c79e8509de71b4ac29ceff72
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813344"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="f46ed-103">Plan for Shared Line Appearance in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f46ed-103">Plan for Shared Line Appearance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f46ed-104">Lisez cette rubrique pour découvrir comment planifier l’apparence de ligne partagée (SLA) dans Skype Entreprise Server 2015, mise à jour cumulative de novembre 2015.</span><span class="sxs-lookup"><span data-stu-id="f46ed-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="f46ed-105">L’apparence de ligne partagée est une fonctionnalité de Skype Entreprise qui permet de gérer plusieurs appels sur un numéro spécifique appelé numéro partagé.</span><span class="sxs-lookup"><span data-stu-id="f46ed-105">Shared Line Appearance is a feature in Skype for Business for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="f46ed-106">Le SLA peut configurer n’importe quel utilisateur Skype Entreprise activé pour la voix d’entreprise en tant que numéro partagé avec plusieurs lignes pour répondre à plusieurs appels.</span><span class="sxs-lookup"><span data-stu-id="f46ed-106">SLA can configure any enterprise voice enabled Skype for Business user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="f46ed-107">Les appels ne sont pas réellement reçus sur le numéro partagé, mais ils sont transmis aux utilisateurs qui agissent en tant que délégués du numéro partagé.</span><span class="sxs-lookup"><span data-stu-id="f46ed-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="f46ed-108">N’importe lequel des délégués peut prendre l’appel pendant que le reste des délégués reçoit une notification sur leur téléphone sur la personne qui a pris l’appel et sur la ligne occupée.</span><span class="sxs-lookup"><span data-stu-id="f46ed-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="f46ed-109">Le nombre de lignes et les délégués sont configurables pour un numéro partagé dans le SLA.</span><span class="sxs-lookup"><span data-stu-id="f46ed-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="f46ed-110">En outre, les options avancées, telles que BusyOption (ce qui se produit lorsque toutes les lignes sont occupées) et MissedCallOption (le cas où aucun délégué ne prend un appel), peuvent également être configurées pour un numéro partagé.</span><span class="sxs-lookup"><span data-stu-id="f46ed-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>
  
<span data-ttu-id="f46ed-111">Le SLA est pris en charge uniquement sur les appareils téléphoniques suivants (il n’est pas pris en charge pour les clients Skype Entreprise sur des ordinateurs, des téléphones mobiles ou d’autres appareils) :</span><span class="sxs-lookup"><span data-stu-id="f46ed-111">SLA is supported only on the following phone devices (it is not supported for Skype for Business clients on computers, mobile phones, or other devices):</span></span> 
  
- <span data-ttu-id="f46ed-112">Polycom VVX300 avec mise à jour du microprogramme 5.4.1</span><span class="sxs-lookup"><span data-stu-id="f46ed-112">Polycom VVX300 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="f46ed-113">Polycom VVX400 avec mise à jour du microprogramme 5.4.1</span><span class="sxs-lookup"><span data-stu-id="f46ed-113">Polycom VVX400 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="f46ed-114">Polycom VVX500 avec mise à jour du microprogramme 5.4.1</span><span class="sxs-lookup"><span data-stu-id="f46ed-114">Polycom VVX500 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="f46ed-115">Polycom VVX600 avec mise à jour du microprogramme 5.4.1</span><span class="sxs-lookup"><span data-stu-id="f46ed-115">Polycom VVX600 with firmware update 5.4.1</span></span>
    
<span data-ttu-id="f46ed-116">Le SLA est une nouvelle fonctionnalité de Skype Entreprise Server, mise à jour cumulative de novembre 2015.</span><span class="sxs-lookup"><span data-stu-id="f46ed-116">SLA is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="f46ed-117">Pour plus d’informations sur le déploiement du SLA, voir [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="f46ed-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).</span></span>
  
## <a name="feature-list"></a><span data-ttu-id="f46ed-118">Liste des fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="f46ed-118">Feature List</span></span>

<span data-ttu-id="f46ed-119">La configuration d’un groupe de SLA active les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f46ed-119">Setting up an SLA group enables the following:</span></span>
  
- <span data-ttu-id="f46ed-120">Tous les délégués du groupe peuvent répondre aux appels entrants vers le même numéro partagé.</span><span class="sxs-lookup"><span data-stu-id="f46ed-120">All delegates in the group can answer inbound calls to the same shared number.</span></span> <span data-ttu-id="f46ed-121">Les appels peuvent être basés sur PSTN ou SIP.</span><span class="sxs-lookup"><span data-stu-id="f46ed-121">The calls can be PSTN-based or SIP-based.</span></span>
    
- <span data-ttu-id="f46ed-122">Les délégués peuvent conserver et prendre des appels.</span><span class="sxs-lookup"><span data-stu-id="f46ed-122">Delegates can hold and pick up calls.</span></span>
    
- <span data-ttu-id="f46ed-123">Les délégués peuvent transférer des appels vers un numéro en dehors du groupe SLA.</span><span class="sxs-lookup"><span data-stu-id="f46ed-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>
    
- <span data-ttu-id="f46ed-124">Les délégués peuvent voir le nombre d’appels actuellement sur le numéro partagé et afficher l’état de chacun de ces appels.</span><span class="sxs-lookup"><span data-stu-id="f46ed-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>
    
- <span data-ttu-id="f46ed-125">Vous pouvez configurer un nombre maximal d’appels simultanés pour le numéro partagé.</span><span class="sxs-lookup"><span data-stu-id="f46ed-125">You can configure a maximum number of concurrent calls for the shared number.</span></span> <span data-ttu-id="f46ed-126">Vous pouvez également définir la façon dont vous souhaitez que les appels supplémentaires soient gérés une fois ce maximum atteint.</span><span class="sxs-lookup"><span data-stu-id="f46ed-126">You can also set how you want additional calls to be handled after this maximum is reached.</span></span> <span data-ttu-id="f46ed-127">Les appels superflus peuvent être rejetés avec une signal occupé, transmis à un autre numéro ou transmis à la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="f46ed-127">Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>
    
- <span data-ttu-id="f46ed-128">Vous pouvez configurer la façon dont vous souhaitez que les appels manqués (appels non pris après un certain temps) soient gérés.</span><span class="sxs-lookup"><span data-stu-id="f46ed-128">You can configure how you want missed calls (calls not picked up after a certain time) to be handled.</span></span> <span data-ttu-id="f46ed-129">Si vous activez la messagerie vocale pour l’identité du groupe, les appels manqués sont automatiquement mis à la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="f46ed-129">If you enable voice mail for the group identity, missed calls automatically go to voice mail.</span></span> <span data-ttu-id="f46ed-130">Si la messagerie vocale n’est pas activée pour l’identité du groupe (numéro partagé), vous pouvez choisir de rejeter les appels manqués avec une signal d’occupé, de les envoyer à un autre numéro ou de les déconnecter.</span><span class="sxs-lookup"><span data-stu-id="f46ed-130">If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>
    

