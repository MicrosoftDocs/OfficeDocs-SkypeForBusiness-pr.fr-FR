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
ms.openlocfilehash: 16173c979fac100297e17cb950f08086b33cf6e0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195947"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="081a8-102">Créer une stratégie de messagerie vocale hébergée par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="081a8-102">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="081a8-103">_**Dernière modification de la rubrique :** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="081a8-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="081a8-104">Une stratégie *par utilisateur* ne peut avoir d’incidence que sur des utilisateurs, groupes et objets Contact individuels.</span><span class="sxs-lookup"><span data-stu-id="081a8-104">A *per-user* policy can only impact individual users, groups, and contact objects.</span></span> <span data-ttu-id="081a8-105">Pour déployer une stratégie par utilisateur, vous devez l’attribuer explicitement à un ou plusieurs utilisateurs, groupes ou objets Contact.</span><span class="sxs-lookup"><span data-stu-id="081a8-105">To deploy a per-user policy, you must explicitly assign the policy to one or more users, groups, or contact objects.</span></span> <span data-ttu-id="081a8-106">Pour plus d’informations, reportez-vous à [la rubrique assigner une stratégie de messagerie vocale hébergée par utilisateur dans Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span><span class="sxs-lookup"><span data-stu-id="081a8-106">For details, see [Assign a per-user hosted voice mail policy in Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span></span>

<span data-ttu-id="081a8-107">Pour plus d’informations sur l’utilisation des stratégies de messagerie vocale hébergée par utilisateur, voir la documentation de Lync Server Management Shell pour les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="081a8-107">For details about working with per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="081a8-108">New-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="081a8-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="081a8-109">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="081a8-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="081a8-110">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="081a8-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="081a8-111">Pour créer une stratégie de messagerie vocale hébergée par utilisateur</span><span class="sxs-lookup"><span data-stu-id="081a8-111">To create a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="081a8-112">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="081a8-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="081a8-p102">Exécutez l’applet de commande New-CsHostedVoicemailPolicy pour créer la stratégie. Par exemple, exécutez :</span><span class="sxs-lookup"><span data-stu-id="081a8-p102">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy. For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="081a8-115">Dans l’exemple précédent, une stratégie de messagerie vocale hébergée est créée avec une étendue site et les paramètres suivants sont définis :</span><span class="sxs-lookup"><span data-stu-id="081a8-115">The previous example creates a hosted voice mail policy with per-user scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="081a8-p103">**Identity** spécifie un identificateur unique pour la stratégie qui englobe l’étendue. Pour une stratégie définie avec une étendue utilisateur, cette valeur de paramètre est définie en tant que chaîne simple, par exemple, ExRedmond.</span><span class="sxs-lookup"><span data-stu-id="081a8-p103">**Identity** specifies a unique identifier for the policy, which includes the scope. For a policy with per-user scope, this parameter value is specified as a simple string, for example, ExRedmond.</span></span>
    
      - <span data-ttu-id="081a8-p104">**Destination** spécifie le nom de domaine complet du service de messagerie unifiée Exchange hébergé. Ce paramètre est facultatif, mais si vous tentez d’activer un utilisateur pour la messagerie vocale hébergée alors que la stratégie affectée à l’utilisateur n’a pas de valeur Destination, l’activation échoue.</span><span class="sxs-lookup"><span data-stu-id="081a8-p104">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="081a8-120">**Description** fournit des informations facultatives décrivant la stratégie.</span><span class="sxs-lookup"><span data-stu-id="081a8-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="081a8-121">**Organisation** spécifie une liste séparée par des virgules des clients Exchange hébergeant des utilisateurs de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="081a8-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="081a8-122">Chaque locataire doit être spécifié avec son nom de domaine complet (FQDN) dans le service de messagerie unifiée Exchange hébergé.</span><span class="sxs-lookup"><span data-stu-id="081a8-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="081a8-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="081a8-123">See Also</span></span>


[<span data-ttu-id="081a8-124">Affectation d’une stratégie de messagerie vocale hébergée par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="081a8-124">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

