---
title: Processus de déploiement pour l’intégration de la messagerie unifiée locale
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
ms.openlocfilehash: 76a45210fa90e5d2493885e54f07bb922f6d0495
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="71dcb-102">Processus de déploiement pour l’intégration de la messagerie unifiée locale et de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71dcb-102">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71dcb-103">_**Dernière modification de la rubrique :** 2012-12-17_</span><span class="sxs-lookup"><span data-stu-id="71dcb-103">_**Topic Last Modified:** 2012-12-17_</span></span>

<span data-ttu-id="71dcb-104">Si vous souhaitez intégrer la messagerie unifiée Exchange avec Lync Server 2013, vous devez effectuer les tâches décrites dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="71dcb-104">If you want to integrate Exchange Unified Messaging (UM) with Lync Server 2013, you must perform the tasks described in this topic.</span></span> <span data-ttu-id="71dcb-105">Veillez également à consulter les meilleures pratiques en matière de planification et de déploiement décrites dans [recommandations en matière d’intégration de la messagerie unifiée locale et de Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="71dcb-105">Also be sure that you review the planning and deployment best practices described in [Guidelines for integrating on-premises Unified Messaging and Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md).</span></span> <span data-ttu-id="71dcb-106">Cette rubrique part du principe que vous avez déployé Lync Server 2013 avec un serveur de médiation colocalisé et que vous avez activé les utilisateurs pour Lync Server 2013, mais pas nécessairement que vous avez effectué toutes les étapes de déploiement et de configuration pour activer Enterprise Voice, comme décrit dans la rubrique [déploiement d’Enterprise Voice dans Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="71dcb-106">This topic assumes that you have deployed Lync Server 2013 with a collocated Mediation Server and that you have enabled users for Lync Server 2013, but not necessarily that you have performed all deployment and configuration steps to enable Enterprise Voice, as described in [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="unified-messaging-integration-process"></a><span data-ttu-id="71dcb-107">Procédure d’intégration de la messagerie unifiée</span><span class="sxs-lookup"><span data-stu-id="71dcb-107">Unified Messaging Integration Process</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="71dcb-108">Il est important que vous vous mettiez en relation avec les administrateurs Exchange de votre organisation pour valider les tâches que chacun de vous sera amené à effectuer afin que l’intégration se déroule le mieux possible.</span><span class="sxs-lookup"><span data-stu-id="71dcb-108">It is important that you coordinate with your organization’s Exchange administrators to confirm the tasks that each of you will perform to help ensure a smooth, successful integration.</span></span>



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
<th><span data-ttu-id="71dcb-109">Phase</span><span class="sxs-lookup"><span data-stu-id="71dcb-109">Phase</span></span></th>
<th><span data-ttu-id="71dcb-110">Étapes</span><span class="sxs-lookup"><span data-stu-id="71dcb-110">Steps</span></span></th>
<th><span data-ttu-id="71dcb-111">Groupes et rôles requis</span><span class="sxs-lookup"><span data-stu-id="71dcb-111">Required groups and roles</span></span></th>
<th><span data-ttu-id="71dcb-112">Documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="71dcb-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71dcb-113">Déployez l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="71dcb-113">Deploy one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="71dcb-114">Microsoft Exchange Server 2007 Service Pack 1 (SP2) ou le dernier Service Pack</span><span class="sxs-lookup"><span data-stu-id="71dcb-114">Microsoft Exchange Server 2007 Service Pack 1 (SP2) or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="71dcb-115">Microsoft Exchange Server 2010 ou le dernier Service Pack</span><span class="sxs-lookup"><span data-stu-id="71dcb-115">Microsoft Exchange Server 2010 or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="71dcb-116">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="71dcb-116">Microsoft Exchange Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="71dcb-117">Si vous utilisez Microsoft Exchange Server 2013, installez les rôles Exchange Server suivants dans la même forêt ou dans une autre forêt que Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="71dcb-117">If you are using Microsoft Exchange Server 2013, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="71dcb-118">Accès client</span><span class="sxs-lookup"><span data-stu-id="71dcb-118">Client Access</span></span></p></li>
<li><p><span data-ttu-id="71dcb-119">Boîte aux lettres</span><span class="sxs-lookup"><span data-stu-id="71dcb-119">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="71dcb-120">Si Microsoft Exchange Server 2013 et la messagerie unifiée Exchange (UM) sont installés dans différentes forêts, configurez chaque forêt Exchange pour approuver la forêt Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="71dcb-120">If Microsoft Exchange Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p>
<p><span data-ttu-id="71dcb-121">Si vous utilisez Exchange 2010, installez les rôles Exchange Server suivants au sein d’une même forêt ou d’une autre forêt que Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="71dcb-121">If you are using Exchange 2010, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="71dcb-122">Messagerie unifiée</span><span class="sxs-lookup"><span data-stu-id="71dcb-122">Unified Messaging</span></span></p></li>
<li><p><span data-ttu-id="71dcb-123">Transport Hub</span><span class="sxs-lookup"><span data-stu-id="71dcb-123">Hub Transport</span></span></p></li>
<li><p><span data-ttu-id="71dcb-124">Accès client</span><span class="sxs-lookup"><span data-stu-id="71dcb-124">Client Access</span></span></p></li>
<li><p><span data-ttu-id="71dcb-125">Boîte aux lettres</span><span class="sxs-lookup"><span data-stu-id="71dcb-125">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="71dcb-126">Si Lync Server 2013 et la messagerie unifiée Exchange (UM) sont installés dans différentes forêts, configurez chaque forêt Exchange pour approuver la forêt Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="71dcb-126">If Lync Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p></td>
<td><p><span data-ttu-id="71dcb-127">Administrateurs Enterprise (s’il s’agit du premier serveur Exchange Server de l’organisation)</span><span class="sxs-lookup"><span data-stu-id="71dcb-127">Enterprise administrators (if this is the first Exchange Server in the organization)</span></span></p>
<p><span data-ttu-id="71dcb-128">- OU -</span><span class="sxs-lookup"><span data-stu-id="71dcb-128">-OR-</span></span></p>
<p><span data-ttu-id="71dcb-129">Administrateur d’organisation Exchange (s’il ne s’agit pas du premier serveur Exchange Server de l’organisation)</span><span class="sxs-lookup"><span data-stu-id="71dcb-129">Exchange Organization administrator (if this is not the first Exchange Server in the organization)</span></span></p></td>
<td><p><span data-ttu-id="71dcb-130">Reportez-vous à la documentation correspondant à votre serveur Exchange Server :</span><span class="sxs-lookup"><span data-stu-id="71dcb-130">See the appropriate documentation for your version of Exchange Server:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="71dcb-131">Documentation de déploiement d’Exchange Server <a href="http://go.microsoft.com/fwlink/p/?linkid=268694">http://go.microsoft.com/fwlink/p/?LinkId=268694</a>2007 à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="71dcb-131">Exchange Server 2007 deployment documentation at <a href="http://go.microsoft.com/fwlink/p/?linkid=268694">http://go.microsoft.com/fwlink/p/?LinkId=268694</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="71dcb-132">Documentation sur le déploiement d’Exchange Server 2010 ou de <a href="http://go.microsoft.com/fwlink/p/?linkid=268695">http://go.microsoft.com/fwlink/p/?LinkId=268695</a>la dernière version du Service Pack.</span><span class="sxs-lookup"><span data-stu-id="71dcb-132">Exchange Server 2010 or latest service pack deployment documentation at <a href="http://go.microsoft.com/fwlink/p/?linkid=268695">http://go.microsoft.com/fwlink/p/?LinkId=268695</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="71dcb-133">Microsoft Exchange Server 2013 Planning and Deployment at <a href="http://go.microsoft.com/fwlink/p/?linkid=266569">http://go.microsoft.com/fwlink/p/?LinkId=266569</a>.</span><span class="sxs-lookup"><span data-stu-id="71dcb-133">Microsoft Exchange Server 2013 Planning and Deployment at <a href="http://go.microsoft.com/fwlink/p/?linkid=266569">http://go.microsoft.com/fwlink/p/?LinkId=266569</a>.</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71dcb-134">Installez les certificats.</span><span class="sxs-lookup"><span data-stu-id="71dcb-134">Install certificates.</span></span></p></td>
<td><p><span data-ttu-id="71dcb-135">Téléchargez et installez des certificats pour chaque serveur de messagerie unifiée Exchange auprès d’une autorité de certification racine de confiance.</span><span class="sxs-lookup"><span data-stu-id="71dcb-135">Download and install certificates for each Exchange UM server from a trusted root certificate authority (CA).</span></span> <span data-ttu-id="71dcb-136">Les certificats sont requis pour la sécurité de niveau de transport mutuel (MTLS) entre les serveurs exécutant Exchange UM et Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="71dcb-136">The certificates are required for mutual Transport Level Security (MTLS) between the servers running Exchange UM and Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="71dcb-137">Administrateurs</span><span class="sxs-lookup"><span data-stu-id="71dcb-137">Administrators</span></span></p></td>
<td><p><span data-ttu-id="71dcb-138"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configurer des certificats sur le serveur exécutant la messagerie unifiée Microsoft Exchange Server</a></span><span class="sxs-lookup"><span data-stu-id="71dcb-138"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71dcb-139">Créez et configurez un nouveau plan de numérotation SIP Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="71dcb-139">Create and configure a new Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="71dcb-140">Sur le serveur de messagerie unifiée Exchange, créez un plan de numérotation SIP en fonction des exigences de déploiement spécifiques de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="71dcb-140">On the Exchange UM server, create a SIP dial plan based on your organization’s specific deployment requirements.</span></span></p></td>
<td><p><span data-ttu-id="71dcb-141">Administrateur d’organisation Exchange</span><span class="sxs-lookup"><span data-stu-id="71dcb-141">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="71dcb-142">Pour Exchange 2007 SP1 ou le dernier Service Pack, &quot;voir Création d’un plan&quot; de numérotation URI SIP de <a href="http://go.microsoft.com/fwlink/p/?linkid=268632">http://go.microsoft.com/fwlink/p/?linkId=268632</a>messagerie unifiée à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="71dcb-142">For Exchange 2007 SP1 or latest service pack, see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268632">http://go.microsoft.com/fwlink/p/?linkId=268632</a>.</span></span></p>
<p><span data-ttu-id="71dcb-143">Pour Exchange 2010 ou le dernier Service Pack, &quot;voir créer un plan&quot; de numérotation de messagerie unifiée à l’adresse. <a href="http://go.microsoft.com/fwlink/p/?linkid=268674">http://go.microsoft.com/fwlink/p/?linkId=268674</a></span><span class="sxs-lookup"><span data-stu-id="71dcb-143">For Exchange 2010 or latest service pack, see &quot;Create a UM Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268674">http://go.microsoft.com/fwlink/p/?linkId=268674</a>.</span></span></p>
<p><span data-ttu-id="71dcb-144">Pour Exchange 2013, voir la messagerie unifiée à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span><span class="sxs-lookup"><span data-stu-id="71dcb-144">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71dcb-145">Configurer les paramètres de sécurité pour le plan de numérotation SIP de MU Exchange.</span><span class="sxs-lookup"><span data-stu-id="71dcb-145">Configure security settings for the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="71dcb-146">Pour chiffrer le trafic vocal d’une entreprise, configurez les paramètres de sécurité sur le plan de numérotation SIP Exchange UM en protocole <strong>SIP sécurisé</strong> ou <strong>sécurisé</strong>.</span><span class="sxs-lookup"><span data-stu-id="71dcb-146">To encrypt Enterprise Voice traffic, configure the security settings on the Exchange UM SIP dial plan as <strong>SIP Secured</strong> or <strong>Secured</strong>.</span></span> <span data-ttu-id="71dcb-147">Cette étape est particulièrement importante si vous avez déployé ou envisagez de déployer des appareils Lync Phone Edition dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="71dcb-147">This is an especially important step if you have deployed or plan to deploy Lync Phone Edition devices in your environment.</span></span> <span data-ttu-id="71dcb-148">Pour que les appareils Lync Phone Edition fonctionnent dans un environnement avec l’intégration à la messagerie unifiée Exchange, les paramètres de chiffrement de Lync Server doivent être alignés avec les paramètres de sécurité du plan de numérotation de messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="71dcb-148">For Lync Phone Edition devices to function in an environment with Exchange UM integration, Lync Server encryption settings must align with the Exchange UM dial plan security settings.</span></span> <span data-ttu-id="71dcb-149">Pour plus d’informations, reportez-vous à la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="71dcb-149">For details, refer to the Deployment documentation.</span></span></p></td>
<td><p><span data-ttu-id="71dcb-150">Administrateur d’organisation Exchange</span><span class="sxs-lookup"><span data-stu-id="71dcb-150">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="71dcb-151"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurer la messagerie unifiée sur Microsoft Exchange pour Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="71dcb-151"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="71dcb-152">Pour Exchange 2007 SP1 ou le dernier Service Pack, voir également :</span><span class="sxs-lookup"><span data-stu-id="71dcb-152">For Exchange 2007 SP1 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="71dcb-153">&quot;Comment configurer la sécurité sur un plan&quot; de numérotation de <a href="http://go.microsoft.com/fwlink/p/?linkid=268696">http://go.microsoft.com/fwlink/p/?LinkId=268696</a>messagerie unifiée à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="71dcb-153">&quot;How to Configure Security on a Unified Messaging Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268696">http://go.microsoft.com/fwlink/p/?LinkId=268696</a>.</span></span></p>
<p><span data-ttu-id="71dcb-154">Pour Exchange 2010 ou le dernier Service Pack, reportez-vous également à :</span><span class="sxs-lookup"><span data-stu-id="71dcb-154">For Exchange 2010 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="71dcb-155">&quot;Configurer la sécurité VoIP sur un plan&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268697">http://go.microsoft.com/fwlink/p/?LinkId=268697</a>de numérotation de messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="71dcb-155">&quot;Configure VoIP Security on a UM Dial Plan&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268697">http://go.microsoft.com/fwlink/p/?LinkId=268697</a>.</span></span></p>
<p><span data-ttu-id="71dcb-156">Pour Exchange 2013, voir la messagerie unifiée à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span><span class="sxs-lookup"><span data-stu-id="71dcb-156">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71dcb-157">Ajoutez des serveurs de messagerie unifiée au plan de numérotation SIP Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="71dcb-157">Add Unified Messaging servers to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="71dcb-158">Pour qu’un serveur de messagerie unifiée installé récemment puisse répondre aux appels entrants et les traiter, vous devez ajouter le serveur de messagerie unifiée au plan de numérotation de la messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="71dcb-158">To enable a newly installed Unified Messaging server to answer and process incoming calls, you must add the Unified Messaging server to a UM dial plan.</span></span> <span data-ttu-id="71dcb-159">Dans le cas présent, ajoutez le serveur au plan de numérotation SIP Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="71dcb-159">In this case, add the server to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="71dcb-160">Administrateurs</span><span class="sxs-lookup"><span data-stu-id="71dcb-160">Administrators</span></span></p>
<p><span data-ttu-id="71dcb-161">Administrateurs Exchange Server</span><span class="sxs-lookup"><span data-stu-id="71dcb-161">Exchange Server administrators</span></span></p></td>
<td><p><span data-ttu-id="71dcb-162">Pour Exchange 2007 SP1 ou le dernier Service Pack, &quot;voir comment ajouter un serveur de messagerie unifiée à&quot; un <a href="http://go.microsoft.com/fwlink/p/?linkid=268681">http://go.microsoft.com/fwlink/p/?linkId=268681</a>plan de numérotation à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="71dcb-162">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add Unified Messaging Server to a Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268681">http://go.microsoft.com/fwlink/p/?linkId=268681</a>.</span></span></p>
<p><span data-ttu-id="71dcb-163">Pour Exchange 2010 ou le dernier Service Pack, &quot;voir afficher ou configurer les propriétés d’un serveur&quot; de <a href="http://go.microsoft.com/fwlink/p/?linkid=268682">http://go.microsoft.com/fwlink/p/?linkId=268682</a>messagerie unifiée à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="71dcb-163">For Exchange 2010 or latest service pack, see &quot;View or Configure the Properties of a UM Server&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268682">http://go.microsoft.com/fwlink/p/?linkId=268682</a>.</span></span></p>
<p><span data-ttu-id="71dcb-164">Pour Exchange 2013, voir la messagerie unifiée à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span><span class="sxs-lookup"><span data-stu-id="71dcb-164">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71dcb-165">Affectez des adresses SIP aux boîtes aux lettres.</span><span class="sxs-lookup"><span data-stu-id="71dcb-165">Configure mailboxes with SIP addresses.</span></span></p></td>
<td><p><span data-ttu-id="71dcb-166">Attribuez des adresses SIP aux boîtes aux lettres des utilisateurs d’Enterprise Voice qui utiliseront les fonctionnalités de messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="71dcb-166">Assign SIP addresses to the mailboxes of Enterprise Voice users who will be using Exchange UM features.</span></span></p></td>
<td><p><span data-ttu-id="71dcb-167">Administrateur Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71dcb-167">Lync Server 2013 administrator</span></span></p>
<p><span data-ttu-id="71dcb-168">Administrateur de destinataires Exchange</span><span class="sxs-lookup"><span data-stu-id="71dcb-168">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="71dcb-169">Pour Exchange 2007 SP1 ou le dernier Service Pack, &quot;voir comment ajouter, supprimer ou modifier une adresse SIP pour un utilisateur&quot; à <a href="http://go.microsoft.com/fwlink/p/?linkid=268698">http://go.microsoft.com/fwlink/p/?LinkId=268698</a>extension de messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="71dcb-169">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add, Remove, or Modify a SIP Address for a UM-Enabled User&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268698">http://go.microsoft.com/fwlink/p/?LinkId=268698</a>.</span></span></p>
<p><span data-ttu-id="71dcb-170">Pour Exchange 2010 ou le dernier Service Pack, &quot;voir modifier une adresse SIP pour un utilisateur&quot; de MU à <a href="http://go.microsoft.com/fwlink/p/?linkid=268699">http://go.microsoft.com/fwlink/p/?LinkId=268699</a>l’adresse.</span><span class="sxs-lookup"><span data-stu-id="71dcb-170">For Exchange 2010 or latest service pack, see &quot;Modify a SIP Address for a UM-Enabled User&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268699">http://go.microsoft.com/fwlink/p/?LinkId=268699</a>.</span></span></p>
<p><span data-ttu-id="71dcb-171">Pour Exchange 2013, voir la messagerie unifiée à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span><span class="sxs-lookup"><span data-stu-id="71dcb-171">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71dcb-172">Exécutez le script exchucutil.ps1.</span><span class="sxs-lookup"><span data-stu-id="71dcb-172">Run the exchucutil.ps1 script.</span></span></p></td>
<td><p><span data-ttu-id="71dcb-173">Sur le serveur exécutant les services de messagerie unifiée Exchange, ouvrez Exchange Management Shell et exécutez le script exchucutil. ps1, qui effectue les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="71dcb-173">On the server running Exchange UM services, open the Exchange Management Shell and run the exchucutil.ps1 script, which does the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="71dcb-174">Octroie à Lync Server 2013 l’autorisation de lire les objets services de domaine Active Directory UM Exchange, notamment les plans de numérotation SIP créés dans la tâche précédente.</span><span class="sxs-lookup"><span data-stu-id="71dcb-174">Grants Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects, specifically, the SIP dial plans created in the previous task.</span></span></p></li>
<li><p><span data-ttu-id="71dcb-175">Crée un objet passerelle IP de messagerie unifiée dans Active Directory pour chaque pool Lync Server 2013 Enterprise Edition ou Standard Edition Server qui héberge les utilisateurs qui sont activés pour Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="71dcb-175">Creates a Unified Messaging IP gateway object in Active Directory for each Lync Server 2013 Enterprise Edition pool or Standard Edition server that hosts users who are enabled for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="71dcb-176">Crée un groupe de recherche UM Exchange pour chaque passerelle.</span><span class="sxs-lookup"><span data-stu-id="71dcb-176">Creates an Exchange UM hunt group for each gateway.</span></span> <span data-ttu-id="71dcb-177">L’identificateur pilote du groupe de recherche est le nom du plan de numérotation associé à la passerelle correspondante.</span><span class="sxs-lookup"><span data-stu-id="71dcb-177">The hunt group pilot identifier will be the name of the dial plan that is associated with the corresponding gateway.</span></span> <span data-ttu-id="71dcb-178">S’il existe plusieurs plans de numérotation, ces identificateurs doivent être mappés un à un.</span><span class="sxs-lookup"><span data-stu-id="71dcb-178">These need to be mapped 1:1 if there is more than one dial plan.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="71dcb-179">Administrateur d’organisation Exchange</span><span class="sxs-lookup"><span data-stu-id="71dcb-179">Exchange Organization administrator</span></span></p>
<p><span data-ttu-id="71dcb-180">Administrateur de destinataires Exchange</span><span class="sxs-lookup"><span data-stu-id="71dcb-180">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="71dcb-181"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurer la messagerie unifiée sur Microsoft Exchange pour Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="71dcb-181"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71dcb-182">Configurer les plans de numérotation Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="71dcb-182">Configure Lync Server 2013 dial plans.</span></span></p></td>
<td><p><span data-ttu-id="71dcb-183">Si vous intégrez une version d’Exchange 2007 SP1 ou le dernier Service Pack ou Exchange 2010, créez un nouveau plan de numérotation vocale d’entreprise avec un nom qui correspond au nom de domaine complet (FQDN) de votre plan de numérotation de messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="71dcb-183">If you are integrating with Exchange 2007 SP1 or latest service pack, or Exchange 2010, create a new Enterprise Voice dial plan with a name that matches the Exchange UM dial plan fully qualified domain name (FQDN).</span></span></p>



> [!NOTE]
> <span data-ttu-id="71dcb-184">Cette opération devra être effectuée pour chaque plan de numérotation de la messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="71dcb-184">You will need to do this for each UM Dial plan.</span></span>


<p><span data-ttu-id="71dcb-185">S’il s’agit d’une intégration à Exchange 2010 SP1, assurez-vous que les plans de numérotation vocale globale, de niveau de site ou de pool d’entreprise appropriés ont été configurés.</span><span class="sxs-lookup"><span data-stu-id="71dcb-185">If you are integrating with Exchange 2010 SP1, ensure that suitable global/site-level or pool-level Enterprise Voice dial plans have been configured.</span></span></p>



> [!NOTE]
> <span data-ttu-id="71dcb-186">S’il s’agit d’une intégration à Exchange 2010 SP1, le plan de numérotation de Lync Server et les noms de plan de numérotation SIP de MU ne doivent pas nécessairement correspondre.</span><span class="sxs-lookup"><span data-stu-id="71dcb-186">If you are integrating with Exchange 2010 SP1, the Lync Server dial plan and Exchange UM SIP dial plan names do not need to match.</span></span>

</td>
<td><p><span data-ttu-id="71dcb-187">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="71dcb-187">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="71dcb-188"><a href="lync-server-2013-configuring-dial-plans.md">Configuration des plans de numérotation dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="71dcb-188"><a href="lync-server-2013-configuring-dial-plans.md">Configuring dial plans in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71dcb-189">Exécutez l’outil d’intégration de la messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="71dcb-189">Run the Exchange UM Integration tool.</span></span></p></td>
<td><p><span data-ttu-id="71dcb-190">Sur Lync Server 2013, exécutez <strong>ocsumutil. exe</strong>, qui :</span><span class="sxs-lookup"><span data-stu-id="71dcb-190">On the Lync Server 2013, run <strong>ocsumutil.exe</strong>, which:</span></span></p>
<ul>
<li><p><span data-ttu-id="71dcb-191">crée des objets Contact Accès abonné et Standard automatique ;</span><span class="sxs-lookup"><span data-stu-id="71dcb-191">Creates Subscriber Access and Auto Attendant contact objects.</span></span></p></li>
<li><p><span data-ttu-id="71dcb-192">Vérifie qu’il existe un plan de numérotation vocale d’entreprise dont le nom correspond au nom de domaine complet du plan de numérotation de messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="71dcb-192">Validates that there is an Enterprise Voice dial plan with a name that matches the Exchange UM dial plan FQDN.</span></span> <span data-ttu-id="71dcb-193">Si vous exécutez Exchange 2010 SP1 ou une version ultérieure, les noms de plan de numérotation n’ont pas besoin d’être identiques et vous pouvez ignorer l’avertissement de l’outil à ce sujet.</span><span class="sxs-lookup"><span data-stu-id="71dcb-193">If you are running Exchange 2010 SP1 or later, the dial plan names do not need to match, and you can ignore the tool’s warning about this.</span></span></p></li>
</ul>
<p><span data-ttu-id="71dcb-194">Cet outil fonctionne en analysant l’annuaire Active Directory pour les paramètres de messagerie unifiée Exchange et en permettant à l’administrateur de Lync Server 2013 d’afficher, de créer et de modifier des objets de contact.</span><span class="sxs-lookup"><span data-stu-id="71dcb-194">This tool works by scanning the Active Directory for Exchange UM settings and allowing the Lync Server 2013 administrator to view, create, and edit contact objects.</span></span></p></td>
<td><p><span data-ttu-id="71dcb-195">RTCUniversalServerAdmins <em>et</em> RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="71dcb-195">RTCUniversalServerAdmins <em>and</em> RTCUniversalUserAdmins</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="71dcb-196">Pour qu’ocsumutil.exe soit exécuté correctement, l’utilisateur doit être membre de ces deux groupes.</span><span class="sxs-lookup"><span data-stu-id="71dcb-196">To run ocsumutil.exe successfully, the user must belong to both of these groups.</span></span>





> [!NOTE]
> <span data-ttu-id="71dcb-197">Pour créer des objets Contact, l’utilisateur qui exécute ocsumutil.exe doit disposer des autorisations d’accès appropriées à l’unité organisationnelle Active Directory dans laquelle les nouveaux objets de contact sont stockés.</span><span class="sxs-lookup"><span data-stu-id="71dcb-197">To create Contact objects, the user who runs ocsumutil.exe must have the correct permission to the Active Directory organizational unit (OU) where the new contact objects are stored.</span></span> <span data-ttu-id="71dcb-198">Cette autorisation peut être accordée en exécutant l’applet de commande <STRONG>Grant-CsOUPermission</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="71dcb-198">This permission can be granted by running the <STRONG>Grant-CsOUPermission</STRONG> cmdlet.</span></span> <span data-ttu-id="71dcb-199">Pour plus d’informations, reportez-vous à la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="71dcb-199">For details, see the Lync Server Management Shell documentation.</span></span>

</td>
<td><p><span data-ttu-id="71dcb-200"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configuration de Lync Server 2013 pour qu’il fonctionne avec la messagerie unifiée sur Microsoft Exchange Server</a></span><span class="sxs-lookup"><span data-stu-id="71dcb-200"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71dcb-201">Le cas échéant, effectuez d’autres étapes de configuration de voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="71dcb-201">If necessary, perform other Enterprise Voice configuration steps.</span></span></p></td>
<td><p><span data-ttu-id="71dcb-202">Si vous n’avez pas encore configuré les paramètres voix entreprise sur vos serveurs ou vos utilisateurs, effectuez une ou plusieurs des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="71dcb-202">If you have not already configured Enterprise Voice settings on your servers or users, do one or more of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="71dcb-203">déployez et configurez</span><span class="sxs-lookup"><span data-stu-id="71dcb-203">Deploy and configure</span></span></p>
<p><span data-ttu-id="71dcb-204">les passerelles de réseau téléphonique commuté (RTC) et les serveurs de médiation ;</span><span class="sxs-lookup"><span data-stu-id="71dcb-204">Public switched telephone network (PSTN) gateways and Mediation Servers</span></span></p></li>
<li><p><span data-ttu-id="71dcb-205">définissez les stratégies vocales, les enregistrements d’utilisation RTC et les itinéraires d’appels sortants ;</span><span class="sxs-lookup"><span data-stu-id="71dcb-205">Define voice policies, PSTN usage records, and outbound call routes.</span></span></p></li>
<li><p><span data-ttu-id="71dcb-206">activez les utilisateurs pour Voix Entreprise ;</span><span class="sxs-lookup"><span data-stu-id="71dcb-206">Enable users for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="71dcb-207">configurez éventuellement les plans de numérotation d’utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="71dcb-207">Optionally, configure specific users with dial plans.</span></span></p></li>
</ul>
<p><span data-ttu-id="71dcb-208">D’autres étapes de configuration sont parfois nécessaires selon les fonctionnalités vocales d’entreprise que vous activez.</span><span class="sxs-lookup"><span data-stu-id="71dcb-208">Other configuration steps may be required depending on the Enterprise Voice features that you enable.</span></span></p></td>
<td><p><span data-ttu-id="71dcb-209">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="71dcb-209">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="71dcb-210">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="71dcb-210">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="71dcb-211">Reportez-vous aux rubriques des sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="71dcb-211">See topics in the following sections:</span></span></p>
<ul>
<li><p><span data-ttu-id="71dcb-212"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configuration des stratégies vocales, des enregistrements d’utilisation RTC et des itinéraires vocaux dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="71dcb-212"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="71dcb-213"><a href="lync-server-2013-deploying-enterprise-voice.md">Déploiement d’Enterprise Voice dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="71dcb-213"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71dcb-214">Activez les utilisateurs d’Enterprise Voice pour la messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="71dcb-214">Enable Enterprise Voice users for Exchange UM.</span></span></p></td>
<td><p><span data-ttu-id="71dcb-215">Sur le serveur de messagerie unifiée Exchange, assurez-vous qu’une stratégie de boîte aux lettres de messagerie unifiée a été créée et que chaque utilisateur dispose d’une attribution de numéro d’extension unique, puis activez l’utilisateur pour la messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="71dcb-215">On the Exchange UM server, ensure that a Unified Messaging mailbox policy has been created and that each user has a unique extension number assignment, and then enable the user for Unified Messaging.</span></span></p></td>
<td><p><span data-ttu-id="71dcb-216">Administrateur de destinataires Exchange</span><span class="sxs-lookup"><span data-stu-id="71dcb-216">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="71dcb-217">Pour Exchange 2007 SP1 ou le dernier Service Pack, &quot;voir activation d’un utilisateur pour la messagerie&quot; unifiée à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=268700">http://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</span><span class="sxs-lookup"><span data-stu-id="71dcb-217">For Exchange 2007 SP1 or latest service pack, see &quot;How to Enable a User for Unified Messaging&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268700">http://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</span></span></p>
<p><span data-ttu-id="71dcb-218">Pour Exchange 2010 ou le dernier Service Pack, &quot;voir Activer un utilisateur pour la&quot; messagerie <a href="http://go.microsoft.com/fwlink/p/?linkid=268701">http://go.microsoft.com/fwlink/p/?LinkId=268701</a>unifiée à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="71dcb-218">For Exchange 2010 or latest service pack, see &quot;Enable a User for Unified Messaging&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268701">http://go.microsoft.com/fwlink/p/?LinkId=268701</a>.</span></span></p>
<p><span data-ttu-id="71dcb-219">Pour Exchange 2013, voir la messagerie unifiée à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span><span class="sxs-lookup"><span data-stu-id="71dcb-219">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

