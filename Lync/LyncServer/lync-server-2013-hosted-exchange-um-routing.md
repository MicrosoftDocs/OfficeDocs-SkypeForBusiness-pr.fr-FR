---
title: 'Lync Server 2013 : Routage de la messagerie unifiée Exchange hébergée'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange UM routing
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398512(v=OCS.15)
ms:contentKeyID: 48184422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90cc1112effd0eac0a25614ee50d7008ee1c5e37
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a><span data-ttu-id="104a1-102">Routage de la messagerie unifiée Exchange hébergée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="104a1-102">Hosted Exchange UM routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="104a1-103">_**Dernière modification de la rubrique:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="104a1-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="104a1-104">L’application de routage de messagerie unifiée Exchange s’exécute sur le serveur frontal pour acheminer les appels vers un déploiement local de messagerie unifiée (MU) sur site ou vers un service de messagerie UNIFIÉe Exchange hébergé.</span><span class="sxs-lookup"><span data-stu-id="104a1-104">The Exchange UM Routing application runs on the Front End Server to route calls, either to an on-premises Microsoft Exchange Server Unified Messaging (UM) deployment or to hosted Exchange UM service.</span></span>

<div>

## <a name="the-exum-routing-application"></a><span data-ttu-id="104a1-105">Application de routage ExUM</span><span class="sxs-lookup"><span data-stu-id="104a1-105">The ExUM Routing Application</span></span>

<span data-ttu-id="104a1-106">L’application de routage de messagerie unifiée Exchange Server 2013 utilise les informations des paramètres de compte d’utilisateur et les paramètres de stratégie de messagerie vocale hébergés pour déterminer le mode de routage des appels pour la boîte vocale hébergée, comme indiqué dans le schéma suivant.</span><span class="sxs-lookup"><span data-stu-id="104a1-106">The Lync Server 2013 Exchange UM Routing application uses information from user account settings and from hosted voice mail policy parameters to determine how to route calls for hosted voice messaging, as shown in the following diagram.</span></span>

<span data-ttu-id="104a1-107">**Exemple de routage de MU Exchange de déploiement mixte**</span><span class="sxs-lookup"><span data-stu-id="104a1-107">**Example of mixed deployment Exchange UM routing**</span></span>

<span data-ttu-id="104a1-108">![Déploiement de la messagerie unifiée Exchange Server en local] (images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "Déploiement de la messagerie unifiée Exchange Server en local")</span><span class="sxs-lookup"><span data-stu-id="104a1-108">![On-premises Lync Server Exchange UM deployment](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "On-premises Lync Server Exchange UM deployment")</span></span>

<span data-ttu-id="104a1-109">Le routage de MU Exchange peut être configuré pour diriger les appels vers les utilisateurs qui sont activés pour la messagerie unifiée Exchange locale, pour les utilisateurs qui sont activés pour la messagerie unifiée Exchange hébergée ou pour une combinaison des deux.</span><span class="sxs-lookup"><span data-stu-id="104a1-109">Exchange UM routing can be configured to route calls to users who are enabled for on-premises Exchange UM, to users who are enabled for hosted Exchange UM, or to a combination of the two.</span></span>

<span data-ttu-id="104a1-110">Par exemple, supposons que la boîte aux lettres de Roy et le service de messagerie unifiée Exchange résident dans un déploiement Exchange local.</span><span class="sxs-lookup"><span data-stu-id="104a1-110">For example, suppose that Roy’s mailbox and Exchange UM service are homed in an on-premises Exchange deployment.</span></span>

  - <span data-ttu-id="104a1-111">Les informations d’adresse proxy du compte utilisateur de Roy fournissent les informations utilisées par l’application de routage ExUM pour diriger ses appels vers un serveur Exchange UM local.</span><span class="sxs-lookup"><span data-stu-id="104a1-111">The proxy address information from Roy’s user account provides the information that the ExUM Routing application uses to route his calls to an on-premises Exchange UM server.</span></span>

<span data-ttu-id="104a1-112">Les services de boîte aux lettres et de messagerie unifiée d’Alice sont situés dans le centre de données du fournisseur de services Exchange hébergé.</span><span class="sxs-lookup"><span data-stu-id="104a1-112">Alice’s mailbox and Exchange UM service are located at a hosted Exchange service provider’s data center.</span></span> <span data-ttu-id="104a1-113">Le routage des appels de messagerie unifiée Exchange est configuré comme suit:</span><span class="sxs-lookup"><span data-stu-id="104a1-113">Routing for her Exchange UM calls is configured as follows:</span></span>

  - <span data-ttu-id="104a1-114">Les valeurs définies dans l’attribut msExchUCVoiceMailSettings du compte d’utilisateur d’Alice indiquent à l’application de routage ExUM de vérifier les détails de routage dans une stratégie de messagerie vocale hébergée.</span><span class="sxs-lookup"><span data-stu-id="104a1-114">The values set in the msExchUCVoiceMailSettings attribute of Alice’s user account tell the ExUM Routing application to check for routing details in a hosted voice mail policy.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="104a1-115">La valeur de l’attribut msExchUCVoiceMailSettings peut être définie par le fournisseur de services Exchange ou par l’administrateur 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="104a1-115">The value of the msExchUCVoiceMailSettings attribute can be set by either the Exchange service provider or the Lync Server 2013 administrator.</span></span> <span data-ttu-id="104a1-116">Dans l’exemple ci-dessus, la valeur (CsHostedVoiceMail = 1) a été définie par l’administrateur de Lync Server 2013 pour activer la messagerie vocale hébergée pour Alice.</span><span class="sxs-lookup"><span data-stu-id="104a1-116">In the example shown in the preceding diagram, the value (CsHostedVoiceMail=1) was set by the Lync Server 2013 administrator to enable hosted voice mail for Alice.</span></span> <span data-ttu-id="104a1-117">Pour plus d’informations sur cet attribut, voir <A href="lync-server-2013-hosted-exchange-user-management.md">gestion des utilisateurs Exchange hébergés dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="104a1-117">For details about this attribute, see <A href="lync-server-2013-hosted-exchange-user-management.md">Hosted Exchange user management in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="104a1-118">La stratégie de messagerie vocale hébergée qui est affectée au compte d’utilisateur d’Alice fournit des informations de routage:</span><span class="sxs-lookup"><span data-stu-id="104a1-118">The hosted voice mail policy that is assigned to Alice’s user account provides routing details:</span></span>
    
      - <span data-ttu-id="104a1-119">La destination est le fournisseur de service de messagerie unifiée Exchange hébergé (LS. ExUm. \<hostedExchangeServer\>. com dans cet exemple).</span><span class="sxs-lookup"><span data-stu-id="104a1-119">Destination is the hosted Exchange UM service provider (ls.ExUm.\<hostedExchangeServer\>.com in this example).</span></span>
    
      - <span data-ttu-id="104a1-120">Les organisations sont identifiées par les ID de locataire, qui sont les noms de domaine complets de routage pour les messages SIP pour les clients Exchange Server situés sur ls. ExUm. \<hostedExchangeServer\>. com (Corp.contoso.com et Corp.litwareinc.com dans cet exemple).</span><span class="sxs-lookup"><span data-stu-id="104a1-120">Organizations are identified by the tenant IDs, which are the routing FQDNs for SIP messages for Exchange Server tenants that are located on ls.ExUm.\<hostedExchangeServer\>.com (corp.contoso.com and corp.litwareinc.com in this example).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="104a1-121">Le nom de domaine complet pour Exchange Online est exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="104a1-121">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

        
        </div>
        
        <span data-ttu-id="104a1-122">Pour plus d’informations, reportez-vous [à stratégies de messagerie vocale hébergées dans Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).</span><span class="sxs-lookup"><span data-stu-id="104a1-122">For details, see [Hosted voice mail policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="104a1-123">Si l’attribut msExchUCVoiceMailSettings et les paramètres d’adresse proxy de messagerie unifiée sont tous deux présents dans un compte d’utilisateur, l’attribut msExchUCVoiceMailSettings est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="104a1-123">If both the msExchUCVoiceMailSettings attribute and the UM proxy address settings are present in a user account, the msExchUCVoiceMailSettings attribute takes precedence.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

