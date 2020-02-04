---
title: 'Lync Server 2013 : création d’une stratégie de messagerie vocale hébergée par utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a per-user hosted voice mail policy
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425867(v=OCS.15)
ms:contentKeyID: 48183902
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 535515fd11c0cb736b5b6fb4b70d041ea3af8a3c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="2e9f6-102">Créer une stratégie de messagerie vocale hébergée par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e9f6-102">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e9f6-103">_**Dernière modification de la rubrique :** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="2e9f6-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="2e9f6-104">Une stratégie *par utilisateur* peut affecter uniquement des utilisateurs, des groupes et des objets de contact individuels.</span><span class="sxs-lookup"><span data-stu-id="2e9f6-104">A *per-user* policy can only impact individual users, groups, and contact objects.</span></span> <span data-ttu-id="2e9f6-105">Pour déployer une stratégie par utilisateur, vous devez affecter explicitement la stratégie à un ou plusieurs utilisateurs, groupes ou objets de contact.</span><span class="sxs-lookup"><span data-stu-id="2e9f6-105">To deploy a per-user policy, you must explicitly assign the policy to one or more users, groups, or contact objects.</span></span> <span data-ttu-id="2e9f6-106">Pour plus d’informations, reportez-vous à [la section affectation d’une stratégie de messagerie vocale hébergée par utilisateur dans Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span><span class="sxs-lookup"><span data-stu-id="2e9f6-106">For details, see [Assign a per-user hosted voice mail policy in Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span></span>

<span data-ttu-id="2e9f6-107">Pour plus d’informations sur l’utilisation des stratégies de messagerie vocale hébergées par utilisateur, voir la documentation Lync Server Management Shell pour les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="2e9f6-107">For details about working with per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="2e9f6-108">Nouveau-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="2e9f6-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="2e9f6-109">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="2e9f6-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="2e9f6-110">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="2e9f6-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="2e9f6-111">Pour créer une stratégie de messagerie vocale hébergée par utilisateur</span><span class="sxs-lookup"><span data-stu-id="2e9f6-111">To create a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="2e9f6-112">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2e9f6-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2e9f6-113">Exécutez l’applet de nouvelle applet de CsHostedVoicemailPolicy pour créer la stratégie.</span><span class="sxs-lookup"><span data-stu-id="2e9f6-113">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy.</span></span> <span data-ttu-id="2e9f6-114">Par exemple, exécutez :</span><span class="sxs-lookup"><span data-stu-id="2e9f6-114">For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="2e9f6-115">L’exemple précédent crée une stratégie de messagerie vocale hébergée avec une étendue par utilisateur et définit les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="2e9f6-115">The previous example creates a hosted voice mail policy with per-user scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="2e9f6-116">**Identity** spécifie un identificateur unique pour la stratégie, qui inclut l’étendue.</span><span class="sxs-lookup"><span data-stu-id="2e9f6-116">**Identity** specifies a unique identifier for the policy, which includes the scope.</span></span> <span data-ttu-id="2e9f6-117">Dans le cas d’une stratégie avec une étendue par utilisateur, la valeur de ce paramètre est spécifiée sous la forme d’une chaîne simple, par exemple, exredmond.</span><span class="sxs-lookup"><span data-stu-id="2e9f6-117">For a policy with per-user scope, this parameter value is specified as a simple string, for example, ExRedmond.</span></span>
    
      - <span data-ttu-id="2e9f6-118">**Destination** spécifie le nom de domaine complet (FQDN) du service Exchange um hébergé.</span><span class="sxs-lookup"><span data-stu-id="2e9f6-118">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="2e9f6-119">Ce paramètre est facultatif, mais si vous tentez d’activer un utilisateur pour la messagerie vocale hébergée et que la stratégie attribuée de l’utilisateur n’a pas de valeur de destination, l’activation échoue.</span><span class="sxs-lookup"><span data-stu-id="2e9f6-119">This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="2e9f6-120">**Description** fournit des informations descriptives supplémentaires sur la stratégie.</span><span class="sxs-lookup"><span data-stu-id="2e9f6-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="2e9f6-121">**Organization** spécifie une liste séparée par des virgules des clients Exchange qui sont des utilisateurs de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2e9f6-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="2e9f6-122">Chaque client doit être spécifié en tant que nom de domaine complet (FQDN) du client sur le service de messagerie unifiée Exchange hébergé.</span><span class="sxs-lookup"><span data-stu-id="2e9f6-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2e9f6-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2e9f6-123">See Also</span></span>


[<span data-ttu-id="2e9f6-124">Affecter une stratégie de messagerie vocale hébergée par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e9f6-124">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

