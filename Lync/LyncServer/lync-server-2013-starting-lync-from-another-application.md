---
title: 'Lync Server 2013 : démarrage de Lync à partir d’une autre application'
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
ms.openlocfilehash: 40e049b2a8a88514b9236ee0172474a5252bfdb1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208310"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="starting-lync-from-another-application"></a><span data-ttu-id="d4287-102">Démarrage de Lync à partir d’une autre application</span><span class="sxs-lookup"><span data-stu-id="d4287-102">Starting Lync from another application</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4287-103">_**Dernière modification de la rubrique :** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="d4287-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="d4287-104">Vous pouvez utiliser des paramètres de ligne de commande pour lancer rapidement Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="d4287-104">You can use command-line parameters to quick-start Lync 2013.</span></span> <span data-ttu-id="d4287-105">Par exemple, si un utilisateur clique sur un numéro de téléphone dans une autre application, l’application peut démarrer une instance de Lync 2013 et initier un appel à ce numéro.</span><span class="sxs-lookup"><span data-stu-id="d4287-105">For example, if a user clicks a phone number in another application, the application can start an instance of Lync 2013 and initiate a call to that number.</span></span>

<span data-ttu-id="d4287-106">Lync 2013 peut également reconnaître une liste de noms de contact délimités par des points-virgules pour les conférences à plusieurs.</span><span class="sxs-lookup"><span data-stu-id="d4287-106">Lync 2013 can also recognize a semicolon-delimited list of contact names for multiparty conferencing.</span></span>

<span data-ttu-id="d4287-107">Si Lync 2013 est configuré pour se connecter automatiquement lorsqu’il est démarré, le démarrage de Lync 2013 avec des paramètres de ligne de commande ouvre la fenêtre principale de Lync.</span><span class="sxs-lookup"><span data-stu-id="d4287-107">If Lync 2013 is configured to automatically sign in when started, then starting Lync 2013 with command-line parameters will open the Lync main window.</span></span> <span data-ttu-id="d4287-108">Si Lync n’est pas configuré pour la connexion automatique au démarrage, la fenêtre de connexion s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="d4287-108">If Lync is not configured to automatically sign in when started, the sign-in window opens.</span></span>

<span data-ttu-id="d4287-109">Le tableau suivant présente les paramètres disponibles.</span><span class="sxs-lookup"><span data-stu-id="d4287-109">The following table shows the available parameters.</span></span>

### <a name="lync-2013-command-line-parameters"></a><span data-ttu-id="d4287-110">Paramètres de ligne de commande Lync 2013</span><span class="sxs-lookup"><span data-stu-id="d4287-110">Lync 2013 Command-Line Parameters</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d4287-111">Extension</span><span class="sxs-lookup"><span data-stu-id="d4287-111">Extension</span></span></th>
<th><span data-ttu-id="d4287-112">Format des données</span><span class="sxs-lookup"><span data-stu-id="d4287-112">Format of Data</span></span></th>
<th><span data-ttu-id="d4287-113">Action</span><span class="sxs-lookup"><span data-stu-id="d4287-113">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4287-114">Téléphone</span><span class="sxs-lookup"><span data-stu-id="d4287-114">tel:</span></span></p></td>
<td><p><span data-ttu-id="d4287-115">URI tel</span><span class="sxs-lookup"><span data-stu-id="d4287-115">tel URI</span></span></p></td>
<td><p><span data-ttu-id="d4287-116">Ouvre la fenêtre de conversation pour un appel audio, mais ne compose pas le numéro spécifié.</span><span class="sxs-lookup"><span data-stu-id="d4287-116">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4287-117">protocoles callto</span><span class="sxs-lookup"><span data-stu-id="d4287-117">callto:</span></span></p></td>
<td><p><span data-ttu-id="d4287-118">tel:, sip: ou URI tel à taper</span><span class="sxs-lookup"><span data-stu-id="d4287-118">tel:, sip:, or typeable tel URI</span></span></p></td>
<td><p><span data-ttu-id="d4287-119">Ouvre la fenêtre de conversation pour un appel audio, mais ne compose pas le numéro spécifié.</span><span class="sxs-lookup"><span data-stu-id="d4287-119">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4287-120">SIP</span><span class="sxs-lookup"><span data-stu-id="d4287-120">sip:</span></span></p></td>
<td><p><span data-ttu-id="d4287-121">URI SIP</span><span class="sxs-lookup"><span data-stu-id="d4287-121">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="d4287-122">Ouvre la fenêtre de conversation avec l’URI SIP spécifié dans la liste des participants.</span><span class="sxs-lookup"><span data-stu-id="d4287-122">Opens the Conversation window with the specified SIP Uniform Resource Identifier (URI) in the participant list.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4287-123">Câbles</span><span class="sxs-lookup"><span data-stu-id="d4287-123">Sips:</span></span></p></td>
<td><p><span data-ttu-id="d4287-124">URI SIP</span><span class="sxs-lookup"><span data-stu-id="d4287-124">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="d4287-125">Si Lync 2013 est configuré pour utiliser le protocole TLS (Transport Layer Security), fonctionne exactement comme SIP :.</span><span class="sxs-lookup"><span data-stu-id="d4287-125">If Lync 2013 is configured to use the Transport Layer Security (TLS) protocol, functions exactly like sip:.</span></span> <span data-ttu-id="d4287-126">Si TLS n’est pas utilisé, affiche une boîte de dialogue informant l’utilisateur qu’un niveau de sécurité supérieur est requis.</span><span class="sxs-lookup"><span data-stu-id="d4287-126">If TLS is not being used, displays a dialog box informing the user that a higher level of security is required.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4287-127">CONF</span><span class="sxs-lookup"><span data-stu-id="d4287-127">conf:</span></span></p></td>
<td><p><span data-ttu-id="d4287-128">URI SIP de la conférence à rejoindre</span><span class="sxs-lookup"><span data-stu-id="d4287-128">SIP URI of conference to join</span></span></p></td>
<td><p><span data-ttu-id="d4287-p104">Si l’URI est automatique, instancie le focus et affiche la vue tableau uniquement. Sinon, affiche la vue tableau mais n’envoie pas INVITE.</span><span class="sxs-lookup"><span data-stu-id="d4287-p104">If URI is self, instantiates the focus and brings up roster-only view. Otherwise, brings up roster view but does not send INVITE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4287-131">messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="d4287-131">im:</span></span></p></td>
<td><p><span data-ttu-id="d4287-132">URI SIP</span><span class="sxs-lookup"><span data-stu-id="d4287-132">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="d4287-133">Affiche une fenêtre de conversation de messagerie instantanée uniquement avec l’URI SIP.</span><span class="sxs-lookup"><span data-stu-id="d4287-133">Displays an instant messaging (IM)-only Conversation window with the SIP URI.</span></span> <span data-ttu-id="d4287-134">Accepte plusieurs URI SIP spécifiés entre chevrons&lt;&gt;() sans séparateur.</span><span class="sxs-lookup"><span data-stu-id="d4287-134">Accepts multiple SIP URIs specified inside angle brackets (&lt;&gt;) without any separator.</span></span></p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d4287-135">Le tableau suivant fournit des exemples de ces paramètres de ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="d4287-135">The following table provides examples of these command-line parameters.</span></span>

### <a name="command-line-parameter-examples"></a><span data-ttu-id="d4287-136">Exemples de paramètres de ligne de commande</span><span class="sxs-lookup"><span data-stu-id="d4287-136">Command-Line Parameter Examples</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d4287-137">Instance</span><span class="sxs-lookup"><span data-stu-id="d4287-137">Instance</span></span></th>
<th><span data-ttu-id="d4287-138">Résultats</span><span class="sxs-lookup"><span data-stu-id="d4287-138">Results</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4287-139">Tél : + 14255550101</span><span class="sxs-lookup"><span data-stu-id="d4287-139">Tel:+14255550101</span></span></p></td>
<td><p><span data-ttu-id="d4287-140">Ouvre une vue téléphone uniquement avec +14255550101.</span><span class="sxs-lookup"><span data-stu-id="d4287-140">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4287-141">Callto:tel:+ 14255550101</span><span class="sxs-lookup"><span data-stu-id="d4287-141">Callto:tel:+ 14255550101</span></span></p></td>
<td><p><span data-ttu-id="d4287-142">Ouvre une vue téléphone uniquement avec +14255550101.</span><span class="sxs-lookup"><span data-stu-id="d4287-142">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4287-143">Callto:sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d4287-143">Callto:sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="d4287-144">Ouvre une vue téléphone uniquement avec kazuto@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="d4287-144">Opens a phone-only view with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4287-145">sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d4287-145">sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="d4287-146">Ouvre une fenêtre de conversation avec kazuto@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="d4287-146">Opens a Conversation window with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4287-147">conf : SIP :https://meet.contoso.com/kazuto/7322994</span><span class="sxs-lookup"><span data-stu-id="d4287-147">conf:sip:https://meet.contoso.com/kazuto/7322994</span></span></p></td>
<td><p><span data-ttu-id="d4287-148">Ouvre une fenêtre de conversation et affiche les options de participation à une réunion.</span><span class="sxs-lookup"><span data-stu-id="d4287-148">Opens a Conversation window and displays meeting audio join options.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

