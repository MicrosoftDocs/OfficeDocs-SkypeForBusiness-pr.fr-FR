---
title: 'Lync Server 2013 : paramètres de négociation pour les partenaires fédérés XMPP'
description: 'Lync Server 2013 : paramètres de négociation pour les partenaires fédérés XMPP.'
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
ms.openlocfilehash: 6ac3d9c69d407dc750a1afb35f0a448869a88f09
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578640"
---
# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="d0c16-103">Paramètres de négociation pour les partenaires fédérés XMPP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0c16-103">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0c16-104">_**Dernière modification de la rubrique :** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="d0c16-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="d0c16-105">Les paramètres des types de négociation dans la configuration d’un partenaire XMPP possèdent un large éventail de combinaisons possibles.</span><span class="sxs-lookup"><span data-stu-id="d0c16-105">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="d0c16-106">Toutes ces combinaisons ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="d0c16-106">Not all of these combinations are valid.</span></span> <span data-ttu-id="d0c16-107">Le tableau détaillé de cette rubrique définit les paramètres valides et non valides.</span><span class="sxs-lookup"><span data-stu-id="d0c16-107">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="d0c16-108">Les configurations courantes sont présentées dans le premier tableau, le second tableau détaillant toutes les combinaisons possibles.</span><span class="sxs-lookup"><span data-stu-id="d0c16-108">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="d0c16-109">Notez que vous ne pouvez pas utiliser SASL ( *simple Authentication and Security Layer* ) **sauf si** le protocole TLS ( *Transport Layer Security* ) est également disponible.</span><span class="sxs-lookup"><span data-stu-id="d0c16-109">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="d0c16-110">SASL est envoyé dans un format non chiffré (lisible) et ne doit jamais être transmis sauf s’il est protégé par un autre moyen, tel que TLS.</span><span class="sxs-lookup"><span data-stu-id="d0c16-110">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="d0c16-111">Méthodes courantes de négociation de Fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="d0c16-111">Common XMPP Federation Negotiation Methods</span></span>

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
<th><span data-ttu-id="d0c16-112">Protocole TLS (Transport Layer Security)</span><span class="sxs-lookup"><span data-stu-id="d0c16-112">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="d0c16-113">Authentification SASL (Simple Authentication and Security Layer)</span><span class="sxs-lookup"><span data-stu-id="d0c16-113">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="d0c16-114">Authentification rappel</span><span class="sxs-lookup"><span data-stu-id="d0c16-114">Dialback Authentication</span></span></th>
<th><span data-ttu-id="d0c16-115">Méthode (s) d’authentification attendue (s)</span><span class="sxs-lookup"><span data-stu-id="d0c16-115">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="d0c16-116">Notes</span><span class="sxs-lookup"><span data-stu-id="d0c16-116">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d0c16-117">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="d0c16-117">Required</span></span></p></td>
<td><p><span data-ttu-id="d0c16-118">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="d0c16-118">Required</span></span></p></td>
<td><p><span data-ttu-id="d0c16-119">False</span><span class="sxs-lookup"><span data-stu-id="d0c16-119">False</span></span></p></td>
<td><p><span data-ttu-id="d0c16-120">SASL sur TLS</span><span class="sxs-lookup"><span data-stu-id="d0c16-120">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="d0c16-121">TLS et SASL sont nécessaires pour s’assurer que le flux de messages SASL est sécurisé.</span><span class="sxs-lookup"><span data-stu-id="d0c16-121">TLS and SASL required helps to ensure that the SASL message stream is secure.</span></span> <span data-ttu-id="d0c16-122">Rappel n’est pas disponible et ne peut pas être utilisé pour une méthode de secours si le partenaire fédéré XMPP n’a pas défini TLS sur obligatoire ou facultatif.</span><span class="sxs-lookup"><span data-stu-id="d0c16-122">Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c16-123">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="d0c16-123">Required</span></span></p></td>
<td><p><span data-ttu-id="d0c16-124">Facultatif</span><span class="sxs-lookup"><span data-stu-id="d0c16-124">Optional</span></span></p></td>
<td><p><span data-ttu-id="d0c16-125">Vrai</span><span class="sxs-lookup"><span data-stu-id="d0c16-125">True</span></span></p></td>
<td><p><span data-ttu-id="d0c16-126">SASL sur TLS, rappel TLS, TCP rappel</span><span class="sxs-lookup"><span data-stu-id="d0c16-126">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="d0c16-127">En exigeant TLS, si le partenaire fédéré XMPP a défini SASL sur Optional ou l’authentification SASL requise est utilisée.</span><span class="sxs-lookup"><span data-stu-id="d0c16-127">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used.</span></span> <span data-ttu-id="d0c16-128">Si SASL n’est pas disponible, rappel over TLS est utilisé.</span><span class="sxs-lookup"><span data-stu-id="d0c16-128">If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c16-129">Facultatif</span><span class="sxs-lookup"><span data-stu-id="d0c16-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="d0c16-130">Facultatif</span><span class="sxs-lookup"><span data-stu-id="d0c16-130">Optional</span></span></p></td>
<td><p><span data-ttu-id="d0c16-131">Vrai</span><span class="sxs-lookup"><span data-stu-id="d0c16-131">True</span></span></p></td>
<td><p><span data-ttu-id="d0c16-132">SASL sur TLS, rappel TLS, TCP rappel</span><span class="sxs-lookup"><span data-stu-id="d0c16-132">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="d0c16-133">Bien que très flexible dans les méthodes de négociation proposées, ces paramètres s’appuient sur les paramètres du partenaire de Fédération XMPP.</span><span class="sxs-lookup"><span data-stu-id="d0c16-133">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings.</span></span> <span data-ttu-id="d0c16-134">Si le partenaire a le protocole TLS facultatif ou obligatoire mais que SASL n’est pas pris en charge, les rappel TLS seront disponibles.</span><span class="sxs-lookup"><span data-stu-id="d0c16-134">If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available.</span></span> <span data-ttu-id="d0c16-135">Si le partenaire utilise TLS et SASL défini sur Optional ou Required, la sélection optimale de TLS sur SASL est utilisée.</span><span class="sxs-lookup"><span data-stu-id="d0c16-135">If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c16-136">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d0c16-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d0c16-137">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d0c16-137">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d0c16-138">Vrai</span><span class="sxs-lookup"><span data-stu-id="d0c16-138">True</span></span></p></td>
<td><p><span data-ttu-id="d0c16-139">TCP rappel</span><span class="sxs-lookup"><span data-stu-id="d0c16-139">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="d0c16-140">Dans de nombreux cas, le protocole TCP rappel est la seule solution possible.</span><span class="sxs-lookup"><span data-stu-id="d0c16-140">In many cases, TCP Dialback is the only possible solution.</span></span> <span data-ttu-id="d0c16-141">Moins souhaitable que d’autres options, il offre un niveau de confiance.</span><span class="sxs-lookup"><span data-stu-id="d0c16-141">Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="d0c16-142">Matrice des méthodes de négociation de Fédération XMPP-terminé</span><span class="sxs-lookup"><span data-stu-id="d0c16-142">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

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
<th><span data-ttu-id="d0c16-143">Protocole TLS (Transport Layer Security)</span><span class="sxs-lookup"><span data-stu-id="d0c16-143">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="d0c16-144">Authentification SASL (Simple Authentication and Security Layer)</span><span class="sxs-lookup"><span data-stu-id="d0c16-144">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="d0c16-145">Authentification rappel</span><span class="sxs-lookup"><span data-stu-id="d0c16-145">Dialback Authentication</span></span></th>
<th><span data-ttu-id="d0c16-146">Méthode d’authentification attendue</span><span class="sxs-lookup"><span data-stu-id="d0c16-146">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="d0c16-147">Remarques, avertissements ou erreurs pour une configuration non valide</span><span class="sxs-lookup"><span data-stu-id="d0c16-147">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d0c16-148">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="d0c16-148">Required</span></span></p></td>
<td><p><span data-ttu-id="d0c16-149">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="d0c16-149">Required</span></span></p></td>
<td><p><span data-ttu-id="d0c16-150">Vrai</span><span class="sxs-lookup"><span data-stu-id="d0c16-150">True</span></span></p></td>
<td><p><span data-ttu-id="d0c16-151">SASL sur TLS</span><span class="sxs-lookup"><span data-stu-id="d0c16-151">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d0c16-152">Rappel ne fonctionne pas si SASL et TLS sont tous deux requis.</span><span class="sxs-lookup"><span data-stu-id="d0c16-152">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c16-153">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="d0c16-153">Required</span></span></p></td>
<td><p><span data-ttu-id="d0c16-154">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="d0c16-154">Required</span></span></p></td>
<td><p><span data-ttu-id="d0c16-155">False</span><span class="sxs-lookup"><span data-stu-id="d0c16-155">False</span></span></p></td>
<td><p><span data-ttu-id="d0c16-156">SASL sur TLS</span><span class="sxs-lookup"><span data-stu-id="d0c16-156">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c16-157">Facultatif</span><span class="sxs-lookup"><span data-stu-id="d0c16-157">Optional</span></span></p></td>
<td><p><span data-ttu-id="d0c16-158">Requis</span><span class="sxs-lookup"><span data-stu-id="d0c16-158">Required</span></span></p></td>
<td><p><span data-ttu-id="d0c16-159">Vrai</span><span class="sxs-lookup"><span data-stu-id="d0c16-159">True</span></span></p></td>
<td><p><span data-ttu-id="d0c16-160">SASL sur TLS, rappel TLS, TCP rappel</span><span class="sxs-lookup"><span data-stu-id="d0c16-160">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d0c16-161">SASL requiert TLS.</span><span class="sxs-lookup"><span data-stu-id="d0c16-161">SASL requires TLS.</span></span> <span data-ttu-id="d0c16-162">Le fait d’autoriser TLS à être facultatif peut entraîner des négociations de session ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="d0c16-162">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c16-163">Facultatif</span><span class="sxs-lookup"><span data-stu-id="d0c16-163">Optional</span></span></p></td>
<td><p><span data-ttu-id="d0c16-164">Requis</span><span class="sxs-lookup"><span data-stu-id="d0c16-164">Required</span></span></p></td>
<td><p><span data-ttu-id="d0c16-165">False</span><span class="sxs-lookup"><span data-stu-id="d0c16-165">False</span></span></p></td>
<td><p><span data-ttu-id="d0c16-166">SASL sur TLS</span><span class="sxs-lookup"><span data-stu-id="d0c16-166">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d0c16-167">SASL requiert TLS.</span><span class="sxs-lookup"><span data-stu-id="d0c16-167">SASL requires TLS.</span></span> <span data-ttu-id="d0c16-168">Le fait d’autoriser TLS à être facultatif peut entraîner des négociations de session ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="d0c16-168">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c16-169">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d0c16-169">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d0c16-170">Requis</span><span class="sxs-lookup"><span data-stu-id="d0c16-170">Required</span></span></p></td>
<td><p><span data-ttu-id="d0c16-171">Vrai</span><span class="sxs-lookup"><span data-stu-id="d0c16-171">True</span></span></p></td>
<td><p><span data-ttu-id="d0c16-172">TCP rappel</span><span class="sxs-lookup"><span data-stu-id="d0c16-172">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d0c16-173">SASL requiert TLS.</span><span class="sxs-lookup"><span data-stu-id="d0c16-173">SASL requires TLS.</span></span> <span data-ttu-id="d0c16-174">Le fait d’autoriser TLS à être facultatif peut entraîner des négociations de session ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="d0c16-174">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c16-175">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d0c16-175">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d0c16-176">Requis</span><span class="sxs-lookup"><span data-stu-id="d0c16-176">Required</span></span></p></td>
<td><p><span data-ttu-id="d0c16-177">False</span><span class="sxs-lookup"><span data-stu-id="d0c16-177">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d0c16-178">Configuration non valide</span><span class="sxs-lookup"><span data-stu-id="d0c16-178">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d0c16-179">Étant donné que SASL requiert TLS et que TLS n’est pas disponible, SASL/TLS ne peut pas aboutir.</span><span class="sxs-lookup"><span data-stu-id="d0c16-179">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed.</span></span> <span data-ttu-id="d0c16-180">TCP rappel est défini sur false et ne peut pas être utilisé.</span><span class="sxs-lookup"><span data-stu-id="d0c16-180">TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c16-181">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="d0c16-181">Required</span></span></p></td>
<td><p><span data-ttu-id="d0c16-182">Facultatif</span><span class="sxs-lookup"><span data-stu-id="d0c16-182">Optional</span></span></p></td>
<td><p><span data-ttu-id="d0c16-183">Vrai</span><span class="sxs-lookup"><span data-stu-id="d0c16-183">True</span></span></p></td>
<td><p><span data-ttu-id="d0c16-184">SASL sur TLS, rappel TLS</span><span class="sxs-lookup"><span data-stu-id="d0c16-184">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c16-185">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="d0c16-185">Required</span></span></p></td>
<td><p><span data-ttu-id="d0c16-186">Facultatif</span><span class="sxs-lookup"><span data-stu-id="d0c16-186">Optional</span></span></p></td>
<td><p><span data-ttu-id="d0c16-187">False</span><span class="sxs-lookup"><span data-stu-id="d0c16-187">False</span></span></p></td>
<td><p><span data-ttu-id="d0c16-188">SASL sur TLS</span><span class="sxs-lookup"><span data-stu-id="d0c16-188">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c16-189">Facultatif</span><span class="sxs-lookup"><span data-stu-id="d0c16-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="d0c16-190">Facultatif</span><span class="sxs-lookup"><span data-stu-id="d0c16-190">Optional</span></span></p></td>
<td><p><span data-ttu-id="d0c16-191">Vrai</span><span class="sxs-lookup"><span data-stu-id="d0c16-191">True</span></span></p></td>
<td><p><span data-ttu-id="d0c16-192">SASL sur TLS, rappel TLS, TCP rappel</span><span class="sxs-lookup"><span data-stu-id="d0c16-192">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d0c16-193">SASL requiert TLS.</span><span class="sxs-lookup"><span data-stu-id="d0c16-193">SASL requires TLS.</span></span> <span data-ttu-id="d0c16-194">Le fait d’autoriser TLS à être facultatif peut entraîner des négociations de session ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="d0c16-194">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c16-195">Facultatif</span><span class="sxs-lookup"><span data-stu-id="d0c16-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="d0c16-196">Facultatif</span><span class="sxs-lookup"><span data-stu-id="d0c16-196">Optional</span></span></p></td>
<td><p><span data-ttu-id="d0c16-197">False</span><span class="sxs-lookup"><span data-stu-id="d0c16-197">False</span></span></p></td>
<td><p><span data-ttu-id="d0c16-198">SASL sur TLS</span><span class="sxs-lookup"><span data-stu-id="d0c16-198">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d0c16-199">SASL requiert TLS.</span><span class="sxs-lookup"><span data-stu-id="d0c16-199">SASL requires TLS.</span></span> <span data-ttu-id="d0c16-200">Le fait d’autoriser TLS à être facultatif peut entraîner des négociations de session ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="d0c16-200">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c16-201">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d0c16-201">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d0c16-202">Facultatif</span><span class="sxs-lookup"><span data-stu-id="d0c16-202">Optional</span></span></p></td>
<td><p><span data-ttu-id="d0c16-203">Vrai</span><span class="sxs-lookup"><span data-stu-id="d0c16-203">True</span></span></p></td>
<td><p><span data-ttu-id="d0c16-204">TCP rappel</span><span class="sxs-lookup"><span data-stu-id="d0c16-204">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d0c16-205">SASL requiert TLS.</span><span class="sxs-lookup"><span data-stu-id="d0c16-205">SASL requires TLS.</span></span> <span data-ttu-id="d0c16-206">Le fait d’autoriser TLS à être facultatif peut entraîner des négociations de session ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="d0c16-206">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c16-207">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d0c16-207">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d0c16-208">Facultatif</span><span class="sxs-lookup"><span data-stu-id="d0c16-208">Optional</span></span></p></td>
<td><p><span data-ttu-id="d0c16-209">False</span><span class="sxs-lookup"><span data-stu-id="d0c16-209">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d0c16-210">Configuration non valide</span><span class="sxs-lookup"><span data-stu-id="d0c16-210">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d0c16-211">SASL requiert TLS.</span><span class="sxs-lookup"><span data-stu-id="d0c16-211">SASL requires TLS.</span></span> <span data-ttu-id="d0c16-212">Le fait d’autoriser TLS à être facultatif peut entraîner des négociations de session ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="d0c16-212">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c16-213">Requis</span><span class="sxs-lookup"><span data-stu-id="d0c16-213">Required</span></span></p></td>
<td><p><span data-ttu-id="d0c16-214">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d0c16-214">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d0c16-215">Vrai</span><span class="sxs-lookup"><span data-stu-id="d0c16-215">True</span></span></p></td>
<td><p><span data-ttu-id="d0c16-216">Rappel TLS</span><span class="sxs-lookup"><span data-stu-id="d0c16-216">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="d0c16-217">La configuration autorise la rappel TLS.</span><span class="sxs-lookup"><span data-stu-id="d0c16-217">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c16-218">Requis</span><span class="sxs-lookup"><span data-stu-id="d0c16-218">Required</span></span></p></td>
<td><p><span data-ttu-id="d0c16-219">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d0c16-219">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d0c16-220">False</span><span class="sxs-lookup"><span data-stu-id="d0c16-220">False</span></span></p></td>
<td><p><span data-ttu-id="d0c16-221">Configuration non valide</span><span class="sxs-lookup"><span data-stu-id="d0c16-221">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d0c16-222">SASL ou rappel doit être activé.</span><span class="sxs-lookup"><span data-stu-id="d0c16-222">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c16-223">Facultatif</span><span class="sxs-lookup"><span data-stu-id="d0c16-223">Optional</span></span></p></td>
<td><p><span data-ttu-id="d0c16-224">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d0c16-224">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d0c16-225">Vrai</span><span class="sxs-lookup"><span data-stu-id="d0c16-225">True</span></span></p></td>
<td><p><span data-ttu-id="d0c16-226">TLS rappel, TCP rappel</span><span class="sxs-lookup"><span data-stu-id="d0c16-226">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="d0c16-227">En fonction des choix de négociation de l’autre point de terminaison, les rappel TCP ou TLS seront acceptées.</span><span class="sxs-lookup"><span data-stu-id="d0c16-227">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c16-228">Facultatif</span><span class="sxs-lookup"><span data-stu-id="d0c16-228">Optional</span></span></p></td>
<td><p><span data-ttu-id="d0c16-229">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d0c16-229">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d0c16-230">False</span><span class="sxs-lookup"><span data-stu-id="d0c16-230">False</span></span></p></td>
<td><p><span data-ttu-id="d0c16-231">Configuration non valide</span><span class="sxs-lookup"><span data-stu-id="d0c16-231">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d0c16-232">SASL ou rappel doit être activé.</span><span class="sxs-lookup"><span data-stu-id="d0c16-232">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c16-233">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d0c16-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d0c16-234">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d0c16-234">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d0c16-235">Vrai</span><span class="sxs-lookup"><span data-stu-id="d0c16-235">True</span></span></p></td>
<td><p><span data-ttu-id="d0c16-236">TCP rappel</span><span class="sxs-lookup"><span data-stu-id="d0c16-236">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="d0c16-237">Le protocole TCP rappel est la seule méthode de négociation disponible</span><span class="sxs-lookup"><span data-stu-id="d0c16-237">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c16-238">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d0c16-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d0c16-239">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="d0c16-239">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d0c16-240">False</span><span class="sxs-lookup"><span data-stu-id="d0c16-240">False</span></span></p></td>
<td><p><span data-ttu-id="d0c16-241">Configuration non valide</span><span class="sxs-lookup"><span data-stu-id="d0c16-241">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d0c16-242">SASL ou rappel doit être activé.</span><span class="sxs-lookup"><span data-stu-id="d0c16-242">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

