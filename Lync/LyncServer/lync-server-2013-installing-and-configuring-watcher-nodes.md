---
title: 'Lync Server 2013 : installation et configuration des nœuds observateur'
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
ms.openlocfilehash: 0cd57e3b78e3e16ac9d640536771cf2b5b90773a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="2f587-102">Installation et configuration des nœuds observateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f587-102">Installing and configuring watcher nodes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f587-103">_**Dernière modification de la rubrique :** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="2f587-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="2f587-104">Les *nœuds observateurs* sont des ordinateurs qui exécutent régulièrement des transactions synthétiques Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2f587-104">*Watcher nodes* are computers that periodically run Lync Server synthetic transactions.</span></span> <span data-ttu-id="2f587-105">Les *transactions synthétiques* sont des applets de commande Windows PowerShell qui vérifient que les scénarios d’utilisateur final clés, tels que la possibilité de se connecter au système ou la possibilité d’échanger des messages instantanés, fonctionnent comme prévu.</span><span class="sxs-lookup"><span data-stu-id="2f587-105">*Synthetic transactions* are Windows PowerShell cmdlets that verify that key end user scenarios—such as the ability to sign in to the system, or the ability to exchange instant messages—are working as expected.</span></span> <span data-ttu-id="2f587-106">Pour Lync Server 2013, System Center Operations Manager peut exécuter les transactions synthétiques indiquées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="2f587-106">For Lync Server 2013, System Center Operations Manager can run the synthetic transactions shown in the following table.</span></span> <span data-ttu-id="2f587-107">Trois types différents de transactions synthétiques sont répertoriés dans le tableau :</span><span class="sxs-lookup"><span data-stu-id="2f587-107">There are three different synthetic transaction types shown in the table:</span></span>

  - <span data-ttu-id="2f587-108">**Valeur par défaut**.</span><span class="sxs-lookup"><span data-stu-id="2f587-108">**Default**.</span></span> <span data-ttu-id="2f587-109">Il s’agit des transactions synthétiques qu’un nœud observateur exécute par défaut.</span><span class="sxs-lookup"><span data-stu-id="2f587-109">These are the synthetic transactions that a watcher node will run by default.</span></span> <span data-ttu-id="2f587-110">Lorsque vous créez un nœud observateur, vous avez la possibilité de spécifier les transactions synthétiques qui seront exécutées par ce nœud.</span><span class="sxs-lookup"><span data-stu-id="2f587-110">When you create a new watcher node, you have the option of specifying which synthetic transactions that node will run.</span></span> <span data-ttu-id="2f587-111">(Il s’agit de l’objectif du paramètre tests utilisé par la cmdlet **New-applet cswatchernodeconfiguration** .) Si vous n’utilisez pas le paramètre tests lors de la création du nœud observateur, il exécutera automatiquement toutes les transactions synthétiques par défaut et n’exécutera aucune des transactions synthétiques non par défaut.</span><span class="sxs-lookup"><span data-stu-id="2f587-111">(That's the purpose of the Tests parameter used by the **New-CsWatcherNodeConfiguration** cmdlet.) If you do not use the Tests parameter when the watcher node is created, it will automatically run all the Default synthetic transactions and will not run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="2f587-112">Cela signifie, par exemple, que le nœud observateur est configuré pour exécuter le test Test-CsAddressBookService, mais qu’il n’est pas configuré pour exécuter le test Test-CsExumConnectivity.</span><span class="sxs-lookup"><span data-stu-id="2f587-112">That means, for example, that the watcher node will be configured to run the Test-CsAddressBookService test, but will not be configured to run the Test-CsExumConnectivity test.</span></span>

  - <span data-ttu-id="2f587-113">**Non défini par défaut**.</span><span class="sxs-lookup"><span data-stu-id="2f587-113">**Non-default**.</span></span> <span data-ttu-id="2f587-114">Comme leur nom l’indique, les transactions synthétiques non par défaut sont des tests qui ne sont pas exécutés par défaut par l’observateur.</span><span class="sxs-lookup"><span data-stu-id="2f587-114">As the name implies, Non-default synthetic transactions are tests that watcher nodes do not run by default.</span></span> <span data-ttu-id="2f587-115">Cependant, le nœud observateur peut être autorisé à exécuter n’importe laquelle des transactions synthétiques non par défaut.</span><span class="sxs-lookup"><span data-stu-id="2f587-115">However, the watcher node can be enabled to run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="2f587-116">Vous pouvez effectuer cette opération lorsque vous créez le nœud observateur (à l’aide de l’applet de commande **New-CsWatcherNodeConfiguration**) ou à tout moment par la suite.</span><span class="sxs-lookup"><span data-stu-id="2f587-116">You can do this when you create the watcher node (by using the **New-CsWatcherNodeConfiguration** cmdlet), or at any time after that.</span></span> <span data-ttu-id="2f587-117">Bon nombre des transactions synthétiques non par défaut nécessitent des étapes de configuration supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="2f587-117">Many of the Non-default synthetic transactions require extra setup steps.</span></span> <span data-ttu-id="2f587-118">Pour plus d’informations, reportez-vous à [instructions de configuration spéciales pour les transactions synthétiques dans Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="2f587-118">For details, see [Special setup instructions for synthetic transactions in Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).</span></span>

  - <span data-ttu-id="2f587-119">**Étendue**.</span><span class="sxs-lookup"><span data-stu-id="2f587-119">**Extended**.</span></span> <span data-ttu-id="2f587-120">Les tests étendus sont un type spécial de transaction synthétique non par défaut.</span><span class="sxs-lookup"><span data-stu-id="2f587-120">Extended tests are a special type of Non-default synthetic transaction.</span></span> <span data-ttu-id="2f587-121">Contrairement à d’autres transactions synthétiques, les tests étendus peuvent être exécutés plusieurs fois à chaque passage.</span><span class="sxs-lookup"><span data-stu-id="2f587-121">Unlike other synthetic transactions, Extended tests can be run multiple times during each pass.</span></span> <span data-ttu-id="2f587-122">Cela peut s’avérer utile pour vérifier des comportements tels que plusieurs itinéraires des communications vocales PSTN pour un pool.</span><span class="sxs-lookup"><span data-stu-id="2f587-122">This can be useful when verifying behavior such as multiple public switched telephone network (PSTN) voice routes for a pool.</span></span> <span data-ttu-id="2f587-123">Vous pouvez configurer ceci en ajoutant simplement plusieurs instances d’un test étendu à un nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="2f587-123">This can be configured simply by adding multiple instances of an Extended test to a watcher node.</span></span>

<span data-ttu-id="2f587-124">Pour plus d’informations sur le processus d’ajout d’autres transactions synthétiques à un nœud observateur, voir [Managing Watcher nodes in Lync Server 2013](lync-server-2013-managing-watcher-nodes.md).</span><span class="sxs-lookup"><span data-stu-id="2f587-124">For details about the process of adding other synthetic transactions to a watcher node, see [Managing watcher nodes in Lync Server 2013](lync-server-2013-managing-watcher-nodes.md).</span></span> <span data-ttu-id="2f587-125">Vous pouvez utiliser Lync Server Management Shell pour supprimer des transactions synthétiques d’un nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="2f587-125">You can use the Lync Server Management Shell to remove synthetic transactions from a watcher node.</span></span>

<span data-ttu-id="2f587-126">Parmi les transactions synthétiques accessibles aux nœuds observateur, citons les suivantes :</span><span class="sxs-lookup"><span data-stu-id="2f587-126">The synthetic transactions available to watcher nodes include the following:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f587-127">Nom de l’applet de commande (nom du test)</span><span class="sxs-lookup"><span data-stu-id="2f587-127">Cmdlet Name (Test Name)</span></span></th>
<th><span data-ttu-id="2f587-128">Description</span><span class="sxs-lookup"><span data-stu-id="2f587-128">Description</span></span></th>
<th><span data-ttu-id="2f587-129">Type de transaction synthétique</span><span class="sxs-lookup"><span data-stu-id="2f587-129">Synthetic Transaction Type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f587-130">Test-CsAddressBookService (ABS)</span><span class="sxs-lookup"><span data-stu-id="2f587-130">Test-CsAddressBookService (ABS)</span></span></p></td>
<td><p><span data-ttu-id="2f587-131">Confirme que les utilisateurs peuvent rechercher des utilisateurs qui ne figurent pas dans leur liste de contacts.</span><span class="sxs-lookup"><span data-stu-id="2f587-131">Confirms that users are able to look up users that aren’t in their contact list.</span></span></p></td>
<td><p><span data-ttu-id="2f587-132">Par défaut</span><span class="sxs-lookup"><span data-stu-id="2f587-132">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f587-133">Test-CsAddressBookWebQuery (ABWQ)</span><span class="sxs-lookup"><span data-stu-id="2f587-133">Test-CsAddressBookWebQuery (ABWQ)</span></span></p></td>
<td><p><span data-ttu-id="2f587-134">Confirme que les utilisateurs peuvent rechercher des utilisateurs qui ne figurent pas dans leur liste de contacts via HTTP.</span><span class="sxs-lookup"><span data-stu-id="2f587-134">Confirms that users are able to look up users that aren’t in their contact list via HTTP.</span></span></p></td>
<td><p><span data-ttu-id="2f587-135">Par défaut</span><span class="sxs-lookup"><span data-stu-id="2f587-135">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f587-136">Test-CsIM (IM)</span><span class="sxs-lookup"><span data-stu-id="2f587-136">Test-CsIM (IM)</span></span></p></td>
<td><p><span data-ttu-id="2f587-137">Confirme que les utilisateurs peuvent envoyer des messages instantanés d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="2f587-137">Confirms that users are able to send peer-to-peer instant messages.</span></span></p></td>
<td><p><span data-ttu-id="2f587-138">Par défaut</span><span class="sxs-lookup"><span data-stu-id="2f587-138">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f587-139">Test-CsP2PAV (P2PAV)</span><span class="sxs-lookup"><span data-stu-id="2f587-139">Test-CsP2PAV (P2PAV)</span></span></p></td>
<td><p><span data-ttu-id="2f587-140">Confirme que les utilisateurs peuvent passer des appels audio d’égal à égal (signalisation uniquement).</span><span class="sxs-lookup"><span data-stu-id="2f587-140">Confirms that users are able to place peer-to-peer audio calls (signaling only).</span></span></p></td>
<td><p><span data-ttu-id="2f587-141">Par défaut</span><span class="sxs-lookup"><span data-stu-id="2f587-141">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f587-142">Test-CsPresence (Presence)</span><span class="sxs-lookup"><span data-stu-id="2f587-142">Test-CsPresence (Presence)</span></span></p></td>
<td><p><span data-ttu-id="2f587-143">Confirme que les utilisateurs peuvent afficher la présence d’autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="2f587-143">Confirms that users are able to view other users’ presence.</span></span></p></td>
<td><p><span data-ttu-id="2f587-144">Par défaut</span><span class="sxs-lookup"><span data-stu-id="2f587-144">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f587-145">Test-CsRegistration (Registration)</span><span class="sxs-lookup"><span data-stu-id="2f587-145">Test-CsRegistration (Registration)</span></span></p></td>
<td><p><span data-ttu-id="2f587-146">Confirme que les utilisateurs peuvent se connecter à Lync.</span><span class="sxs-lookup"><span data-stu-id="2f587-146">Confirms that users are able sign in to Lync.</span></span></p></td>
<td><p><span data-ttu-id="2f587-147">Par défaut</span><span class="sxs-lookup"><span data-stu-id="2f587-147">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f587-148">Test-CsAudioConferencingProvider (ACP)</span><span class="sxs-lookup"><span data-stu-id="2f587-148">Test-CsAudioConferencingProvider (ACP)</span></span></p></td>
<td><p><span data-ttu-id="2f587-149">Non utilisé avec la version locale de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f587-149">Not used with the on-premises version of Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="2f587-150">Étendue</span><span class="sxs-lookup"><span data-stu-id="2f587-150">Extended</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f587-151">Test-CsPstnPeerToPeerCall (PSTN)</span><span class="sxs-lookup"><span data-stu-id="2f587-151">Test-CsPstnPeerToPeerCall (PSTN)</span></span></p></td>
<td><p><span data-ttu-id="2f587-152">Confirme que les utilisateurs peuvent passer des appels à des personnes à l’extérieur de l’entreprise et recevoir des appels de celles-ci (numéros PSTN).</span><span class="sxs-lookup"><span data-stu-id="2f587-152">Confirms that users are able to place and receive calls with people outside of the enterprise (PSTN numbers).</span></span></p></td>
<td><p><span data-ttu-id="2f587-153">Non par défaut, étendu</span><span class="sxs-lookup"><span data-stu-id="2f587-153">Non-default, Extended</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f587-154">Test-CsAVConference (AvConference)</span><span class="sxs-lookup"><span data-stu-id="2f587-154">Test-CsAVConference (AvConference)</span></span></p></td>
<td><p><span data-ttu-id="2f587-155">Confirme que les utilisateurs peuvent créer des conférences audio/vidéo et participer à celles-ci.</span><span class="sxs-lookup"><span data-stu-id="2f587-155">Confirms that users are able to create and participate in an audio/video conference.</span></span></p></td>
<td><p><span data-ttu-id="2f587-156">Par défaut</span><span class="sxs-lookup"><span data-stu-id="2f587-156">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f587-157">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span><span class="sxs-lookup"><span data-stu-id="2f587-157">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="2f587-158">Confirme que les serveurs Edge A/V peuvent accepter des connexions pour les appels et les téléconférences d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="2f587-158">Confirms that the A/V Edge servers are able to accept connections for peer-to-peer calls and conference calls.</span></span></p></td>
<td><p><span data-ttu-id="2f587-159">Non défini par défaut</span><span class="sxs-lookup"><span data-stu-id="2f587-159">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f587-160">Test-CsDataConference (DataConference)</span><span class="sxs-lookup"><span data-stu-id="2f587-160">Test-CsDataConference (DataConference)</span></span></p></td>
<td><p><span data-ttu-id="2f587-161">Confirme que les utilisateurs peuvent participer à une conférence de collaboration de données, une réunion en ligne qui comprend des activités telles que des tableaux blancs et des sondages.</span><span class="sxs-lookup"><span data-stu-id="2f587-161">Confirms that users can participate in a data collaboration conference, an online meeting that includes activities such as whiteboards and polls.</span></span></p></td>
<td><p><span data-ttu-id="2f587-162">Non défini par défaut</span><span class="sxs-lookup"><span data-stu-id="2f587-162">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f587-163">Test-CsExumConnectivity (ExumConnectivity)</span><span class="sxs-lookup"><span data-stu-id="2f587-163">Test-CsExumConnectivity (ExumConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="2f587-164">Confirme qu’un utilisateur peut se connecter à la messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="2f587-164">Confirms that a user can connect to Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="2f587-165">Non défini par défaut</span><span class="sxs-lookup"><span data-stu-id="2f587-165">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f587-166">Test-CsGroupIM (GroupIM)</span><span class="sxs-lookup"><span data-stu-id="2f587-166">Test-CsGroupIM (GroupIM)</span></span></p></td>
<td><p><span data-ttu-id="2f587-167">Confirme que les utilisateurs peuvent envoyer des messages instantanés dans des conférences et participer à des conversations par messagerie instantanée comptant trois personnes ou plus.</span><span class="sxs-lookup"><span data-stu-id="2f587-167">Confirms that users are able to send instant messages in conferences and participate in instant message conversations with three or more people.</span></span></p></td>
<td><p><span data-ttu-id="2f587-168">Par défaut</span><span class="sxs-lookup"><span data-stu-id="2f587-168">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f587-169">Test-CsGroupIM – TestJoinLauncher (JoinLauncher)</span><span class="sxs-lookup"><span data-stu-id="2f587-169">Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</span></span></p></td>
<td><p><span data-ttu-id="2f587-170">Confirme que les utilisateurs peuvent créer des réunions planifiées et y participer via un lien d’adresse web.</span><span class="sxs-lookup"><span data-stu-id="2f587-170">Confirms that users are able to create and join scheduled meetings via a web address link.</span></span></p></td>
<td><p><span data-ttu-id="2f587-171">Non défini par défaut</span><span class="sxs-lookup"><span data-stu-id="2f587-171">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f587-172">Test-CsMCXP2PIM (MCXP2PIM)</span><span class="sxs-lookup"><span data-stu-id="2f587-172">Test-CsMCXP2PIM (MCXP2PIM)</span></span></p></td>
<td><p><span data-ttu-id="2f587-173">Confirme que les utilisateurs d’appareil mobile peuvent inscrire et envoyer des messages instantanés.</span><span class="sxs-lookup"><span data-stu-id="2f587-173">Confirms that mobile device users are able to register and send instant messages.</span></span></p></td>
<td><p><span data-ttu-id="2f587-174">Non défini par défaut</span><span class="sxs-lookup"><span data-stu-id="2f587-174">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f587-175">Test-Cspersistentchatmessage ne (PersistentChatMessage)</span><span class="sxs-lookup"><span data-stu-id="2f587-175">Test-CsPersistentChatMessage (PersistentChatMessage)</span></span></p></td>
<td><p><span data-ttu-id="2f587-176">Confirme que les utilisateurs peuvent échanger des messages à l’aide du service de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="2f587-176">Confirms that users can exchange messages by using the Persistent Chat service.</span></span></p></td>
<td><p><span data-ttu-id="2f587-177">Non défini par défaut</span><span class="sxs-lookup"><span data-stu-id="2f587-177">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f587-178">Test-CsUnifiedContactStore (UnifiedContactStore)</span><span class="sxs-lookup"><span data-stu-id="2f587-178">Test-CsUnifiedContactStore (UnifiedContactStore)</span></span></p></td>
<td><p><span data-ttu-id="2f587-179">Confirme que les contacts d’un utilisateur sont accessibles via le magasin de contacts unifié.</span><span class="sxs-lookup"><span data-stu-id="2f587-179">Confirms that a user's contacts can be accessed through the unified contact store.</span></span> <span data-ttu-id="2f587-180">Le magasin de contacts unifié offre aux utilisateurs la possibilité de maintenir un ensemble unique de contacts accessibles via Lync 2013, Outlook et/ou Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="2f587-180">The unified contact store provides a way for users to maintain a single set of contacts that can be accessed by using Lync 2013, Outlook, and/or Outlook Web Access.</span></span></p></td>
<td><p><span data-ttu-id="2f587-181">Non défini par défaut</span><span class="sxs-lookup"><span data-stu-id="2f587-181">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f587-182">Test-CsXmppIM (XmppIM)</span><span class="sxs-lookup"><span data-stu-id="2f587-182">Test-CsXmppIM (XmppIM)</span></span></p></td>
<td><p><span data-ttu-id="2f587-183">Confirme qu’un message instantané peut être envoyé via la passerelle XMPP (Extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="2f587-183">Confirms that an instant message can be sent across the XMPP (Extensible Messaging and Presence Protocol) gateway.</span></span></p></td>
<td><p><span data-ttu-id="2f587-184">Non défini par défaut</span><span class="sxs-lookup"><span data-stu-id="2f587-184">Non-default</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2f587-185">Vous n’avez pas besoin d’installer les nœuds observateur afin d’utiliser System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="2f587-185">You do not need to install watcher nodes in order to use System Center Operations Manager.</span></span> <span data-ttu-id="2f587-186">Si vous n’installez pas ces nœuds, vous pouvez toujours obtenir des alertes en temps réel à partir des composants Lync Server 2013 lorsqu’un problème se produit.</span><span class="sxs-lookup"><span data-stu-id="2f587-186">If you do not install these nodes, you can still get real-time alerts from Lync Server 2013 components when an issue occurs.</span></span> <span data-ttu-id="2f587-187">(Le pack d’administration des composants et des utilisateurs n’utilise pas de nœuds observateur.) Toutefois, les nœuds observateurs sont requis si vous souhaitez surveiller des scénarios de bout en bout à l’aide du pack d’administration actif.</span><span class="sxs-lookup"><span data-stu-id="2f587-187">(The Component and User Management Pack does not use watcher nodes.) However, watcher nodes are required if you want to monitor end-to-end scenarios by using the Active Monitoring Management pack.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2f587-188">Les administrateurs peuvent également exécuter des transactions synthétiques manuellement, et ce sans avoir besoin d’utiliser ou d’installer Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="2f587-188">Administrators can also run synthetic transactions manually, without needing to use, or install, Operations Manager.</span></span> <span data-ttu-id="2f587-189">Pour plus d’informations sur les différentes cmdlets test-CS, voir l' <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">index des applets de commande Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2f587-189">For details about the various Test-Cs cmdlets, see the <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 cmdlets index</A>.</span></span>



</div>

<span data-ttu-id="2f587-190">En fonction de la taille de votre déploiement, les transactions synthétiques peuvent utiliser une grande quantité de mémoire d’ordinateur et de temps processeur.</span><span class="sxs-lookup"><span data-stu-id="2f587-190">Depending on the size of your deployment, synthetic transactions may use a large amount of computer memory and processor time.</span></span> <span data-ttu-id="2f587-191">Pour cette raison, nous vous recommandons d’utiliser un ordinateur dédié comme nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="2f587-191">For this reason, we recommend that you use a dedicated computer as a watcher node.</span></span> <span data-ttu-id="2f587-192">Par exemple, vous ne devez pas configurer un serveur frontal pour qu’il serve de nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="2f587-192">For example, you should not configure a Front End Server to act as a watcher node.</span></span> <span data-ttu-id="2f587-193">Les nœuds observateurs doivent respecter les spécifications matérielles suivantes :</span><span class="sxs-lookup"><span data-stu-id="2f587-193">Watcher nodes should meet the following hardware specifications:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2f587-194">Un nœud d’observateur Microsoft Lync Server 2010 hérité ne peut pas être colocalisé sur le même ordinateur avec un nœud observateur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2f587-194">A legacy Microsoft Lync Server 2010 watcher node cannot be collocated on the same machine with a Lync Server 2013 watcher node.</span></span> <span data-ttu-id="2f587-195">Cela est dû au fait que les fichiers système principaux de Lync Server 2010 et Lync Server 2013 ne peuvent pas être installés sur le même ordinateur.</span><span class="sxs-lookup"><span data-stu-id="2f587-195">This is because the core system files for Lync Server 2010 and Lync Server 2013 cannot be installed on the same computer.</span></span><BR><span data-ttu-id="2f587-196">Toutefois, les nœuds observateurs Lync Server 2013 peuvent surveiller simultanément Lync Server 2013 et Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2f587-196">However, Lync Server 2013 watcher nodes can simultaneously monitor both Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="2f587-197">Les transactions synthétiques par défaut sont prises en charge sur les deux versions du produit.</span><span class="sxs-lookup"><span data-stu-id="2f587-197">The Default synthetic transactions are supported on both product versions.</span></span>



</div>

<span data-ttu-id="2f587-198">Les nœuds observateur Lync Server 2013 peuvent être déployés à l’intérieur ou à l’extérieur d’une entreprise pour vérifier les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="2f587-198">Lync Server 2013 watcher nodes may be deployed inside or outside of an enterprise to help verify:</span></span>

  - <span></span>  
    <span data-ttu-id="2f587-199">Connectivité aux pools pour les utilisateurs au sein de l’entreprise</span><span class="sxs-lookup"><span data-stu-id="2f587-199">Connectivity to pools for users inside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="2f587-200">Connectivité par le biais des réseaux de périmètre pour les utilisateurs distants qui travaillent à l’extérieur de l’entreprise</span><span class="sxs-lookup"><span data-stu-id="2f587-200">Connectivity through perimeter networks for remote users who work outside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="2f587-201">Connectivité aux Branch Office Appliances</span><span class="sxs-lookup"><span data-stu-id="2f587-201">Connectivity to branch office appliances.</span></span>

  - <span></span>  
    <span data-ttu-id="2f587-202">Connectivité à Lync Server 2010 au sein de l’entreprise et via les réseaux de périmètre.</span><span class="sxs-lookup"><span data-stu-id="2f587-202">Connectivity to Lync Server 2010 inside the enterprise and through perimeter networks.</span></span>

<span data-ttu-id="2f587-203">Différentes options d’authentification sont disponibles pour l’intérieur et l’extérieur de l’entreprise afin de simplifier l’administration.</span><span class="sxs-lookup"><span data-stu-id="2f587-203">Different authentication options are available for inside and outside of the enterprise to help simplify administration.</span></span> <span data-ttu-id="2f587-204">Pour plus d’informations, reportez-vous [à la rubrique Configuration d’un nœud observateur pour exécuter des transactions synthétiques dans Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="2f587-204">For details, see [Configuring a watcher node to run synthetic transactions in Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).</span></span>

<span data-ttu-id="2f587-205">Pour configurer un ordinateur pour qu’il serve de nœud observateur, vous devez effectuer les étapes suivantes après avoir installé System Center Operations Manager et importé les packs d’administration Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2f587-205">To configure a computer to act as a watcher node, you must complete the following steps after you have installed System Center Operations Manager and imported the Lync Server 2013 management packs.</span></span>

<span data-ttu-id="2f587-206">Avant d’installer les fichiers principaux de Lync Server 2013 et les fichiers de l’agent System Center, vous devez également vous assurer que l’ordinateur du nœud observateur remplit toutes les conditions préalables à l’installation de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2f587-206">Before you install the Lync Server 2013 core files and the System Center agent files, you should also make sure that the watcher node computer meets all the prerequisites for installing Lync Server 2013.</span></span> <span data-ttu-id="2f587-207">Par ailleurs, les éléments suivants doivent être installés sur l’ordinateur du nœud observateur :</span><span class="sxs-lookup"><span data-stu-id="2f587-207">In addition, the watcher node computer should also have the following items installed:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f587-208">Composant matériel</span><span class="sxs-lookup"><span data-stu-id="2f587-208">Hardware component</span></span></th>
<th><span data-ttu-id="2f587-209">Spécification minimale</span><span class="sxs-lookup"><span data-stu-id="2f587-209">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f587-210">UC</span><span class="sxs-lookup"><span data-stu-id="2f587-210">CPU</span></span></p></td>
<td><p><span data-ttu-id="2f587-211">Un des processeurs suivants :</span><span class="sxs-lookup"><span data-stu-id="2f587-211">One of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2f587-212">processeur 64 bits, quadruple cœur, 2,33 GHz ou supérieur</span><span class="sxs-lookup"><span data-stu-id="2f587-212">64-bit processor, quad-core, 2.33 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="2f587-213">processeur double cœur 64 bits, 2 cœurs, 2,33 GHz ou supérieur</span><span class="sxs-lookup"><span data-stu-id="2f587-213">64-bit 2-way processor, dual-core, 2.33 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f587-214">Mémoire</span><span class="sxs-lookup"><span data-stu-id="2f587-214">Memory</span></span></p></td>
<td><p><span data-ttu-id="2f587-215">8 Go</span><span class="sxs-lookup"><span data-stu-id="2f587-215">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f587-216">Système d’exploitation réseau</span><span class="sxs-lookup"><span data-stu-id="2f587-216">Network operating system</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="2f587-217">1 carte réseau 1 Gbits/s</span><span class="sxs-lookup"><span data-stu-id="2f587-217">1 network adapter 1 Gbps</span></span></p></li>
<li><p><span data-ttu-id="2f587-218">Windows Server 2008 R2, Windows Server 2012 ou</span><span class="sxs-lookup"><span data-stu-id="2f587-218">Windows Server 2008 R2, Windows Server 2012, or</span></span></p>
<p><span data-ttu-id="2f587-219">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="2f587-219">Windows Server 2012 R2</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


  - <span data-ttu-id="2f587-220">Version complète du .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="2f587-220">The full version of .NET Framework 4.5.</span></span>

  - <span data-ttu-id="2f587-221">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="2f587-221">Windows Identity Foundation.</span></span>

  - <span data-ttu-id="2f587-222">Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="2f587-222">Windows PowerShell 3.0.</span></span>

<span data-ttu-id="2f587-223">Dès que toutes ces conditions préalables sont remplies, vous pouvez configurer le nœud observateur en effectuant les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="2f587-223">As soon as all these prerequisites have been met, you can configure the watcher node by:</span></span>

  - <span data-ttu-id="2f587-224">Installation des fichiers principaux de Lync Server 2013 sur l’ordinateur du nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="2f587-224">Installing the Lync Server 2013 core files on the watcher node computer.</span></span>

  - <span data-ttu-id="2f587-225">Installation de l’agent System Center Operations Manager sur l’ordinateur du nœud observateur.</span><span class="sxs-lookup"><span data-stu-id="2f587-225">Installing System Center Operations Manager agent on the watcher node computer.</span></span>

  - <span data-ttu-id="2f587-226">Exécution du fichier exécutable Watchernode.msi</span><span class="sxs-lookup"><span data-stu-id="2f587-226">Running the Watchernode.msi executable file.</span></span>

  - <span data-ttu-id="2f587-227">Utilisation des applets de commande **CsWatcherNodeConfiguration** pour configurer les utilisateurs de test qui seront employés par le nœud observateur</span><span class="sxs-lookup"><span data-stu-id="2f587-227">Using the **CsWatcherNodeConfiguration** cmdlets to configure test users to be employed by the watcher node.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

