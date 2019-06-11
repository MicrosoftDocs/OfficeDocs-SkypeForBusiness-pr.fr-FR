---
title: 'Lync Server 2013 : Solutions de résistance de sites de succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch-site resiliency solutions
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398234(v=OCS.15)
ms:contentKeyID: 48183517
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce14328aed7ae4769d2f2aff18edb9c6135fe025
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a><span data-ttu-id="98502-102">Solutions de résistance de sites de succursale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98502-102">Branch-site resiliency solutions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98502-103">_**Dernière modification de la rubrique:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="98502-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="98502-104">Mettre en œuvre la résistance des sites de succursale pour votre organisation présente des avantages évidents.</span><span class="sxs-lookup"><span data-stu-id="98502-104">There are obvious advantages to providing branch-site resiliency to your organization.</span></span> <span data-ttu-id="98502-105">En particulier, si vous perdez la connexion au site central, les utilisateurs du site de succursale continuent d’avoir accès au service voix entreprise et à la messagerie vocale (si vous configurez les paramètres de reroutage de la messagerie vocale; pour plus d’informations, voir [Configuration requise pour la résilience du site de succursale pour Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).</span><span class="sxs-lookup"><span data-stu-id="98502-105">Specifically, if you lose the connection to the central site, branch site users will continue to have Enterprise Voice service and voice mail (if you configure voice mail rerouting settings; for details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).</span></span> <span data-ttu-id="98502-106">Cependant, pour les sites comportant moins de 25 utilisateurs, une solution de résistance peut ne pas être assez rentable.</span><span class="sxs-lookup"><span data-stu-id="98502-106">However, for sites with fewer than 25 users, a resiliency solution may not provide a sufficient return on investment.</span></span>

<span data-ttu-id="98502-p102">Si vous décidez de mettre en œuvre la résistance pour les sites de succursale, vous disposez de trois options. Le tableau ci-dessous peut vous aider à déterminer l’option appropriée.</span><span class="sxs-lookup"><span data-stu-id="98502-p102">If you decide to provide branch-site resiliency, you have three options. The following table can help you determine the best option for your organization.</span></span>

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98502-109">Si vous…</span><span class="sxs-lookup"><span data-stu-id="98502-109">If you…</span></span></th>
<th><span data-ttu-id="98502-110">Nous vous recommandons d’utiliser un…</span><span class="sxs-lookup"><span data-stu-id="98502-110">We recommend that you use a…</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98502-111">Hébergez entre 25 et 1 000 utilisateurs sur le site de succursale, et si un déploiement complet n’est pas rentable ou si vous ne disposez pas d’une prise en charge d’administration locale.</span><span class="sxs-lookup"><span data-stu-id="98502-111">Host between 25 and 1000 users at your branch site, and if the return on investment does not support a full deployment or where local administrative support is unavailable</span></span></p></td>
<td><p><span data-ttu-id="98502-112">Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="98502-112">Survivable Branch Appliance</span></span></p>
<p><span data-ttu-id="98502-113">L’application branche Survivable est un serveur de Blades standard doté d’un serveur d’archivage et de médiation Lync Server s’exécutant sur Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="98502-113">The Survivable Branch Appliance is an industry-standard blade server with a Lync Server Registrar and Mediation Server running on Windows Server 2008 R2.</span></span> <span data-ttu-id="98502-114">L’unité de branchement Survivable comporte également une passerelle RTC (réseau téléphonique commuté).</span><span class="sxs-lookup"><span data-stu-id="98502-114">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="98502-115">Des périphériques tiers qualifiés (développés par les partenaires de Microsoft dans le programme de qualification/certification Survivable Branch Appliance (SBA) assurent une connexion PSTN continue en cas de panne du réseau étendu, mais ils ne fournissent pas de services de conférence et de présence résistants, car ces fonctionnalités dépendent des serveurs frontaux du site central.</span><span class="sxs-lookup"><span data-stu-id="98502-115">Qualified third-party devices (developed by Microsoft partners in the Survivable Branch Appliance (SBA) qualification/certification program) provide a continuous PSTN connection in the event of WAN failure, but this approach does not provide resilient presence and conferencing because these features depend on Front End Servers at the central site.</span></span></p>
<p><span data-ttu-id="98502-116">Pour plus d’informations sur les appareils de branche &quot;survivables, voir détails sur&quot; le périphérique de branchement survivant plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="98502-116">For details about Survivable Branch Appliances, see &quot;Survivable Branch Appliance Details,&quot; later in this topic.</span></span></p>
<p><span data-ttu-id="98502-117"><strong>Remarque:</strong> Si vous décidez également d’utiliser une ligne SIP avec votre appareil de branchement survivant, contactez le fournisseur de votre application pour savoir quel fournisseur de services est le plus approprié pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="98502-117"><strong>Note:</strong> If you decide to also use a SIP trunk with your Survivable Branch Appliance, contact your Survivable Branch Appliance vendor to learn about which service provider is best for your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98502-118">Héberger entre 1000 et 2000 sur votre site de succursale, ne pas disposer d’une connexion WAN fiable et avoir reçu des administrateurs Lync Server</span><span class="sxs-lookup"><span data-stu-id="98502-118">Host between 1000 and 2000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="98502-119">Serveur de succursales survivant ou deux dispositifs de branchement plus survivant.</span><span class="sxs-lookup"><span data-stu-id="98502-119">Survivable Branch Server or two Survivable Branch Appliances.</span></span></p>
<p><span data-ttu-id="98502-120">Le serveur de succursales Survivables est une configuration matérielle requise pour la réunion Windows Server sur laquelle sont installés les logiciels serveur Bureau d’enregistrement et médiation de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="98502-120">The Survivable Branch Server is a Windows Server meeting specified hardware requirements that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="98502-121">Il doit se connecter à une passerelle PSTN ou à une jonction SIP à un fournisseur de services téléphoniques.</span><span class="sxs-lookup"><span data-stu-id="98502-121">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span></p>
<p><span data-ttu-id="98502-122">Pour plus d’informations sur les serveurs de succursales Survivables, voir &quot;détails&quot; sur le serveur de succursales survivant plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="98502-122">For details about Survivable Branch Servers, see &quot;Survivable Branch Server Details,&quot; later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98502-123">Si vous avez besoin de fonctionnalités de présence et de conférence en plus des fonctionnalités vocales pour les utilisateurs de 5000 et que vous disposez d’un administrateur Lync Server expérimenté</span><span class="sxs-lookup"><span data-stu-id="98502-123">If you require presence and conferencing features in addition to voice features for up to 5000 users, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="98502-124">Procédez à un déploiement de site central avec un serveur Standard Edition au lieu d’un déploiement de site de succursale.</span><span class="sxs-lookup"><span data-stu-id="98502-124">Deploy as a central site with a Standard Edition server rather than as a branch site.</span></span></p>
<p><span data-ttu-id="98502-125">Le déploiement de Lync Server à une échelle complète fournit une connexion RTC continue et une présence et une audioconférence résilientes en cas de panne du réseau étendu.</span><span class="sxs-lookup"><span data-stu-id="98502-125">A full-scale Lync Server deployment provides a continuous PSTN connection and resilient presence and conferencing in the event of WAN failure.</span></span></p>
<p><span data-ttu-id="98502-126">Pour plus d’informations sur la préparation de cette solution, voir <a href="lync-server-2013-planning-for-your-organization.md">planification de l’Organisation pour Lync server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">déterminer la configuration système requise pour Lync Server 2013</a>et <a href="lync-server-2013-determining-your-infrastructure-requirements.md">déterminer la configuration requise pour votre infrastructure pour Lync Server 2013</a>, et autres sections pertinentes de la documentation relative à la planification.</span><span class="sxs-lookup"><span data-stu-id="98502-126">For details about preparing for this solution, see <a href="lync-server-2013-planning-for-your-organization.md">Organization planning for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">Determining your infrastructure requirements for Lync Server 2013</a>, and other relevant sections of the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a><span data-ttu-id="98502-127">Topologies résistantes</span><span class="sxs-lookup"><span data-stu-id="98502-127">Resiliency Topologies</span></span>

<span data-ttu-id="98502-128">La figure suivante montre les topologies recommandées pour la résistance des sites de succursale.</span><span class="sxs-lookup"><span data-stu-id="98502-128">The following figure shows the recommended topologies for branch-site resiliency.</span></span>

<span data-ttu-id="98502-129">**Options de résistance pour sites de succursale**</span><span class="sxs-lookup"><span data-stu-id="98502-129">**Branch site resiliency options**</span></span>

<span data-ttu-id="98502-130">Options de résilience de la ![succursale vocale] Options de résilience de la (images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "succursale vocale")</span><span class="sxs-lookup"><span data-stu-id="98502-130">![Voice Branch Resiliency Options](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Voice Branch Resiliency Options")</span></span>

</div>

<div>

## <a name="survivable-branch-appliance-details"></a><span data-ttu-id="98502-131">Survivable Branch Appliance en détail</span><span class="sxs-lookup"><span data-stu-id="98502-131">Survivable Branch Appliance Details</span></span>

<span data-ttu-id="98502-132">L’application de succursales survivant du serveur Lync inclut les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="98502-132">The Lync Server Survivable Branch Appliance includes the following components:</span></span>

  - <span data-ttu-id="98502-133">serveur d’inscriptions pour l’authentification et l’inscription des utilisateurs et routage des appels ;</span><span class="sxs-lookup"><span data-stu-id="98502-133">A Registrar for user authentication, registration and call routing</span></span>

  - <span data-ttu-id="98502-134">serveur de médiation pour la signalisation entre le serveur d’inscriptions et la passerelle PSTN ;</span><span class="sxs-lookup"><span data-stu-id="98502-134">A Mediation Server for handling signaling between the Registrar and a PSTN gateway</span></span>

  - <span data-ttu-id="98502-135">passerelle PSTN pour le routage des appels vers le PSTN comme moyen de transport secondaire en cas de panne du réseau étendu ;</span><span class="sxs-lookup"><span data-stu-id="98502-135">A PSTN gateway for routing calls to the PSTN as a fallback transport in the event of a WAN outage</span></span>

  - <span data-ttu-id="98502-136">SQL Server Express pour le stockage local des données d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="98502-136">SQL Server Express for local user data storage</span></span>

<span data-ttu-id="98502-137">L’unité de branchement Survivable inclut également des Trunks RTC, des ports analogiques et une carte Ethernet.</span><span class="sxs-lookup"><span data-stu-id="98502-137">The Survivable Branch Appliance also includes PSTN trunks, analog ports, and an Ethernet adapter.</span></span>

<span data-ttu-id="98502-138">Si la connexion WAN d’un site de succursale à un site central devient indisponible, les utilisateurs de succursales internes continuent d’être enregistrés auprès du Bureau d’enregistrement d’appliances Survivables et de bénéficier d’un service vocal ininterrompu à l’aide de la connexion de l’appareil de branchement survivant. sur PSTN.</span><span class="sxs-lookup"><span data-stu-id="98502-138">If the branch site’s WAN connection to a central site becomes unavailable, internal branch users continue to be registered with the Survivable Branch Appliance Registrar and obtain uninterrupted voice service by using the Survivable Branch Appliance connection to the PSTN.</span></span> <span data-ttu-id="98502-139">De même, les utilisateurs du site de succursale se connectant de leur domicile ou d’autres emplacements distants pourront s’enregistrer avec un serveur d’inscriptions du site central si la liaison de réseau étendu vers le site de succursale est indisponible.</span><span class="sxs-lookup"><span data-stu-id="98502-139">Branch site users who connect from home or other remote locations will be able to register with a Registrar server at a central site if the WAN link to the branch site is unavailable.</span></span> <span data-ttu-id="98502-140">Ces utilisateurs disposeront de la fonctionnalité de communication unifiée complète, la seule exception étant que les appels entrants vers le site de succursale seront transmis à la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="98502-140">These users will have full unified communications functionality, with the one exception that inbound calls to the branch site will go to voice mail.</span></span> <span data-ttu-id="98502-141">Lorsque la connexion de réseau étendu redevient disponible, les utilisateurs du site de succursale disposent de nouveau des fonctionnalités complètes de communication.</span><span class="sxs-lookup"><span data-stu-id="98502-141">When the WAN connection becomes available, full functionality should be restored to branch site users.</span></span> <span data-ttu-id="98502-142">Par ailleurs, le basculement vers l’appareil de branchement survivant ou la restauration du service nécessite la présence d’un administrateur informatique.</span><span class="sxs-lookup"><span data-stu-id="98502-142">Neither the failover to the Survivable Branch Appliance nor the restoration of service requires the presence of an IT administrator.</span></span>

<span data-ttu-id="98502-143">Lync Server prend en charge jusqu’à deux appareils de succursales survivant sur un site de succursale.</span><span class="sxs-lookup"><span data-stu-id="98502-143">Lync Server supports up to two Survivable Branch Appliance at a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="98502-144">Les utilisateurs qui sont hébergés sur une unité de branchement Survivable Lync Server ne peuvent pas créer de nouvelles salles de conversation ou afficher la carte de la salle pour les salles existantes.</span><span class="sxs-lookup"><span data-stu-id="98502-144">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new Chat Rooms or view the Room Card for existing rooms.</span></span>



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a><span data-ttu-id="98502-145">Vue d’ensemble du déploiement du Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="98502-145">Survivable Branch Appliance Deployment Overview</span></span>

<span data-ttu-id="98502-146">Le matériel de branchement survivant est fabriqué par des fabricants d’équipements d’origine en partenariat avec Microsoft et déployés en leur nom par des détaillants à la valeur.</span><span class="sxs-lookup"><span data-stu-id="98502-146">The Survivable Branch Appliance is manufactured by original equipment manufacturers in partnership with Microsoft and deployed on their behalf by value-added retailers.</span></span> <span data-ttu-id="98502-147">Ce déploiement ne doit se produire qu’après le déploiement de Lync Server sur le site central, une connexion WAN au site de succursale est en place, et les utilisateurs du site de succursale activés pour Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="98502-147">This deployment should occur only after Lync Server has been deployed at the central site, a WAN connection to the branch site is in place, and branch site users are enabled for Enterprise Voice.</span></span>

<span data-ttu-id="98502-148">Pour plus d’informations sur ces étapes, reportez-vous à la rubrique [déploiement d’une unité ou d’un serveur à l’aide de Lync server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="98502-148">For details about these phases, see [Deploying a Survivable Branch Appliance or Server with Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98502-149">Phase</span><span class="sxs-lookup"><span data-stu-id="98502-149">Phase</span></span></th>
<th><span data-ttu-id="98502-150">Étapes</span><span class="sxs-lookup"><span data-stu-id="98502-150">Steps</span></span></th>
<th><span data-ttu-id="98502-151">Droits d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="98502-151">User Rights</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98502-152">Configurer les services de domaine Active Directory pour l’unité de branchement Survivable</span><span class="sxs-lookup"><span data-stu-id="98502-152">Set up Active Directory Domain Services for the Survivable Branch Appliance</span></span></p></td>
<td><p><span data-ttu-id="98502-153"><strong>Sur le site central :</strong></span><span class="sxs-lookup"><span data-stu-id="98502-153"><strong>At the central site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="98502-154">Créer un compte d’utilisateur de domaine (ou une identité d’entreprise) pour le technicien qui installera et activer l’unité de branchement survivant sur le site de la succursale.</span><span class="sxs-lookup"><span data-stu-id="98502-154">Create a domain user account (or enterprise identity) for the technician who will install and activate the Survivable Branch Appliance at the branch site.</span></span></p></li>
<li><p><span data-ttu-id="98502-155">Créer un compte d’ordinateur (à l’aide du nom de domaine complet (FQDN, Fully Qualified Domain Name) pour l’appareil de succursale Survivable dans les services de domaine Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="98502-155">Create a computer account (with the applicable fully qualified domain name (FQDN)) for Survivable Branch Appliance in Active Directory Domain Services.</span></span></p></li>
<li><p><span data-ttu-id="98502-156">Dans le générateur de topologie, créez et publiez l’appareil de branchement survivant.</span><span class="sxs-lookup"><span data-stu-id="98502-156">In Topology Builder, create and publish the Survivable Branch Appliance.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="98502-157">Le compte d’utilisateur du technicien doit être membre du groupe RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="98502-157">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span> <span data-ttu-id="98502-158">L’unité de branchement survivant doit appartenir au groupe RTCSBAUniversalServices, qui se produit automatiquement lorsque vous utilisez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="98502-158">The Survivable Branch Appliance must belong to the RTCSBAUniversalServices group, which happens automatically when you use Topology Builder.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98502-159">Installez et activez l’unité de branchement Survivable.</span><span class="sxs-lookup"><span data-stu-id="98502-159">Install, and activate the Survivable Branch Appliance.</span></span></p></td>
<td><p><span data-ttu-id="98502-160"><strong>Sur le site de succursale :</strong></span><span class="sxs-lookup"><span data-stu-id="98502-160"><strong>At the branch site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="98502-161">Connectez l’unité de branchement survivant à un port Ethernet et un port PSTN.</span><span class="sxs-lookup"><span data-stu-id="98502-161">Connect the Survivable Branch Appliance to an Ethernet port and PSTN port.</span></span></p></li>
<li><p><span data-ttu-id="98502-162">Démarrez l’unité de branchement Survivable.</span><span class="sxs-lookup"><span data-stu-id="98502-162">Start the Survivable Branch Appliance.</span></span></p></li>
<li><p><span data-ttu-id="98502-163">Rejoignez l’unité de branchement Survivable au domaine, en utilisant le compte d’utilisateur de domaine créé pour l’unité de branchement survivant sur le site central.</span><span class="sxs-lookup"><span data-stu-id="98502-163">Join the Survivable Branch Appliance to the domain, using the domain user account created for the Survivable Branch Appliance at the central site.</span></span> <span data-ttu-id="98502-164">Définissez le nom de domaine complet et l’adresse IP de sorte qu’ils correspondent au nom de domaine complet créé pour le compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="98502-164">Set the FQDN and IP address to match the FQDN created in the computer account.</span></span></p></li>
<li><p><span data-ttu-id="98502-165">Configurez l’unité de branchement Survivable à l’aide de l’interface utilisateur OEM.</span><span class="sxs-lookup"><span data-stu-id="98502-165">Configure the Survivable Branch Appliance using the OEM user interface.</span></span></p></li>
<li><p><span data-ttu-id="98502-166">Testez la connectivité PSTN.</span><span class="sxs-lookup"><span data-stu-id="98502-166">Test PSTN connectivity.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="98502-167">Le compte d’utilisateur du technicien doit être membre du groupe RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="98502-167">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a><span data-ttu-id="98502-168">Serveur Survivable Branch Server en détail</span><span class="sxs-lookup"><span data-stu-id="98502-168">Survivable Branch Server Details</span></span>

<span data-ttu-id="98502-169">Dans le générateur de topologie, créez le site de succursale, ajoutez le serveur de succursales survivant à ce site, puis exécutez l’Assistant Déploiement de Lync Server sur l’ordinateur sur lequel vous voulez installer le rôle.</span><span class="sxs-lookup"><span data-stu-id="98502-169">In Topology Builder create the branch site, add the Survivable Branch Server to that site, and then run the Lync Server Deployment Wizard on the computer where you want to install the role.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="98502-170">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="98502-170">See Also</span></span>


[<span data-ttu-id="98502-171">Déploiement de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98502-171">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

