---
title: Planification du mode partage de lignes dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Pour plus d’informations sur la planification de l’apparence des lignes partagées (SLA) dans Skype entreprise Server 2015, la mise à jour cumulative 2015 de novembre, reportez-vous à cette rubrique.
ms.openlocfilehash: 14f0f6cbd163ecff42543d3ad57bed0020434cfb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802434"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="5e48d-103">Planification du mode partage de lignes dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5e48d-103">Plan for Shared Line Appearance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5e48d-104">Pour plus d’informations sur la planification de l’apparence des lignes partagées (SLA) dans Skype entreprise Server 2015, la mise à jour cumulative 2015 de novembre, reportez-vous à cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="5e48d-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="5e48d-105">L’apparence des lignes partagées est une fonctionnalité de Skype entreprise permettant de gérer plusieurs appels sur un numéro particulier appelé numéro partagé.</span><span class="sxs-lookup"><span data-stu-id="5e48d-105">Shared Line Appearance is a feature in Skype for Business for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="5e48d-106">SLA peut configurer n’importe quel utilisateur Skype entreprise doté d’un numéro de téléphone partagé sur plusieurs lignes pour répondre à des appels multiples.</span><span class="sxs-lookup"><span data-stu-id="5e48d-106">SLA can configure any enterprise voice enabled Skype for Business user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="5e48d-107">Les appels ne sont pas reçus réellement sur le numéro partagé, mais ils sont transférés vers les utilisateurs qui agissent en tant que délégués pour le numéro partagé.</span><span class="sxs-lookup"><span data-stu-id="5e48d-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="5e48d-108">Les délégués peuvent prendre l’appel, tandis que les autres reçoivent une notification sur leur téléphone indiquant le nom de la personne qui a pris l’appel et la ligne qui est occupée.</span><span class="sxs-lookup"><span data-stu-id="5e48d-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="5e48d-109">Le nombre de lignes et le nombre de délégués sont configurables pour un numéro partagé en mode partage de lignes.</span><span class="sxs-lookup"><span data-stu-id="5e48d-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="5e48d-110">De plus, les options avancées, comme BusyOption (ce qui est le cas lorsque toutes les lignes sont occupées) et MissedCallOption (ce qui est le cas lorsqu’aucun des délégués ne prend d’appel), peuvent également être configurées pour un numéro partagé.</span><span class="sxs-lookup"><span data-stu-id="5e48d-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>
  
<span data-ttu-id="5e48d-111">Le SLA est uniquement pris en charge sur les appareils mobiles suivants (il n’est pas pris en charge pour les clients Skype entreprise sur des ordinateurs, des téléphones mobiles ou d’autres appareils) :</span><span class="sxs-lookup"><span data-stu-id="5e48d-111">SLA is supported only on the following phone devices (it is not supported for Skype for Business clients on computers, mobile phones, or other devices):</span></span> 
  
- <span data-ttu-id="5e48d-112">Polycom VVX300 avec mise à jour du microprogramme 5.4.1</span><span class="sxs-lookup"><span data-stu-id="5e48d-112">Polycom VVX300 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="5e48d-113">Polycom VVX400 avec mise à jour du microprogramme 5.4.1</span><span class="sxs-lookup"><span data-stu-id="5e48d-113">Polycom VVX400 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="5e48d-114">Polycom VVX500 avec mise à jour du microprogramme 5.4.1</span><span class="sxs-lookup"><span data-stu-id="5e48d-114">Polycom VVX500 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="5e48d-115">Polycom VVX600 avec mise à jour du microprogramme 5.4.1</span><span class="sxs-lookup"><span data-stu-id="5e48d-115">Polycom VVX600 with firmware update 5.4.1</span></span>
    
<span data-ttu-id="5e48d-116">SLA est une nouvelle fonctionnalité de Skype entreprise Server, la mise à jour cumulative 2015 de novembre.</span><span class="sxs-lookup"><span data-stu-id="5e48d-116">SLA is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="5e48d-117">Pour plus d’informations sur le déploiement du mode partage de lignes, reportez-vous à la rubrique [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="5e48d-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).</span></span>
  
## <a name="feature-list"></a><span data-ttu-id="5e48d-118">Liste des fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="5e48d-118">Feature List</span></span>

<span data-ttu-id="5e48d-119">La configuration d’un groupe de mode partage de lignes permet les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="5e48d-119">Setting up an SLA group enables the following:</span></span>
  
- <span data-ttu-id="5e48d-p102">Tous les délégués du groupe peuvent répondre aux appels entrants vers le même numéro partagé. Ces appels peuvent être basés sur RTC ou le protocole SIP.</span><span class="sxs-lookup"><span data-stu-id="5e48d-p102">All delegates in the group can answer inbound calls to the same shared number. The calls can be PSTN-based or SIP-based.</span></span>
    
- <span data-ttu-id="5e48d-122">Les délégués peuvent mettre en attente des appels ou les prendre.</span><span class="sxs-lookup"><span data-stu-id="5e48d-122">Delegates can hold and pick up calls.</span></span>
    
- <span data-ttu-id="5e48d-123">Les délégués peuvent transférer des appels vers un numéro extérieur au groupe de mode partage de lignes.</span><span class="sxs-lookup"><span data-stu-id="5e48d-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>
    
- <span data-ttu-id="5e48d-124">Les délégués peuvent voir le nombre d’appels actuels sur le numéro partagé et afficher le statut de chacun de ces appels.</span><span class="sxs-lookup"><span data-stu-id="5e48d-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>
    
- <span data-ttu-id="5e48d-p103">Vous pouvez configurer un nombre maximal d’appels simultanés pour le numéro partagé. Vous pouvez également définir comment traiter les nouveaux appels une fois cette limite atteinte. Les appels hors limite peuvent être rejetés avec une tonalité Occupé, transférés vers un autre numéro ou transférés vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="5e48d-p103">You can configure a maximum number of concurrent calls for the shared number. You can also set how you want additional calls to be handled after this maximum is reached. Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>
    
- <span data-ttu-id="5e48d-p104">Vous pouvez définir comment traiter les appels manqués (appels non pris après un certain temps). Si vous activez la messagerie vocale pour le groupe, les appels manqués sont redirigés automatiquement vers la messagerie vocale. Si vous n’avez pas activé la messagerie vocale pour le groupe (numéro partagé), vous pouvez décider de rejeter les appels manqués avec une tonalité Occupé, de les transférer vers un autre numéro ou de les déconnecter.</span><span class="sxs-lookup"><span data-stu-id="5e48d-p104">You can configure how you want missed calls (calls not picked up after a certain time) to be handled. If you enable voice mail for the group identity, missed calls automatically go to voice mail. If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>
    

