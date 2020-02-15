---
title: 'Lync Server 2013 : routage de messagerie unifiée Exchange hébergée'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM routing
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398512(v=OCS.15)
ms:contentKeyID: 48184422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57efdcebe52f9b32f30c22ebcbf107d3cd9d8a7d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a><span data-ttu-id="0c500-102">Routage de messagerie unifiée Exchange hébergée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c500-102">Hosted Exchange UM routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c500-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="0c500-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="0c500-104">L’application de routage de messagerie unifiée Exchange s’exécute sur le serveur frontal pour acheminer les appels, soit vers un déploiement de messagerie unifiée Microsoft Exchange Server local, soit vers un service de messagerie UNIFIÉe Exchange hébergé.</span><span class="sxs-lookup"><span data-stu-id="0c500-104">The Exchange UM Routing application runs on the Front End Server to route calls, either to an on-premises Microsoft Exchange Server Unified Messaging (UM) deployment or to hosted Exchange UM service.</span></span>

<div>

## <a name="the-exum-routing-application"></a><span data-ttu-id="0c500-105">Application de routage ExUM</span><span class="sxs-lookup"><span data-stu-id="0c500-105">The ExUM Routing Application</span></span>

<span data-ttu-id="0c500-106">L’application de routage de messagerie unifiée Exchange Lync Server 2013 utilise les informations des paramètres de compte d’utilisateur et de stratégie de messagerie vocale hébergée pour déterminer comment acheminer les appels pour la messagerie vocale hébergée, comme illustré dans le diagramme suivant.</span><span class="sxs-lookup"><span data-stu-id="0c500-106">The Lync Server 2013 Exchange UM Routing application uses information from user account settings and from hosted voice mail policy parameters to determine how to route calls for hosted voice messaging, as shown in the following diagram.</span></span>

<span data-ttu-id="0c500-107">**Exemple de routage sur un déploiement de messagerie unifiée Exchange mixte**</span><span class="sxs-lookup"><span data-stu-id="0c500-107">**Example of mixed deployment Exchange UM routing**</span></span>

<span data-ttu-id="0c500-108">![Déploiement de la messagerie unifiée Lync Server Exchange sur site](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "Déploiement de la messagerie unifiée Lync Server Exchange sur site")</span><span class="sxs-lookup"><span data-stu-id="0c500-108">![On-premises Lync Server Exchange UM deployment](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "On-premises Lync Server Exchange UM deployment")</span></span>

<span data-ttu-id="0c500-109">Le routage de messagerie unifiée Exchange peut être configuré pour acheminer les appels aux utilisateurs qui sont activés pour la messagerie unifiée Exchange locale, aux utilisateurs qui sont activés pour la messagerie unifiée Exchange hébergée ou à une combinaison des deux.</span><span class="sxs-lookup"><span data-stu-id="0c500-109">Exchange UM routing can be configured to route calls to users who are enabled for on-premises Exchange UM, to users who are enabled for hosted Exchange UM, or to a combination of the two.</span></span>

<span data-ttu-id="0c500-110">Par exemple, supposons que la boîte aux lettres de Roy et le service de messagerie unifiée Exchange sont hébergés dans un déploiement Exchange local.</span><span class="sxs-lookup"><span data-stu-id="0c500-110">For example, suppose that Roy’s mailbox and Exchange UM service are homed in an on-premises Exchange deployment.</span></span>

  - <span data-ttu-id="0c500-111">Les informations d’adresse proxy du compte d’utilisateur de Roy fournissent les informations utilisées par l’application de routage ExUM pour acheminer ses appels vers un serveur de messagerie unifiée Exchange local.</span><span class="sxs-lookup"><span data-stu-id="0c500-111">The proxy address information from Roy’s user account provides the information that the ExUM Routing application uses to route his calls to an on-premises Exchange UM server.</span></span>

<span data-ttu-id="0c500-112">La boîte aux lettres d’Alice et le service de messagerie unifiée Exchange se trouvent dans le centre de données d’un fournisseur de services Exchange hébergé.</span><span class="sxs-lookup"><span data-stu-id="0c500-112">Alice’s mailbox and Exchange UM service are located at a hosted Exchange service provider’s data center.</span></span> <span data-ttu-id="0c500-113">Le routage des appels de messagerie unifiée Exchange est configuré comme suit :</span><span class="sxs-lookup"><span data-stu-id="0c500-113">Routing for her Exchange UM calls is configured as follows:</span></span>

  - <span data-ttu-id="0c500-114">Les valeurs définies dans l’attribut msExchUCVoiceMailSettings du compte utilisateur d’Alice indiquent à l’application de routage ExUM de contrôler les informations de routage dans une stratégie de messagerie vocale hébergée.</span><span class="sxs-lookup"><span data-stu-id="0c500-114">The values set in the msExchUCVoiceMailSettings attribute of Alice’s user account tell the ExUM Routing application to check for routing details in a hosted voice mail policy.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0c500-115">La valeur de l’attribut msExchUCVoiceMailSettings peut être définie par le fournisseur de services Exchange ou par l’administrateur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0c500-115">The value of the msExchUCVoiceMailSettings attribute can be set by either the Exchange service provider or the Lync Server 2013 administrator.</span></span> <span data-ttu-id="0c500-116">Dans l’exemple illustré dans le diagramme précédent, la valeur (CsHostedVoiceMail = 1) a été définie par l’administrateur Lync Server 2013 pour activer la messagerie vocale hébergée pour Alice.</span><span class="sxs-lookup"><span data-stu-id="0c500-116">In the example shown in the preceding diagram, the value (CsHostedVoiceMail=1) was set by the Lync Server 2013 administrator to enable hosted voice mail for Alice.</span></span> <span data-ttu-id="0c500-117">Pour plus d’informations sur cet attribut, consultez la rubrique <A href="lync-server-2013-hosted-exchange-user-management.md">gestion des utilisateurs Exchange hébergés dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="0c500-117">For details about this attribute, see <A href="lync-server-2013-hosted-exchange-user-management.md">Hosted Exchange user management in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="0c500-118">La stratégie de messagerie vocale hébergée attribuée au compte utilisateur d’Alice fournit les détails de routage suivants :</span><span class="sxs-lookup"><span data-stu-id="0c500-118">The hosted voice mail policy that is assigned to Alice’s user account provides routing details:</span></span>
    
      - <span data-ttu-id="0c500-119">La destination est le fournisseur de services de messagerie unifiée Exchange hébergé (LS. ExUm. \<hostedExchangeServer\>. com dans cet exemple).</span><span class="sxs-lookup"><span data-stu-id="0c500-119">Destination is the hosted Exchange UM service provider (ls.ExUm.\<hostedExchangeServer\>.com in this example).</span></span>
    
      - <span data-ttu-id="0c500-120">Les organisations sont identifiées par les ID de client, qui sont les noms de domaine complets de routage pour les messages SIP pour les clients Exchange Server qui se trouvent sur ls. ExUm. \<hostedExchangeServer\>. com (Corp.contoso.com et Corp.litwareinc.com dans cet exemple).</span><span class="sxs-lookup"><span data-stu-id="0c500-120">Organizations are identified by the tenant IDs, which are the routing FQDNs for SIP messages for Exchange Server tenants that are located on ls.ExUm.\<hostedExchangeServer\>.com (corp.contoso.com and corp.litwareinc.com in this example).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="0c500-121">Le nom de domaine complet pour Exchange Online est exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="0c500-121">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

        
        </div>
        
        <span data-ttu-id="0c500-122">Pour plus d’informations, reportez-vous à [stratégies de messagerie vocale hébergée dans Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).</span><span class="sxs-lookup"><span data-stu-id="0c500-122">For details, see [Hosted voice mail policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0c500-123">Si les paramètres d’attribut msExchUCVoiceMailSettings et d’adresse proxy de messagerie unifiée sont tous deux présents dans un compte d’utilisateur, l’attribut msExchUCVoiceMailSettings est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="0c500-123">If both the msExchUCVoiceMailSettings attribute and the UM proxy address settings are present in a user account, the msExchUCVoiceMailSettings attribute takes precedence.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

