---
title: 'Lync Server 2013 : Paramètres de négociation pour les partenaires fédérés XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 995ee34d0a2dcf28ca6aa4f8158d0e08d1533191
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="a367c-102">Paramètres de négociation pour les partenaires fédérés XMPP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a367c-102">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a367c-103">_**Dernière modification de la rubrique :** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="a367c-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="a367c-104">Les paramètres des types de négociations dans la configuration d’un partenaire XMPP possèdent une large gamme de combinaisons possibles.</span><span class="sxs-lookup"><span data-stu-id="a367c-104">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="a367c-105">Toutes ces combinaisons ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="a367c-105">Not all of these combinations are valid.</span></span> <span data-ttu-id="a367c-106">Le tableau décrit dans cette rubrique définit les paramètres valides et non valides.</span><span class="sxs-lookup"><span data-stu-id="a367c-106">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="a367c-107">Les configurations courantes sont présentées dans la première table, la deuxième table présentant toutes les combinaisons possibles.</span><span class="sxs-lookup"><span data-stu-id="a367c-107">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="a367c-108">Notez que vous ne pouvez pas utiliser *l’authentification simple et la couche de sécurité* (SASL) **, sauf si** le protocole TLS ( *Transport Layer Security* ) est également disponible.</span><span class="sxs-lookup"><span data-stu-id="a367c-108">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="a367c-109">SASL est envoyé dans un format non chiffré (lisible) et ne doit jamais être transmis tant qu’il est protégé par un autre moyen, tel que TLS.</span><span class="sxs-lookup"><span data-stu-id="a367c-109">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="a367c-110">Méthodes courantes de négociation de Fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="a367c-110">Common XMPP Federation Negotiation Methods</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a367c-111">TLS (Transport Layer Security)</span><span class="sxs-lookup"><span data-stu-id="a367c-111">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="a367c-112">Authentification simple et couche de sécurité (SASL)</span><span class="sxs-lookup"><span data-stu-id="a367c-112">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="a367c-113">Authentification Dialback</span><span class="sxs-lookup"><span data-stu-id="a367c-113">Dialback Authentication</span></span></th>
<th><span data-ttu-id="a367c-114">Méthode (s) d’authentification attendue</span><span class="sxs-lookup"><span data-stu-id="a367c-114">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="a367c-115">Remarques</span><span class="sxs-lookup"><span data-stu-id="a367c-115">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a367c-116">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="a367c-116">Required</span></span></p></td>
<td><p><span data-ttu-id="a367c-117">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="a367c-117">Required</span></span></p></td>
<td><p><span data-ttu-id="a367c-118">False</span><span class="sxs-lookup"><span data-stu-id="a367c-118">False</span></span></p></td>
<td><p><span data-ttu-id="a367c-119">SASL via TLS</span><span class="sxs-lookup"><span data-stu-id="a367c-119">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="a367c-120">TLS et SASL requis permettent de s’assurer que le flux de messages SASL est sécurisé.</span><span class="sxs-lookup"><span data-stu-id="a367c-120">TLS and SASL required helps to ensure that the SASL message stream is secure.</span></span> <span data-ttu-id="a367c-121">Dialback n’est pas disponible et ne peut pas être utilisé pour une méthode de secours si le partenaire fédéré de XMPP n’a pas configuré TLS sur requis ou facultatif.</span><span class="sxs-lookup"><span data-stu-id="a367c-121">Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a367c-122">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="a367c-122">Required</span></span></p></td>
<td><p><span data-ttu-id="a367c-123">Facultatif</span><span class="sxs-lookup"><span data-stu-id="a367c-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="a367c-124">Vrai</span><span class="sxs-lookup"><span data-stu-id="a367c-124">True</span></span></p></td>
<td><p><span data-ttu-id="a367c-125">SASL via TLS, TLS Dialback, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="a367c-125">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="a367c-126">Par le biais du protocole TLS, si le partenaire fédéré XMPP a défini SASL sur l’option Optional ou Required SASL est utilisé.</span><span class="sxs-lookup"><span data-stu-id="a367c-126">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used.</span></span> <span data-ttu-id="a367c-127">Si SASL n’est pas disponible, Dialback sur TLS sera utilisé.</span><span class="sxs-lookup"><span data-stu-id="a367c-127">If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a367c-128">Facultatif </span><span class="sxs-lookup"><span data-stu-id="a367c-128">Optional</span></span></p></td>
<td><p><span data-ttu-id="a367c-129">Facultatif</span><span class="sxs-lookup"><span data-stu-id="a367c-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="a367c-130">Vrai</span><span class="sxs-lookup"><span data-stu-id="a367c-130">True</span></span></p></td>
<td><p><span data-ttu-id="a367c-131">SASL via TLS, TLS Dialback, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="a367c-131">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="a367c-132">S’ils sont très flexibles dans les méthodes de négociation proposées, ces paramètres dépendent des paramètres du partenaire de Fédération XMPP.</span><span class="sxs-lookup"><span data-stu-id="a367c-132">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings.</span></span> <span data-ttu-id="a367c-133">Si les protocoles TLS sont facultatifs ou requis alors que SASL n’est pas pris en charge, les Dialback TLS seront disponibles.</span><span class="sxs-lookup"><span data-stu-id="a367c-133">If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available.</span></span> <span data-ttu-id="a367c-134">Si le partenaire utilise les protocoles TLS et SASL définis sur facultatif ou requis, la sélection optimale de TLS sur SASL est utilisée.</span><span class="sxs-lookup"><span data-stu-id="a367c-134">If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a367c-135">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="a367c-135">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a367c-136">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="a367c-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a367c-137">Vrai</span><span class="sxs-lookup"><span data-stu-id="a367c-137">True</span></span></p></td>
<td><p><span data-ttu-id="a367c-138">TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="a367c-138">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="a367c-139">Dans de nombreux cas, TCP Dialback est la seule solution possible.</span><span class="sxs-lookup"><span data-stu-id="a367c-139">In many cases, TCP Dialback is the only possible solution.</span></span> <span data-ttu-id="a367c-140">Moins désirable que d’autres options, il fournit un certain niveau de confiance.</span><span class="sxs-lookup"><span data-stu-id="a367c-140">Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="a367c-141">Matrice des méthodes de négociation de Fédération XMPP-complet</span><span class="sxs-lookup"><span data-stu-id="a367c-141">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a367c-142">TLS (Transport Layer Security)</span><span class="sxs-lookup"><span data-stu-id="a367c-142">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="a367c-143">Authentification simple et couche de sécurité (SASL)</span><span class="sxs-lookup"><span data-stu-id="a367c-143">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="a367c-144">Authentification Dialback</span><span class="sxs-lookup"><span data-stu-id="a367c-144">Dialback Authentication</span></span></th>
<th><span data-ttu-id="a367c-145">Méthode d’authentification attendue</span><span class="sxs-lookup"><span data-stu-id="a367c-145">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="a367c-146">Remarques, avertissement ou erreur pour une configuration incorrecte</span><span class="sxs-lookup"><span data-stu-id="a367c-146">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a367c-147">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="a367c-147">Required</span></span></p></td>
<td><p><span data-ttu-id="a367c-148">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="a367c-148">Required</span></span></p></td>
<td><p><span data-ttu-id="a367c-149">Vrai</span><span class="sxs-lookup"><span data-stu-id="a367c-149">True</span></span></p></td>
<td><p><span data-ttu-id="a367c-150">SASL via TLS</span><span class="sxs-lookup"><span data-stu-id="a367c-150">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a367c-151">Dialback ne fonctionnera pas si les protocoles SASL et TLS sont requis.</span><span class="sxs-lookup"><span data-stu-id="a367c-151">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a367c-152">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="a367c-152">Required</span></span></p></td>
<td><p><span data-ttu-id="a367c-153">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="a367c-153">Required</span></span></p></td>
<td><p><span data-ttu-id="a367c-154">False</span><span class="sxs-lookup"><span data-stu-id="a367c-154">False</span></span></p></td>
<td><p><span data-ttu-id="a367c-155">SASL via TLS</span><span class="sxs-lookup"><span data-stu-id="a367c-155">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a367c-156">Facultatif</span><span class="sxs-lookup"><span data-stu-id="a367c-156">Optional</span></span></p></td>
<td><p><span data-ttu-id="a367c-157">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="a367c-157">Required</span></span></p></td>
<td><p><span data-ttu-id="a367c-158">Vrai</span><span class="sxs-lookup"><span data-stu-id="a367c-158">True</span></span></p></td>
<td><p><span data-ttu-id="a367c-159">SASL via TLS, TLS Dialback, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="a367c-159">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a367c-160">SASL nécessite le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="a367c-160">SASL requires TLS.</span></span> <span data-ttu-id="a367c-161">L’autorisation d’une connexion de TLS pouvant être facultative risque de provoquer des négociations de session en échec.</span><span class="sxs-lookup"><span data-stu-id="a367c-161">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a367c-162">Facultatif</span><span class="sxs-lookup"><span data-stu-id="a367c-162">Optional</span></span></p></td>
<td><p><span data-ttu-id="a367c-163">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="a367c-163">Required</span></span></p></td>
<td><p><span data-ttu-id="a367c-164">False</span><span class="sxs-lookup"><span data-stu-id="a367c-164">False</span></span></p></td>
<td><p><span data-ttu-id="a367c-165">SASL via TLS</span><span class="sxs-lookup"><span data-stu-id="a367c-165">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a367c-166">SASL nécessite le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="a367c-166">SASL requires TLS.</span></span> <span data-ttu-id="a367c-167">L’autorisation d’une connexion de TLS pouvant être facultative risque de provoquer des négociations de session en échec.</span><span class="sxs-lookup"><span data-stu-id="a367c-167">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a367c-168">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="a367c-168">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a367c-169">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="a367c-169">Required</span></span></p></td>
<td><p><span data-ttu-id="a367c-170">Vrai</span><span class="sxs-lookup"><span data-stu-id="a367c-170">True</span></span></p></td>
<td><p><span data-ttu-id="a367c-171">TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="a367c-171">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a367c-172">SASL nécessite le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="a367c-172">SASL requires TLS.</span></span> <span data-ttu-id="a367c-173">L’autorisation d’une connexion de TLS pouvant être facultative risque de provoquer des négociations de session en échec.</span><span class="sxs-lookup"><span data-stu-id="a367c-173">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a367c-174">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="a367c-174">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a367c-175">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="a367c-175">Required</span></span></p></td>
<td><p><span data-ttu-id="a367c-176">False</span><span class="sxs-lookup"><span data-stu-id="a367c-176">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a367c-177">Configuration non valide</span><span class="sxs-lookup"><span data-stu-id="a367c-177">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a367c-178">Dans la mesure où SASL nécessite le protocole TLS et que TLS n’est pas disponible, la fonctionnalité SASL/TLS ne peut pas aboutir.</span><span class="sxs-lookup"><span data-stu-id="a367c-178">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed.</span></span> <span data-ttu-id="a367c-179">TCP Dialback est défini sur false et ne peut pas être utilisé.</span><span class="sxs-lookup"><span data-stu-id="a367c-179">TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a367c-180">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="a367c-180">Required</span></span></p></td>
<td><p><span data-ttu-id="a367c-181">Facultatif</span><span class="sxs-lookup"><span data-stu-id="a367c-181">Optional</span></span></p></td>
<td><p><span data-ttu-id="a367c-182">Vrai</span><span class="sxs-lookup"><span data-stu-id="a367c-182">True</span></span></p></td>
<td><p><span data-ttu-id="a367c-183">SASL via TLS, TLS Dialback</span><span class="sxs-lookup"><span data-stu-id="a367c-183">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a367c-184">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="a367c-184">Required</span></span></p></td>
<td><p><span data-ttu-id="a367c-185">Facultatif</span><span class="sxs-lookup"><span data-stu-id="a367c-185">Optional</span></span></p></td>
<td><p><span data-ttu-id="a367c-186">False</span><span class="sxs-lookup"><span data-stu-id="a367c-186">False</span></span></p></td>
<td><p><span data-ttu-id="a367c-187">SASL via TLS</span><span class="sxs-lookup"><span data-stu-id="a367c-187">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a367c-188">Facultatif </span><span class="sxs-lookup"><span data-stu-id="a367c-188">Optional</span></span></p></td>
<td><p><span data-ttu-id="a367c-189">Facultatif</span><span class="sxs-lookup"><span data-stu-id="a367c-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="a367c-190">Vrai</span><span class="sxs-lookup"><span data-stu-id="a367c-190">True</span></span></p></td>
<td><p><span data-ttu-id="a367c-191">SASL via TLS, TLS Dialback, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="a367c-191">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a367c-192">SASL nécessite le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="a367c-192">SASL requires TLS.</span></span> <span data-ttu-id="a367c-193">L’autorisation d’une connexion de TLS pouvant être facultative risque de provoquer des négociations de session en échec.</span><span class="sxs-lookup"><span data-stu-id="a367c-193">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a367c-194">Facultatif </span><span class="sxs-lookup"><span data-stu-id="a367c-194">Optional</span></span></p></td>
<td><p><span data-ttu-id="a367c-195">Facultatif</span><span class="sxs-lookup"><span data-stu-id="a367c-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="a367c-196">False</span><span class="sxs-lookup"><span data-stu-id="a367c-196">False</span></span></p></td>
<td><p><span data-ttu-id="a367c-197">SASL via TLS</span><span class="sxs-lookup"><span data-stu-id="a367c-197">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a367c-198">SASL nécessite le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="a367c-198">SASL requires TLS.</span></span> <span data-ttu-id="a367c-199">L’autorisation d’une connexion de TLS pouvant être facultative risque de provoquer des négociations de session en échec.</span><span class="sxs-lookup"><span data-stu-id="a367c-199">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a367c-200">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="a367c-200">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a367c-201">Facultatif</span><span class="sxs-lookup"><span data-stu-id="a367c-201">Optional</span></span></p></td>
<td><p><span data-ttu-id="a367c-202">Vrai</span><span class="sxs-lookup"><span data-stu-id="a367c-202">True</span></span></p></td>
<td><p><span data-ttu-id="a367c-203">TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="a367c-203">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a367c-204">SASL nécessite le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="a367c-204">SASL requires TLS.</span></span> <span data-ttu-id="a367c-205">L’autorisation d’une connexion de TLS pouvant être facultative risque de provoquer des négociations de session en échec.</span><span class="sxs-lookup"><span data-stu-id="a367c-205">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a367c-206">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="a367c-206">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a367c-207">Facultatif</span><span class="sxs-lookup"><span data-stu-id="a367c-207">Optional</span></span></p></td>
<td><p><span data-ttu-id="a367c-208">False</span><span class="sxs-lookup"><span data-stu-id="a367c-208">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a367c-209">Configuration non valide</span><span class="sxs-lookup"><span data-stu-id="a367c-209">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a367c-210">SASL nécessite le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="a367c-210">SASL requires TLS.</span></span> <span data-ttu-id="a367c-211">L’autorisation d’une connexion de TLS pouvant être facultative risque de provoquer des négociations de session en échec.</span><span class="sxs-lookup"><span data-stu-id="a367c-211">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a367c-212">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="a367c-212">Required</span></span></p></td>
<td><p><span data-ttu-id="a367c-213">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="a367c-213">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a367c-214">Vrai</span><span class="sxs-lookup"><span data-stu-id="a367c-214">True</span></span></p></td>
<td><p><span data-ttu-id="a367c-215">Dialback TLS</span><span class="sxs-lookup"><span data-stu-id="a367c-215">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="a367c-216">La configuration autorise Dialback TLS.</span><span class="sxs-lookup"><span data-stu-id="a367c-216">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a367c-217">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="a367c-217">Required</span></span></p></td>
<td><p><span data-ttu-id="a367c-218">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="a367c-218">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a367c-219">False</span><span class="sxs-lookup"><span data-stu-id="a367c-219">False</span></span></p></td>
<td><p><span data-ttu-id="a367c-220">Configuration non valide</span><span class="sxs-lookup"><span data-stu-id="a367c-220">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a367c-221">SASL ou Dialback doit être activé.</span><span class="sxs-lookup"><span data-stu-id="a367c-221">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a367c-222">Facultatif</span><span class="sxs-lookup"><span data-stu-id="a367c-222">Optional</span></span></p></td>
<td><p><span data-ttu-id="a367c-223">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="a367c-223">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a367c-224">Vrai</span><span class="sxs-lookup"><span data-stu-id="a367c-224">True</span></span></p></td>
<td><p><span data-ttu-id="a367c-225">Dialback TLS, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="a367c-225">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="a367c-226">En fonction des choix de négociation des autres points de terminaison, les protocoles TCP ou TLS Dialback seront acceptés.</span><span class="sxs-lookup"><span data-stu-id="a367c-226">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a367c-227">Facultatif</span><span class="sxs-lookup"><span data-stu-id="a367c-227">Optional</span></span></p></td>
<td><p><span data-ttu-id="a367c-228">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="a367c-228">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a367c-229">False</span><span class="sxs-lookup"><span data-stu-id="a367c-229">False</span></span></p></td>
<td><p><span data-ttu-id="a367c-230">Configuration non valide</span><span class="sxs-lookup"><span data-stu-id="a367c-230">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a367c-231">SASL ou Dialback doit être activé.</span><span class="sxs-lookup"><span data-stu-id="a367c-231">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a367c-232">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="a367c-232">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a367c-233">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="a367c-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a367c-234">Vrai</span><span class="sxs-lookup"><span data-stu-id="a367c-234">True</span></span></p></td>
<td><p><span data-ttu-id="a367c-235">TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="a367c-235">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="a367c-236">TCP Dialback est la seule méthode de négociation disponible.</span><span class="sxs-lookup"><span data-stu-id="a367c-236">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a367c-237">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="a367c-237">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a367c-238">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="a367c-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="a367c-239">False</span><span class="sxs-lookup"><span data-stu-id="a367c-239">False</span></span></p></td>
<td><p><span data-ttu-id="a367c-240">Configuration non valide</span><span class="sxs-lookup"><span data-stu-id="a367c-240">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="a367c-241">SASL ou Dialback doit être activé.</span><span class="sxs-lookup"><span data-stu-id="a367c-241">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

