---
title: 'Lync Server 2013 : activation des utilisateurs pour la messagerie vocale hébergée'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for hosted voice mail
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413062(v=OCS.15)
ms:contentKeyID: 48185919
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c0975f6be3d78ec7634859b26e7ed35e7efee5a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501031"
---
# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a><span data-ttu-id="c9c68-102">Activer les utilisateurs pour la messagerie vocale hébergée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9c68-102">Enable users for hosted voice mail in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9c68-103">_**Dernière modification de la rubrique :** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="c9c68-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="c9c68-104">Suivez la procédure pour activer les utilisateurs Lync Server 2013 pour la messagerie vocale sur un service de messagerie unifiée Exchange hébergé.</span><span class="sxs-lookup"><span data-stu-id="c9c68-104">Follow the procedure to enable Lync Server 2013 users for voice mail on a hosted Exchange Unified Messaging (UM) service.</span></span>

<span data-ttu-id="c9c68-105">Pour plus d’informations, voir [Hosted Exchange User Management in Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="c9c68-105">For details, see [Hosted Exchange user management in Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="c9c68-106">Pour plus d’informations sur la cmdlet [Set-Csuser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) , voir la documentation de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c9c68-106">For details about the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c9c68-107">Avant de pouvoir activer un utilisateur Lync Server 2013 pour la messagerie vocale hébergée, une stratégie de messagerie vocale hébergée qui s’applique à son compte d’utilisateur doit être déployée.</span><span class="sxs-lookup"><span data-stu-id="c9c68-107">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to their user account must be deployed.</span></span> <span data-ttu-id="c9c68-108">Pour plus d’informations, reportez-vous à <A href="lync-server-2013-hosted-voice-mail-policies.md">stratégies de messagerie vocale hébergée dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c9c68-108">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a><span data-ttu-id="c9c68-109">Pour activer les utilisateurs pour la messagerie vocale hébergée</span><span class="sxs-lookup"><span data-stu-id="c9c68-109">To enable users for hosted voice mail</span></span>

1.  <span data-ttu-id="c9c68-110">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c9c68-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c9c68-p102">Exécutez la cmdlet Set-CsUser pour configurer le compte d’utilisateur pour la messagerie vocale hébergée. Par exemple, exécutez :</span><span class="sxs-lookup"><span data-stu-id="c9c68-p102">Run the Set-CsUser cmdlet to configure the user account for hosted voice mail. For example, run:</span></span>
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    <span data-ttu-id="c9c68-113">L’exemple qui précède définit les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="c9c68-113">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="c9c68-114">**HostedVoiceMail** permet d’acheminer les appels de la messagerie vocale d’un utilisateur vers la messagerie unifiée Exchange hébergée.</span><span class="sxs-lookup"><span data-stu-id="c9c68-114">**HostedVoiceMail** enables a user’s voice mail calls to be routed to hosted Exchange UM.</span></span> <span data-ttu-id="c9c68-115">Il signale également à Microsoft Lync 2013 l’indicateur d’appel de messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="c9c68-115">It also signals Microsoft Lync 2013 to light up the “call voice mail” indicator.</span></span>
    
      - <span data-ttu-id="c9c68-p104">**Identité** indique le compte d’utilisateur à modifier. Vous pouvez définir la valeur d’identité dans l’un des formats suivants :</span><span class="sxs-lookup"><span data-stu-id="c9c68-p104">**Identity** specifies the user account to be modified. The Identity value can be specified using any of the following formats:</span></span>
        
          - <span data-ttu-id="c9c68-118">l’adresse SIP de l’utilisateur ;</span><span class="sxs-lookup"><span data-stu-id="c9c68-118">The user's SIP address</span></span>
        
          - <span data-ttu-id="c9c68-119">le nom d’utilisateur principal Active Directory ;</span><span class="sxs-lookup"><span data-stu-id="c9c68-119">The user's Active Directory User-Principal-Name</span></span>
        
          - <span data-ttu-id="c9c68-120">Nom de connexion au domaine de l’utilisateur \\ (par exemple, Contoso \\ kenmyer)</span><span class="sxs-lookup"><span data-stu-id="c9c68-120">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
        
          - <span data-ttu-id="c9c68-121">le nom complet des services de domaine Active Directory de l’utilisateur (par exemple, Ken Myer).</span><span class="sxs-lookup"><span data-stu-id="c9c68-121">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="c9c68-122">Si vous utilisez le Display-Name en tant que valeur Identity, vous pouvez utiliser le \* caractère générique astérisque ().</span><span class="sxs-lookup"><span data-stu-id="c9c68-122">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="c9c68-123">Par exemple, l’identité « \* Smith » renvoie tous les utilisateurs dont l' Display-Name se termine par la valeur de chaîne « Smith ».</span><span class="sxs-lookup"><span data-stu-id="c9c68-123">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c9c68-124">Le nom de compte SAM Active Directory de l’utilisateur ne peut pas être utilisé comme valeur d’identité, car il n’est pas forcément unique dans la forêt.</span><span class="sxs-lookup"><span data-stu-id="c9c68-124">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

