---
title: 'Lync Server 2013: démarrage de Lync à partir d’une autre application'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Starting Lync from another application
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398376(v=OCS.15)
ms:contentKeyID: 48184184
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35e2d28a8083a7e7f1e693ddf55c5cfe3e758e96
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="starting-lync-from-another-application"></a><span data-ttu-id="3bdec-102">Démarrage de Lync à partir d’une autre application</span><span class="sxs-lookup"><span data-stu-id="3bdec-102">Starting Lync from another application</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3bdec-103">_**Dernière modification de la rubrique:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="3bdec-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="3bdec-104">Vous pouvez utiliser des paramètres de ligne de commande pour démarrer rapidement Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3bdec-104">You can use command-line parameters to quick-start Lync 2013.</span></span> <span data-ttu-id="3bdec-105">Par exemple, si un utilisateur clique sur un numéro de téléphone dans une autre application, l’application peut démarrer une instance de Lync 2013 et lancer un appel vers ce numéro.</span><span class="sxs-lookup"><span data-stu-id="3bdec-105">For example, if a user clicks a phone number in another application, the application can start an instance of Lync 2013 and initiate a call to that number.</span></span>

<span data-ttu-id="3bdec-106">Lync 2013 peut également reconnaître une liste délimitée par des points-virgules de noms de contacts pour les conférences multipièces.</span><span class="sxs-lookup"><span data-stu-id="3bdec-106">Lync 2013 can also recognize a semicolon-delimited list of contact names for multiparty conferencing.</span></span>

<span data-ttu-id="3bdec-107">Si Lync 2013 est configuré de manière à se connecter automatiquement au démarrage, puis en démarrant Lync 2013 avec des paramètres de ligne de commande, vous ouvrez la fenêtre principale de Lync.</span><span class="sxs-lookup"><span data-stu-id="3bdec-107">If Lync 2013 is configured to automatically sign in when started, then starting Lync 2013 with command-line parameters will open the Lync main window.</span></span> <span data-ttu-id="3bdec-108">Si Lync n’est pas configuré de manière à se connecter automatiquement au démarrage, la fenêtre de connexion s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="3bdec-108">If Lync is not configured to automatically sign in when started, the sign-in window opens.</span></span>

<span data-ttu-id="3bdec-109">Le tableau suivant répertorie les paramètres disponibles.</span><span class="sxs-lookup"><span data-stu-id="3bdec-109">The following table shows the available parameters.</span></span>

### <a name="lync-2013-command-line-parameters"></a><span data-ttu-id="3bdec-110">Paramètres de ligne de commande Lync 2013</span><span class="sxs-lookup"><span data-stu-id="3bdec-110">Lync 2013 Command-Line Parameters</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3bdec-111">Long</span><span class="sxs-lookup"><span data-stu-id="3bdec-111">Extension</span></span></th>
<th><span data-ttu-id="3bdec-112">Format des données</span><span class="sxs-lookup"><span data-stu-id="3bdec-112">Format of Data</span></span></th>
<th><span data-ttu-id="3bdec-113">Action</span><span class="sxs-lookup"><span data-stu-id="3bdec-113">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3bdec-114">tel</span><span class="sxs-lookup"><span data-stu-id="3bdec-114">tel:</span></span></p></td>
<td><p><span data-ttu-id="3bdec-115">URI tel</span><span class="sxs-lookup"><span data-stu-id="3bdec-115">tel URI</span></span></p></td>
<td><p><span data-ttu-id="3bdec-116">Ouvre la fenêtre de conversation pour un appel audio sans composer le numéro spécifié.</span><span class="sxs-lookup"><span data-stu-id="3bdec-116">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bdec-117">callto</span><span class="sxs-lookup"><span data-stu-id="3bdec-117">callto:</span></span></p></td>
<td><p><span data-ttu-id="3bdec-118">Tel:, SIP: ou URI tel de type</span><span class="sxs-lookup"><span data-stu-id="3bdec-118">tel:, sip:, or typeable tel URI</span></span></p></td>
<td><p><span data-ttu-id="3bdec-119">Ouvre la fenêtre de conversation pour un appel audio sans composer le numéro spécifié.</span><span class="sxs-lookup"><span data-stu-id="3bdec-119">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3bdec-120">SIP</span><span class="sxs-lookup"><span data-stu-id="3bdec-120">sip:</span></span></p></td>
<td><p><span data-ttu-id="3bdec-121">URI SIP</span><span class="sxs-lookup"><span data-stu-id="3bdec-121">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="3bdec-122">Ouvre la fenêtre de conversation avec l’URI (Uniform Resource Identifier) SIP spécifié dans la liste des participants.</span><span class="sxs-lookup"><span data-stu-id="3bdec-122">Opens the Conversation window with the specified SIP Uniform Resource Identifier (URI) in the participant list.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bdec-123">Quels</span><span class="sxs-lookup"><span data-stu-id="3bdec-123">Sips:</span></span></p></td>
<td><p><span data-ttu-id="3bdec-124">URI SIP</span><span class="sxs-lookup"><span data-stu-id="3bdec-124">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="3bdec-125">Si Lync 2013 est configuré pour utiliser le protocole TLS (Transport Layer Security), fonctionne exactement comme pour SIP:.</span><span class="sxs-lookup"><span data-stu-id="3bdec-125">If Lync 2013 is configured to use the Transport Layer Security (TLS) protocol, functions exactly like sip:.</span></span> <span data-ttu-id="3bdec-126">Si TLS n’est pas utilisé, affiche une boîte de dialogue informant l’utilisateur qu’un niveau de sécurité supérieur est requis.</span><span class="sxs-lookup"><span data-stu-id="3bdec-126">If TLS is not being used, displays a dialog box informing the user that a higher level of security is required.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3bdec-127">donne</span><span class="sxs-lookup"><span data-stu-id="3bdec-127">conf:</span></span></p></td>
<td><p><span data-ttu-id="3bdec-128">URI SIP de la Conférence à rejoindre</span><span class="sxs-lookup"><span data-stu-id="3bdec-128">SIP URI of conference to join</span></span></p></td>
<td><p><span data-ttu-id="3bdec-129">Si URI est Self, instancie le focus et affiche le focus uniquement.</span><span class="sxs-lookup"><span data-stu-id="3bdec-129">If URI is self, instantiates the focus and brings up roster-only view.</span></span> <span data-ttu-id="3bdec-130">Dans le cas contraire, ouvre l’affichage de la liste, mais n’envoie pas d’invitation.</span><span class="sxs-lookup"><span data-stu-id="3bdec-130">Otherwise, brings up roster view but does not send INVITE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bdec-131">Pseudo</span><span class="sxs-lookup"><span data-stu-id="3bdec-131">im:</span></span></p></td>
<td><p><span data-ttu-id="3bdec-132">URI SIP</span><span class="sxs-lookup"><span data-stu-id="3bdec-132">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="3bdec-133">Affiche une fenêtre de conversation par messagerie instantanée uniquement avec l’URI SIP.</span><span class="sxs-lookup"><span data-stu-id="3bdec-133">Displays an instant messaging (IM)-only Conversation window with the SIP URI.</span></span> <span data-ttu-id="3bdec-134">Accepte plusieurs URI SIP spécifiés entre crochets (&lt;&gt;) sans séparateur.</span><span class="sxs-lookup"><span data-stu-id="3bdec-134">Accepts multiple SIP URIs specified inside angle brackets (&lt;&gt;) without any separator.</span></span></p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3bdec-135">Le tableau suivant contient des exemples de ces paramètres de ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="3bdec-135">The following table provides examples of these command-line parameters.</span></span>

### <a name="command-line-parameter-examples"></a><span data-ttu-id="3bdec-136">Exemples de paramètres de ligne de commande</span><span class="sxs-lookup"><span data-stu-id="3bdec-136">Command-Line Parameter Examples</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3bdec-137">Instanci</span><span class="sxs-lookup"><span data-stu-id="3bdec-137">Instance</span></span></th>
<th><span data-ttu-id="3bdec-138">Conduit</span><span class="sxs-lookup"><span data-stu-id="3bdec-138">Results</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3bdec-139">Tel: + 14255550101</span><span class="sxs-lookup"><span data-stu-id="3bdec-139">Tel:+14255550101</span></span></p></td>
<td><p><span data-ttu-id="3bdec-140">Ouvre une seule vue de téléphone avec + 14255550101.</span><span class="sxs-lookup"><span data-stu-id="3bdec-140">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bdec-141">Callto: tel: + 14255550101</span><span class="sxs-lookup"><span data-stu-id="3bdec-141">Callto:tel:+ 14255550101</span></span></p></td>
<td><p><span data-ttu-id="3bdec-142">Ouvre une seule vue de téléphone avec + 14255550101.</span><span class="sxs-lookup"><span data-stu-id="3bdec-142">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3bdec-143">Callto:sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3bdec-143">Callto:sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="3bdec-144">Ouvre une seule vue de téléphone avec kazuto@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="3bdec-144">Opens a phone-only view with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bdec-145">sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3bdec-145">sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="3bdec-146">Ouvre une fenêtre de conversation avec kazuto@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="3bdec-146">Opens a Conversation window with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3bdec-147">conf: SIP:https://meet.contoso.com/kazuto/7322994</span><span class="sxs-lookup"><span data-stu-id="3bdec-147">conf:sip:https://meet.contoso.com/kazuto/7322994</span></span></p></td>
<td><p><span data-ttu-id="3bdec-148">Ouvre une fenêtre de conversation et affiche les options de participation à une réunion audio.</span><span class="sxs-lookup"><span data-stu-id="3bdec-148">Opens a Conversation window and displays meeting audio join options.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

