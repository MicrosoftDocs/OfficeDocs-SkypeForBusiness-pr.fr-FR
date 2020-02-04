---
title: 'Lync Server 2013 : Contrôle d’appel distant et normalisation des numéros de téléphone'
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
ms.openlocfilehash: 6eff9fb48e9730549d67638c69d8655d8f04d710
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a><span data-ttu-id="9b6dd-102">Contrôle d’appel distant et normalisation des numéros de téléphone dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b6dd-102">Remote call control and phone number normalization in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b6dd-103">_**Dernière modification de la rubrique :** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="9b6dd-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="9b6dd-104">Les clients Lync téléchargent les règles de normalisation des numéros de téléphone dans le cadre du téléchargement de fichiers du service de carnet d’adresses (ABS).</span><span class="sxs-lookup"><span data-stu-id="9b6dd-104">Lync clients download phone number normalization rules as part of the Address Book Service (ABS) file download.</span></span> <span data-ttu-id="9b6dd-105">Dans les scénarios de contrôle d’appel distant, les règles de normalisation des numéros de téléphone du service de carnet d’adresses sont appliquées aux appels de contrôles d’appel distants entrants et sortants.</span><span class="sxs-lookup"><span data-stu-id="9b6dd-105">In remote call control scenarios, Address Book Service phone number normalization rules are applied to both incoming and outgoing remote call control calls.</span></span> <span data-ttu-id="9b6dd-106">Pour les appels entrants vers un utilisateur prenant en charge le contrôle d’appel distant, le numéro de téléphone de l’appelant est d’abord normalisé au format E. 164 par la passerelle SIP/CSTA ou le protocole PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="9b6dd-106">For incoming calls to a remote call control-enabled user, the phone number of the caller is first normalized to E.164 format by either the SIP/CSTA gateway or private branch exchange (PBX).</span></span> <span data-ttu-id="9b6dd-107">Lorsque Lync Server 2013 reçoit l’appel de la passerelle, il effectue la recherche de numéro inverse (RNL) sur le numéro de téléphone de l’appelant par rapport au numéro normalisé de la liste de contacts Microsoft Office Outlook du destinataire ou de la liste d’adresses globale qui est stockée dans Service de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="9b6dd-107">When Lync Server 2013 receives the call from the gateway, it performs reverse number lookup (RNL) on the phone number of the caller against the normalized number in the callee’s Microsoft Office Outlook Contacts list or the global address list (GAL) that is stored in the Address Book Service.</span></span> <span data-ttu-id="9b6dd-108">Si la recherche par numéro inverse trouve une correspondance, l’appelant est identifié par son nom dans la notification de l’appel entrant.</span><span class="sxs-lookup"><span data-stu-id="9b6dd-108">If reverse number lookup successfully finds a match, the caller is identified by name in the incoming call notification.</span></span>

<span data-ttu-id="9b6dd-109">Pour les appels sortants de contrôle d’appel distant, Lync applique les règles de normalisation du numéro de téléphone du service de carnet d’adresses au numéro composé avant de router l’appel vers la passerelle SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="9b6dd-109">For outgoing remote call control calls, Lync applies the Address Book Service phone number normalization rules to the dialed number before routing the call to the SIP/CSTA gateway.</span></span>

<span data-ttu-id="9b6dd-110">Pour plus d’informations sur la création de règles de normalisation des numéros de téléphone pour le contrôle d’appel distant, voir [plans de numérotation et règles de normalisation dans Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="9b6dd-110">For details about creating phone number normalization rules for remote call control, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<div>

## <a name="migrating-phone-number-normalization-rules"></a><span data-ttu-id="9b6dd-111">Migration des règles de normalisation des numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="9b6dd-111">Migrating Phone Number Normalization Rules</span></span>

<span data-ttu-id="9b6dd-112">Si vous migrez des utilisateurs déjà activés pour le contrôle d’appel distant, reportez-vous aux rubriques suivantes dans la documentation relative à la migration :</span><span class="sxs-lookup"><span data-stu-id="9b6dd-112">If you are migrating users previously enabled for remote call control, see the following topics in the Migration documentation:</span></span>

  - <span data-ttu-id="9b6dd-113">Pour Lync Server 2010, voir [migrer le carnet d’adresses](migrate-address-book.md) dans la documentation relative à la migration.</span><span class="sxs-lookup"><span data-stu-id="9b6dd-113">For Lync Server 2010, see [Migrate Address Book](migrate-address-book.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="9b6dd-114">Pour Communications Server 2007 R2, voir [migrer le carnet d’adresses](migrate-address-book_1.md) dans la documentation de migration.</span><span class="sxs-lookup"><span data-stu-id="9b6dd-114">For Communications Server 2007 R2, see [Migrate Address Book](migrate-address-book_1.md) in the Migration documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

