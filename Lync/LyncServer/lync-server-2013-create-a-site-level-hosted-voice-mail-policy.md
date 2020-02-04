---
title: 'Lync Server 2013 : création d’une stratégie de messagerie vocale hébergée au niveau du site'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site-level hosted voice mail policy
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398216(v=OCS.15)
ms:contentKeyID: 48183481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6aeae2e533bd62cf1f3e24e7ceff69b870ebc7b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="04c8a-102">Créer une stratégie de messagerie vocale hébergée au niveau du site dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04c8a-102">Create a site-level hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04c8a-103">_**Dernière modification de la rubrique :** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="04c8a-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="04c8a-104">Une stratégie de *site* peut influer sur l’ensemble des utilisateurs hébergés sur le site pour lesquels la stratégie est définie.</span><span class="sxs-lookup"><span data-stu-id="04c8a-104">A *site* policy can impact all users that are homed on the site for which the policy is defined.</span></span> <span data-ttu-id="04c8a-105">Si un utilisateur est configuré pour l’accès à la messagerie unifiée Exchange hébergé sans avoir reçu une stratégie par utilisateur, la stratégie de site s’applique.</span><span class="sxs-lookup"><span data-stu-id="04c8a-105">If a user is configured for hosted Exchange UM access and has not been assigned a Per-user policy, the site policy applies.</span></span> <span data-ttu-id="04c8a-106">Si vous n’avez pas déployé de stratégie de site, la politique globale s’applique.</span><span class="sxs-lookup"><span data-stu-id="04c8a-106">If you have not deployed a site policy, the global policy applies.</span></span>

<span data-ttu-id="04c8a-107">Pour plus d’informations sur la configuration des stratégies de site, voir la documentation Lync Server Management Shell pour les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="04c8a-107">For details about configuring site policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="04c8a-108">Nouveau-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="04c8a-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="04c8a-109">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="04c8a-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="04c8a-110">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="04c8a-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a><span data-ttu-id="04c8a-111">Pour créer une stratégie de messagerie vocale hébergée sur un site</span><span class="sxs-lookup"><span data-stu-id="04c8a-111">To create a site hosted voice mail policy</span></span>

1.  <span data-ttu-id="04c8a-112">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="04c8a-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="04c8a-113">Exécutez l’applet de nouvelle applet de CsHostedVoicemailPolicy pour créer la stratégie.</span><span class="sxs-lookup"><span data-stu-id="04c8a-113">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy.</span></span> <span data-ttu-id="04c8a-114">Par exemple, exécutez :</span><span class="sxs-lookup"><span data-stu-id="04c8a-114">For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="04c8a-115">Cet exemple crée une stratégie de messagerie vocale hébergée avec l’étendue du site et définit les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="04c8a-115">This example creates a hosted voice mail policy with site scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="04c8a-116">**Identity** spécifie un identificateur unique pour la stratégie, qui inclut l’étendue.</span><span class="sxs-lookup"><span data-stu-id="04c8a-116">**Identity** specifies a unique identifier for the policy, which includes the scope.</span></span> <span data-ttu-id="04c8a-117">Dans le cas d’une stratégie avec l’étendue du site, la valeur du paramètre Identity doit être spécifiée dans le `site:` \* \<nom\>\* du format, par exemple `site:Redmond`.</span><span class="sxs-lookup"><span data-stu-id="04c8a-117">For a policy with site scope, the Identity parameter value must be specified in the format `site:`*\<name\>*, for example, `site:Redmond`.</span></span>
    
      - <span data-ttu-id="04c8a-118">**Destination** spécifie le nom de domaine complet (FQDN) du service Exchange um hébergé.</span><span class="sxs-lookup"><span data-stu-id="04c8a-118">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="04c8a-119">Ce paramètre est facultatif, mais si vous tentez d’activer un utilisateur pour la messagerie vocale hébergée et que la stratégie attribuée de l’utilisateur n’a pas de valeur de destination, l’activation échoue.</span><span class="sxs-lookup"><span data-stu-id="04c8a-119">This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="04c8a-120">**Description** fournit des informations descriptives supplémentaires sur la stratégie.</span><span class="sxs-lookup"><span data-stu-id="04c8a-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="04c8a-121">**Organization** spécifie une liste séparée par des virgules des clients Exchange qui sont des utilisateurs de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="04c8a-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="04c8a-122">Chaque client doit être spécifié en tant que nom de domaine complet (FQDN) du client sur le service de messagerie unifiée Exchange hébergé.</span><span class="sxs-lookup"><span data-stu-id="04c8a-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

