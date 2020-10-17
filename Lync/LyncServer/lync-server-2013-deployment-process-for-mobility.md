---
title: 'Lync Server 2013 : processus de déploiement pour la mobilité'
description: 'Lync Server 2013 : processus de déploiement pour la mobilité.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for mobility
ms:assetid: 5a1cebda-c14b-4ff4-9c36-f7caa868160f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690023(v=OCS.15)
ms:contentKeyID: 48184220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b49d69af899f6d9f2ac1db5040d017a9d62ce9eb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551040"
---
# <a name="deployment-process-for-mobility-in-lync-server-2013"></a><span data-ttu-id="c64b3-103">Processus de déploiement pour la mobilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c64b3-103">Deployment process for mobility in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c64b3-104">_**Dernière modification de la rubrique :** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="c64b3-104">_**Topic Last Modified:** 2013-02-19_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

<span data-ttu-id="c64b3-105">Cette section décrit la séquence d’étapes nécessaires au déploiement de la fonctionnalité de mobilité Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c64b3-105">This section describes the sequence of steps required to deploy the Lync Server 2013 mobility feature.</span></span>

### <a name="mobility-deployment-process"></a><span data-ttu-id="c64b3-106">Processus de déploiement de mobilité</span><span class="sxs-lookup"><span data-stu-id="c64b3-106">Mobility Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c64b3-107">Phase</span><span class="sxs-lookup"><span data-stu-id="c64b3-107">Phase</span></span></th>
<th><span data-ttu-id="c64b3-108">Étapes</span><span class="sxs-lookup"><span data-stu-id="c64b3-108">Steps</span></span></th>
<th><span data-ttu-id="c64b3-109">Autorisations</span><span class="sxs-lookup"><span data-stu-id="c64b3-109">Permissions</span></span></th>
<th><span data-ttu-id="c64b3-110">Documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="c64b3-110">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c64b3-111">Créer des enregistrements DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="c64b3-111">Create Domain Name System (DNS) records</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c64b3-112">Créez un enregistrement DNS CNAMe ou A (hôte, si IPv6, AAAA) interne pour résoudre l’URL du service de découverte automatique interne.</span><span class="sxs-lookup"><span data-stu-id="c64b3-112">Create an internal DNS CNAME or A (host, if IPv6, AAAA) record to resolve the internal Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="c64b3-113">Créez un enregistrement DNS CNAMe ou A (hôte, si IPv6, AAAA) externe pour résoudre l’URL du service de découverte automatique externe.</span><span class="sxs-lookup"><span data-stu-id="c64b3-113">Create an external DNS CNAME or A (host, if IPv6, AAAA) record to resolve the external Autodiscover Service URL.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c64b3-114">Admins du domaine</span><span class="sxs-lookup"><span data-stu-id="c64b3-114">Domain Admins</span></span></p>
<p><span data-ttu-id="c64b3-115">DnsAdmins</span><span class="sxs-lookup"><span data-stu-id="c64b3-115">DnsAdmins</span></span></p></td>
<td><p><span data-ttu-id="c64b3-116"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Création d’enregistrements DNS pour le service de découverte automatique dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c64b3-116"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Creating DNS records for the Autodiscover Service in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c64b3-117">Modifier les certificats</span><span class="sxs-lookup"><span data-stu-id="c64b3-117">Modify certificates</span></span></p></td>
<td><p><span data-ttu-id="c64b3-118">Ajouter des entrées d’autres noms de sujet aux certificats suivants pour prendre en charge les connexions sécurisées pour les utilisateurs mobiles :</span><span class="sxs-lookup"><span data-stu-id="c64b3-118">Add subject alternative name entries to the following certificates to support secure connections for mobile users:</span></span></p>
<ul>
<li><p><span data-ttu-id="c64b3-119">Certificat directeur</span><span class="sxs-lookup"><span data-stu-id="c64b3-119">Director certificate</span></span></p></li>
<li><p><span data-ttu-id="c64b3-120">Certificat de pool frontal</span><span class="sxs-lookup"><span data-stu-id="c64b3-120">Front End pool certificate</span></span></p></li>
<li><p><span data-ttu-id="c64b3-121">certificat de proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="c64b3-121">Reverse proxy certificate</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c64b3-122">Administrateur local</span><span class="sxs-lookup"><span data-stu-id="c64b3-122">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="c64b3-123"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modification des certificats pour la mobilité dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c64b3-123"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modifying certificates for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c64b3-124">Configurer le proxy inverse</span><span class="sxs-lookup"><span data-stu-id="c64b3-124">Configure the reverse proxy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c64b3-125">Affecter des certificats mis à jour avec d’autres noms de sujet à l’écouteur SSL (Secure Sockets Layer)</span><span class="sxs-lookup"><span data-stu-id="c64b3-125">Assign certificates updated with subject alternative names to the Secure Sockets Layer (SSL) Listener.</span></span></p></li>
<li><p><span data-ttu-id="c64b3-126">Reconfigurez la règle de publication Web pour l’URL du service de découverte automatique externe.</span><span class="sxs-lookup"><span data-stu-id="c64b3-126">Reconfigure the web publishing rule for the external Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="c64b3-127">Assurez-vous qu’il existe une règle de publication Web pour l’URL de services Web Lync Server 2013 externe sur votre pool frontal.</span><span class="sxs-lookup"><span data-stu-id="c64b3-127">Be sure that a web publishing rule exists for the external Lync Server 2013 Web Services URL on your Front End pool.</span></span></p></li>
</ul>
<p><span data-ttu-id="c64b3-128">Ou</span><span class="sxs-lookup"><span data-stu-id="c64b3-128">Or</span></span></p>
<ul>
<li><p><span data-ttu-id="c64b3-129">Si vous choisissez d’utiliser le protocole HTTP pour la demande de découverte automatique initiale et de ne pas mettre à jour les listes des autres noms de sujet sur les certificats, configurez une nouvelle règle de publication Web ou reconfigurez une règle de publication existante pour le port 80 HTTP.</span><span class="sxs-lookup"><span data-stu-id="c64b3-129">If you choose to use HTTP for the initial Autodiscover request and do not update subject alternative name lists on the certificates, configure a new web publishing rule or reconfigure an existing publishing rule for port 80 HTTP.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c64b3-130">Administrateur local</span><span class="sxs-lookup"><span data-stu-id="c64b3-130">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="c64b3-131"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuration du proxy inverse pour la mobilité dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c64b3-131"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c64b3-132">Tester votre déploiement de mobilité pour Lync 2010 mobile à l’aide du service de mobilité MCX</span><span class="sxs-lookup"><span data-stu-id="c64b3-132">Test your mobility deployment for Lync 2010 Mobile using the Mcx Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="c64b3-133">Exécuter <strong>Test-CsMcxP2PIM</strong> pour tester l’envoi d’un message instantané d’une personne à une autre</span><span class="sxs-lookup"><span data-stu-id="c64b3-133">Run <strong>Test-CsMcxP2PIM</strong> to test sending an instant message from one person to another.</span></span></p>
<p><span data-ttu-id="c64b3-134">Consultez la documentation de l’applet de commande Lync Server Management Shell pour <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">test-CsMcxP2PIM</a> pour obtenir la liste complète des options.</span><span class="sxs-lookup"><span data-stu-id="c64b3-134">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="c64b3-135">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="c64b3-135">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c64b3-136"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Vérification de votre déploiement de mobilité dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c64b3-136"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c64b3-137">Tester votre déploiement de mobilité pour les clients mobiles Lync 2013 utilisant les composants Web UCWA</span><span class="sxs-lookup"><span data-stu-id="c64b3-137">Test your mobility deployment for Lync 2013 Mobile clients using the UCWA Web components</span></span></p></td>
<td><p><span data-ttu-id="c64b3-138">La cmdlet <strong>test-CsUcwaConference</strong> permet de tester et de vérifier que les utilisateurs de test prédéfinis ou une paire d’utilisateurs réels peuvent utiliser UCWA pour créer et participer à une conférence.</span><span class="sxs-lookup"><span data-stu-id="c64b3-138">Use the <strong>Test-CsUcwaConference</strong> cmdlet to test and verify that pre-defined test users or a pair of actual users can use UCWA to create and participate in a conference.</span></span></p>
<p><span data-ttu-id="c64b3-139">Consultez la documentation de l’applet de commande Lync Server Management Shell pour <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">test-CsUcwaConference</a> pour obtenir la liste complète des options.</span><span class="sxs-lookup"><span data-stu-id="c64b3-139">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="c64b3-140">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="c64b3-140">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c64b3-141"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Vérification de votre déploiement de mobilité dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c64b3-141"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c64b3-142">Configurer les notifications de type push</span><span class="sxs-lookup"><span data-stu-id="c64b3-142">Configure for push notifications</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c64b3-143">Pour les serveurs Edge Lync Server 2013, ajoutez un fournisseur d’hébergement Lync Server Online et configurez la Fédération des fournisseurs d’hébergement.</span><span class="sxs-lookup"><span data-stu-id="c64b3-143">For Lync Server 2013 Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="c64b3-144">Pour les serveurs Edge Lync Server 2010, ajoutez un fournisseur d’hébergement Lync Server Online et configurez la Fédération des fournisseurs d’hébergement.</span><span class="sxs-lookup"><span data-stu-id="c64b3-144">For Lync Server 2010  Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="c64b3-145">Pour les serveurs Edge Office Communications Server 2007 R2, ajoutez un partenaire fédéré.</span><span class="sxs-lookup"><span data-stu-id="c64b3-145">For Office Communications Server 2007 R2 Edge Servers, add a federated partner.</span></span></p></li>
<li><p><span data-ttu-id="c64b3-146">Si vous souhaitez prendre en charge les notifications de type push sur un réseau Wi-Fi, configurer une règle de pare-feu sortante pour le port TCP 5223</span><span class="sxs-lookup"><span data-stu-id="c64b3-146">If you want to support push notifications over a Wi-Fi network, configure a firewall rule outbound for TCP port 5223.</span></span></p></li>
<li><p><span data-ttu-id="c64b3-147">Utiliser l’applet de commande <strong>Set-CsPushNotificationConfiguration</strong> pour activer les notifications de type push vers le service APNS (Apple Push Notification Service) et le service MPNS (Microsoft Push Notification Service).</span><span class="sxs-lookup"><span data-stu-id="c64b3-147">Use the <strong>Set-CsPushNotificationConfiguration</strong> cmdlet to enable push notifications to the Apple Push Notification Service (APNS) and Microsoft Push Notification Service (MPNS).</span></span> <span data-ttu-id="c64b3-148">Cette fonctionnalité est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="c64b3-148">This feature is disabled by default.</span></span></p></li>
<li><p><span data-ttu-id="c64b3-149">Utiliser l’applet de commande <strong>Test-CsFederatedPartner</strong> pour tester la configuration de la fédération et l’applet de commande <strong>Test-CsMCXPushNotification</strong> pour tester les notifications de type push</span><span class="sxs-lookup"><span data-stu-id="c64b3-149">Use the <strong>Test-CsFederatedPartner</strong> cmdlet to test the federation configuration and the <strong>Test-CsMCXPushNotification</strong> cmdlet to test push notifications.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="c64b3-150">Les notifications de type transmission sont utilisées pour les clients mobiles Lync 2010 sur les appareils Apple et Windows Phone</span><span class="sxs-lookup"><span data-stu-id="c64b3-150">Push notifications are used for Lync 2010 Mobile clients on Apple devices and Windows Phone</span></span><BR><span data-ttu-id="c64b3-151">La notification de type « transmission » est requise pour les clients mobiles Lync 2013 sur Windows Phone uniquement</span><span class="sxs-lookup"><span data-stu-id="c64b3-151">Push notification is required for Lync 2013 Mobile clients on Windows Phone only</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="c64b3-152">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="c64b3-152">RtcUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="c64b3-153"><a href="lync-server-2013-configuring-for-push-notifications.md">Configuration des notifications de type transmission dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c64b3-153"><a href="lync-server-2013-configuring-for-push-notifications.md">Configuring for push notifications in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c64b3-154">Configurer la stratégie de mobilité</span><span class="sxs-lookup"><span data-stu-id="c64b3-154">Configure mobility policy</span></span></p></td>
<td><p><span data-ttu-id="c64b3-155">Utilisez l’applet de commande <strong>Set-CsMobilityPolicy</strong> pour activer ou désactiver :</span><span class="sxs-lookup"><span data-stu-id="c64b3-155">Use the <strong>Set-CsMobilityPolicy</strong> cmdlet to allow or disallow:</span></span></p>
<ul>
<li><p><span data-ttu-id="c64b3-156">Appel via le Bureau</span><span class="sxs-lookup"><span data-stu-id="c64b3-156">Call via Work</span></span></p></li>
<li><p><span data-ttu-id="c64b3-157">Activer l’audio IP et la vidéo IP</span><span class="sxs-lookup"><span data-stu-id="c64b3-157">Enable IP Audio and IP Video</span></span></p></li>
<li><p><span data-ttu-id="c64b3-158">Exiger WiFi pour l’audio IP et/ou la vidéo IP</span><span class="sxs-lookup"><span data-stu-id="c64b3-158">Require WiFi for IP Audio and/or IP Video</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c64b3-159">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="c64b3-159">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c64b3-160"><a href="lync-server-2013-configuring-mobility-policy.md">Configuration de la stratégie de mobilité dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c64b3-160"><a href="lync-server-2013-configuring-mobility-policy.md">Configuring mobility policy in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

