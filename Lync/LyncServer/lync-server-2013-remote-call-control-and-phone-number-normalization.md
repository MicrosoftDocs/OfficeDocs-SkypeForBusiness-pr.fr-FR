---
title: 'Lync Server 2013 : contrôle d’appel distant et normalisation des numéros de téléphone'
description: 'Lync Server 2013 : contrôle d’appel distant et normalisation de numéro de téléphone.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remote call control and phone number normalization
ms:assetid: 291d9e87-4c65-4ea2-888f-517741391de5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558630(v=OCS.15)
ms:contentKeyID: 48183696
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edcb50678da7111aba066745bce5e356dd1ac7f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555810"
---
# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a><span data-ttu-id="39d10-103">Contrôle d’appel distant et normalisation des numéros de téléphone dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39d10-103">Remote call control and phone number normalization in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39d10-104">_**Dernière modification de la rubrique :** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="39d10-104">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="39d10-105">Les clients Lync téléchargent les règles de normalisation des numéros de téléphone dans le cadre du téléchargement de fichiers du service de carnet d’adresses (ABS).</span><span class="sxs-lookup"><span data-stu-id="39d10-105">Lync clients download phone number normalization rules as part of the Address Book Service (ABS) file download.</span></span> <span data-ttu-id="39d10-106">Dans les scénarios de contrôle d’appel distant, ces règles s’appliquent aux appels entrants et sortants de contrôle d’appel distant.</span><span class="sxs-lookup"><span data-stu-id="39d10-106">In remote call control scenarios, Address Book Service phone number normalization rules are applied to both incoming and outgoing remote call control calls.</span></span> <span data-ttu-id="39d10-107">Pour les appels entrants vers un utilisateur pour lequel le contrôle d’appel distant est activé, le numéro de téléphone de l’appelant est d’abord normalisé au format E.164 par la passerelle SIP/CSTA ou par un système PBX.</span><span class="sxs-lookup"><span data-stu-id="39d10-107">For incoming calls to a remote call control-enabled user, the phone number of the caller is first normalized to E.164 format by either the SIP/CSTA gateway or private branch exchange (PBX).</span></span> <span data-ttu-id="39d10-108">Lorsque Lync Server 2013 reçoit l’appel de la passerelle, il effectue une recherche de numéro inversée (RNL) sur le numéro de téléphone de l’appelant par rapport au numéro normalisé de la liste de contacts Microsoft Office Outlook de l’appelé ou de la liste d’adresses globale (LAG) stockée dans le service de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="39d10-108">When Lync Server 2013 receives the call from the gateway, it performs reverse number lookup (RNL) on the phone number of the caller against the normalized number in the callee’s Microsoft Office Outlook Contacts list or the global address list (GAL) that is stored in the Address Book Service.</span></span> <span data-ttu-id="39d10-109">Si une correspondance est trouvée, l’appelant est identifié par son nom dans la notification d’appel entrant.</span><span class="sxs-lookup"><span data-stu-id="39d10-109">If reverse number lookup successfully finds a match, the caller is identified by name in the incoming call notification.</span></span>

<span data-ttu-id="39d10-110">Pour les appels de contrôle d’appel distant sortants, Lync applique les règles de normalisation du service de carnet d’adresses au numéro composé avant d’acheminer l’appel vers la passerelle SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="39d10-110">For outgoing remote call control calls, Lync applies the Address Book Service phone number normalization rules to the dialed number before routing the call to the SIP/CSTA gateway.</span></span>

<span data-ttu-id="39d10-111">Pour plus d’informations sur la création de règles de normalisation des numéros de téléphone pour le contrôle d’appel distant, voir [Dial plans and Normalization Rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="39d10-111">For details about creating phone number normalization rules for remote call control, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<div>

## <a name="migrating-phone-number-normalization-rules"></a><span data-ttu-id="39d10-112">Migration des règles de normalisation des numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="39d10-112">Migrating Phone Number Normalization Rules</span></span>

<span data-ttu-id="39d10-113">Si vous migrez des utilisateurs pour lesquels le contrôle d’appel distant était activé, voir les rubriques suivantes dans la documentation de migration :</span><span class="sxs-lookup"><span data-stu-id="39d10-113">If you are migrating users previously enabled for remote call control, see the following topics in the Migration documentation:</span></span>

  - <span data-ttu-id="39d10-114">Pour Lync Server 2010, voir [Migrate Address Book](migrate-address-book.md) dans la documentation de migration.</span><span class="sxs-lookup"><span data-stu-id="39d10-114">For Lync Server 2010, see [Migrate Address Book](migrate-address-book.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="39d10-115">Pour Communications Server 2007 R2, consultez la rubrique [Migrate Address Book](migrate-address-book.md) dans la documentation de migration.</span><span class="sxs-lookup"><span data-stu-id="39d10-115">For Communications Server 2007 R2, see [Migrate Address Book](migrate-address-book.md) in the Migration documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

