---
title: 'Lync Server 2013 : démarrage de Lync à partir d’une autre application'
description: 'Lync Server 2013 : démarrage de Lync à partir d’une autre application.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Starting Lync from another application
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398376(v=OCS.15)
ms:contentKeyID: 48184184
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd64b8b9f335638b54a0bf6473b5d159c97a0e7f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562700"
---
# <a name="starting-lync-from-another-application"></a><span data-ttu-id="303f7-103">Démarrage de Lync à partir d’une autre application</span><span class="sxs-lookup"><span data-stu-id="303f7-103">Starting Lync from another application</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="303f7-104">_**Dernière modification de la rubrique :** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="303f7-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="303f7-105">Vous pouvez utiliser des paramètres de ligne de commande pour lancer rapidement Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="303f7-105">You can use command-line parameters to quick-start Lync 2013.</span></span> <span data-ttu-id="303f7-106">Par exemple, si un utilisateur clique sur un numéro de téléphone dans une autre application, l’application peut démarrer une instance de Lync 2013 et initier un appel à ce numéro.</span><span class="sxs-lookup"><span data-stu-id="303f7-106">For example, if a user clicks a phone number in another application, the application can start an instance of Lync 2013 and initiate a call to that number.</span></span>

<span data-ttu-id="303f7-107">Lync 2013 peut également reconnaître une liste de noms de contact délimités par des points-virgules pour les conférences à plusieurs.</span><span class="sxs-lookup"><span data-stu-id="303f7-107">Lync 2013 can also recognize a semicolon-delimited list of contact names for multiparty conferencing.</span></span>

<span data-ttu-id="303f7-108">Si Lync 2013 est configuré pour se connecter automatiquement lorsqu’il est démarré, le démarrage de Lync 2013 avec des paramètres de ligne de commande ouvre la fenêtre principale de Lync.</span><span class="sxs-lookup"><span data-stu-id="303f7-108">If Lync 2013 is configured to automatically sign in when started, then starting Lync 2013 with command-line parameters will open the Lync main window.</span></span> <span data-ttu-id="303f7-109">Si Lync n’est pas configuré pour la connexion automatique au démarrage, la fenêtre de connexion s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="303f7-109">If Lync is not configured to automatically sign in when started, the sign-in window opens.</span></span>

<span data-ttu-id="303f7-110">Le tableau suivant présente les paramètres disponibles.</span><span class="sxs-lookup"><span data-stu-id="303f7-110">The following table shows the available parameters.</span></span>

### <a name="lync-2013-command-line-parameters"></a><span data-ttu-id="303f7-111">Paramètres de Command-Line Lync 2013</span><span class="sxs-lookup"><span data-stu-id="303f7-111">Lync 2013 Command-Line Parameters</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="303f7-112">Extension</span><span class="sxs-lookup"><span data-stu-id="303f7-112">Extension</span></span></th>
<th><span data-ttu-id="303f7-113">Format des données</span><span class="sxs-lookup"><span data-stu-id="303f7-113">Format of Data</span></span></th>
<th><span data-ttu-id="303f7-114">Action</span><span class="sxs-lookup"><span data-stu-id="303f7-114">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="303f7-115">Téléphone</span><span class="sxs-lookup"><span data-stu-id="303f7-115">tel:</span></span></p></td>
<td><p><span data-ttu-id="303f7-116">URI tel</span><span class="sxs-lookup"><span data-stu-id="303f7-116">tel URI</span></span></p></td>
<td><p><span data-ttu-id="303f7-117">Ouvre la fenêtre de conversation pour un appel audio, mais ne compose pas le numéro spécifié.</span><span class="sxs-lookup"><span data-stu-id="303f7-117">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="303f7-118">protocoles callto</span><span class="sxs-lookup"><span data-stu-id="303f7-118">callto:</span></span></p></td>
<td><p><span data-ttu-id="303f7-119">tel:, sip: ou URI tel à taper</span><span class="sxs-lookup"><span data-stu-id="303f7-119">tel:, sip:, or typeable tel URI</span></span></p></td>
<td><p><span data-ttu-id="303f7-120">Ouvre la fenêtre de conversation pour un appel audio, mais ne compose pas le numéro spécifié.</span><span class="sxs-lookup"><span data-stu-id="303f7-120">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="303f7-121">SIP</span><span class="sxs-lookup"><span data-stu-id="303f7-121">sip:</span></span></p></td>
<td><p><span data-ttu-id="303f7-122">URI SIP</span><span class="sxs-lookup"><span data-stu-id="303f7-122">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="303f7-123">Ouvre la fenêtre de conversation avec l’URI SIP spécifié dans la liste des participants.</span><span class="sxs-lookup"><span data-stu-id="303f7-123">Opens the Conversation window with the specified SIP Uniform Resource Identifier (URI) in the participant list.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="303f7-124">Câbles</span><span class="sxs-lookup"><span data-stu-id="303f7-124">Sips:</span></span></p></td>
<td><p><span data-ttu-id="303f7-125">URI SIP</span><span class="sxs-lookup"><span data-stu-id="303f7-125">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="303f7-126">Si Lync 2013 est configuré pour utiliser le protocole TLS (Transport Layer Security), fonctionne exactement comme SIP :.</span><span class="sxs-lookup"><span data-stu-id="303f7-126">If Lync 2013 is configured to use the Transport Layer Security (TLS) protocol, functions exactly like sip:.</span></span> <span data-ttu-id="303f7-127">Si TLS n’est pas utilisé, affiche une boîte de dialogue informant l’utilisateur qu’un niveau de sécurité supérieur est requis.</span><span class="sxs-lookup"><span data-stu-id="303f7-127">If TLS is not being used, displays a dialog box informing the user that a higher level of security is required.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="303f7-128">CONF</span><span class="sxs-lookup"><span data-stu-id="303f7-128">conf:</span></span></p></td>
<td><p><span data-ttu-id="303f7-129">URI SIP de la conférence à rejoindre</span><span class="sxs-lookup"><span data-stu-id="303f7-129">SIP URI of conference to join</span></span></p></td>
<td><p><span data-ttu-id="303f7-p104">Si l’URI est automatique, instancie le focus et affiche la vue tableau uniquement. Sinon, affiche la vue tableau mais n’envoie pas INVITE.</span><span class="sxs-lookup"><span data-stu-id="303f7-p104">If URI is self, instantiates the focus and brings up roster-only view. Otherwise, brings up roster view but does not send INVITE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="303f7-132">messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="303f7-132">im:</span></span></p></td>
<td><p><span data-ttu-id="303f7-133">URI SIP</span><span class="sxs-lookup"><span data-stu-id="303f7-133">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="303f7-134">Affiche une fenêtre de conversation de messagerie instantanée uniquement avec l’URI SIP.</span><span class="sxs-lookup"><span data-stu-id="303f7-134">Displays an instant messaging (IM)-only Conversation window with the SIP URI.</span></span> <span data-ttu-id="303f7-135">Accepte plusieurs URI SIP spécifiés entre chevrons ( &lt; &gt; ) sans séparateur.</span><span class="sxs-lookup"><span data-stu-id="303f7-135">Accepts multiple SIP URIs specified inside angle brackets (&lt;&gt;) without any separator.</span></span></p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="303f7-136">Le tableau suivant fournit des exemples de ces paramètres de ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="303f7-136">The following table provides examples of these command-line parameters.</span></span>

### <a name="command-line-parameter-examples"></a><span data-ttu-id="303f7-137">Exemples de paramètres de ligne de commande</span><span class="sxs-lookup"><span data-stu-id="303f7-137">Command-Line Parameter Examples</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="303f7-138">Instance</span><span class="sxs-lookup"><span data-stu-id="303f7-138">Instance</span></span></th>
<th><span data-ttu-id="303f7-139">Résultats</span><span class="sxs-lookup"><span data-stu-id="303f7-139">Results</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="303f7-140">Tél : + 14255550101</span><span class="sxs-lookup"><span data-stu-id="303f7-140">Tel:+14255550101</span></span></p></td>
<td><p><span data-ttu-id="303f7-141">Ouvre une vue téléphone uniquement avec +14255550101.</span><span class="sxs-lookup"><span data-stu-id="303f7-141">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="303f7-142">Callto:tel:+ 14255550101</span><span class="sxs-lookup"><span data-stu-id="303f7-142">Callto:tel:+ 14255550101</span></span></p></td>
<td><p><span data-ttu-id="303f7-143">Ouvre une vue téléphone uniquement avec +14255550101.</span><span class="sxs-lookup"><span data-stu-id="303f7-143">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="303f7-144">Callto:sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="303f7-144">Callto:sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="303f7-145">Ouvre une vue téléphone uniquement avec kazuto@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="303f7-145">Opens a phone-only view with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="303f7-146">sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="303f7-146">sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="303f7-147">Ouvre une fenêtre de conversation avec kazuto@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="303f7-147">Opens a Conversation window with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="303f7-148">conf : SIP :https://meet.contoso.com/kazuto/7322994</span><span class="sxs-lookup"><span data-stu-id="303f7-148">conf:sip:https://meet.contoso.com/kazuto/7322994</span></span></p></td>
<td><p><span data-ttu-id="303f7-149">Ouvre une fenêtre de conversation et affiche les options de participation à une réunion.</span><span class="sxs-lookup"><span data-stu-id="303f7-149">Opens a Conversation window and displays meeting audio join options.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

