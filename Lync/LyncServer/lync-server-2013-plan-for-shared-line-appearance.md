---
title: 'Lync Server 2013 : planification de l’apparence des lignes partagées'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Shared Line Appearance
ms:assetid: a35c83d8-f531-445b-a8d2-d5d8cec77c6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712151(v=OCS.15)
ms:contentKeyID: 72522136
ms.date: 03/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 755bff84b8902e346135139d1c8c5b26c55605c1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755164"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="ed51e-102">Planifier l’apparence des lignes partagées dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed51e-102">Plan for Shared Line Appearance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed51e-103">_**Dernière modification de la rubrique :** 2016-03-21_</span><span class="sxs-lookup"><span data-stu-id="ed51e-103">_**Topic Last Modified:** 2016-03-21_</span></span>

<span data-ttu-id="ed51e-104">Pour plus d’informations sur la planification de l’apparence des lignes partagées dans Lync Server 2013, consultez la mise à jour cumulative 2016.</span><span class="sxs-lookup"><span data-stu-id="ed51e-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="ed51e-105">L’apparence des lignes partagées est une fonctionnalité de Lync Server 2013, mise à jour cumulative 2016 avril pour le traitement des appels multiples sur un numéro particulier appelé numéro partagé.</span><span class="sxs-lookup"><span data-stu-id="ed51e-105">Shared Line Appearance is a feature in Lync Server 2013, Cumulative Update April 2016 for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="ed51e-106">SLA peut configurer tout utilisateur de Lync pour l’entreprise à l’aide d’un numéro partagé avec plusieurs lignes pour répondre à plusieurs appels.</span><span class="sxs-lookup"><span data-stu-id="ed51e-106">SLA can configure any enterprise voice enabled Lync user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="ed51e-107">Les appels ne sont pas reçus réellement sur le numéro partagé, mais ils sont transférés vers les utilisateurs qui agissent en tant que délégués pour le numéro partagé.</span><span class="sxs-lookup"><span data-stu-id="ed51e-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="ed51e-108">Les délégués peuvent prendre l’appel, tandis que les autres reçoivent une notification sur leur téléphone indiquant le nom de la personne qui a pris l’appel et la ligne qui est occupée.</span><span class="sxs-lookup"><span data-stu-id="ed51e-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="ed51e-109">Le nombre de lignes et le nombre de délégués sont configurables pour un numéro partagé en mode partage de lignes.</span><span class="sxs-lookup"><span data-stu-id="ed51e-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="ed51e-110">De plus, les options avancées, comme BusyOption (ce qui est le cas lorsque toutes les lignes sont occupées) et MissedCallOption (ce qui est le cas lorsqu’aucun des délégués ne prend d’appel), peuvent également être configurées pour un numéro partagé.</span><span class="sxs-lookup"><span data-stu-id="ed51e-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>

<span data-ttu-id="ed51e-111">Le SLA est uniquement pris en charge sur les appareils mobiles suivants (il n’est pas pris en charge pour les clients Lync sur des ordinateurs, des téléphones mobiles ou d’autres appareils) :</span><span class="sxs-lookup"><span data-stu-id="ed51e-111">SLA is supported only on the following phone devices (it is not supported for Lync clients on computers, mobile phones, or other devices):</span></span>

  - <span data-ttu-id="ed51e-112">Polycom VVX300 avec mise à jour du microprogramme 5.4.1</span><span class="sxs-lookup"><span data-stu-id="ed51e-112">Polycom VVX300 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="ed51e-113">Polycom VVX400 avec mise à jour du microprogramme 5.4.1</span><span class="sxs-lookup"><span data-stu-id="ed51e-113">Polycom VVX400 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="ed51e-114">Polycom VVX500 avec mise à jour du microprogramme 5.4.1</span><span class="sxs-lookup"><span data-stu-id="ed51e-114">Polycom VVX500 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="ed51e-115">Polycom VVX600 avec mise à jour du microprogramme 5.4.1</span><span class="sxs-lookup"><span data-stu-id="ed51e-115">Polycom VVX600 with firmware update 5.4.1</span></span>

<span data-ttu-id="ed51e-116">SLA est une nouvelle fonctionnalité de Lync Server 2013, mise à jour cumulative 2016 avril.</span><span class="sxs-lookup"><span data-stu-id="ed51e-116">SLA is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="ed51e-117">Pour plus d’informations sur le déploiement du contrat de service d’application, voir [déploiement d’une ligne partagée dans Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="ed51e-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).</span></span>

<div>

## <a name="feature-list"></a><span data-ttu-id="ed51e-118">Liste des fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="ed51e-118">Feature List</span></span>

<span data-ttu-id="ed51e-119">La configuration d’un groupe de mode partage de lignes permet les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="ed51e-119">Setting up an SLA group enables the following:</span></span>

  - <span data-ttu-id="ed51e-p102">Tous les délégués du groupe peuvent répondre aux appels entrants vers le même numéro partagé. Ces appels peuvent être basés sur RTC ou le protocole SIP.</span><span class="sxs-lookup"><span data-stu-id="ed51e-p102">All delegates in the group can answer inbound calls to the same shared number. The calls can be PSTN-based or SIP-based.</span></span>

  - <span data-ttu-id="ed51e-122">Les délégués peuvent mettre en attente des appels ou les prendre.</span><span class="sxs-lookup"><span data-stu-id="ed51e-122">Delegates can hold and pick up calls.</span></span>

  - <span data-ttu-id="ed51e-123">Les délégués peuvent transférer des appels vers un numéro extérieur au groupe de mode partage de lignes.</span><span class="sxs-lookup"><span data-stu-id="ed51e-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>

  - <span data-ttu-id="ed51e-124">Les délégués peuvent voir le nombre d’appels actuels sur le numéro partagé et afficher le statut de chacun de ces appels.</span><span class="sxs-lookup"><span data-stu-id="ed51e-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>

  - <span data-ttu-id="ed51e-p103">Vous pouvez configurer un nombre maximal d’appels simultanés pour le numéro partagé. Vous pouvez également définir comment traiter les nouveaux appels une fois cette limite atteinte. Les appels hors limite peuvent être rejetés avec une tonalité Occupé, transférés vers un autre numéro ou transférés vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="ed51e-p103">You can configure a maximum number of concurrent calls for the shared number. You can also set how you want additional calls to be handled after this maximum is reached. Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>

  - <span data-ttu-id="ed51e-p104">Vous pouvez définir comment traiter les appels manqués (appels non pris après un certain temps). Si vous activez la messagerie vocale pour le groupe, les appels manqués sont redirigés automatiquement vers la messagerie vocale. Si vous n’avez pas activé la messagerie vocale pour le groupe (numéro partagé), vous pouvez décider de rejeter les appels manqués avec une tonalité Occupé, de les transférer vers un autre numéro ou de les déconnecter.</span><span class="sxs-lookup"><span data-stu-id="ed51e-p104">You can configure how you want missed calls (calls not picked up after a certain time) to be handled. If you enable voice mail for the group identity, missed calls automatically go to voice mail. If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

