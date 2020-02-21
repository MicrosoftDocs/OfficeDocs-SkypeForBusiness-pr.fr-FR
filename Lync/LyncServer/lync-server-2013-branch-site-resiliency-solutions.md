---
title: 'Lync Server 2013 : solutions de résistance de site de succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency solutions
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398234(v=OCS.15)
ms:contentKeyID: 48183517
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42ede6730357f50967f13089e02e32ad1a21d8ce
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a><span data-ttu-id="b45b6-102">Solutions de résistance de site de succursale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b45b6-102">Branch-site resiliency solutions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b45b6-103">_**Dernière modification de la rubrique :** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="b45b6-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="b45b6-104">Mettre en œuvre la résistance des sites de succursale pour votre organisation présente des avantages évidents.</span><span class="sxs-lookup"><span data-stu-id="b45b6-104">There are obvious advantages to providing branch-site resiliency to your organization.</span></span> <span data-ttu-id="b45b6-105">En particulier, si vous perdez la connexion au site central, les utilisateurs de site de succursale continueront à utiliser le service voix entreprise et la messagerie vocale (si vous configurez les paramètres de réacheminement de la messagerie vocale ; pour plus d’informations, consultez la rubrique [Configuration requise pour la résistance des sites de succursale pour Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).</span><span class="sxs-lookup"><span data-stu-id="b45b6-105">Specifically, if you lose the connection to the central site, branch site users will continue to have Enterprise Voice service and voice mail (if you configure voice mail rerouting settings; for details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).</span></span> <span data-ttu-id="b45b6-106">Cependant, pour les sites comportant moins de 25 utilisateurs une solution de résistance peut ne pas être assez rentable.</span><span class="sxs-lookup"><span data-stu-id="b45b6-106">However, for sites with fewer than 25 users, a resiliency solution may not provide a sufficient return on investment.</span></span>

<span data-ttu-id="b45b6-p102">Si vous décidez de mettre en œuvre la résistance pour les sites de succursale, vous disposez de trois options. Le tableau suivant peut vous aider à déterminer l’option appropriée.</span><span class="sxs-lookup"><span data-stu-id="b45b6-p102">If you decide to provide branch-site resiliency, you have three options. The following table can help you determine the best option for your organization.</span></span>

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b45b6-109">Si vous…</span><span class="sxs-lookup"><span data-stu-id="b45b6-109">If you…</span></span></th>
<th><span data-ttu-id="b45b6-110">Nous vous recommandons d’utiliser un…</span><span class="sxs-lookup"><span data-stu-id="b45b6-110">We recommend that you use a…</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b45b6-111">Hébergez entre 25 et 1 000 utilisateurs sur le site de succursale, et si un déploiement complet n’est pas rentable ou si vous ne disposez pas d’un support d’administration local</span><span class="sxs-lookup"><span data-stu-id="b45b6-111">Host between 25 and 1000 users at your branch site, and if the return on investment does not support a full deployment or where local administrative support is unavailable</span></span></p></td>
<td><p><span data-ttu-id="b45b6-112">Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="b45b6-112">Survivable Branch Appliance</span></span></p>
<p><span data-ttu-id="b45b6-113">Le Survivable Branch Appliance est un serveur lame standard avec un serveur de médiation et de serveur d’inscriptions Lync Server s’exécutant sur Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="b45b6-113">The Survivable Branch Appliance is an industry-standard blade server with a Lync Server Registrar and Mediation Server running on Windows Server 2008 R2.</span></span> <span data-ttu-id="b45b6-114">Le Survivable Branch Appliance contient également une passerelle RTC (réseau téléphonique commuté).</span><span class="sxs-lookup"><span data-stu-id="b45b6-114">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="b45b6-115">Des périphériques tiers qualifiés (développés par les partenaires de Microsoft dans le programme de qualification/certification Survivable Branch Appliance (SBA)) assurent une connexion PSTN continue en cas de panne du WAN, mais ils ne fournissent pas de services de conférence et de présence résistants, car ces fonctionnalités dépendent des serveurs frontaux du site central.</span><span class="sxs-lookup"><span data-stu-id="b45b6-115">Qualified third-party devices (developed by Microsoft partners in the Survivable Branch Appliance (SBA) qualification/certification program) provide a continuous PSTN connection in the event of WAN failure, but this approach does not provide resilient presence and conferencing because these features depend on Front End Servers at the central site.</span></span></p>
<p><span data-ttu-id="b45b6-116">Pour plus d’informations sur Survivable Branch Appliances, voir &quot;Survivable Branch&quot; Appliance Details, plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="b45b6-116">For details about Survivable Branch Appliances, see &quot;Survivable Branch Appliance Details,&quot; later in this topic.</span></span></p>
<p><span data-ttu-id="b45b6-117"><strong>Remarque :</strong> Si vous décidez d’utiliser également une jonction SIP avec votre Survivable Branch appliance, contactez votre fournisseur Survivable Branch Appliance pour en savoir plus sur le fournisseur de services qui convient le mieux à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b45b6-117"><strong>Note:</strong> If you decide to also use a SIP trunk with your Survivable Branch Appliance, contact your Survivable Branch Appliance vendor to learn about which service provider is best for your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b45b6-118">Hôte entre 1000 et 2000 utilisateurs sur votre site de succursale, absence de connexion WAN fiable et disponibilité des administrateurs Lync Server formés</span><span class="sxs-lookup"><span data-stu-id="b45b6-118">Host between 1000 and 2000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="b45b6-119">Survivable Branch Server ou deux Survivable Branch Appliances.</span><span class="sxs-lookup"><span data-stu-id="b45b6-119">Survivable Branch Server or two Survivable Branch Appliances.</span></span></p>
<p><span data-ttu-id="b45b6-120">Le Survivable Branch Server est une configuration matérielle requise pour une réunion Windows Server sur lequel le logiciel de serveur d’inscriptions et de médiation Lync Server est installé.</span><span class="sxs-lookup"><span data-stu-id="b45b6-120">The Survivable Branch Server is a Windows Server meeting specified hardware requirements that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="b45b6-121">Il doit se connecter à une passerelle PSTN ou à une jonction SIP à un fournisseur de services téléphoniques.</span><span class="sxs-lookup"><span data-stu-id="b45b6-121">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span></p>
<p><span data-ttu-id="b45b6-122">Pour plus d’informations sur les serveurs Survivable &quot;Branch Server, voir Survivable&quot; Branch Server Details, plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="b45b6-122">For details about Survivable Branch Servers, see &quot;Survivable Branch Server Details,&quot; later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b45b6-123">Si vous avez besoin de fonctionnalités de présence et de conférence en plus des fonctionnalités vocales pour un maximum de 5000 utilisateurs et que des administrateurs Lync Server formés sont disponibles ;</span><span class="sxs-lookup"><span data-stu-id="b45b6-123">If you require presence and conferencing features in addition to voice features for up to 5000 users, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="b45b6-124">Procédez à un déploiement de site central avec un serveur Standard Edition au lieu d’un déploiement de site de succursale.</span><span class="sxs-lookup"><span data-stu-id="b45b6-124">Deploy as a central site with a Standard Edition server rather than as a branch site.</span></span></p>
<p><span data-ttu-id="b45b6-125">Un déploiement Lync Server complet offre une connexion RTC continue et une présence et une conférence résistantes en cas de panne de réseau étendu (WAN).</span><span class="sxs-lookup"><span data-stu-id="b45b6-125">A full-scale Lync Server deployment provides a continuous PSTN connection and resilient presence and conferencing in the event of WAN failure.</span></span></p>
<p><span data-ttu-id="b45b6-126">Pour plus d’informations sur la préparation de cette solution, reportez-vous à la rubrique <a href="lync-server-2013-planning-for-your-organization.md">Organization Planning for Lync server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">Determining Your System Requirements for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">Determining Your infrastructure requirements for Lync Server 2013</a>, et d’autres sections pertinentes de la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="b45b6-126">For details about preparing for this solution, see <a href="lync-server-2013-planning-for-your-organization.md">Organization planning for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">Determining your infrastructure requirements for Lync Server 2013</a>, and other relevant sections of the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a><span data-ttu-id="b45b6-127">Topologies résistantes</span><span class="sxs-lookup"><span data-stu-id="b45b6-127">Resiliency Topologies</span></span>

<span data-ttu-id="b45b6-128">La figure suivante montre les topologies recommandées pour la résistance des sites de succursale.</span><span class="sxs-lookup"><span data-stu-id="b45b6-128">The following figure shows the recommended topologies for branch-site resiliency.</span></span>

<span data-ttu-id="b45b6-129">**Options de résistance pour sites de succursale**</span><span class="sxs-lookup"><span data-stu-id="b45b6-129">**Branch site resiliency options**</span></span>

<span data-ttu-id="b45b6-130">![Options de résistance des succursales vocales](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Options de résistance des succursales vocales")</span><span class="sxs-lookup"><span data-stu-id="b45b6-130">![Voice Branch Resiliency Options](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Voice Branch Resiliency Options")</span></span>

</div>

<div>

## <a name="survivable-branch-appliance-details"></a><span data-ttu-id="b45b6-131">Survivable Branch Appliance en détail</span><span class="sxs-lookup"><span data-stu-id="b45b6-131">Survivable Branch Appliance Details</span></span>

<span data-ttu-id="b45b6-132">Le Survivable Branch Appliance Lync Server inclut les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="b45b6-132">The Lync Server Survivable Branch Appliance includes the following components:</span></span>

  - <span data-ttu-id="b45b6-133">un serveur d’inscriptions pour l’authentification et l’inscription des utilisateurs, et le routage des appels ;</span><span class="sxs-lookup"><span data-stu-id="b45b6-133">A Registrar for user authentication, registration and call routing</span></span>

  - <span data-ttu-id="b45b6-134">un serveur de médiation pour la signalisation entre le serveur d’inscriptions et la passerelle PSTN ;</span><span class="sxs-lookup"><span data-stu-id="b45b6-134">A Mediation Server for handling signaling between the Registrar and a PSTN gateway</span></span>

  - <span data-ttu-id="b45b6-135">une passerelle PSTN pour le routage des appels vers le PSTN comme moyen de transport secondaire en cas de panne du WAN ;</span><span class="sxs-lookup"><span data-stu-id="b45b6-135">A PSTN gateway for routing calls to the PSTN as a fallback transport in the event of a WAN outage</span></span>

  - <span data-ttu-id="b45b6-136">SQL Server Express pour le stockage local des données d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b45b6-136">SQL Server Express for local user data storage</span></span>

<span data-ttu-id="b45b6-137">Le Survivable Branch Appliance inclut également des jonctions PSTN, des ports analogiques et une carte Ethernet.</span><span class="sxs-lookup"><span data-stu-id="b45b6-137">The Survivable Branch Appliance also includes PSTN trunks, analog ports, and an Ethernet adapter.</span></span>

<span data-ttu-id="b45b6-138">Si la connexion WAN du site de succursale à un site central devient indisponible, les utilisateurs de la succursale peuvent continuer à être enregistrés auprès du serveur Survivable Branch appliance et obtenir des services vocaux ininterrompus à l’aide de la connexion Survivable Branch appliance. au réseau téléphonique commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="b45b6-138">If the branch site’s WAN connection to a central site becomes unavailable, internal branch users continue to be registered with the Survivable Branch Appliance Registrar and obtain uninterrupted voice service by using the Survivable Branch Appliance connection to the PSTN.</span></span> <span data-ttu-id="b45b6-139">De même, les utilisateurs du site de succursale se connectant de leur domicile ou d’autres emplacements distants pourront s’enregistrer avec un serveur d’inscriptions du site central si la liaison WAN vers le site de succursale est indisponible.</span><span class="sxs-lookup"><span data-stu-id="b45b6-139">Branch site users who connect from home or other remote locations will be able to register with a Registrar server at a central site if the WAN link to the branch site is unavailable.</span></span> <span data-ttu-id="b45b6-140">Ces utilisateurs disposeront de la fonctionnalité de communication unifiée complète, la seule exception étant que les appels entrants vers le site de succursale seront transmis à la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="b45b6-140">These users will have full unified communications functionality, with the one exception that inbound calls to the branch site will go to voice mail.</span></span> <span data-ttu-id="b45b6-141">Lorsque la connexion WAN redevient disponible, les utilisateurs du site de succursale disposent de nouveau des fonctionnalités complètes de communication.</span><span class="sxs-lookup"><span data-stu-id="b45b6-141">When the WAN connection becomes available, full functionality should be restored to branch site users.</span></span> <span data-ttu-id="b45b6-142">Ni le basculement vers le Survivable Branch Appliance ni la restauration du service ne nécessitent la présence d’un administrateur informatique.</span><span class="sxs-lookup"><span data-stu-id="b45b6-142">Neither the failover to the Survivable Branch Appliance nor the restoration of service requires the presence of an IT administrator.</span></span>

<span data-ttu-id="b45b6-143">Lync Server prend en charge jusqu’à deux Survivable Branch appliance sur un site de succursale.</span><span class="sxs-lookup"><span data-stu-id="b45b6-143">Lync Server supports up to two Survivable Branch Appliance at a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b45b6-144">Les utilisateurs hébergés sur une appliance Survivable Branch Lync Server ne peuvent pas créer de nouvelles salles de conversation ni afficher la carte de salle pour les salles existantes.</span><span class="sxs-lookup"><span data-stu-id="b45b6-144">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new Chat Rooms or view the Room Card for existing rooms.</span></span>



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a><span data-ttu-id="b45b6-145">Vue d’ensemble du déploiement du Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="b45b6-145">Survivable Branch Appliance Deployment Overview</span></span>

<span data-ttu-id="b45b6-146">Le Survivable Branch Appliance est fabriqué par les fabricants d’équipements d’origine en partenariat avec Microsoft et déployés pour leur compte par des détaillants à valeur ajoutée.</span><span class="sxs-lookup"><span data-stu-id="b45b6-146">The Survivable Branch Appliance is manufactured by original equipment manufacturers in partnership with Microsoft and deployed on their behalf by value-added retailers.</span></span> <span data-ttu-id="b45b6-147">Ce déploiement ne doit avoir lieu qu’une fois que Lync Server a été déployé sur le site central, une connexion WAN au site de succursale est en place et les utilisateurs de site de succursale sont activés pour voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="b45b6-147">This deployment should occur only after Lync Server has been deployed at the central site, a WAN connection to the branch site is in place, and branch site users are enabled for Enterprise Voice.</span></span>

<span data-ttu-id="b45b6-148">Pour plus d’informations sur ces phases, voir [Deploying a Survivable Branch Appliance or Server with Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="b45b6-148">For details about these phases, see [Deploying a Survivable Branch Appliance or Server with Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b45b6-149">Phase</span><span class="sxs-lookup"><span data-stu-id="b45b6-149">Phase</span></span></th>
<th><span data-ttu-id="b45b6-150">Étapes</span><span class="sxs-lookup"><span data-stu-id="b45b6-150">Steps</span></span></th>
<th><span data-ttu-id="b45b6-151">Droits d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="b45b6-151">User Rights</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b45b6-152">Configurer les services de domaine Active Directory pour le Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="b45b6-152">Set up Active Directory Domain Services for the Survivable Branch Appliance</span></span></p></td>
<td><p><span data-ttu-id="b45b6-153"><strong>Sur le site central :</strong></span><span class="sxs-lookup"><span data-stu-id="b45b6-153"><strong>At the central site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="b45b6-154">Créez un compte d’utilisateur de domaine (ou une identité d’entreprise) pour le technicien qui installera et activera le Survivable Branch appliance sur le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="b45b6-154">Create a domain user account (or enterprise identity) for the technician who will install and activate the Survivable Branch Appliance at the branch site.</span></span></p></li>
<li><p><span data-ttu-id="b45b6-155">Créez un compte d’ordinateur (avec le nom de domaine complet applicable) pour Survivable Branch Appliance dans les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b45b6-155">Create a computer account (with the applicable fully qualified domain name (FQDN)) for Survivable Branch Appliance in Active Directory Domain Services.</span></span></p></li>
<li><p><span data-ttu-id="b45b6-156">Dans le générateur de topologies, créez et publiez le Survivable Branch appliance.</span><span class="sxs-lookup"><span data-stu-id="b45b6-156">In Topology Builder, create and publish the Survivable Branch Appliance.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="b45b6-157">Le compte d’utilisateur du technicien doit être membre du groupe RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="b45b6-157">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span> <span data-ttu-id="b45b6-158">Le Survivable Branch appliance doit appartenir au groupe RTCSBAUniversalServices, qui se produit automatiquement lorsque vous utilisez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="b45b6-158">The Survivable Branch Appliance must belong to the RTCSBAUniversalServices group, which happens automatically when you use Topology Builder.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b45b6-159">Installez et activez le Survivable Branch appliance.</span><span class="sxs-lookup"><span data-stu-id="b45b6-159">Install, and activate the Survivable Branch Appliance.</span></span></p></td>
<td><p><span data-ttu-id="b45b6-160"><strong>Sur le site de succursale :</strong></span><span class="sxs-lookup"><span data-stu-id="b45b6-160"><strong>At the branch site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="b45b6-161">Connectez le Survivable Branch appliance à un port Ethernet et un port PSTN.</span><span class="sxs-lookup"><span data-stu-id="b45b6-161">Connect the Survivable Branch Appliance to an Ethernet port and PSTN port.</span></span></p></li>
<li><p><span data-ttu-id="b45b6-162">Démarrez le Survivable Branch appliance.</span><span class="sxs-lookup"><span data-stu-id="b45b6-162">Start the Survivable Branch Appliance.</span></span></p></li>
<li><p><span data-ttu-id="b45b6-163">Rejoignez le Survivable Branch Appliance au domaine à l’aide du compte d’utilisateur de domaine créé pour le Survivable Branch appliance sur le site central.</span><span class="sxs-lookup"><span data-stu-id="b45b6-163">Join the Survivable Branch Appliance to the domain, using the domain user account created for the Survivable Branch Appliance at the central site.</span></span> <span data-ttu-id="b45b6-164">Définissez le nom de domaine complet et l’adresse IP de sorte qu’ils correspondent au nom de domaine complet créé pour le compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b45b6-164">Set the FQDN and IP address to match the FQDN created in the computer account.</span></span></p></li>
<li><p><span data-ttu-id="b45b6-165">Configurez le Survivable Branch appliance à l’aide de l’interface utilisateur OEM.</span><span class="sxs-lookup"><span data-stu-id="b45b6-165">Configure the Survivable Branch Appliance using the OEM user interface.</span></span></p></li>
<li><p><span data-ttu-id="b45b6-166">Testez la connectivité PSTN.</span><span class="sxs-lookup"><span data-stu-id="b45b6-166">Test PSTN connectivity.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="b45b6-167">Le compte d’utilisateur du technicien doit être membre du groupe RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="b45b6-167">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a><span data-ttu-id="b45b6-168">Serveur Survivable Branch Server en détail</span><span class="sxs-lookup"><span data-stu-id="b45b6-168">Survivable Branch Server Details</span></span>

<span data-ttu-id="b45b6-169">Dans le générateur de topologies, créez le site de succursale, ajoutez le serveur Survivable Branch Server à ce site, puis exécutez l’Assistant Déploiement de Lync Server sur l’ordinateur sur lequel vous souhaitez installer le rôle.</span><span class="sxs-lookup"><span data-stu-id="b45b6-169">In Topology Builder create the branch site, add the Survivable Branch Server to that site, and then run the Lync Server Deployment Wizard on the computer where you want to install the role.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b45b6-170">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b45b6-170">See Also</span></span>


[<span data-ttu-id="b45b6-171">Déploiement de Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b45b6-171">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

