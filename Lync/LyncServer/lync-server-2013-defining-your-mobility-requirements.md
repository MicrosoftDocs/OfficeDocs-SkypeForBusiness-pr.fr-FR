---
title: 'Lync Server 2013 : définition de vos besoins en matière de mobilité'
description: 'Lync Server 2013 : définition de vos besoins en matière de mobilité.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your mobility requirements
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690039(v=OCS.15)
ms:contentKeyID: 48185226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fbc1a443946f0c879397f41628cfe788b428ff6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545540"
---
# <a name="defining-your-mobility-requirements-for-lync-server-2013"></a><span data-ttu-id="c7310-103">Définition de la configuration requise pour la mobilité pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7310-103">Defining your mobility requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7310-104">_**Dernière modification de la rubrique :** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="c7310-104">_**Topic Last Modified:** 2013-02-14_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="c7310-105">Lors de la phase de planification de la fonctionnalité de mobilité Lync Server 2013, lorsque vous utilisez les clients mobiles Lync 2010 mobile et Lync 2013, vous prenez des décisions qui déterminent vos étapes de déploiement.</span><span class="sxs-lookup"><span data-stu-id="c7310-105">During the planning phase for the Lync Server 2013 mobility feature, when you are using Lync 2010 Mobile and Lync 2013 Mobile clients, you make decisions that determine your deployment steps.</span></span>

<span data-ttu-id="c7310-106">Voici les décisions que vous devez prendre en compte :</span><span class="sxs-lookup"><span data-stu-id="c7310-106">Here are the decisions that you must consider:</span></span>

  - <span data-ttu-id="c7310-107">**Souhaitez-vous utiliser la découverte automatique des clients mobiles Lync ?**</span><span class="sxs-lookup"><span data-stu-id="c7310-107">**Do you want to use automatic discovery for Lync mobile clients?**</span></span>
    
    <span data-ttu-id="c7310-108">Si vous souhaitez prendre en charge la découverte automatique, vous devez créer des enregistrements DNS (Domain Name System) internes et externes, ajouter d’autres noms de sujet aux certificats sur les serveurs frontaux, les directeurs et le proxy inverse, et modifier les règles de publication existantes sur le proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="c7310-108">If you want to support automatic discovery, you need to create new internal and external Domain Name System (DNS) records, add subject alternative names to certificates on the Front End Servers, Directors, and reverse proxy, and modify the existing publishing rules on the reverse proxy.</span></span> <span data-ttu-id="c7310-109">Pour plus d’informations, voir [Technical Requirements for Mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="c7310-109">For details, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span> <span data-ttu-id="c7310-110">La découverte automatique permet aux utilisateurs de localiser automatiquement les services Web Lync Server 2013 depuis n’importe quel emplacement à l’intérieur ou à l’extérieur du réseau d’entreprise, sans avoir à entrer des URL dans leurs paramètres d’appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="c7310-110">With automatic discovery, users can automatically locate Lync Server 2013 Web Services from anywhere inside or outside the corporate network, without entering URLs in their mobile device settings.</span></span>
    
    <span data-ttu-id="c7310-111">Si vous utilisez des paramètres manuels au lieu de la découverte automatique, les utilisateurs mobiles doivent entrer manuellement les URL suivantes dans leurs appareils mobiles :</span><span class="sxs-lookup"><span data-stu-id="c7310-111">If you use manual settings instead of automatic discovery, mobile users need to manually enter the following URLs in their mobile devices:</span></span>
    
      - <span data-ttu-id="c7310-112">https:// \<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.svc/root pour l’accès externe</span><span class="sxs-lookup"><span data-stu-id="c7310-112">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access</span></span>
    
      - <span data-ttu-id="c7310-113">https:// \<IntPoolFQDN\> /Autodiscover/autodiscoverservice. svc/root pour l’accès interne</span><span class="sxs-lookup"><span data-stu-id="c7310-113">https://\<IntPoolFQDN\>/AutoDiscover/ autodiscoverservice.svc/Root for internal access</span></span>
    
    <span data-ttu-id="c7310-p102">Nous vous conseillons vivement d’utiliser la découverte automatique. Les paramètres manuels s’utilisent principalement à des fins de dépannage.</span><span class="sxs-lookup"><span data-stu-id="c7310-p102">We strongly recommend using automatic discovery. The primary use of manual settings is for troubleshooting.</span></span>

  - <span data-ttu-id="c7310-116">**Si vous décidez de prendre en charge la découverte automatique, souhaitez-vous mettre à jour les certificats sur le proxy inverse avec d’autres noms de sujet pour chaque domaine IP ?**</span><span class="sxs-lookup"><span data-stu-id="c7310-116">**If you decide to support automatic discovery, are you willing to update certificates on the reverse proxy with subject alternative names for each SIP domain?**</span></span>
    
    <span data-ttu-id="c7310-117">Si vous avez de nombreux domaines IP, la mise à jour des certificats publics sur le proxy inverse peut être très coûteuse.</span><span class="sxs-lookup"><span data-stu-id="c7310-117">If you have many SIP domains, updating public certificates on the reverse proxy can become very expensive.</span></span> <span data-ttu-id="c7310-118">Dans ce cas, vous pouvez choisir d’implémenter la découverte automatique de sorte que la demande de service de découverte automatique initiale utilise le protocole HTTP sur le port 80, au lieu d’utiliser le protocole HTTPs sur le port 443.</span><span class="sxs-lookup"><span data-stu-id="c7310-118">If this is the case, you can choose to implement automatic discovery so that the initial Autodiscover Service request uses HTTP on port 80, instead of using HTTPS on port 443.</span></span> <span data-ttu-id="c7310-119">Toutefois, il ne s’agit pas de l’approche recommandée.</span><span class="sxs-lookup"><span data-stu-id="c7310-119">However, this is not the recommended approach.</span></span> <span data-ttu-id="c7310-120">Si vous décidez de choisir cette alternative, vous n’avez pas besoin de mettre à jour les certificats sur le proxy inverse, mais vous devez créer une règle de publication Web pour HTTP sur le port 80.</span><span class="sxs-lookup"><span data-stu-id="c7310-120">If you decide to choose this alternative, you do not need to update the certificates on the reverse proxy, but you need to create a web publishing rule for HTTP on port 80.</span></span> <span data-ttu-id="c7310-121">Pour plus d’informations, reportez-vous à [configuration technique requise pour la mobilité dans Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="c7310-121">For more details, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="c7310-122">**Souhaitez-vous prendre en charge les clients mobiles Lync internes et externes au réseau d’entreprise, ou uniquement ceux internes au réseau d’entreprise ?**</span><span class="sxs-lookup"><span data-stu-id="c7310-122">**Do you want to support Lync mobile clients both internal and external to the corporate network, or support clients only inside the corporate network?**</span></span>
    
    <span data-ttu-id="c7310-p104">Lorsque vous prenez en charge les clients mobiles internes et externes à votre réseau, les appareils mobiles peuvent accéder aux fonctionnalités de mobilité depuis n’importe quel emplacement. La configuration par défaut consiste à prendre en charge les clients internes et externes au réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="c7310-p104">If you want to support mobile clients internal and external to your network, mobile devices can access mobility features from any location. The default configuration is to support clients both internal and external to the corporate network.</span></span>
    
    <span data-ttu-id="c7310-125">Bien que la configuration par défaut permette au trafic des clients mobiles de traverser le site externe, vous pouvez limiter ce trafic au réseau d’entreprise interne.</span><span class="sxs-lookup"><span data-stu-id="c7310-125">Although the default configuration enables mobile client traffic to go through the external site, you can restrict mobile client traffic to the internal corporate network.</span></span> <span data-ttu-id="c7310-126">Dans ce cas, les utilisateurs peuvent utiliser les applications mobiles Lync sur leur appareil mobile uniquement lorsqu’ils se trouvent sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="c7310-126">When you restrict the traffic to the internal network, users can use Lync mobile applications on their mobile devices only when they are inside the network.</span></span>
    
    <span data-ttu-id="c7310-127">Pour les déploiements qui prennent en charge la mobilité à l’aide du service de mobilité MCX et de Lync 2010 mobile, vous exécutez l’applet **de commande Set-CsMcxConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="c7310-127">For deployments that support mobility using the Mcx mobility service and Lync 2010 Mobile, you run the **Set-CsMcxConfiguration** cmdlet.</span></span> <span data-ttu-id="c7310-128">Pour définir la mobilité pour un usage interne uniquement, vous devez utiliser une commande similaire à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="c7310-128">To set mobility for internal use only, you would use a command similar to the following:</span></span>
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c7310-129">Aucune configuration supplémentaire n’est requise pour UCWA.</span><span class="sxs-lookup"><span data-stu-id="c7310-129">There are no additional configurations required for UCWA.</span></span> <span data-ttu-id="c7310-130">UCWA n’a pas de configuration équivalente uniquement en interne.</span><span class="sxs-lookup"><span data-stu-id="c7310-130">UCWA does not have an equivalent internal-only configuration.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c7310-131">Si vous utilisez un &nbsp; serveur frontal ou des pools frontaux Lync server 2013 et <STRONG>que vous ne disposez pas</STRONG> &nbsp; de serveurs frontaux ou de pools frontaux Lync Server 2010, <STRONG>il n’est pas nécessaire d’utiliser la persistance basée sur les cookies</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="c7310-131">If you are using a Lync Server 2013&nbsp;Front End Server or Front End pools and <STRONG>you do not have</STRONG> any Lync Server 2010&nbsp;Front End Servers or Front End pools, <STRONG>there is no requirement for cookie-based persistence</STRONG>.</span></span> <span data-ttu-id="c7310-132">Si vous avez besoin de conserver les &nbsp; serveurs frontaux ou les pools frontaux Lync server 2010, les mêmes règles s’appliquent toujours comme dans Lync server 2010 pour la persistance basée sur les cookies.</span><span class="sxs-lookup"><span data-stu-id="c7310-132">If you need to retain any Lync Server 2010&nbsp;Front End Servers or Front End pools, the same rules still apply as in Lync Server 2010 for cookie-based persistence.</span></span>

    
    </div>

  - <span data-ttu-id="c7310-133">**Souhaitez-vous prendre en charge les notifications push pour les appareils Apple iOS et Windows Phone ?**</span><span class="sxs-lookup"><span data-stu-id="c7310-133">**Do you want to support push notifications for Apple iOS devices and Windows Phones?**</span></span>
    
    <span data-ttu-id="c7310-134">Si vous prenez en charge les notifications push, les appareils Apple iOS et Windows Phones reçoivent une notification des événements qui se produisent pendant que l’application mobile est inactive.</span><span class="sxs-lookup"><span data-stu-id="c7310-134">If you support push notifications, supported Apple iOS devices and Windows Phones receive a notification of events that occur when the mobile application is inactive.</span></span> <span data-ttu-id="c7310-135">Vous devez configurer votre serveur Edge de sorte qu’il dispose d’une relation de Fédération avec le service de notifications d’envoi sur le Cloud de Lync Server, qui se trouve dans le centre de contenu Lync Online et exécute une applet de commande pour activer les notifications de transmission.</span><span class="sxs-lookup"><span data-stu-id="c7310-135">You must configure your Edge Server to have a federation relationship with the cloud-based Lync Server Push Notification Service, which is located in the Lync Online datacenter, and run a cmdlet to enable push notifications.</span></span>
    
    <span data-ttu-id="c7310-136">Si vous souhaitez prendre en charge les notifications de type transmission sur votre réseau Wi-Fi, en plus de prendre en charge les notifications de type transmission sur les réseaux de données ou 3G des fournisseurs d’appareils mobiles, vous devez ouvrir le port 5223 sortant sur votre entreprise Wi-Fi réseau.</span><span class="sxs-lookup"><span data-stu-id="c7310-136">If you want to support push notifications over your Wi-Fi network, in addition to supporting push notifications over the mobile device providers' 3G or data networks, you must open port 5223 outbound on your enterprise Wi-Fi network.</span></span> <span data-ttu-id="c7310-137">Le fait de prendre en charge les notifications push sur le réseau Wi-Fi permet de prendre en charge les appareils mobiles qui utilisent uniquement le réseau Wi-Fi et ceux bénéficiant d’une mauvaise réception à l’intérieur.</span><span class="sxs-lookup"><span data-stu-id="c7310-137">Supporting push notifications over the Wi-Fi network supports mobile devices that use only Wi-Fi and mobile devices that have poor indoor reception.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c7310-138">L’ouverture du port TCP 5223 est requise uniquement lors de la prise en charge des appareils Apple exécutant le client mobile Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="c7310-138">Opening port TCP 5223 is required only when supporting Apple devices running the Lync 2010 Mobile client.</span></span>

    
    </div>
    
    <span data-ttu-id="c7310-139">Si vous ne prenez pas en charge les notifications de type diffuser, les utilisateurs des appareils mobiles Apple et des téléphones Windows ne pourront pas découvrir les événements, tels que les invitations de messagerie instantanée ou les messages manqués, qui se produisent lorsque l’application mobile est inactive.</span><span class="sxs-lookup"><span data-stu-id="c7310-139">If you do not support push notifications, users of Apple mobile devices and Windows Phones will not find out about events—such as instant message invitations or missed messages—that occur when the mobile application is inactive.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c7310-140">Les clients mobiles Lync 2013 sur les appareils Apple ne nécessitent pas de notification de transmission.</span><span class="sxs-lookup"><span data-stu-id="c7310-140">Lync 2013 Mobile clients on Apple devices do not require push notification.</span></span> <span data-ttu-id="c7310-141">Les clients mobiles Lync 2013 sur Windows Phone utilisent la notification de transmission.</span><span class="sxs-lookup"><span data-stu-id="c7310-141">The Lync 2013 Mobile clients on Windows Phone use push notification.</span></span> <span data-ttu-id="c7310-142">La planification de la notification de transmission et le centre de notifications poussés restent identiques pour Lync mobile sur Windows Phone et les appareils Apple qui ne peuvent pas exécuter le client mobile Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="c7310-142">Planning for push notification and the push notification clearinghouse remain the same for Lync Mobile on Windows Phone and Apple devices that are not able to run the Lync 2013 Mobile client.</span></span>

    
    </div>

  - <span data-ttu-id="c7310-143">**Voulez-vous que tous les utilisateurs aient accès aux fonctionnalités de mobilité ou voulez-vous être en mesure de spécifier les utilisateurs qui ont accès à ces fonctionnalités ?**</span><span class="sxs-lookup"><span data-stu-id="c7310-143">**Do you want all users to have access to mobility features, or do you want to be able to specify which users have access to these features?**</span></span>
    
    <span data-ttu-id="c7310-144">Le tableau décrit les fonctionnalités disponibles pour les utilisateurs dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c7310-144">The table describes features available to users in Lync Server 2013.</span></span> <span data-ttu-id="c7310-145">Les paramètres par défaut autorisent les appels via le bureau, la voix sur IP (VoIP) et l’activation de la mobilité.</span><span class="sxs-lookup"><span data-stu-id="c7310-145">The defaults allow Call via Work, allow Voice over IP (VoIP), and enable Mobility.</span></span> <span data-ttu-id="c7310-146">Voici l’ensemble complet des options disponibles :</span><span class="sxs-lookup"><span data-stu-id="c7310-146">Here is the full set of available options:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="c7310-147">Nom/étendue de la fonctionnalité/paramètre (les noms de paramètres de stratégie ne peuvent pas être identiques)</span><span class="sxs-lookup"><span data-stu-id="c7310-147">Feature/Parameter Name/Scope (Policy parameter names may not be the same)</span></span></th>
    <th><span data-ttu-id="c7310-148">Description</span><span class="sxs-lookup"><span data-stu-id="c7310-148">Description</span></span></th>
    <th><span data-ttu-id="c7310-149">Introduit</span><span class="sxs-lookup"><span data-stu-id="c7310-149">Introduced</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="c7310-150">Activer la mobilité</span><span class="sxs-lookup"><span data-stu-id="c7310-150">Enable Mobility</span></span></p>
    <p><span data-ttu-id="c7310-151">Nom du paramètre : <code>EnableMobility</code></span><span class="sxs-lookup"><span data-stu-id="c7310-151">Parameter Name : <code>EnableMobility</code></span></span></p>
    <p><span data-ttu-id="c7310-152">Étendue : Global/site/User</span><span class="sxs-lookup"><span data-stu-id="c7310-152">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="c7310-153">Paramètres d’administration pour contrôler les utilisateurs d’une étendue donnée sur laquelle Lync mobile est installé, si la stratégie est définie sur false, l’utilisateur ne peut pas se connecter au client.</span><span class="sxs-lookup"><span data-stu-id="c7310-153">Administrative setting to control users in a given scope that have the Lync Mobile installed, If the policy is set to False, the user would not be able to sign into the client.</span></span></p>
    <p><span data-ttu-id="c7310-154">Le paramètre par défaut est True.</span><span class="sxs-lookup"><span data-stu-id="c7310-154">The default setting is True.</span></span></p></td>
    <td><p><span data-ttu-id="c7310-155">Mise à jour cumulative pour Lync Server 2010 : novembre 2011</span><span class="sxs-lookup"><span data-stu-id="c7310-155">Cumulative Update for Lync Server 2010: November 2011</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c7310-156">Activer la voix en extérieur</span><span class="sxs-lookup"><span data-stu-id="c7310-156">Enable Outside Voice</span></span></p>
    <p><span data-ttu-id="c7310-157">Nom du paramètre : <code>EnableOutsideVoice</code></span><span class="sxs-lookup"><span data-stu-id="c7310-157">Parameter Name : <code>EnableOutsideVoice</code></span></span></p>
    <p><span data-ttu-id="c7310-158">Étendue : Global/site/User</span><span class="sxs-lookup"><span data-stu-id="c7310-158">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="c7310-159">Contrôle la capacité d’un utilisateur à utiliser l’appel via le bureau, une fonctionnalité qui permet aux utilisateurs de passer et de recevoir des appels à l’aide de leur numéro professionnel au lieu de leur numéro de téléphone mobile.</span><span class="sxs-lookup"><span data-stu-id="c7310-159">Controls a user’s ability to use Call Via Work, a feature that enables users to make and receive calls by using their work number instead of their mobile number.</span></span> <span data-ttu-id="c7310-160">Si la valeur est définie sur false, l’utilisateur ne peut pas passer ou recevoir des appels à l’aide de son numéro de travail à partir de son appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="c7310-160">If set to False, the user will not be able to make or receive calls by using their work number from their mobile device.</span></span></p>
    <p><span data-ttu-id="c7310-161">Le paramètre par défaut est true.</span><span class="sxs-lookup"><span data-stu-id="c7310-161">The default setting is True</span></span></p></td>
    <td><p><span data-ttu-id="c7310-162">Mise à jour cumulative pour Lync Server 2010 : novembre 2011</span><span class="sxs-lookup"><span data-stu-id="c7310-162">Cumulative Update for Lync Server 2010: November 2011</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="c7310-163">Activer l’audio et la vidéo IP</span><span class="sxs-lookup"><span data-stu-id="c7310-163">Enable IP Audio and Video</span></span></p>
    <p><span data-ttu-id="c7310-164">Nom du paramètre : <code>EnableIPAudioVideo</code></span><span class="sxs-lookup"><span data-stu-id="c7310-164">Parameter Name : <code>EnableIPAudioVideo</code></span></span></p>
    <p><span data-ttu-id="c7310-165">Étendue : Global/site/User</span><span class="sxs-lookup"><span data-stu-id="c7310-165">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="c7310-166">Contrôle si un utilisateur peut utiliser VoIP pour passer ou recevoir des appels vocaux ou vidéo sur son appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="c7310-166">Controls whether a user can use VoIP to make or receive voice or video calls on their mobile device.</span></span> <span data-ttu-id="c7310-167">Si la valeur est définie sur false, l’utilisateur ne sera pas en mesure d’effectuer ou de recevoir des appels VoIP ou vidéo sur son appareil.</span><span class="sxs-lookup"><span data-stu-id="c7310-167">If set to False, the user will not be able to make or receive VoIP or video calls on their device.</span></span></p>
    <p><span data-ttu-id="c7310-168">Le paramètre par défaut est True.</span><span class="sxs-lookup"><span data-stu-id="c7310-168">The default setting is True.</span></span></p></td>
    <td><p><span data-ttu-id="c7310-169">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7310-169">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c7310-170">Exiger WiFi pour l’audio IP</span><span class="sxs-lookup"><span data-stu-id="c7310-170">Require WiFi for IP Audio</span></span></p>
    <p><span data-ttu-id="c7310-171">Nom du paramètre : <code>RequireWiFiForIPAudio</code></span><span class="sxs-lookup"><span data-stu-id="c7310-171">Parameter Name : <code>RequireWiFiForIPAudio</code></span></span></p>
    <p><span data-ttu-id="c7310-172">Étendue : Global/site/User</span><span class="sxs-lookup"><span data-stu-id="c7310-172">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="c7310-173">Ce paramètre définit si le client devra passer et recevoir des appels via VoIP sur WiFi au lieu du réseau de données cellulaires.</span><span class="sxs-lookup"><span data-stu-id="c7310-173">This setting defines whether the client will be required to make and receive calls over VoIP on WiFi instead of the cellular data network.</span></span> <span data-ttu-id="c7310-174">Si la valeur est définie sur true, l’utilisateur peut passer et recevoir des appels VoIP uniquement lorsqu’il est connecté à un réseau WiFi.</span><span class="sxs-lookup"><span data-stu-id="c7310-174">If set to True, the user can make and receive VoIP calls only when connected to a WiFi network.</span></span></p>
    <p><span data-ttu-id="c7310-175">Le paramètre par défaut est False.</span><span class="sxs-lookup"><span data-stu-id="c7310-175">The default setting is False.</span></span></p></td>
    <td><p><span data-ttu-id="c7310-176">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7310-176">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="c7310-177">Exiger WiFi pour la vidéo IP</span><span class="sxs-lookup"><span data-stu-id="c7310-177">Require WiFi for IP Video</span></span></p>
    <p><span data-ttu-id="c7310-178">Nom du paramètre : <code>RequireWiFiForIPVideo</code></span><span class="sxs-lookup"><span data-stu-id="c7310-178">Parameter Name : <code>RequireWiFiForIPVideo</code></span></span></p>
    <p><span data-ttu-id="c7310-179">Étendue : Global/site/User</span><span class="sxs-lookup"><span data-stu-id="c7310-179">Scope: Global/Site/User</span></span></p></td>
    <td><p><span data-ttu-id="c7310-180">Ce paramètre définit si le client devra passer et recevoir des appels vidéo sur Wi-Fi au lieu de le faire sur le réseau de données cellulaires.</span><span class="sxs-lookup"><span data-stu-id="c7310-180">This setting defines whether the client will be required to make and receive video calls on Wi-Fi instead of on the cellular data network.</span></span> <span data-ttu-id="c7310-181">Si la valeur est définie sur true, l’utilisateur peut passer et recevoir des appels vidéo uniquement lorsqu’il est connecté à un réseau Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="c7310-181">If set to True, the user can make and receive video calls only when connected to a Wi-Fi network.</span></span></p>
    <p><span data-ttu-id="c7310-182">Le paramètre par défaut est False.</span><span class="sxs-lookup"><span data-stu-id="c7310-182">The default setting is False.</span></span></p></td>
    <td><p><span data-ttu-id="c7310-183">Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7310-183">Microsoft Lync Server 2013</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="c7310-184">Pour obtenir une description des paramètres de stratégie que vous pouvez configurer et gérer les stratégies, consultez les rubrique [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), [Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) et [Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy).</span><span class="sxs-lookup"><span data-stu-id="c7310-184">For a description of the policy settings that you can configure, and how to manage the policies, see [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), [Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) and [Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy).</span></span>

  - <span data-ttu-id="c7310-185">**Souhaitez-vous que les utilisateurs qui ne sont pas activés pour Voix Entreprise puissent utiliser la fonctionnalité Cliquez pour participer afin de rejoindre des conférences ?**</span><span class="sxs-lookup"><span data-stu-id="c7310-185">**Do you want users who are not enabled for Enterprise Voice to be able to use Click to Join to join conferences?**</span></span>
    
    <span data-ttu-id="c7310-186">Pour que les utilisateurs puissent accéder aux fonctionnalités de mobilité et à Appel via le bureau, ils doivent être activés pour Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="c7310-186">For users to have access to mobility features and Call via Work, they must be enabled for Enterprise Voice.</span></span> <span data-ttu-id="c7310-187">Toutefois, les utilisateurs qui ne sont pas activés pour voix entreprise peuvent participer à des conférences en cliquant sur le lien sur leur appareil mobile, s’ils disposent d’une stratégie de voix appropriée.</span><span class="sxs-lookup"><span data-stu-id="c7310-187">However, users who are not enabled for Enterprise Voice can join conferences by clicking the link on their mobile device, if they have an appropriate voice policy assigned to them.</span></span> <span data-ttu-id="c7310-188">Vous pouvez affecter une stratégie de voix spécifique à ces utilisateurs ou vous assurer qu’il existe une stratégie globale ou une stratégie au niveau du site qui s’applique à ces utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c7310-188">You can either assign a specific voice policy to these users or make sure that a global policy or site-level policy exists that applies to them.</span></span> <span data-ttu-id="c7310-189">La stratégie de voix que vous affectez doit avoir des itinéraires et des itinéraires d’utilisation du réseau téléphonique commuté (PSTN) qui définissent les domaines dans lesquels les utilisateurs peuvent participer à une conférence.</span><span class="sxs-lookup"><span data-stu-id="c7310-189">The voice policy that you assign must have public switched telephone network (PSTN) usage records and routes that define the areas to which users can dial out to join a conference.</span></span> <span data-ttu-id="c7310-190">Pour plus d’informations sur la stratégie de voix, les enregistrements d’utilisation RTC et les itinéraires, voir [Configuration des stratégies de voix, des enregistrements d’utilisation PSTN et des itinéraires des communications vocales dans Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="c7310-190">For details about setting voice policy, PSTN usage records, and routes, see [Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c7310-191">Les utilisateurs mobiles qui souhaitent utiliser l’option Cliquer pour rejoindre nécessitent une stratégie de voix, ainsi que les enregistrements d’utilisation RTC et les itinéraires vocaux associés, car le fait de cliquer sur le lien sur l’appareil mobile entraîne un appel sortant de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c7310-191">Mobile users who want to use Click to Join require a voice policy, along with the related PSTN usage records and voice routes, because clicking the link on the mobile device results in an outbound call from Lync Server 2013.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="c7310-192">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c7310-192">See Also</span></span>


[<span data-ttu-id="c7310-193">Configuration technique requise pour la mobilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7310-193">Technical requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-mobility.md)  


[<span data-ttu-id="c7310-194">Configuration des stratégies de voix, des enregistrements d’utilisation RTC et des itinéraires des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7310-194">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

