---
title: 'Lync Server 2013 : gestion des utilisateurs Exchange hébergés'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange user management
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399037(v=OCS.15)
ms:contentKeyID: 48185887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1cceaeaa869d1e058251a62d237c563143a4ae4c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-user-management-in-lync-server-2013"></a><span data-ttu-id="17401-102">Gestion des utilisateurs Exchange hébergés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17401-102">Hosted Exchange user management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17401-103">_**Dernière modification de la rubrique :** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="17401-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="17401-104">Pour fournir des services de messagerie vocale pour les utilisateurs de Lync Server 2013 dont les boîtes aux lettres sont situées sur un service Exchange hébergé, vous devez activer leurs comptes d’utilisateur pour la messagerie vocale hébergée.</span><span class="sxs-lookup"><span data-stu-id="17401-104">To provide voice mail services for Lync Server 2013 users whose mailboxes are located on a hosted Exchange service, you must enable their user accounts for hosted voice mail.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="17401-105">Avant de pouvoir activer un utilisateur Lync Server 2013 pour la messagerie vocale hébergée, une stratégie de messagerie vocale hébergée qui s’applique au compte d’utilisateur correspondant doit être déployée.</span><span class="sxs-lookup"><span data-stu-id="17401-105">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to the corresponding user account must be deployed.</span></span> <span data-ttu-id="17401-106">Cette stratégie peut être déployée au niveau global, du site ou de chaque utilisateur à condition qu’elle s’applique à l’utilisateur que vous souhaitez activer.</span><span class="sxs-lookup"><span data-stu-id="17401-106">The policy can be global, site, or per-user in scope, as long as it applies to the user whom you want to enable.</span></span> <span data-ttu-id="17401-107">Pour plus d’informations, reportez-vous à <A href="lync-server-2013-hosted-voice-mail-policies.md">stratégies de messagerie vocale hébergée dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="17401-107">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a><span data-ttu-id="17401-108">L’attribut msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="17401-108">The msExchUCVoiceMailSettings Attribute</span></span>

<span data-ttu-id="17401-109">Lync Server 2013 introduit un nouvel attribut utilisateur nommé **msExchUCVoiceMailSettings**, qui est créé dans le cadre de la préparation du schéma Active Directory de lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17401-109">Lync Server 2013 introduces a new user attribute named **msExchUCVoiceMailSettings**, which is created as part of the Lync Server 2013 Active Directory schema preparation.</span></span> <span data-ttu-id="17401-110">Cet attribut à valeurs multiples contient les paramètres de messagerie vocale qui sont partagés par Lync Server 2013 et le service Exchange hébergé.</span><span class="sxs-lookup"><span data-stu-id="17401-110">This multivalued attribute holds voice mail settings that are shared by Lync Server 2013 and the hosted Exchange service.</span></span>

<span data-ttu-id="17401-111">Le service Exchange hébergé peut dans certains cas définir la valeur de l’attribut msExchUCVoiceMailSettings lors du processus d’activation de la messagerie unifiée (UM) Exchange ou de transfert des boîtes aux lettres vers un serveur Exchange hébergé.</span><span class="sxs-lookup"><span data-stu-id="17401-111">The hosted Exchange service may in some cases set the value of the msExchUCVoiceMailSettings attribute in the process of enabling Exchange UM, or during the process of transferring mailboxes to a hosted Exchange Server.</span></span> <span data-ttu-id="17401-112">Si cet attribut n’est pas défini par Exchange, l’administrateur Lync Server 2013 doit le définir en exécutant la cmdlet Set-CsUser, comme décrit plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="17401-112">If this attribute is not set by Exchange, the Lync Server 2013 administrator must set it by running the Set-CsUser cmdlet, as described earlier in this topic.</span></span>

<span data-ttu-id="17401-113">Les paires clé/valeur de l’attribut et leurs auteurs sont indiqués dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="17401-113">The attribute’s key/value pairs and their authors are shown in the following table.</span></span>

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a><span data-ttu-id="17401-114">Les paires clé/valeur de l’attribut msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="17401-114">The msExchUCVoiceMailSettings Attribute Key/Value Pairs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="17401-115">Valeur</span><span class="sxs-lookup"><span data-stu-id="17401-115">Value</span></span></th>
<th><span data-ttu-id="17401-116">Auteur</span><span class="sxs-lookup"><span data-stu-id="17401-116">Author</span></span></th>
<th><span data-ttu-id="17401-117">Signification</span><span class="sxs-lookup"><span data-stu-id="17401-117">Meaning</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17401-118">ExchangeHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="17401-118">ExchangeHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="17401-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="17401-119">Exchange</span></span></p></td>
<td><p><span data-ttu-id="17401-120">L’utilisateur a été activé pour accéder à la messagerie unifiée hébergée par Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="17401-120">User has been enabled for hosted UM access by Exchange Server.</span></span> <span data-ttu-id="17401-121">L’application de routage de messagerie unifiée Exchange vérifie la stratégie de messagerie vocale hébergée de l’utilisateur pour les détails de routage.</span><span class="sxs-lookup"><span data-stu-id="17401-121">The Exchange UM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17401-122">ExchangeHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="17401-122">ExchangeHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="17401-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="17401-123">Exchange</span></span></p></td>
<td><p><span data-ttu-id="17401-124">L’utilisateur a été désactivé pour accéder à la messagerie unifiée hébergée par Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="17401-124">User has been disabled for hosted UM access by Exchange Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17401-125">CsHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="17401-125">CsHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="17401-126">Lync Server</span><span class="sxs-lookup"><span data-stu-id="17401-126">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="17401-127">L’accès à la messagerie unifiée hébergée par Lync Server 2013 a été activé pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="17401-127">User has been enabled for hosted UM access by Lync Server 2013.</span></span> <span data-ttu-id="17401-128">L’application de routage ExUM de Lync Server 2013 vérifie la stratégie de messagerie vocale hébergée de l’utilisateur pour les détails de routage.</span><span class="sxs-lookup"><span data-stu-id="17401-128">The Lync Server 2013 ExUM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17401-129">CsHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="17401-129">CsHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="17401-130">Lync Server</span><span class="sxs-lookup"><span data-stu-id="17401-130">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="17401-131">L’utilisateur a été désactivé pour l’accès à la messagerie unifiée hébergée par Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17401-131">User has been disabled for hosted UM access by Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="17401-132">Si l’attribut possède déjà des valeurs autres que l’une des paires clé/valeur de Lync Server 2013 (CSHostedVoiceMail = 0 ou CSHostedVoiceMail = 1), un avertissement indique que l’attribut peut être géré par une autre application.</span><span class="sxs-lookup"><span data-stu-id="17401-132">If the attribute already has values other than one of the Lync Server 2013 key/value pairs (CSHostedVoiceMail=0 or CSHostedVoiceMail=1), a warning will indicate that the attribute may be managed by a different application.</span></span> <span data-ttu-id="17401-133">Par exemple, un avertissement s’affiche si la paire clé/valeur ExchangeHostedVoiceMail=0 ou ExchangeHostedVoiceMail=1 existe déjà.</span><span class="sxs-lookup"><span data-stu-id="17401-133">For example, a warning is displayed if the key/value pair ExchangeHostedVoiceMail=0 or ExchangeHostedVoiceMail=1 is already present.</span></span> <span data-ttu-id="17401-134">Dans ce cas, vous pouvez modifier la valeur en éditant Active Directory ou en exécutant la cmdlet suivante pour appliquer une valeur nulle :</span><span class="sxs-lookup"><span data-stu-id="17401-134">In that case, you can change the value by editing it the Active Directory, or run the following cmdlet to set the value to null:</span></span><BR><span data-ttu-id="17401-135">Set-CsUser –identité utilisateur –HostedVoicemail $null</span><span class="sxs-lookup"><span data-stu-id="17401-135">Set-CsUser –identity user –HostedVoicemail $null</span></span>



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a><span data-ttu-id="17401-136">Activation des utilisateurs pour la messagerie vocale hébergée</span><span class="sxs-lookup"><span data-stu-id="17401-136">Enabling Users for Hosted Voice Mail</span></span>

<span data-ttu-id="17401-137">Pour acheminer les appels de messagerie vocale d’un utilisateur vers une messagerie unifiée (UM) Exchange, vous devez exécuter la cmdlet Set-CsUser afin de définir la valeur du paramètre *HostedVoiceMail*.</span><span class="sxs-lookup"><span data-stu-id="17401-137">To enable a user’s voice mail calls to be routed to hosted Exchange UM, you must run the Set-CsUser cmdlet to set the value of the *HostedVoiceMail* parameter.</span></span> <span data-ttu-id="17401-138">Ce paramètre signale également à Lync Server 2013 l’indicateur d’appel de messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="17401-138">This parameter also signals Lync Server 2013 to light up the “call voice mail” indicator.</span></span>

  - <span data-ttu-id="17401-139">L’exemple suivant active le compte de Pilar Ackerman pour la messagerie vocale hébergée :</span><span class="sxs-lookup"><span data-stu-id="17401-139">The following example enables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    <span data-ttu-id="17401-p108">La cmdlet vérifie qu’une stratégie de messagerie vocale hébergée (au niveau global, du site ou de chaque utilisateur) s’applique à cet utilisateur. Si aucune stratégie ne s’applique, la cmdlet échoue.</span><span class="sxs-lookup"><span data-stu-id="17401-p108">The cmdlet verifies that a hosted voice mail policy (global, site-level or per-user) applies to this user. If no policy applies, the cmdlet fails.</span></span>

  - <span data-ttu-id="17401-142">L’exemple suivant désactive le compte de Pilar Ackerman pour la messagerie vocale hébergée :</span><span class="sxs-lookup"><span data-stu-id="17401-142">The following example disables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    <span data-ttu-id="17401-p109">La cmdlet vérifie qu’aucune stratégie de messagerie vocale hébergée (au niveau global, du site ou de chaque utilisateur) ne s’applique à cet utilisateur. Si une stratégie s’applique, la cmdlet échoue.</span><span class="sxs-lookup"><span data-stu-id="17401-p109">The cmdlet verifies that no hosted voice mail policy (global, site-level or per-user) applies to this user. If a policy does apply, the cmdlet fails.</span></span>

<span data-ttu-id="17401-145">Pour plus d’informations sur l’utilisation de la cmdlet Set-CsUser, voir la documentation de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="17401-145">For details about using the Set-CsUser cmdlet, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

