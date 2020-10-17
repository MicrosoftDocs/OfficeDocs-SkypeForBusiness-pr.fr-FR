---
title: 'Lync Server 2013 : affecter une stratégie de messagerie vocale hébergée par utilisateur'
description: 'Lync Server 2013 : affectez une stratégie de messagerie vocale hébergée par utilisateur.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user hosted voice mail policy
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398919(v=OCS.15)
ms:contentKeyID: 48185456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 071d504c452b4d3adb1b636cb5c4ff8835200107
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559890"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="8cf73-103">Affectation d’une stratégie de messagerie vocale hébergée par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cf73-103">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>

 


<span data-ttu-id="8cf73-p101">Le déploiement d’une ou de plusieurs stratégies de messagerie vocale hébergée par utilisateur est facultatif. Si vous déployez des stratégies par utilisateur, vous devez les attribuer explicitement à des utilisateurs, des groupes ou des objets contact.</span><span class="sxs-lookup"><span data-stu-id="8cf73-p101">Deploying one or more per-user hosted voice mail policies is optional. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact objects.</span></span>

<span data-ttu-id="8cf73-106">Pour plus d’informations sur l’attribution ou la suppression de l’attribution de stratégies de messagerie vocale hébergée par utilisateur, voir la documentation de Lync Server Management Shell pour les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="8cf73-106">For details about assigning or removing the assignment of per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="8cf73-107">Grant-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="8cf73-107">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="8cf73-108">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="8cf73-108">Remove-CsHostedVoicemailPolicy</span></span>

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="8cf73-109">Pour attribuer une stratégie de messagerie vocale hébergée par utilisateur</span><span class="sxs-lookup"><span data-stu-id="8cf73-109">To assign a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="8cf73-110">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8cf73-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8cf73-p102">Exécutez la cmdlet Grant-CsHostedVoicemailPolicy pour attribuer la stratégie de messagerie vocale hébergée par utilisateur à des utilisateurs individuels, des groupes et des objets contact. Par exemple, exécutez :</span><span class="sxs-lookup"><span data-stu-id="8cf73-p102">Run the Grant-CsHostedVoicemailPolicy cmdlet to assign the per-user hosted voice mail policy to individual users, groups, and contact objects. For example, run:</span></span>
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    <span data-ttu-id="8cf73-113">Dans cet exemple, la stratégie de messagerie vocale hébergée ExRedmond est attribuée à l’utilisateur Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="8cf73-113">This example assigned the ExRedmond hosted voice mail policy to user Ken Myer.</span></span>
    
    <span data-ttu-id="8cf73-p103">**Identité** indique le compte d’utilisateur à modifier. Vous pouvez définir la valeur d’identité dans l’un des formats suivants :</span><span class="sxs-lookup"><span data-stu-id="8cf73-p103">**Identity** specifies the user account to be modified. The Identity value can be specified using any of the following formats:</span></span>
    
      - <span data-ttu-id="8cf73-116">l’adresse SIP de l’utilisateur ;</span><span class="sxs-lookup"><span data-stu-id="8cf73-116">The user's SIP address</span></span>
    
      - <span data-ttu-id="8cf73-117">le nom d’utilisateur principal Active Directory ;</span><span class="sxs-lookup"><span data-stu-id="8cf73-117">The user's Active Directory User-Principal-Name</span></span>
    
      - <span data-ttu-id="8cf73-118">Nom de connexion au domaine de l’utilisateur \\ (par exemple, Contoso \\ kenmyer)</span><span class="sxs-lookup"><span data-stu-id="8cf73-118">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
    
      - <span data-ttu-id="8cf73-119">le nom complet des services de domaine Active Directory de l’utilisateur (par exemple, Ken Myer).</span><span class="sxs-lookup"><span data-stu-id="8cf73-119">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="8cf73-120">Si vous utilisez le Display-Name en tant que valeur Identity, vous pouvez utiliser le \* caractère générique astérisque ().</span><span class="sxs-lookup"><span data-stu-id="8cf73-120">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="8cf73-121">Par exemple, l’identité « \* Smith » renvoie tous les utilisateurs dont l' Display-Name se termine par la valeur de chaîne « Smith ».</span><span class="sxs-lookup"><span data-stu-id="8cf73-121">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="8cf73-122">Le nom de compte SAM Active Directory de l’utilisateur ne peut pas être utilisé comme valeur d’identité, car il n’est pas forcément unique dans la forêt.</span><span class="sxs-lookup"><span data-stu-id="8cf73-122">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>


