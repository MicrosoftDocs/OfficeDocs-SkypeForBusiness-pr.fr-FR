---
title: Processus de déploiement pour l’intégration de la messagerie unifiée locale
description: Processus de déploiement pour l’intégration de la messagerie unifiée locale.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48183664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c1b8f528edb970893198ed06b821535a398f09d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569520"
---
# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="b9ee9-103">Processus de déploiement pour l’intégration de la messagerie unifiée locale et de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9ee9-103">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9ee9-104">_**Dernière modification de la rubrique :** 2012-12-17_</span><span class="sxs-lookup"><span data-stu-id="b9ee9-104">_**Topic Last Modified:** 2012-12-17_</span></span>

<span data-ttu-id="b9ee9-105">Si vous souhaitez intégrer la messagerie unifiée Exchange avec Lync Server 2013, vous devez effectuer les tâches décrites dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-105">If you want to integrate Exchange Unified Messaging (UM) with Lync Server 2013, you must perform the tasks described in this topic.</span></span> <span data-ttu-id="b9ee9-106">Veillez également à consulter les meilleures pratiques de planification et de déploiement décrites dans la rubrique [recommandations pour l’intégration de la messagerie unifiée locale et Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="b9ee9-106">Also be sure that you review the planning and deployment best practices described in [Guidelines for integrating on-premises Unified Messaging and Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md).</span></span> <span data-ttu-id="b9ee9-107">Cette rubrique suppose que vous avez déployé Lync Server 2013 avec un serveur de médiation colocalisé et que vous avez activé les utilisateurs pour Lync Server 2013, mais pas nécessairement que vous ayez effectué toutes les étapes de déploiement et de configuration pour activer voix entreprise, comme décrit dans [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-107">This topic assumes that you have deployed Lync Server 2013 with a collocated Mediation Server and that you have enabled users for Lync Server 2013, but not necessarily that you have performed all deployment and configuration steps to enable Enterprise Voice, as described in [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="unified-messaging-integration-process"></a><span data-ttu-id="b9ee9-108">Processus d’intégration de la messagerie unifiée</span><span class="sxs-lookup"><span data-stu-id="b9ee9-108">Unified Messaging Integration Process</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="b9ee9-109">Il est important de se concerter avec les administrateurs Exchange de votre organisation pour confirmer les tâches que chacun de vous effectuera afin de garantir une intégration sans problème.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-109">It is important that you coordinate with your organization’s Exchange administrators to confirm the tasks that each of you will perform to help ensure a smooth, successful integration.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b9ee9-110">Phase</span><span class="sxs-lookup"><span data-stu-id="b9ee9-110">Phase</span></span></th>
<th><span data-ttu-id="b9ee9-111">Étapes</span><span class="sxs-lookup"><span data-stu-id="b9ee9-111">Steps</span></span></th>
<th><span data-ttu-id="b9ee9-112">Groupes et rôles requis</span><span class="sxs-lookup"><span data-stu-id="b9ee9-112">Required groups and roles</span></span></th>
<th><span data-ttu-id="b9ee9-113">Documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="b9ee9-113">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9ee9-114">Déployez l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="b9ee9-114">Deploy one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b9ee9-115">Microsoft Exchange Server 2007 Service Pack 1 (SP2) ou Service Pack le plus récent</span><span class="sxs-lookup"><span data-stu-id="b9ee9-115">Microsoft Exchange Server 2007 Service Pack 1 (SP2) or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="b9ee9-116">Microsoft Exchange Server 2010 ou Service Pack le plus récent</span><span class="sxs-lookup"><span data-stu-id="b9ee9-116">Microsoft Exchange Server 2010 or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="b9ee9-117">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9ee9-117">Microsoft Exchange Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="b9ee9-118">Si vous utilisez Microsoft Exchange Server 2013, installez les rôles Exchange Server suivants dans la même forêt ou dans une autre forêt que Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="b9ee9-118">If you are using Microsoft Exchange Server 2013, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="b9ee9-119">Accès client</span><span class="sxs-lookup"><span data-stu-id="b9ee9-119">Client Access</span></span></p></li>
<li><p><span data-ttu-id="b9ee9-120">Boîte aux lettres</span><span class="sxs-lookup"><span data-stu-id="b9ee9-120">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="b9ee9-121">Si Microsoft Exchange Server 2013 et la messagerie unifiée Exchange sont installés dans des forêts différentes, configurez chaque forêt Exchange pour qu’elle approuve la forêt Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-121">If Microsoft Exchange Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p>
<p><span data-ttu-id="b9ee9-122">Si vous utilisez Exchange 2010, installez les rôles Exchange Server suivants dans la même forêt ou dans une autre forêt que Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="b9ee9-122">If you are using Exchange 2010, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="b9ee9-123">Messagerie unifiée</span><span class="sxs-lookup"><span data-stu-id="b9ee9-123">Unified Messaging</span></span></p></li>
<li><p><span data-ttu-id="b9ee9-124">Transport Hub</span><span class="sxs-lookup"><span data-stu-id="b9ee9-124">Hub Transport</span></span></p></li>
<li><p><span data-ttu-id="b9ee9-125">Accès client</span><span class="sxs-lookup"><span data-stu-id="b9ee9-125">Client Access</span></span></p></li>
<li><p><span data-ttu-id="b9ee9-126">Boîte aux lettres</span><span class="sxs-lookup"><span data-stu-id="b9ee9-126">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="b9ee9-127">Si Lync Server 2013 et la messagerie unifiée Exchange sont installés dans des forêts différentes, configurez chaque forêt Exchange pour qu’elle approuve la forêt Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-127">If Lync Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p></td>
<td><p><span data-ttu-id="b9ee9-128">Administrateurs Enterprise (s’il s’agit du premier serveur Exchange Server de l’organisation)</span><span class="sxs-lookup"><span data-stu-id="b9ee9-128">Enterprise administrators (if this is the first Exchange Server in the organization)</span></span></p>
<p><span data-ttu-id="b9ee9-129">- OU -</span><span class="sxs-lookup"><span data-stu-id="b9ee9-129">-OR-</span></span></p>
<p><span data-ttu-id="b9ee9-130">Administrateur d’organisation Exchange (s’il ne s’agit pas du premier serveur Exchange Server de l’organisation)</span><span class="sxs-lookup"><span data-stu-id="b9ee9-130">Exchange Organization administrator (if this is not the first Exchange Server in the organization)</span></span></p></td>
<td><p><span data-ttu-id="b9ee9-131">Voir la documentation correspondant à votre serveur Exchange Server :</span><span class="sxs-lookup"><span data-stu-id="b9ee9-131">See the appropriate documentation for your version of Exchange Server:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b9ee9-132">Documentation de déploiement d’Exchange Server 2007 à l’adresse <a href="https://go.microsoft.com/fwlink/p/?linkid=268694">https://go.microsoft.com/fwlink/p/?LinkId=268694</a> .</span><span class="sxs-lookup"><span data-stu-id="b9ee9-132">Exchange Server 2007 deployment documentation at <a href="https://go.microsoft.com/fwlink/p/?linkid=268694">https://go.microsoft.com/fwlink/p/?LinkId=268694</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b9ee9-133">Exchange Server 2010 ou la documentation de déploiement du Service Pack la plus récente à l’adresse <a href="https://go.microsoft.com/fwlink/p/?linkid=268695">https://go.microsoft.com/fwlink/p/?LinkId=268695</a> .</span><span class="sxs-lookup"><span data-stu-id="b9ee9-133">Exchange Server 2010 or latest service pack deployment documentation at <a href="https://go.microsoft.com/fwlink/p/?linkid=268695">https://go.microsoft.com/fwlink/p/?LinkId=268695</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="b9ee9-134">Planification et déploiement de Microsoft Exchange Server 2013 à l’adresse <a href="https://go.microsoft.com/fwlink/p/?linkid=266569">https://go.microsoft.com/fwlink/p/?LinkId=266569</a> .</span><span class="sxs-lookup"><span data-stu-id="b9ee9-134">Microsoft Exchange Server 2013 Planning and Deployment at <a href="https://go.microsoft.com/fwlink/p/?linkid=266569">https://go.microsoft.com/fwlink/p/?LinkId=266569</a>.</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9ee9-135">Installez les certificats.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-135">Install certificates.</span></span></p></td>
<td><p><span data-ttu-id="b9ee9-136">Téléchargez et installez des certificats pour chaque serveur de messagerie unifiée Exchange à partir d’une autorité de certification racine de confiance.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-136">Download and install certificates for each Exchange UM server from a trusted root certificate authority (CA).</span></span> <span data-ttu-id="b9ee9-137">Les certificats sont requis pour la sécurité MTLS (Mutual Transport Level Security) entre les serveurs exécutant la messagerie unifiée Exchange et Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-137">The certificates are required for mutual Transport Level Security (MTLS) between the servers running Exchange UM and Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="b9ee9-138">Administrateurs</span><span class="sxs-lookup"><span data-stu-id="b9ee9-138">Administrators</span></span></p></td>
<td><p><span data-ttu-id="b9ee9-139"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configurer des certificats sur le serveur exécutant la messagerie unifiée Microsoft Exchange Server</a></span><span class="sxs-lookup"><span data-stu-id="b9ee9-139"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9ee9-140">Créez et configurez un nouveau plan de numérotation SIP de messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-140">Create and configure a new Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="b9ee9-141">Sur le serveur de messagerie unifiée Exchange, créez un plan de numérotation SIP basé sur les exigences spécifiques de votre organisation en matière de déploiement.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-141">On the Exchange UM server, create a SIP dial plan based on your organization’s specific deployment requirements.</span></span></p></td>
<td><p><span data-ttu-id="b9ee9-142">Administrateur d’organisation Exchange</span><span class="sxs-lookup"><span data-stu-id="b9ee9-142">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="b9ee9-143">Pour Exchange 2007 SP1 ou le Service Pack le plus récent, consultez &quot; la rubrique How to Create a Unified Messaging SIP URI SIP dial plan &quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268632">https://go.microsoft.com/fwlink/p/?linkId=268632</a> .</span><span class="sxs-lookup"><span data-stu-id="b9ee9-143">For Exchange 2007 SP1 or latest service pack, see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268632">https://go.microsoft.com/fwlink/p/?linkId=268632</a>.</span></span></p>
<p><span data-ttu-id="b9ee9-144">Pour Exchange 2010 ou le Service Pack le plus récent, consultez &quot; la rubrique créer un plan de numérotation de messagerie unifiée &quot; à l’adresse <a href="https://go.microsoft.com/fwlink/p/?linkid=268674">https://go.microsoft.com/fwlink/p/?linkId=268674</a> .</span><span class="sxs-lookup"><span data-stu-id="b9ee9-144">For Exchange 2010 or latest service pack, see &quot;Create a UM Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268674">https://go.microsoft.com/fwlink/p/?linkId=268674</a>.</span></span></p>
<p><span data-ttu-id="b9ee9-145">Pour Exchange 2013, consultez la rubrique Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> .</span><span class="sxs-lookup"><span data-stu-id="b9ee9-145">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9ee9-146">Configurez les paramètres de sécurité pour le plan de numérotation SIP de messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-146">Configure security settings for the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="b9ee9-147">Pour chiffrer le trafic voix entreprise, configurez les paramètres de sécurité du plan de numérotation SIP de messagerie unifiée Exchange en mode <strong>sécurisé SIP</strong> ou <strong>sécurisé</strong>.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-147">To encrypt Enterprise Voice traffic, configure the security settings on the Exchange UM SIP dial plan as <strong>SIP Secured</strong> or <strong>Secured</strong>.</span></span> <span data-ttu-id="b9ee9-148">Cette étape est particulièrement importante si vous avez déployé ou si vous envisagez de déployer des appareils Lync Phone Edition dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-148">This is an especially important step if you have deployed or plan to deploy Lync Phone Edition devices in your environment.</span></span> <span data-ttu-id="b9ee9-149">Pour que les appareils Lync Phone Edition fonctionnent dans un environnement avec l’intégration de la messagerie unifiée Exchange, les paramètres de chiffrement de Lync Server doivent s’aligner sur les paramètres de sécurité du plan de numérotation de messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-149">For Lync Phone Edition devices to function in an environment with Exchange UM integration, Lync Server encryption settings must align with the Exchange UM dial plan security settings.</span></span> <span data-ttu-id="b9ee9-150">Pour plus d’informations, voir la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-150">For details, refer to the Deployment documentation.</span></span></p></td>
<td><p><span data-ttu-id="b9ee9-151">Administrateur d’organisation Exchange</span><span class="sxs-lookup"><span data-stu-id="b9ee9-151">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="b9ee9-152"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configuration de la messagerie unifiée sur Microsoft Exchange pour Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b9ee9-152"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="b9ee9-153">Pour Exchange 2007 SP1 ou le Service Pack le plus récent, voir également :</span><span class="sxs-lookup"><span data-stu-id="b9ee9-153">For Exchange 2007 SP1 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="b9ee9-154">&quot;Comment configurer la sécurité sur un plan de numérotation de messagerie unifiée &quot; à l’adresse <a href="https://go.microsoft.com/fwlink/p/?linkid=268696">https://go.microsoft.com/fwlink/p/?LinkId=268696</a> .</span><span class="sxs-lookup"><span data-stu-id="b9ee9-154">&quot;How to Configure Security on a Unified Messaging Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268696">https://go.microsoft.com/fwlink/p/?LinkId=268696</a>.</span></span></p>
<p><span data-ttu-id="b9ee9-155">Pour Exchange 2010 ou Service Pack le plus récent, voir également :</span><span class="sxs-lookup"><span data-stu-id="b9ee9-155">For Exchange 2010 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="b9ee9-156">&quot;Configurez la sécurité VoIP sur un plan de numérotation de messagerie unifiée &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268697">https://go.microsoft.com/fwlink/p/?LinkId=268697</a> .</span><span class="sxs-lookup"><span data-stu-id="b9ee9-156">&quot;Configure VoIP Security on a UM Dial Plan&quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268697">https://go.microsoft.com/fwlink/p/?LinkId=268697</a>.</span></span></p>
<p><span data-ttu-id="b9ee9-157">Pour Exchange 2013, consultez la rubrique Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> .</span><span class="sxs-lookup"><span data-stu-id="b9ee9-157">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9ee9-158">Ajoutez des serveurs de messagerie unifiée au plan de numérotation SIP de messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-158">Add Unified Messaging servers to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="b9ee9-159">Pour qu’un serveur de messagerie unifiée récemment installé puisse répondre aux appels entrants et les traiter, vous devez ajouter le serveur de messagerie unifiée au plan de numérotation de la messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-159">To enable a newly installed Unified Messaging server to answer and process incoming calls, you must add the Unified Messaging server to a UM dial plan.</span></span> <span data-ttu-id="b9ee9-160">Dans ce cas, ajoutez le serveur au plan de numérotation SIP de messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-160">In this case, add the server to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="b9ee9-161">Administrateurs</span><span class="sxs-lookup"><span data-stu-id="b9ee9-161">Administrators</span></span></p>
<p><span data-ttu-id="b9ee9-162">Administrateurs Exchange Server</span><span class="sxs-lookup"><span data-stu-id="b9ee9-162">Exchange Server administrators</span></span></p></td>
<td><p><span data-ttu-id="b9ee9-163">Pour Exchange 2007 SP1 ou le Service Pack le plus récent, consultez &quot; la rubrique ajouter un serveur de messagerie unifiée à un plan de numérotation &quot; à l’adresse <a href="https://go.microsoft.com/fwlink/p/?linkid=268681">https://go.microsoft.com/fwlink/p/?linkId=268681</a> .</span><span class="sxs-lookup"><span data-stu-id="b9ee9-163">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add Unified Messaging Server to a Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268681">https://go.microsoft.com/fwlink/p/?linkId=268681</a>.</span></span></p>
<p><span data-ttu-id="b9ee9-164">Pour Exchange 2010 ou le Service Pack le plus récent, voir &quot; afficher ou configurer les propriétés d’un serveur de messagerie unifiée &quot; à l’adresse <a href="https://go.microsoft.com/fwlink/p/?linkid=268682">https://go.microsoft.com/fwlink/p/?linkId=268682</a> .</span><span class="sxs-lookup"><span data-stu-id="b9ee9-164">For Exchange 2010 or latest service pack, see &quot;View or Configure the Properties of a UM Server&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268682">https://go.microsoft.com/fwlink/p/?linkId=268682</a>.</span></span></p>
<p><span data-ttu-id="b9ee9-165">Pour Exchange 2013, consultez la rubrique Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> .</span><span class="sxs-lookup"><span data-stu-id="b9ee9-165">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9ee9-166">Attribuez des adresses SIP aux boîtes aux lettres.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-166">Configure mailboxes with SIP addresses.</span></span></p></td>
<td><p><span data-ttu-id="b9ee9-167">Attribuer des adresses SIP aux boîtes aux lettres des utilisateurs voix entreprise qui utiliseront les fonctionnalités de messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-167">Assign SIP addresses to the mailboxes of Enterprise Voice users who will be using Exchange UM features.</span></span></p></td>
<td><p><span data-ttu-id="b9ee9-168">Administrateur Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9ee9-168">Lync Server 2013 administrator</span></span></p>
<p><span data-ttu-id="b9ee9-169">Administrateur de destinataires Exchange</span><span class="sxs-lookup"><span data-stu-id="b9ee9-169">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="b9ee9-170">Pour Exchange 2007 SP1 ou le Service Pack le plus récent, consultez &quot; la rubrique Procédure d’ajout, de suppression ou de modification d’une adresse SIP pour un utilisateur UM-Enabled à l’adresse &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268698">https://go.microsoft.com/fwlink/p/?LinkId=268698</a> .</span><span class="sxs-lookup"><span data-stu-id="b9ee9-170">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add, Remove, or Modify a SIP Address for a UM-Enabled User&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268698">https://go.microsoft.com/fwlink/p/?LinkId=268698</a>.</span></span></p>
<p><span data-ttu-id="b9ee9-171">Pour Exchange 2010 ou le Service Pack le plus récent, consultez la rubrique &quot; modifier une adresse SIP pour un utilisateur UM-Enabled à l’adresse &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268699">https://go.microsoft.com/fwlink/p/?LinkId=268699</a> .</span><span class="sxs-lookup"><span data-stu-id="b9ee9-171">For Exchange 2010 or latest service pack, see &quot;Modify a SIP Address for a UM-Enabled User&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268699">https://go.microsoft.com/fwlink/p/?LinkId=268699</a>.</span></span></p>
<p><span data-ttu-id="b9ee9-172">Pour Exchange 2013, consultez la rubrique Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> .</span><span class="sxs-lookup"><span data-stu-id="b9ee9-172">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9ee9-173">Exécutez le script exchucutil.ps1.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-173">Run the exchucutil.ps1 script.</span></span></p></td>
<td><p><span data-ttu-id="b9ee9-174">Sur le serveur exécutant les services de messagerie unifiée Exchange, ouvrez l’environnement de commande Exchange Management Shell et exécutez le script exchucutil.ps1, qui effectue les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="b9ee9-174">On the server running Exchange UM services, open the Exchange Management Shell and run the exchucutil.ps1 script, which does the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b9ee9-175">Autorise Lync Server 2013 à lire les objets des services de domaine Active Directory de messagerie unifiée Exchange, en particulier les plans de numérotation SIP créés lors de la tâche précédente.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-175">Grants Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects, specifically, the SIP dial plans created in the previous task.</span></span></p></li>
<li><p><span data-ttu-id="b9ee9-176">Crée un objet passerelle IP de messagerie unifiée dans Active Directory pour chaque pool Lync Server 2013 Enterprise Edition ou serveur Standard Edition qui héberge les utilisateurs activés pour voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-176">Creates a Unified Messaging IP gateway object in Active Directory for each Lync Server 2013 Enterprise Edition pool or Standard Edition server that hosts users who are enabled for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="b9ee9-177">Crée un groupement de postes de messagerie unifiée Exchange pour chaque passerelle.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-177">Creates an Exchange UM hunt group for each gateway.</span></span> <span data-ttu-id="b9ee9-178">L’identificateur pilote du groupe de recherche est le nom du plan de numérotation associé à la passerelle correspondante.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-178">The hunt group pilot identifier will be the name of the dial plan that is associated with the corresponding gateway.</span></span> <span data-ttu-id="b9ee9-179">S’il existe plusieurs plans de numérotation, ces identificateurs doivent être mappés un à un.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-179">These need to be mapped 1:1 if there is more than one dial plan.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="b9ee9-180">Administrateur d’organisation Exchange</span><span class="sxs-lookup"><span data-stu-id="b9ee9-180">Exchange Organization administrator</span></span></p>
<p><span data-ttu-id="b9ee9-181">Administrateur de destinataires Exchange</span><span class="sxs-lookup"><span data-stu-id="b9ee9-181">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="b9ee9-182"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configuration de la messagerie unifiée sur Microsoft Exchange pour Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b9ee9-182"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9ee9-183">Configurez les plans de numérotation Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-183">Configure Lync Server 2013 dial plans.</span></span></p></td>
<td><p><span data-ttu-id="b9ee9-184">Si vous intégrez Exchange 2007 SP1 ou le Service Pack le plus récent, ou Exchange 2010, créez un nouveau plan de numérotation voix entreprise dont le nom correspond au nom de domaine complet (FQDN) du plan de numérotation de messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-184">If you are integrating with Exchange 2007 SP1 or latest service pack, or Exchange 2010, create a new Enterprise Voice dial plan with a name that matches the Exchange UM dial plan fully qualified domain name (FQDN).</span></span></p>



> [!NOTE]
> <span data-ttu-id="b9ee9-185">Vous devrez effectuer cette opération pour chaque plan de numérotation de messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-185">You will need to do this for each UM Dial plan.</span></span>


<p><span data-ttu-id="b9ee9-186">Si vous intégrez Exchange 2010 SP1, assurez-vous que des plans de numérotation voix entreprise appropriés au niveau du site ou au niveau du pool ont été configurés.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-186">If you are integrating with Exchange 2010 SP1, ensure that suitable global/site-level or pool-level Enterprise Voice dial plans have been configured.</span></span></p>



> [!NOTE]
> <span data-ttu-id="b9ee9-187">Si vous intégrez avec Exchange 2010 SP1, le plan de numérotation Lync Server et les noms de plan de numérotation SIP de la messagerie unifiée Exchange ne doivent pas nécessairement correspondre.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-187">If you are integrating with Exchange 2010 SP1, the Lync Server dial plan and Exchange UM SIP dial plan names do not need to match.</span></span>

</td>
<td><p><span data-ttu-id="b9ee9-188">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="b9ee9-188">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="b9ee9-189"><a href="lync-server-2013-configuring-dial-plans.md">Configuration des plans de numérotation dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b9ee9-189"><a href="lync-server-2013-configuring-dial-plans.md">Configuring dial plans in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9ee9-190">Exécutez l’outil d’intégration de la messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-190">Run the Exchange UM Integration tool.</span></span></p></td>
<td><p><span data-ttu-id="b9ee9-191">Sur le serveur Lync Server 2013, exécutez <strong>ocsumutil.exe</strong>, qui :</span><span class="sxs-lookup"><span data-stu-id="b9ee9-191">On the Lync Server 2013, run <strong>ocsumutil.exe</strong>, which:</span></span></p>
<ul>
<li><p><span data-ttu-id="b9ee9-192">crée des objets Contact Accès abonné et Standard automatique ;</span><span class="sxs-lookup"><span data-stu-id="b9ee9-192">Creates Subscriber Access and Auto Attendant contact objects.</span></span></p></li>
<li><p><span data-ttu-id="b9ee9-193">Vérifie qu’il existe un plan de numérotation voix entreprise dont le nom correspond au nom de domaine complet du plan de numérotation de messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-193">Validates that there is an Enterprise Voice dial plan with a name that matches the Exchange UM dial plan FQDN.</span></span> <span data-ttu-id="b9ee9-194">Si vous exécutez Exchange 2010 SP1 ou une version ultérieure, les noms de plan de numérotation n’ont pas besoin de correspondre, et vous pouvez ignorer l’avertissement de l’outil à ce sujet.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-194">If you are running Exchange 2010 SP1 or later, the dial plan names do not need to match, and you can ignore the tool’s warning about this.</span></span></p></li>
</ul>
<p><span data-ttu-id="b9ee9-195">Cet outil fonctionne en analysant Active Directory pour les paramètres de messagerie unifiée Exchange et en autorisant l’administrateur Lync Server 2013 à afficher, créer et modifier des objets contact.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-195">This tool works by scanning the Active Directory for Exchange UM settings and allowing the Lync Server 2013 administrator to view, create, and edit contact objects.</span></span></p></td>
<td><p><span data-ttu-id="b9ee9-196">RTCUniversalServerAdmins <em>et</em> RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="b9ee9-196">RTCUniversalServerAdmins <em>and</em> RTCUniversalUserAdmins</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="b9ee9-197">Pour qu’ocsumutil.exe s’exécute correctement, l’utilisateur doit être membre de ces deux groupes.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-197">To run ocsumutil.exe successfully, the user must belong to both of these groups.</span></span>





> [!NOTE]
> <span data-ttu-id="b9ee9-198">Pour créer des objets Contact, l’utilisateur qui exécute ocsumutil.exe doit disposer des autorisations d’accès appropriées à l’unité organisationnelle Active Directory dans laquelle les nouveaux objets de contact sont stockés.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-198">To create Contact objects, the user who runs ocsumutil.exe must have the correct permission to the Active Directory organizational unit (OU) where the new contact objects are stored.</span></span> <span data-ttu-id="b9ee9-199">Cette autorisation peut être accordée en exécutant l’applet de commande <STRONG>Grant-CsOUPermission</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="b9ee9-199">This permission can be granted by running the <STRONG>Grant-CsOUPermission</STRONG> cmdlet.</span></span> <span data-ttu-id="b9ee9-200">Pour plus d’informations, voir la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-200">For details, see the Lync Server Management Shell documentation.</span></span>

</td>
<td><p><span data-ttu-id="b9ee9-201"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configurer Lync Server 2013 pour qu’il fonctionne avec la messagerie unifiée sur Microsoft Exchange Server</a></span><span class="sxs-lookup"><span data-stu-id="b9ee9-201"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9ee9-202">Si nécessaire, procédez à d’autres étapes de configuration de Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-202">If necessary, perform other Enterprise Voice configuration steps.</span></span></p></td>
<td><p><span data-ttu-id="b9ee9-203">Si vous n’avez pas déjà configuré les paramètres Voix Entreprise sur vos serveurs ou pour vos utilisateurs, effectuez une ou plusieurs des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="b9ee9-203">If you have not already configured Enterprise Voice settings on your servers or users, do one or more of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b9ee9-204">Déployer et configurer</span><span class="sxs-lookup"><span data-stu-id="b9ee9-204">Deploy and configure</span></span></p>
<p><span data-ttu-id="b9ee9-205">Passerelles PSTN (réseau téléphonique commuté) et serveurs de médiation</span><span class="sxs-lookup"><span data-stu-id="b9ee9-205">Public switched telephone network (PSTN) gateways and Mediation Servers</span></span></p></li>
<li><p><span data-ttu-id="b9ee9-206">définissez les stratégies de voix, les enregistrements d’utilisation PSTN et les itinéraires d’appels sortants ;</span><span class="sxs-lookup"><span data-stu-id="b9ee9-206">Define voice policies, PSTN usage records, and outbound call routes.</span></span></p></li>
<li><p><span data-ttu-id="b9ee9-207">activez les utilisateurs pour Voix Entreprise ;</span><span class="sxs-lookup"><span data-stu-id="b9ee9-207">Enable users for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="b9ee9-208">configurez éventuellement les plans de numérotation d’utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-208">Optionally, configure specific users with dial plans.</span></span></p></li>
</ul>
<p><span data-ttu-id="b9ee9-209">D’autres étapes de configuration peuvent être nécessaires selon les fonctionnalités Voix Entreprise que vous activez.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-209">Other configuration steps may be required depending on the Enterprise Voice features that you enable.</span></span></p></td>
<td><p><span data-ttu-id="b9ee9-210">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="b9ee9-210">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="b9ee9-211">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="b9ee9-211">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="b9ee9-212">Voir les rubriques des sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="b9ee9-212">See topics in the following sections:</span></span></p>
<ul>
<li><p><span data-ttu-id="b9ee9-213"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configuration des stratégies de voix, des enregistrements d’utilisation RTC et des itinéraires des communications vocales dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b9ee9-213"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="b9ee9-214"><a href="lync-server-2013-deploying-enterprise-voice.md">Déploiement de voix entreprise dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b9ee9-214"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9ee9-215">Activez les utilisateurs voix entreprise pour la messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-215">Enable Enterprise Voice users for Exchange UM.</span></span></p></td>
<td><p><span data-ttu-id="b9ee9-216">Sur le serveur de messagerie UNIFIÉe Exchange, vérifiez qu’une stratégie de boîte aux lettres de messagerie unifiée a été créée et que chaque utilisateur a une attribution unique de numéro de poste, puis activez l’utilisateur pour la messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="b9ee9-216">On the Exchange UM server, ensure that a Unified Messaging mailbox policy has been created and that each user has a unique extension number assignment, and then enable the user for Unified Messaging.</span></span></p></td>
<td><p><span data-ttu-id="b9ee9-217">Administrateur de destinataires Exchange</span><span class="sxs-lookup"><span data-stu-id="b9ee9-217">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="b9ee9-218">Pour Exchange 2007 SP1 ou le Service Pack le plus récent, consultez &quot; la rubrique How to Enable a User for Unified Messaging &quot; à l’adresse <a href="https://go.microsoft.com/fwlink/p/?linkid=268700">https://go.microsoft.com/fwlink/p/?LinkId=268700</a> .</span><span class="sxs-lookup"><span data-stu-id="b9ee9-218">For Exchange 2007 SP1 or latest service pack, see &quot;How to Enable a User for Unified Messaging&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268700">https://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</span></span></p>
<p><span data-ttu-id="b9ee9-219">Pour Exchange 2010 ou le Service Pack le plus récent, voir &quot; activer un utilisateur pour la messagerie unifiée &quot; à l’adresse <a href="https://go.microsoft.com/fwlink/p/?linkid=268701">https://go.microsoft.com/fwlink/p/?LinkId=268701</a> .</span><span class="sxs-lookup"><span data-stu-id="b9ee9-219">For Exchange 2010 or latest service pack, see &quot;Enable a User for Unified Messaging&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268701">https://go.microsoft.com/fwlink/p/?LinkId=268701</a>.</span></span></p>
<p><span data-ttu-id="b9ee9-220">Pour Exchange 2013, consultez la rubrique Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> .</span><span class="sxs-lookup"><span data-stu-id="b9ee9-220">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

