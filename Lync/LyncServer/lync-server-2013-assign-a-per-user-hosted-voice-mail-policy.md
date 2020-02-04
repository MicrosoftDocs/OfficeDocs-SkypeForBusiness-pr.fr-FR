---
title: 'Lync Server 2013 : affectation d’une stratégie de messagerie vocale hébergée par utilisateur'
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
ms.openlocfilehash: 95413733a9b23ce1f749ebb16521a3349b00165d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722954"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="6b0f7-102">Affecter une stratégie de messagerie vocale hébergée par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b0f7-102">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>

 


<span data-ttu-id="6b0f7-103">Le déploiement d’une ou plusieurs stratégies de messagerie vocale hébergées par utilisateur est facultatif.</span><span class="sxs-lookup"><span data-stu-id="6b0f7-103">Deploying one or more per-user hosted voice mail policies is optional.</span></span> <span data-ttu-id="6b0f7-104">Si vous déployez des stratégies par utilisateur, vous devez les affecter explicitement aux utilisateurs, groupes ou objets de contact.</span><span class="sxs-lookup"><span data-stu-id="6b0f7-104">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact objects.</span></span>

<span data-ttu-id="6b0f7-105">Pour plus d’informations sur l’attribution ou la suppression de l’attribution de stratégies de messagerie vocale hébergées par utilisateur, voir la documentation Lync Server Management Shell pour les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="6b0f7-105">For details about assigning or removing the assignment of per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="6b0f7-106">Grant-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="6b0f7-106">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="6b0f7-107">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="6b0f7-107">Remove-CsHostedVoicemailPolicy</span></span>

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="6b0f7-108">Pour attribuer une stratégie de messagerie vocale hébergée par utilisateur</span><span class="sxs-lookup"><span data-stu-id="6b0f7-108">To assign a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="6b0f7-109">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="6b0f7-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="6b0f7-110">Exécutez l’applet de passe Grant-CsHostedVoicemailPolicy pour affecter la stratégie de messagerie vocale hébergée par utilisateur à des utilisateurs, des groupes et des objets de contact individuels.</span><span class="sxs-lookup"><span data-stu-id="6b0f7-110">Run the Grant-CsHostedVoicemailPolicy cmdlet to assign the per-user hosted voice mail policy to individual users, groups, and contact objects.</span></span> <span data-ttu-id="6b0f7-111">Par exemple, exécutez :</span><span class="sxs-lookup"><span data-stu-id="6b0f7-111">For example, run:</span></span>
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    <span data-ttu-id="6b0f7-112">Dans cet exemple, la stratégie de messagerie vocale hébergée exredmond est affectée à l’utilisateur Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="6b0f7-112">This example assigned the ExRedmond hosted voice mail policy to user Ken Myer.</span></span>
    
    <span data-ttu-id="6b0f7-113">**Identité** indique le compte d’utilisateur à modifier.</span><span class="sxs-lookup"><span data-stu-id="6b0f7-113">**Identity** specifies the user account to be modified.</span></span> <span data-ttu-id="6b0f7-114">La valeur IDENTITY peut être spécifiée en utilisant l’un des formats suivants :</span><span class="sxs-lookup"><span data-stu-id="6b0f7-114">The Identity value can be specified using any of the following formats:</span></span>
    
      - <span data-ttu-id="6b0f7-115">Adresse SIP de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="6b0f7-115">The user's SIP address</span></span>
    
      - <span data-ttu-id="6b0f7-116">Nom d’utilisateur principal d’Active Directory de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="6b0f7-116">The user's Active Directory User-Principal-Name</span></span>
    
      - <span data-ttu-id="6b0f7-117">Le nom de connexion\\au domaine de l’utilisateur (par\\exemple, contoso kenmyer);</span><span class="sxs-lookup"><span data-stu-id="6b0f7-117">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
    
      - <span data-ttu-id="6b0f7-118">Nom d’affichage des services de domaine Active Directory de l’utilisateur (par exemple, Ken Myer).</span><span class="sxs-lookup"><span data-stu-id="6b0f7-118">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="6b0f7-119">Si vous utilisez le nom d’affichage comme valeur d’identité, vous pouvez utiliser le caractère\*générique astérisque ().</span><span class="sxs-lookup"><span data-stu-id="6b0f7-119">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="6b0f7-120">Par exemple, l’identité «\* Smith » renvoie tous les utilisateurs qui ont un nom d’affichage qui se termine par la valeur de chaîne « Smith ».</span><span class="sxs-lookup"><span data-stu-id="6b0f7-120">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="6b0f7-121">Le nom de compte SAM-nom Active Directory de l’utilisateur ne peut pas être utilisé en tant que valeur d’identité, car le nom de compte SAM n’est pas nécessairement unique dans la forêt.</span><span class="sxs-lookup"><span data-stu-id="6b0f7-121">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>


