---
title: 'Lync Server 2013 : paramètres de négociation pour les partenaires fédérés XMPP'
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
ms.openlocfilehash: c190e4a45a70bd527aa8fc6323a671d481f04872
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039096"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="2df73-102">Paramètres de négociation pour les partenaires fédérés XMPP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2df73-102">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2df73-103">_**Dernière modification de la rubrique :** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="2df73-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="2df73-104">Les paramètres des types de négociation dans la configuration d’un partenaire XMPP possèdent un large éventail de combinaisons possibles.</span><span class="sxs-lookup"><span data-stu-id="2df73-104">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="2df73-105">Toutes ces combinaisons ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="2df73-105">Not all of these combinations are valid.</span></span> <span data-ttu-id="2df73-106">Le tableau détaillé de cette rubrique définit les paramètres valides et non valides.</span><span class="sxs-lookup"><span data-stu-id="2df73-106">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="2df73-107">Les configurations courantes sont présentées dans le premier tableau, le second tableau détaillant toutes les combinaisons possibles.</span><span class="sxs-lookup"><span data-stu-id="2df73-107">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="2df73-108">Notez que vous ne pouvez pas utiliser SASL ( *simple Authentication and Security Layer* ) **sauf si** le protocole TLS ( *Transport Layer Security* ) est également disponible.</span><span class="sxs-lookup"><span data-stu-id="2df73-108">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="2df73-109">SASL est envoyé dans un format non chiffré (lisible) et ne doit jamais être transmis sauf s’il est protégé par un autre moyen, tel que TLS.</span><span class="sxs-lookup"><span data-stu-id="2df73-109">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="2df73-110">Méthodes courantes de négociation de Fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="2df73-110">Common XMPP Federation Negotiation Methods</span></span>

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
<th><span data-ttu-id="2df73-111">Protocole TLS (Transport Layer Security)</span><span class="sxs-lookup"><span data-stu-id="2df73-111">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="2df73-112">Authentification SASL (Simple Authentication and Security Layer)</span><span class="sxs-lookup"><span data-stu-id="2df73-112">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="2df73-113">Authentification rappel</span><span class="sxs-lookup"><span data-stu-id="2df73-113">Dialback Authentication</span></span></th>
<th><span data-ttu-id="2df73-114">Méthode (s) d’authentification attendue (s)</span><span class="sxs-lookup"><span data-stu-id="2df73-114">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="2df73-115">Notes</span><span class="sxs-lookup"><span data-stu-id="2df73-115">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2df73-116">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="2df73-116">Required</span></span></p></td>
<td><p><span data-ttu-id="2df73-117">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="2df73-117">Required</span></span></p></td>
<td><p><span data-ttu-id="2df73-118">False</span><span class="sxs-lookup"><span data-stu-id="2df73-118">False</span></span></p></td>
<td><p><span data-ttu-id="2df73-119">SASL sur TLS</span><span class="sxs-lookup"><span data-stu-id="2df73-119">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="2df73-120">TLS et SASL sont nécessaires pour s’assurer que le flux de messages SASL est sécurisé.</span><span class="sxs-lookup"><span data-stu-id="2df73-120">TLS and SASL required helps to ensure that the SASL message stream is secure.</span></span> <span data-ttu-id="2df73-121">Rappel n’est pas disponible et ne peut pas être utilisé pour une méthode de secours si le partenaire fédéré XMPP n’a pas défini TLS sur obligatoire ou facultatif.</span><span class="sxs-lookup"><span data-stu-id="2df73-121">Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df73-122">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="2df73-122">Required</span></span></p></td>
<td><p><span data-ttu-id="2df73-123">Facultatif</span><span class="sxs-lookup"><span data-stu-id="2df73-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="2df73-124">Vrai</span><span class="sxs-lookup"><span data-stu-id="2df73-124">True</span></span></p></td>
<td><p><span data-ttu-id="2df73-125">SASL sur TLS, rappel TLS, TCP rappel</span><span class="sxs-lookup"><span data-stu-id="2df73-125">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="2df73-126">En exigeant TLS, si le partenaire fédéré XMPP a défini SASL sur Optional ou l’authentification SASL requise est utilisée.</span><span class="sxs-lookup"><span data-stu-id="2df73-126">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used.</span></span> <span data-ttu-id="2df73-127">Si SASL n’est pas disponible, rappel over TLS est utilisé.</span><span class="sxs-lookup"><span data-stu-id="2df73-127">If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df73-128">Facultatif</span><span class="sxs-lookup"><span data-stu-id="2df73-128">Optional</span></span></p></td>
<td><p><span data-ttu-id="2df73-129">Facultatif</span><span class="sxs-lookup"><span data-stu-id="2df73-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="2df73-130">Vrai</span><span class="sxs-lookup"><span data-stu-id="2df73-130">True</span></span></p></td>
<td><p><span data-ttu-id="2df73-131">SASL sur TLS, rappel TLS, TCP rappel</span><span class="sxs-lookup"><span data-stu-id="2df73-131">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="2df73-132">Bien que très flexible dans les méthodes de négociation proposées, ces paramètres s’appuient sur les paramètres du partenaire de Fédération XMPP.</span><span class="sxs-lookup"><span data-stu-id="2df73-132">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings.</span></span> <span data-ttu-id="2df73-133">Si le partenaire a le protocole TLS facultatif ou obligatoire mais que SASL n’est pas pris en charge, les rappel TLS seront disponibles.</span><span class="sxs-lookup"><span data-stu-id="2df73-133">If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available.</span></span> <span data-ttu-id="2df73-134">Si le partenaire utilise TLS et SASL défini sur Optional ou Required, la sélection optimale de TLS sur SASL est utilisée.</span><span class="sxs-lookup"><span data-stu-id="2df73-134">If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df73-135">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="2df73-135">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2df73-136">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="2df73-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2df73-137">Vrai</span><span class="sxs-lookup"><span data-stu-id="2df73-137">True</span></span></p></td>
<td><p><span data-ttu-id="2df73-138">TCP rappel</span><span class="sxs-lookup"><span data-stu-id="2df73-138">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="2df73-139">Dans de nombreux cas, le protocole TCP rappel est la seule solution possible.</span><span class="sxs-lookup"><span data-stu-id="2df73-139">In many cases, TCP Dialback is the only possible solution.</span></span> <span data-ttu-id="2df73-140">Moins souhaitable que d’autres options, il offre un niveau de confiance.</span><span class="sxs-lookup"><span data-stu-id="2df73-140">Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="2df73-141">Matrice des méthodes de négociation de Fédération XMPP-terminé</span><span class="sxs-lookup"><span data-stu-id="2df73-141">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

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
<th><span data-ttu-id="2df73-142">Protocole TLS (Transport Layer Security)</span><span class="sxs-lookup"><span data-stu-id="2df73-142">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="2df73-143">Authentification SASL (Simple Authentication and Security Layer)</span><span class="sxs-lookup"><span data-stu-id="2df73-143">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="2df73-144">Authentification rappel</span><span class="sxs-lookup"><span data-stu-id="2df73-144">Dialback Authentication</span></span></th>
<th><span data-ttu-id="2df73-145">Méthode d’authentification attendue</span><span class="sxs-lookup"><span data-stu-id="2df73-145">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="2df73-146">Remarques, avertissements ou erreurs pour une configuration non valide</span><span class="sxs-lookup"><span data-stu-id="2df73-146">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2df73-147">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="2df73-147">Required</span></span></p></td>
<td><p><span data-ttu-id="2df73-148">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="2df73-148">Required</span></span></p></td>
<td><p><span data-ttu-id="2df73-149">Vrai</span><span class="sxs-lookup"><span data-stu-id="2df73-149">True</span></span></p></td>
<td><p><span data-ttu-id="2df73-150">SASL sur TLS</span><span class="sxs-lookup"><span data-stu-id="2df73-150">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2df73-151">Rappel ne fonctionne pas si SASL et TLS sont tous deux requis.</span><span class="sxs-lookup"><span data-stu-id="2df73-151">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df73-152">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="2df73-152">Required</span></span></p></td>
<td><p><span data-ttu-id="2df73-153">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="2df73-153">Required</span></span></p></td>
<td><p><span data-ttu-id="2df73-154">False</span><span class="sxs-lookup"><span data-stu-id="2df73-154">False</span></span></p></td>
<td><p><span data-ttu-id="2df73-155">SASL sur TLS</span><span class="sxs-lookup"><span data-stu-id="2df73-155">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df73-156">Facultatif</span><span class="sxs-lookup"><span data-stu-id="2df73-156">Optional</span></span></p></td>
<td><p><span data-ttu-id="2df73-157">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="2df73-157">Required</span></span></p></td>
<td><p><span data-ttu-id="2df73-158">Vrai</span><span class="sxs-lookup"><span data-stu-id="2df73-158">True</span></span></p></td>
<td><p><span data-ttu-id="2df73-159">SASL sur TLS, rappel TLS, TCP rappel</span><span class="sxs-lookup"><span data-stu-id="2df73-159">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2df73-160">SASL requiert TLS.</span><span class="sxs-lookup"><span data-stu-id="2df73-160">SASL requires TLS.</span></span> <span data-ttu-id="2df73-161">Le fait d’autoriser TLS à être facultatif peut entraîner des négociations de session ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="2df73-161">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df73-162">Facultatif</span><span class="sxs-lookup"><span data-stu-id="2df73-162">Optional</span></span></p></td>
<td><p><span data-ttu-id="2df73-163">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="2df73-163">Required</span></span></p></td>
<td><p><span data-ttu-id="2df73-164">False</span><span class="sxs-lookup"><span data-stu-id="2df73-164">False</span></span></p></td>
<td><p><span data-ttu-id="2df73-165">SASL sur TLS</span><span class="sxs-lookup"><span data-stu-id="2df73-165">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2df73-166">SASL requiert TLS.</span><span class="sxs-lookup"><span data-stu-id="2df73-166">SASL requires TLS.</span></span> <span data-ttu-id="2df73-167">Le fait d’autoriser TLS à être facultatif peut entraîner des négociations de session ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="2df73-167">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df73-168">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="2df73-168">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2df73-169">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="2df73-169">Required</span></span></p></td>
<td><p><span data-ttu-id="2df73-170">Vrai</span><span class="sxs-lookup"><span data-stu-id="2df73-170">True</span></span></p></td>
<td><p><span data-ttu-id="2df73-171">TCP rappel</span><span class="sxs-lookup"><span data-stu-id="2df73-171">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2df73-172">SASL requiert TLS.</span><span class="sxs-lookup"><span data-stu-id="2df73-172">SASL requires TLS.</span></span> <span data-ttu-id="2df73-173">Le fait d’autoriser TLS à être facultatif peut entraîner des négociations de session ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="2df73-173">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df73-174">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="2df73-174">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2df73-175">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="2df73-175">Required</span></span></p></td>
<td><p><span data-ttu-id="2df73-176">False</span><span class="sxs-lookup"><span data-stu-id="2df73-176">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2df73-177">Configuration non valide</span><span class="sxs-lookup"><span data-stu-id="2df73-177">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2df73-178">Étant donné que SASL requiert TLS et que TLS n’est pas disponible, SASL/TLS ne peut pas aboutir.</span><span class="sxs-lookup"><span data-stu-id="2df73-178">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed.</span></span> <span data-ttu-id="2df73-179">TCP rappel est défini sur false et ne peut pas être utilisé.</span><span class="sxs-lookup"><span data-stu-id="2df73-179">TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df73-180">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="2df73-180">Required</span></span></p></td>
<td><p><span data-ttu-id="2df73-181">Facultatif</span><span class="sxs-lookup"><span data-stu-id="2df73-181">Optional</span></span></p></td>
<td><p><span data-ttu-id="2df73-182">Vrai</span><span class="sxs-lookup"><span data-stu-id="2df73-182">True</span></span></p></td>
<td><p><span data-ttu-id="2df73-183">SASL sur TLS, rappel TLS</span><span class="sxs-lookup"><span data-stu-id="2df73-183">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df73-184">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="2df73-184">Required</span></span></p></td>
<td><p><span data-ttu-id="2df73-185">Facultatif</span><span class="sxs-lookup"><span data-stu-id="2df73-185">Optional</span></span></p></td>
<td><p><span data-ttu-id="2df73-186">False</span><span class="sxs-lookup"><span data-stu-id="2df73-186">False</span></span></p></td>
<td><p><span data-ttu-id="2df73-187">SASL sur TLS</span><span class="sxs-lookup"><span data-stu-id="2df73-187">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df73-188">Facultatif</span><span class="sxs-lookup"><span data-stu-id="2df73-188">Optional</span></span></p></td>
<td><p><span data-ttu-id="2df73-189">Facultatif</span><span class="sxs-lookup"><span data-stu-id="2df73-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="2df73-190">Vrai</span><span class="sxs-lookup"><span data-stu-id="2df73-190">True</span></span></p></td>
<td><p><span data-ttu-id="2df73-191">SASL sur TLS, rappel TLS, TCP rappel</span><span class="sxs-lookup"><span data-stu-id="2df73-191">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2df73-192">SASL requiert TLS.</span><span class="sxs-lookup"><span data-stu-id="2df73-192">SASL requires TLS.</span></span> <span data-ttu-id="2df73-193">Le fait d’autoriser TLS à être facultatif peut entraîner des négociations de session ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="2df73-193">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df73-194">Facultatif</span><span class="sxs-lookup"><span data-stu-id="2df73-194">Optional</span></span></p></td>
<td><p><span data-ttu-id="2df73-195">Facultatif</span><span class="sxs-lookup"><span data-stu-id="2df73-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="2df73-196">False</span><span class="sxs-lookup"><span data-stu-id="2df73-196">False</span></span></p></td>
<td><p><span data-ttu-id="2df73-197">SASL sur TLS</span><span class="sxs-lookup"><span data-stu-id="2df73-197">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2df73-198">SASL requiert TLS.</span><span class="sxs-lookup"><span data-stu-id="2df73-198">SASL requires TLS.</span></span> <span data-ttu-id="2df73-199">Le fait d’autoriser TLS à être facultatif peut entraîner des négociations de session ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="2df73-199">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df73-200">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="2df73-200">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2df73-201">Facultatif</span><span class="sxs-lookup"><span data-stu-id="2df73-201">Optional</span></span></p></td>
<td><p><span data-ttu-id="2df73-202">Vrai</span><span class="sxs-lookup"><span data-stu-id="2df73-202">True</span></span></p></td>
<td><p><span data-ttu-id="2df73-203">TCP rappel</span><span class="sxs-lookup"><span data-stu-id="2df73-203">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2df73-204">SASL requiert TLS.</span><span class="sxs-lookup"><span data-stu-id="2df73-204">SASL requires TLS.</span></span> <span data-ttu-id="2df73-205">Le fait d’autoriser TLS à être facultatif peut entraîner des négociations de session ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="2df73-205">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df73-206">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="2df73-206">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2df73-207">Facultatif</span><span class="sxs-lookup"><span data-stu-id="2df73-207">Optional</span></span></p></td>
<td><p><span data-ttu-id="2df73-208">False</span><span class="sxs-lookup"><span data-stu-id="2df73-208">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2df73-209">Configuration non valide</span><span class="sxs-lookup"><span data-stu-id="2df73-209">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2df73-210">SASL requiert TLS.</span><span class="sxs-lookup"><span data-stu-id="2df73-210">SASL requires TLS.</span></span> <span data-ttu-id="2df73-211">Le fait d’autoriser TLS à être facultatif peut entraîner des négociations de session ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="2df73-211">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df73-212">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="2df73-212">Required</span></span></p></td>
<td><p><span data-ttu-id="2df73-213">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="2df73-213">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2df73-214">Vrai</span><span class="sxs-lookup"><span data-stu-id="2df73-214">True</span></span></p></td>
<td><p><span data-ttu-id="2df73-215">Rappel TLS</span><span class="sxs-lookup"><span data-stu-id="2df73-215">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="2df73-216">La configuration autorise la rappel TLS.</span><span class="sxs-lookup"><span data-stu-id="2df73-216">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df73-217">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="2df73-217">Required</span></span></p></td>
<td><p><span data-ttu-id="2df73-218">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="2df73-218">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2df73-219">False</span><span class="sxs-lookup"><span data-stu-id="2df73-219">False</span></span></p></td>
<td><p><span data-ttu-id="2df73-220">Configuration non valide</span><span class="sxs-lookup"><span data-stu-id="2df73-220">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2df73-221">SASL ou rappel doit être activé.</span><span class="sxs-lookup"><span data-stu-id="2df73-221">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df73-222">Facultatif</span><span class="sxs-lookup"><span data-stu-id="2df73-222">Optional</span></span></p></td>
<td><p><span data-ttu-id="2df73-223">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="2df73-223">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2df73-224">Vrai</span><span class="sxs-lookup"><span data-stu-id="2df73-224">True</span></span></p></td>
<td><p><span data-ttu-id="2df73-225">TLS rappel, TCP rappel</span><span class="sxs-lookup"><span data-stu-id="2df73-225">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="2df73-226">En fonction des choix de négociation de l’autre point de terminaison, les rappel TCP ou TLS seront acceptées.</span><span class="sxs-lookup"><span data-stu-id="2df73-226">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df73-227">Facultatif</span><span class="sxs-lookup"><span data-stu-id="2df73-227">Optional</span></span></p></td>
<td><p><span data-ttu-id="2df73-228">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="2df73-228">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2df73-229">False</span><span class="sxs-lookup"><span data-stu-id="2df73-229">False</span></span></p></td>
<td><p><span data-ttu-id="2df73-230">Configuration non valide</span><span class="sxs-lookup"><span data-stu-id="2df73-230">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2df73-231">SASL ou rappel doit être activé.</span><span class="sxs-lookup"><span data-stu-id="2df73-231">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df73-232">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="2df73-232">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2df73-233">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="2df73-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2df73-234">Vrai</span><span class="sxs-lookup"><span data-stu-id="2df73-234">True</span></span></p></td>
<td><p><span data-ttu-id="2df73-235">TCP rappel</span><span class="sxs-lookup"><span data-stu-id="2df73-235">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="2df73-236">Le protocole TCP rappel est la seule méthode de négociation disponible</span><span class="sxs-lookup"><span data-stu-id="2df73-236">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df73-237">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="2df73-237">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2df73-238">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="2df73-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="2df73-239">False</span><span class="sxs-lookup"><span data-stu-id="2df73-239">False</span></span></p></td>
<td><p><span data-ttu-id="2df73-240">Configuration non valide</span><span class="sxs-lookup"><span data-stu-id="2df73-240">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="2df73-241">SASL ou rappel doit être activé.</span><span class="sxs-lookup"><span data-stu-id="2df73-241">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

