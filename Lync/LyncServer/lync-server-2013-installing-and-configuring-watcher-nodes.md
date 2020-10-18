---
title: 'Lync Server 2013 : installation et configuration des nœuds observateur'
description: 'Lync Server 2013 : installation et configuration des nœuds observateur.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing and configuring watcher nodes
ms:assetid: 61f6deea-e3ef-4468-9be8-a65705815ebb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204943(v=OCS.15)
ms:contentKeyID: 48184284
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87bf43e1651fabfa0137d09234d663cc905e947b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574000"
---
# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="dde3b-103">Installation et configuration des nœuds observateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dde3b-103">Installing and configuring watcher nodes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dde3b-104">_**Dernière modification de la rubrique :** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="dde3b-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="dde3b-105">Les *nœuds observateurs* sont des ordinateurs qui exécutent régulièrement des transactions synthétiques Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dde3b-105">*Watcher nodes* are computers that periodically run Lync Server synthetic transactions.</span></span> <span data-ttu-id="dde3b-106">Les *transactions synthétiques* sont des applets de commande Windows PowerShell qui vérifient que les scénarios d’utilisateur final clés, tels que la possibilité de se connecter au système ou la possibilité d’échanger des messages instantanés, fonctionnent comme prévu.</span><span class="sxs-lookup"><span data-stu-id="dde3b-106">*Synthetic transactions* are Windows PowerShell cmdlets that verify that key end user scenarios—such as the ability to sign in to the system, or the ability to exchange instant messages—are working as expected.</span></span> <span data-ttu-id="dde3b-107">Pour Lync Server 2013, System Center Operations Manager peut exécuter les transactions synthétiques indiquées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="dde3b-107">For Lync Server 2013, System Center Operations Manager can run the synthetic transactions shown in the following table.</span></span> <span data-ttu-id="dde3b-108">Trois types différents de transactions synthétiques sont répertoriés dans le tableau :</span><span class="sxs-lookup"><span data-stu-id="dde3b-108">There are three different synthetic transaction types shown in the table:</span></span>

  - <span data-ttu-id="dde3b-109">**Valeur par défaut**.</span><span class="sxs-lookup"><span data-stu-id="dde3b-109">**Default**.</span></span> <span data-ttu-id="dde3b-110">Il s’agit des transactions synthétiques qu’un nœud observateur exécute par défaut.</span><span class="sxs-lookup"><span data-stu-id="dde3b-110">These are the synthetic transactions that a watcher node will run by default.</span></span> <span data-ttu-id="dde3b-111">Lorsque vous créez un nœud observateur, vous avez la possibilité de spécifier les transactions synthétiques qui seront exécutées par ce nœud.</span><span class="sxs-lookup"><span data-stu-id="dde3b-111">When you create a new watcher node, you have the option of specifying which synthetic transactions that node will run.</span></span> <span data-ttu-id="dde3b-112">(Il s’agit de l’objectif du paramètre tests utilisé par la cmdlet **New-applet cswatchernodeconfiguration** .) Si vous n’utilisez pas le paramètre tests lors de la création du nœud observateur, il exécutera automatiquement toutes les transactions synthétiques par défaut et n’exécutera aucune des transactions synthétiques non par défaut.</span><span class="sxs-lookup"><span data-stu-id="dde3b-112">(That's the purpose of the Tests parameter used by the **New-CsWatcherNodeConfiguration** cmdlet.) If you do not use the Tests parameter when the watcher node is created, it will automatically run all the Default synthetic transactions and will not run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="dde3b-113">Cela signifie, par exemple, que le nœud observateur est configuré pour exécuter le test Test-CsAddressBookService, mais qu’il n’est pas configuré pour exécuter le test Test-CsExumConnectivity.</span><span class="sxs-lookup"><span data-stu-id="dde3b-113">That means, for example, that the watcher node will be configured to run the Test-CsAddressBookService test, but will not be configured to run the Test-CsExumConnectivity test.</span></span>

  - <span data-ttu-id="dde3b-114">**Non défini par défaut**.</span><span class="sxs-lookup"><span data-stu-id="dde3b-114">**Non-default**.</span></span> <span data-ttu-id="dde3b-115">Comme leur nom l’indique, les transactions synthétiques non par défaut sont des tests qui ne sont pas exécutés par défaut par l’observateur.</span><span class="sxs-lookup"><span data-stu-id="dde3b-115">As the name implies, Non-default synthetic transactions are tests that watcher nodes do not run by default.</span></span> <span data-ttu-id="dde3b-116">Cependant, le nœud observateur peut être autorisé à exécuter n’importe laquelle des transactions synthétiques non par défaut.</span><span class="sxs-lookup"><span data-stu-id="dde3b-116">However, the watcher node can be enabled to run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="dde3b-117">Vous pouvez effectuer cette opération lorsque vous créez le nœud observateur (à l’aide de l’applet de commande **New-CsWatcherNodeConfiguration**) ou à tout moment par la suite.</span><span class="sxs-lookup"><span data-stu-id="dde3b-117">You can do this when you create the watcher node (by using the **New-CsWatcherNodeConfiguration** cmdlet), or at any time after that.</span></span> <span data-ttu-id="dde3b-118">Bon nombre des transactions synthétiques non par défaut nécessitent des étapes de configuration supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="dde3b-118">Many of the Non-default synthetic transactions require extra setup steps.</span></span> <span data-ttu-id="dde3b-119">Pour plus d’informations, reportez-vous à [instructions de configuration spéciales pour les transactions synthétiques dans Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="dde3b-119">For details, see [Special setup instructions for synthetic transactions in Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).</span></span>

  - <span data-ttu-id="dde3b-120">**Étendue**.</span><span class="sxs-lookup"><span data-stu-id="dde3b-120">**Extended**.</span></span> <span data-ttu-id="dde3b-121">Les tests étendus sont un type spécial de transaction synthétique non par défaut.</span><span class="sxs-lookup"><span data-stu-id="dde3b-121">Extended tests are a special type of Non-default synthetic transaction.</span></span> <span data-ttu-id="dde3b-122">Contrairement à d’autres transactions synthétiques, les tests étendus peuvent être exécutés plusieurs fois à chaque passage.</span><span class="sxs-lookup"><span data-stu-id="dde3b-122">Unlike other synthetic transactions, Extended tests can be run multiple times during each pass.</span></span> <span data-ttu-id="dde3b-123">Cela peut s’avérer utile pour vérifier des comportements tels que plusieurs itinéraires des communications vocales PSTN pour un pool.</span><span class="sxs-lookup"><span data-stu-id="dde3b-123">This can be useful when verifying behavior such as multiple public switched telephone network (PSTN) voice routes for a pool.</span></span> <span data-ttu-id="dde3b-124">Vous pouvez configurer ceci en ajoutant simplement plusieurs instances d’un test étendu à un nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="dde3b-124">This can be configured simply by adding multiple instances of an Extended test to a watcher node.</span></span>

<span data-ttu-id="dde3b-125">Pour plus d’informations sur le processus d’ajout d’autres transactions synthétiques à un nœud observateur, voir [Managing Watcher nodes in Lync Server 2013](lync-server-2013-managing-watcher-nodes.md).</span><span class="sxs-lookup"><span data-stu-id="dde3b-125">For details about the process of adding other synthetic transactions to a watcher node, see [Managing watcher nodes in Lync Server 2013](lync-server-2013-managing-watcher-nodes.md).</span></span> <span data-ttu-id="dde3b-126">Vous pouvez utiliser Lync Server Management Shell pour supprimer des transactions synthétiques d’un nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="dde3b-126">You can use the Lync Server Management Shell to remove synthetic transactions from a watcher node.</span></span>

<span data-ttu-id="dde3b-127">Parmi les transactions synthétiques accessibles aux nœuds observateur, citons les suivantes :</span><span class="sxs-lookup"><span data-stu-id="dde3b-127">The synthetic transactions available to watcher nodes include the following:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dde3b-128">Nom de l’applet de commande (nom du test)</span><span class="sxs-lookup"><span data-stu-id="dde3b-128">Cmdlet Name (Test Name)</span></span></th>
<th><span data-ttu-id="dde3b-129">Description</span><span class="sxs-lookup"><span data-stu-id="dde3b-129">Description</span></span></th>
<th><span data-ttu-id="dde3b-130">Type de transaction synthétique</span><span class="sxs-lookup"><span data-stu-id="dde3b-130">Synthetic Transaction Type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dde3b-131">Test-CsAddressBookService (ABS)</span><span class="sxs-lookup"><span data-stu-id="dde3b-131">Test-CsAddressBookService (ABS)</span></span></p></td>
<td><p><span data-ttu-id="dde3b-132">Confirme que les utilisateurs peuvent rechercher des utilisateurs qui ne figurent pas dans leur liste de contacts.</span><span class="sxs-lookup"><span data-stu-id="dde3b-132">Confirms that users are able to look up users that aren’t in their contact list.</span></span></p></td>
<td><p><span data-ttu-id="dde3b-133">Par défaut</span><span class="sxs-lookup"><span data-stu-id="dde3b-133">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dde3b-134">Test-CsAddressBookWebQuery (ABWQ)</span><span class="sxs-lookup"><span data-stu-id="dde3b-134">Test-CsAddressBookWebQuery (ABWQ)</span></span></p></td>
<td><p><span data-ttu-id="dde3b-135">Confirme que les utilisateurs peuvent rechercher des utilisateurs qui ne figurent pas dans leur liste de contacts via HTTP.</span><span class="sxs-lookup"><span data-stu-id="dde3b-135">Confirms that users are able to look up users that aren’t in their contact list via HTTP.</span></span></p></td>
<td><p><span data-ttu-id="dde3b-136">Par défaut</span><span class="sxs-lookup"><span data-stu-id="dde3b-136">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dde3b-137">Test-CsIM (IM)</span><span class="sxs-lookup"><span data-stu-id="dde3b-137">Test-CsIM (IM)</span></span></p></td>
<td><p><span data-ttu-id="dde3b-138">Confirme que les utilisateurs peuvent envoyer des messages instantanés d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="dde3b-138">Confirms that users are able to send peer-to-peer instant messages.</span></span></p></td>
<td><p><span data-ttu-id="dde3b-139">Par défaut</span><span class="sxs-lookup"><span data-stu-id="dde3b-139">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dde3b-140">Test-CsP2PAV (P2PAV)</span><span class="sxs-lookup"><span data-stu-id="dde3b-140">Test-CsP2PAV (P2PAV)</span></span></p></td>
<td><p><span data-ttu-id="dde3b-141">Confirme que les utilisateurs peuvent passer des appels audio d’égal à égal (signalisation uniquement).</span><span class="sxs-lookup"><span data-stu-id="dde3b-141">Confirms that users are able to place peer-to-peer audio calls (signaling only).</span></span></p></td>
<td><p><span data-ttu-id="dde3b-142">Par défaut</span><span class="sxs-lookup"><span data-stu-id="dde3b-142">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dde3b-143">Test-CsPresence (Presence)</span><span class="sxs-lookup"><span data-stu-id="dde3b-143">Test-CsPresence (Presence)</span></span></p></td>
<td><p><span data-ttu-id="dde3b-144">Confirme que les utilisateurs peuvent afficher la présence d’autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="dde3b-144">Confirms that users are able to view other users’ presence.</span></span></p></td>
<td><p><span data-ttu-id="dde3b-145">Par défaut</span><span class="sxs-lookup"><span data-stu-id="dde3b-145">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dde3b-146">Test-CsRegistration (Registration)</span><span class="sxs-lookup"><span data-stu-id="dde3b-146">Test-CsRegistration (Registration)</span></span></p></td>
<td><p><span data-ttu-id="dde3b-147">Confirme que les utilisateurs peuvent se connecter à Lync.</span><span class="sxs-lookup"><span data-stu-id="dde3b-147">Confirms that users are able sign in to Lync.</span></span></p></td>
<td><p><span data-ttu-id="dde3b-148">Par défaut</span><span class="sxs-lookup"><span data-stu-id="dde3b-148">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dde3b-149">Test-CsAudioConferencingProvider (ACP)</span><span class="sxs-lookup"><span data-stu-id="dde3b-149">Test-CsAudioConferencingProvider (ACP)</span></span></p></td>
<td><p><span data-ttu-id="dde3b-150">Non utilisé avec la version locale de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dde3b-150">Not used with the on-premises version of Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="dde3b-151">Étendue</span><span class="sxs-lookup"><span data-stu-id="dde3b-151">Extended</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dde3b-152">Test-CsPstnPeerToPeerCall (PSTN)</span><span class="sxs-lookup"><span data-stu-id="dde3b-152">Test-CsPstnPeerToPeerCall (PSTN)</span></span></p></td>
<td><p><span data-ttu-id="dde3b-153">Confirme que les utilisateurs peuvent passer des appels à des personnes à l’extérieur de l’entreprise et recevoir des appels de celles-ci (numéros PSTN).</span><span class="sxs-lookup"><span data-stu-id="dde3b-153">Confirms that users are able to place and receive calls with people outside of the enterprise (PSTN numbers).</span></span></p></td>
<td><p><span data-ttu-id="dde3b-154">Non par défaut, étendu</span><span class="sxs-lookup"><span data-stu-id="dde3b-154">Non-default, Extended</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dde3b-155">Test-CsAVConference (AvConference)</span><span class="sxs-lookup"><span data-stu-id="dde3b-155">Test-CsAVConference (AvConference)</span></span></p></td>
<td><p><span data-ttu-id="dde3b-156">Confirme que les utilisateurs peuvent créer des conférences audio/vidéo et participer à celles-ci.</span><span class="sxs-lookup"><span data-stu-id="dde3b-156">Confirms that users are able to create and participate in an audio/video conference.</span></span></p></td>
<td><p><span data-ttu-id="dde3b-157">Par défaut</span><span class="sxs-lookup"><span data-stu-id="dde3b-157">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dde3b-158">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span><span class="sxs-lookup"><span data-stu-id="dde3b-158">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="dde3b-159">Confirme que les serveurs Edge A/V peuvent accepter des connexions pour les appels et les téléconférences d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="dde3b-159">Confirms that the A/V Edge servers are able to accept connections for peer-to-peer calls and conference calls.</span></span></p></td>
<td><p><span data-ttu-id="dde3b-160">Non défini par défaut</span><span class="sxs-lookup"><span data-stu-id="dde3b-160">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dde3b-161">Test-CsDataConference (DataConference)</span><span class="sxs-lookup"><span data-stu-id="dde3b-161">Test-CsDataConference (DataConference)</span></span></p></td>
<td><p><span data-ttu-id="dde3b-162">Confirme que les utilisateurs peuvent participer à une conférence de collaboration de données, une réunion en ligne qui comprend des activités telles que des tableaux blancs et des sondages.</span><span class="sxs-lookup"><span data-stu-id="dde3b-162">Confirms that users can participate in a data collaboration conference, an online meeting that includes activities such as whiteboards and polls.</span></span></p></td>
<td><p><span data-ttu-id="dde3b-163">Non défini par défaut</span><span class="sxs-lookup"><span data-stu-id="dde3b-163">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dde3b-164">Test-CsExumConnectivity (ExumConnectivity)</span><span class="sxs-lookup"><span data-stu-id="dde3b-164">Test-CsExumConnectivity (ExumConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="dde3b-165">Confirme qu’un utilisateur peut se connecter à la messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="dde3b-165">Confirms that a user can connect to Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="dde3b-166">Non défini par défaut</span><span class="sxs-lookup"><span data-stu-id="dde3b-166">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dde3b-167">Test-CsGroupIM (GroupIM)</span><span class="sxs-lookup"><span data-stu-id="dde3b-167">Test-CsGroupIM (GroupIM)</span></span></p></td>
<td><p><span data-ttu-id="dde3b-168">Confirme que les utilisateurs peuvent envoyer des messages instantanés dans des conférences et participer à des conversations par messagerie instantanée comptant trois personnes ou plus.</span><span class="sxs-lookup"><span data-stu-id="dde3b-168">Confirms that users are able to send instant messages in conferences and participate in instant message conversations with three or more people.</span></span></p></td>
<td><p><span data-ttu-id="dde3b-169">Par défaut</span><span class="sxs-lookup"><span data-stu-id="dde3b-169">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dde3b-170">Test-CsGroupIM – TestJoinLauncher (JoinLauncher)</span><span class="sxs-lookup"><span data-stu-id="dde3b-170">Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</span></span></p></td>
<td><p><span data-ttu-id="dde3b-171">Confirme que les utilisateurs peuvent créer des réunions planifiées et y participer via un lien d’adresse web.</span><span class="sxs-lookup"><span data-stu-id="dde3b-171">Confirms that users are able to create and join scheduled meetings via a web address link.</span></span></p></td>
<td><p><span data-ttu-id="dde3b-172">Non défini par défaut</span><span class="sxs-lookup"><span data-stu-id="dde3b-172">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dde3b-173">Test-CsMCXP2PIM (MCXP2PIM)</span><span class="sxs-lookup"><span data-stu-id="dde3b-173">Test-CsMCXP2PIM (MCXP2PIM)</span></span></p></td>
<td><p><span data-ttu-id="dde3b-174">Confirme que les utilisateurs d’appareil mobile peuvent inscrire et envoyer des messages instantanés.</span><span class="sxs-lookup"><span data-stu-id="dde3b-174">Confirms that mobile device users are able to register and send instant messages.</span></span></p></td>
<td><p><span data-ttu-id="dde3b-175">Non défini par défaut</span><span class="sxs-lookup"><span data-stu-id="dde3b-175">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dde3b-176">Test-CsPersistentChatMessage (PersistentChatMessage)</span><span class="sxs-lookup"><span data-stu-id="dde3b-176">Test-CsPersistentChatMessage (PersistentChatMessage)</span></span></p></td>
<td><p><span data-ttu-id="dde3b-177">Confirme que les utilisateurs peuvent échanger des messages à l’aide du service de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="dde3b-177">Confirms that users can exchange messages by using the Persistent Chat service.</span></span></p></td>
<td><p><span data-ttu-id="dde3b-178">Non défini par défaut</span><span class="sxs-lookup"><span data-stu-id="dde3b-178">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dde3b-179">Test-CsUnifiedContactStore (UnifiedContactStore)</span><span class="sxs-lookup"><span data-stu-id="dde3b-179">Test-CsUnifiedContactStore (UnifiedContactStore)</span></span></p></td>
<td><p><span data-ttu-id="dde3b-180">Confirme que les contacts d’un utilisateur sont accessibles via le magasin de contacts unifié.</span><span class="sxs-lookup"><span data-stu-id="dde3b-180">Confirms that a user's contacts can be accessed through the unified contact store.</span></span> <span data-ttu-id="dde3b-181">Le magasin de contacts unifié offre aux utilisateurs la possibilité de maintenir un ensemble unique de contacts accessibles via Lync 2013, Outlook et/ou Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="dde3b-181">The unified contact store provides a way for users to maintain a single set of contacts that can be accessed by using Lync 2013, Outlook, and/or Outlook Web Access.</span></span></p></td>
<td><p><span data-ttu-id="dde3b-182">Non défini par défaut</span><span class="sxs-lookup"><span data-stu-id="dde3b-182">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dde3b-183">Test-CsXmppIM (XmppIM)</span><span class="sxs-lookup"><span data-stu-id="dde3b-183">Test-CsXmppIM (XmppIM)</span></span></p></td>
<td><p><span data-ttu-id="dde3b-184">Confirme qu’un message instantané peut être envoyé via la passerelle XMPP (Extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="dde3b-184">Confirms that an instant message can be sent across the XMPP (Extensible Messaging and Presence Protocol) gateway.</span></span></p></td>
<td><p><span data-ttu-id="dde3b-185">Non défini par défaut</span><span class="sxs-lookup"><span data-stu-id="dde3b-185">Non-default</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dde3b-186">Vous n’avez pas besoin d’installer les nœuds observateur afin d’utiliser System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="dde3b-186">You do not need to install watcher nodes in order to use System Center Operations Manager.</span></span> <span data-ttu-id="dde3b-187">Si vous n’installez pas ces nœuds, vous pouvez toujours obtenir des alertes en temps réel à partir des composants Lync Server 2013 lorsqu’un problème se produit.</span><span class="sxs-lookup"><span data-stu-id="dde3b-187">If you do not install these nodes, you can still get real-time alerts from Lync Server 2013 components when an issue occurs.</span></span> <span data-ttu-id="dde3b-188">(Le pack d’administration des composants et des utilisateurs n’utilise pas de nœuds observateur.) Toutefois, les nœuds observateurs sont requis si vous souhaitez surveiller des scénarios de bout en bout à l’aide du pack d’administration actif.</span><span class="sxs-lookup"><span data-stu-id="dde3b-188">(The Component and User Management Pack does not use watcher nodes.) However, watcher nodes are required if you want to monitor end-to-end scenarios by using the Active Monitoring Management pack.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dde3b-189">Les administrateurs peuvent également exécuter des transactions synthétiques manuellement, et ce sans avoir besoin d’utiliser ou d’installer Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="dde3b-189">Administrators can also run synthetic transactions manually, without needing to use, or install, Operations Manager.</span></span> <span data-ttu-id="dde3b-190">Pour plus d’informations sur les différentes applets de commande Test-Cs, voir l' <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">index des applets de commande Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="dde3b-190">For details about the various Test-Cs cmdlets, see the <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 cmdlets index</A>.</span></span>



</div>

<span data-ttu-id="dde3b-191">En fonction de la taille de votre déploiement, les transactions synthétiques peuvent utiliser une grande quantité de mémoire d’ordinateur et de temps processeur.</span><span class="sxs-lookup"><span data-stu-id="dde3b-191">Depending on the size of your deployment, synthetic transactions may use a large amount of computer memory and processor time.</span></span> <span data-ttu-id="dde3b-192">Pour cette raison, nous vous recommandons d’utiliser un ordinateur dédié comme nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="dde3b-192">For this reason, we recommend that you use a dedicated computer as a watcher node.</span></span> <span data-ttu-id="dde3b-193">Par exemple, vous ne devez pas configurer un serveur frontal pour qu’il serve de nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="dde3b-193">For example, you should not configure a Front End Server to act as a watcher node.</span></span> <span data-ttu-id="dde3b-194">Les nœuds observateurs doivent respecter les spécifications matérielles suivantes :</span><span class="sxs-lookup"><span data-stu-id="dde3b-194">Watcher nodes should meet the following hardware specifications:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dde3b-195">Un nœud d’observateur Microsoft Lync Server 2010 hérité ne peut pas être colocalisé sur le même ordinateur avec un nœud observateur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dde3b-195">A legacy Microsoft Lync Server 2010 watcher node cannot be collocated on the same machine with a Lync Server 2013 watcher node.</span></span> <span data-ttu-id="dde3b-196">Cela est dû au fait que les fichiers système principaux de Lync Server 2010 et Lync Server 2013 ne peuvent pas être installés sur le même ordinateur.</span><span class="sxs-lookup"><span data-stu-id="dde3b-196">This is because the core system files for Lync Server 2010 and Lync Server 2013 cannot be installed on the same computer.</span></span><BR><span data-ttu-id="dde3b-197">Toutefois, les nœuds observateurs Lync Server 2013 peuvent surveiller simultanément Lync Server 2013 et Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="dde3b-197">However, Lync Server 2013 watcher nodes can simultaneously monitor both Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="dde3b-198">Les transactions synthétiques par défaut sont prises en charge sur les deux versions du produit.</span><span class="sxs-lookup"><span data-stu-id="dde3b-198">The Default synthetic transactions are supported on both product versions.</span></span>



</div>

<span data-ttu-id="dde3b-199">Les nœuds observateur Lync Server 2013 peuvent être déployés à l’intérieur ou à l’extérieur d’une entreprise pour vérifier les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="dde3b-199">Lync Server 2013 watcher nodes may be deployed inside or outside of an enterprise to help verify:</span></span>

  - <span></span>  
    <span data-ttu-id="dde3b-200">Connectivité aux pools pour les utilisateurs au sein de l’entreprise</span><span class="sxs-lookup"><span data-stu-id="dde3b-200">Connectivity to pools for users inside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="dde3b-201">Connectivité par le biais des réseaux de périmètre pour les utilisateurs distants qui travaillent à l’extérieur de l’entreprise</span><span class="sxs-lookup"><span data-stu-id="dde3b-201">Connectivity through perimeter networks for remote users who work outside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="dde3b-202">Connectivité aux Branch Office Appliances</span><span class="sxs-lookup"><span data-stu-id="dde3b-202">Connectivity to branch office appliances.</span></span>

  - <span></span>  
    <span data-ttu-id="dde3b-203">Connectivité à Lync Server 2010 au sein de l’entreprise et via les réseaux de périmètre.</span><span class="sxs-lookup"><span data-stu-id="dde3b-203">Connectivity to Lync Server 2010 inside the enterprise and through perimeter networks.</span></span>

<span data-ttu-id="dde3b-204">Différentes options d’authentification sont disponibles pour l’intérieur et l’extérieur de l’entreprise afin de simplifier l’administration.</span><span class="sxs-lookup"><span data-stu-id="dde3b-204">Different authentication options are available for inside and outside of the enterprise to help simplify administration.</span></span> <span data-ttu-id="dde3b-205">Pour plus d’informations, reportez-vous [à la rubrique Configuration d’un nœud observateur pour exécuter des transactions synthétiques dans Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="dde3b-205">For details, see [Configuring a watcher node to run synthetic transactions in Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).</span></span>

<span data-ttu-id="dde3b-206">Pour configurer un ordinateur pour qu’il serve de nœud observateur, vous devez effectuer les étapes suivantes après avoir installé System Center Operations Manager et importé les packs d’administration Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dde3b-206">To configure a computer to act as a watcher node, you must complete the following steps after you have installed System Center Operations Manager and imported the Lync Server 2013 management packs.</span></span>

<span data-ttu-id="dde3b-207">Avant d’installer les fichiers principaux de Lync Server 2013 et les fichiers de l’agent System Center, vous devez également vous assurer que l’ordinateur du nœud observateur remplit toutes les conditions préalables à l’installation de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dde3b-207">Before you install the Lync Server 2013 core files and the System Center agent files, you should also make sure that the watcher node computer meets all the prerequisites for installing Lync Server 2013.</span></span> <span data-ttu-id="dde3b-208">Par ailleurs, les éléments suivants doivent être installés sur l’ordinateur du nœud observateur :</span><span class="sxs-lookup"><span data-stu-id="dde3b-208">In addition, the watcher node computer should also have the following items installed:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dde3b-209">Composant matériel</span><span class="sxs-lookup"><span data-stu-id="dde3b-209">Hardware component</span></span></th>
<th><span data-ttu-id="dde3b-210">Spécification minimale</span><span class="sxs-lookup"><span data-stu-id="dde3b-210">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dde3b-211">UC</span><span class="sxs-lookup"><span data-stu-id="dde3b-211">CPU</span></span></p></td>
<td><p><span data-ttu-id="dde3b-212">Un des processeurs suivants :</span><span class="sxs-lookup"><span data-stu-id="dde3b-212">One of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dde3b-213">processeur 64 bits, quadruple cœur, 2,33 GHz ou supérieur</span><span class="sxs-lookup"><span data-stu-id="dde3b-213">64-bit processor, quad-core, 2.33 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="dde3b-214">processeur double cœur 64 bits, 2 cœurs, 2,33 GHz ou supérieur</span><span class="sxs-lookup"><span data-stu-id="dde3b-214">64-bit 2-way processor, dual-core, 2.33 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dde3b-215">Mémoire</span><span class="sxs-lookup"><span data-stu-id="dde3b-215">Memory</span></span></p></td>
<td><p><span data-ttu-id="dde3b-216">8 Go</span><span class="sxs-lookup"><span data-stu-id="dde3b-216">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dde3b-217">Système d’exploitation réseau</span><span class="sxs-lookup"><span data-stu-id="dde3b-217">Network operating system</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dde3b-218">1 carte réseau 1 Gbits/s</span><span class="sxs-lookup"><span data-stu-id="dde3b-218">1 network adapter 1 Gbps</span></span></p></li>
<li><p><span data-ttu-id="dde3b-219">Windows Server 2008 R2, Windows Server 2012 ou</span><span class="sxs-lookup"><span data-stu-id="dde3b-219">Windows Server 2008 R2, Windows Server 2012, or</span></span></p>
<p><span data-ttu-id="dde3b-220">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="dde3b-220">Windows Server 2012 R2</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


  - <span data-ttu-id="dde3b-221">Version complète du .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="dde3b-221">The full version of .NET Framework 4.5.</span></span>

  - <span data-ttu-id="dde3b-222">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="dde3b-222">Windows Identity Foundation.</span></span>

  - <span data-ttu-id="dde3b-223">Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="dde3b-223">Windows PowerShell 3.0.</span></span>

<span data-ttu-id="dde3b-224">Dès que toutes ces conditions préalables sont remplies, vous pouvez configurer le nœud observateur en effectuant les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="dde3b-224">As soon as all these prerequisites have been met, you can configure the watcher node by:</span></span>

  - <span data-ttu-id="dde3b-225">Installation des fichiers principaux de Lync Server 2013 sur l’ordinateur du nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="dde3b-225">Installing the Lync Server 2013 core files on the watcher node computer.</span></span>

  - <span data-ttu-id="dde3b-226">Installation de l’agent System Center Operations Manager sur l’ordinateur du nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="dde3b-226">Installing System Center Operations Manager agent on the watcher node computer.</span></span>

  - <span data-ttu-id="dde3b-227">Exécution du fichier exécutable Watchernode.msi</span><span class="sxs-lookup"><span data-stu-id="dde3b-227">Running the Watchernode.msi executable file.</span></span>

  - <span data-ttu-id="dde3b-228">Utilisation des applets de commande **CsWatcherNodeConfiguration** pour configurer les utilisateurs de test qui seront employés par le nœud observateur</span><span class="sxs-lookup"><span data-stu-id="dde3b-228">Using the **CsWatcherNodeConfiguration** cmdlets to configure test users to be employed by the watcher node.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

