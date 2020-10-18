---
title: 'Lync Server 2013 : topologies et composants pour la mobilité'
description: 'Lync Server 2013 : topologies et composants pour la mobilité.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for mobility
ms:assetid: be3cae7a-095d-4785-91ba-6fac99eba92a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690037(v=OCS.15)
ms:contentKeyID: 48185282
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 731991c3395bd3014270430483c6047dd5487185
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576020"
---
# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a><span data-ttu-id="bd092-103">Topologies et composants pour la mobilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd092-103">Topologies and components for mobility in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd092-104">_**Dernière modification de la rubrique :** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="bd092-104">_**Topic Last Modified:** 2013-02-17_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="bd092-105">Pour prendre en charge les applications mobiles Lync sur des appareils mobiles, Lync Server 2013 fournit trois services : Lync Server 2013 MCX Mobility service, Lync Server 2013 Autodiscover Service et Lync Server 2013 service de notification poussé.</span><span class="sxs-lookup"><span data-stu-id="bd092-105">To support Lync mobile applications on mobile devices, Lync Server 2013 provides three services: Lync Server 2013 Mcx Mobility Service, Lync Server 2013 Autodiscover Service, and Lync Server 2013 Push Notification Service.</span></span> <span data-ttu-id="bd092-106">Les mises à jour cumulatives pour Lync Server 2013 : février 2013 ajoutent un service gratuit, mais avancé, pour les clients mobiles Lync 2013 — prise en charge de la mobilité via l’utilisation de l’API Web Unified Communications, ou UCWA.</span><span class="sxs-lookup"><span data-stu-id="bd092-106">The Cumulative Updates for Lync Server 2013: February 2013 adds a complimentary, but advanced, service for Lync 2013 Mobile clients—mobility support through the use of the Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="bd092-107">Cette section décrit brièvement ces composants et identifie les topologies Lync Server 2013 qui prennent en charge la mobilité.</span><span class="sxs-lookup"><span data-stu-id="bd092-107">This section briefly describes these components and identifies the Lync Server 2013 topologies that support mobility.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bd092-108">Les services de mobilité sont aussi disponibles dans des déploiements hybrides.</span><span class="sxs-lookup"><span data-stu-id="bd092-108">Mobility services are also available in hybrid deployments.</span></span> <span data-ttu-id="bd092-109">Vous n’êtes pas obligé de déployer des services pour prendre en charge la mobilité si vos utilisateurs sont hébergés en ligne.</span><span class="sxs-lookup"><span data-stu-id="bd092-109">You are not required to deploy services for supporting mobility if your users are homed online.</span></span> <span data-ttu-id="bd092-110">Vous devez définir un paramètre pour le service de découverte automatique pour permettre aux utilisateurs mobiles de trouver leur identité en ligne.</span><span class="sxs-lookup"><span data-stu-id="bd092-110">You do need to define a setting for the Autodiscover Service to enable mobile users to find their online identity.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bd092-111">Si vous planifiez une connectivité utilisateur externe (par exemple, la Fédération, l’accès des utilisateurs externes ou les fonctionnalités de mobilité), vous devez utiliser des serveurs Edge avec le serveur Standard Edition et le serveur frontal ou le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="bd092-111">If you are planning any external user connectivity (for example, federation, external user access, or mobility features), you must use Edge Servers with Standard Edition server and the Front End Server or Front End pool.</span></span> <span data-ttu-id="bd092-112">Le serveur Standard Edition et le serveur frontal ou le pool frontal ne disposent pas des composants nécessaires pour permettre aux utilisateurs externes d’accéder à votre déploiement interne ou au déploiement interne de communiquer avec vos utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="bd092-112">The Standard Edition server and the Front End Server or Front End pool do not have the necessary components to enable external users to access your internal deployment, or for the internal deployment to communicate with your external users.</span></span> <span data-ttu-id="bd092-113">Pour tous les scénarios qui incluent les utilisateurs externes qui collaborent ou communiquent avec des utilisateurs internes, y compris la mobilité, vous devez déployer au moins un serveur Edge et un proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="bd092-113">For all scenarios that include external users collaborating or communicating with internal users, including mobility, you must deploy at least one Edge Server and one reverse proxy.</span></span><BR><span data-ttu-id="bd092-114">La <EM>notification d’envoi</EM> utilise un type de Fédération pour Lync Online Services, qui héberge le centre d’échanges de notifications (échanges).</span><span class="sxs-lookup"><span data-stu-id="bd092-114"><EM>Push notification</EM> uses a type of federation to the Lync Online services, which hosts the Push Notification Clearing House (PNCH).</span></span> <span data-ttu-id="bd092-115">Notifications push désigne les alertes sonores, les alertes à l’écran (texte) et les badges qui sont envoyés par les applications à Apple iPhone, iPad et Windows Phone, lorsque l’appareil mobile est inactif.</span><span class="sxs-lookup"><span data-stu-id="bd092-115">Push notification refers to the sound alerts, on-screen alerts (text), and badges that are pushed by applications to the Apple iPhone, iPad, and Windows Phone, when the mobile device is inactive.</span></span> <span data-ttu-id="bd092-116">ÉCHANGES reçoit des notifications de type transmission de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bd092-116">PNCH receives push notifications from Lync Server.</span></span> <span data-ttu-id="bd092-117">Lorsque échanges reçoit une notification d’un message, échanges transfère une notification aux clients mobiles via le service Apple Notification Services ou le service de notification directe de Lync Server 2013, en fonction du client mobile auquel le message est destiné.</span><span class="sxs-lookup"><span data-stu-id="bd092-117">When PNCH receives a notification of a message, PNCH forwards a notification to mobile clients through either the Apple Push Notification Services or Lync Server 2013 Push Notification Service, based on the mobile client that the message is intended for.</span></span> <span data-ttu-id="bd092-118">Le PNCH est un service obligatoire pour ces clients mobiles.</span><span class="sxs-lookup"><span data-stu-id="bd092-118">PNCH is a required service for these mobile clients.</span></span> <span data-ttu-id="bd092-119">Pour se fédérer à Lync Online, échanges utilise des serveurs Edge et des certificats pour garantir la confidentialité et l’authentification, les stratégies et les enregistrements DNS (Domain Name System) correctement configurés.</span><span class="sxs-lookup"><span data-stu-id="bd092-119">To federate to Lync Online, PNCH uses Edge Servers and certificates to ensure confidentiality and authentication, policies, and correctly configured domain name system (DNS) records.</span></span> <span data-ttu-id="bd092-120">Les clients mobiles Lync Symbian Symbian et Android n’utilisent pas échanges.</span><span class="sxs-lookup"><span data-stu-id="bd092-120">Nokia Symbian and Android-based Lync Mobile clients do not use PNCH.</span></span> <span data-ttu-id="bd092-121">Pour plus d’informations sur la planification et le déploiement des serveurs Edge, consultez la rubrique <A href="lync-server-2013-planning-for-external-user-access.md">planification de l’accès des utilisateurs externes dans Lync server 2013</A> et <A href="lync-server-2013-deploying-external-user-access.md">déploiement de l’accès des utilisateurs externes dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="bd092-121">For details about planning and deploying Edge Servers, see <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external user access in Lync Server 2013</A> and <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="bd092-122">Les clients mobiles Lync 2013 pour les périphériques Apple introduits avec les mises à jour cumulatives pour Lync Server 2013 : février 2013 n’utilisent plus la notification de transmission ou le centre d’échanges de notifications (échanges).</span><span class="sxs-lookup"><span data-stu-id="bd092-122">The Lync 2013 Mobile clients for Apple devices introduced with the Cumulative Updates for Lync Server 2013: February 2013 no longer use push notification or the push notification clearing house (PNCH).</span></span> <span data-ttu-id="bd092-123">Les clients mobiles Lync 2013 sur Windows Phone utilisent toujours la notification de transmission et le (échanges).</span><span class="sxs-lookup"><span data-stu-id="bd092-123">Lync 2013 Mobile clients on Windows Phone still use push notification and the (PNCH).</span></span>



</div>

<div>

## <a name="mobility-components"></a><span data-ttu-id="bd092-124">Composants de mobilité</span><span class="sxs-lookup"><span data-stu-id="bd092-124">Mobility Components</span></span>

<span data-ttu-id="bd092-125">Les services qui prennent en charge la mobilité sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="bd092-125">The services that support mobility are as follows:</span></span>

  - <span data-ttu-id="bd092-126">**API Web de communications unifiées Lync Server 2013 (UCWA)**     Fournit des services pour les communications en temps réel avec des clients mobiles et Web dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd092-126">**Lync Server 2013 Unified Communications Web API (UCWA)**   Provides services for real-time communications with mobile and web clients in Lync Server 2013.</span></span> <span data-ttu-id="bd092-127">Lorsque vous déployez les mises à jour cumulatives pour Lync Server 2013 : février 2013 sur le serveur frontal et le directeur, l’installation crée un répertoire virtuel dans les services Web internes et externes (Ucwa).</span><span class="sxs-lookup"><span data-stu-id="bd092-127">When you deploy the Cumulative Updates for Lync Server 2013: February 2013 to the Front End Server and Director, the installation creates a virtual directory in the internal and external web services (Ucwa).</span></span> <span data-ttu-id="bd092-128">Un composant Web qui fait partie du répertoire virtuel Ucwa accepte les appels des clients à extension UCWA.</span><span class="sxs-lookup"><span data-stu-id="bd092-128">A web component that is part of the Ucwa virtual directory accepts calls from UCWA-enabled clients.</span></span> <span data-ttu-id="bd092-129">Les applications clientes communiquent via une interface REST pour la présence, les contacts, la messagerie instantanée, la voix sur IP, la vidéoconférence et la collaboration.</span><span class="sxs-lookup"><span data-stu-id="bd092-129">The client apps communicate over a REST interface for presence, contacts, instant messaging, VoIP, video conferencing, and collaboration.</span></span> <span data-ttu-id="bd092-130">UCWA utilise un canal basé sur P-GET pour envoyer des événements, tels qu’un appel entrant, un message instantané entrant ou un message à l’application cliente.</span><span class="sxs-lookup"><span data-stu-id="bd092-130">UCWA uses a P-GET based channel to send events, such as an incoming call, incoming instant message, or a message to the client app.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bd092-131"><EM>Rest</EM> ou Representational State Transfer, est un style d’architecture logicielle pour les systèmes distribués qui a été largement adopté sous de nombreuses formes et qui est bien adapté aux exigences des services Web en général.</span><span class="sxs-lookup"><span data-stu-id="bd092-131"><EM>REST</EM> or representational state transfer, is a software architectural style for distributed systems that has been widely adopted in many forms and is well suited to the requirements of Web services in general.</span></span>

    
    </div>

  - <span data-ttu-id="bd092-132">**Service de mobilité Lync Server 2013 (MCX)**     Ce service prend en charge les fonctionnalités Lync, telles que la messagerie instantanée, la présence et les contacts, sur les appareils mobiles.</span><span class="sxs-lookup"><span data-stu-id="bd092-132">**Lync Server 2013 Mobility Service (Mcx)**   This service supports Lync functionality, such as instant messaging (IM), presence, and contacts, on mobile devices.</span></span> <span data-ttu-id="bd092-133">Le service de mobilité est installé sur chaque serveur frontal dans chaque pool qui doit prendre en charge la fonctionnalité Lync sur les appareils mobiles.</span><span class="sxs-lookup"><span data-stu-id="bd092-133">The Mobility Service is installed on every Front End Server in each pool that is to support Lync functionality on mobile devices.</span></span> <span data-ttu-id="bd092-134">Lorsque vous installez Lync Server 2013, un nouveau répertoire virtuel (MCX) est créé sous le site Web interne et le site Web externe sur vos serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="bd092-134">When you install Lync Server 2013, a new virtual directory (Mcx) is created under both the internal website and the external website on your Front End Servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bd092-135">Lync Server 2013 avec les mises à jour cumulatives pour Lync Server 2013 : le 2013 février prend en charge le service de mobilité introduit dans la mise à jour cumulative de Lync Server 2010 : novembre 2011, communément appelée MCX, et le composant Web UCWA.</span><span class="sxs-lookup"><span data-stu-id="bd092-135">Lync Server 2013 with the Cumulative Updates for Lync Server 2013: February 2013 supports both the Mobility service introduced in the Cumulative Update for Lync Server 2010: November 2011, commonly known as Mcx, and the UCWA web component.</span></span> <span data-ttu-id="bd092-136">L’Association de ces deux services de mobilité offre une interopérabilité et une utilisation par les utilisateurs avec les clients mobiles Lync 2010 mobile et Lync 2013 sur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd092-136">The combination of these two mobility services provides interoperability and use by users with Lync 2010 Mobile and Lync 2013 Mobile clients on Lync Server 2013.</span></span>

    
    </div>

  - <span data-ttu-id="bd092-137">Service de découverte **automatique Lync Server 2013**     Ce service identifie l’emplacement de l’utilisateur et permet aux appareils mobiles et à d’autres clients Lync de localiser les ressources, telles que les URL internes et externes des services Web Lync Server 2013, ainsi que l’URL du MCX ou de UCWA, quel que soit l’emplacement réseau.</span><span class="sxs-lookup"><span data-stu-id="bd092-137">**Lync Server 2013 Autodiscover Service**   This service identifies the location of the user and enables mobile devices and other Lync clients to locate resources—such as the internal and external URLs for Lync Server 2013 Web Services, and the URL for the Mcx or UCWA—regardless of network location.</span></span> <span data-ttu-id="bd092-138">La découverte automatique utilise des noms d’hôte codés en dur (lyncdiscoverinternal pour les utilisateurs au sein du réseau ; lyncdiscover pour les utilisateurs en dehors du réseau) et le domaine SIP de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bd092-138">Automatic discovery uses hardcoded host names (lyncdiscoverinternal for users inside the network; lyncdiscover for users outside the network) and the SIP domain of the user.</span></span> <span data-ttu-id="bd092-139">Il prend en charge les connexions client qui utilisent le protocole HTTP ou HTTPs.</span><span class="sxs-lookup"><span data-stu-id="bd092-139">It supports client connections that use either HTTP or HTTPS.</span></span>
    
    <span data-ttu-id="bd092-140">Le service de découverte automatique est installé sur chaque serveur frontal et sur chaque directeur de chaque pool qui prend en charge la fonctionnalité Lync sur les appareils mobiles.</span><span class="sxs-lookup"><span data-stu-id="bd092-140">The Autodiscover Service is installed on every Front End Server and on every Director in each pool that is to support Lync functionality on mobile devices.</span></span> <span data-ttu-id="bd092-141">Lorsque vous installez le service de découverte automatique, un nouveau répertoire virtuel (découverte automatique) est créé sous le site Web interne et le site Web externe, sur les serveurs frontaux et les directeurs.</span><span class="sxs-lookup"><span data-stu-id="bd092-141">When you install the Autodiscover Service, a new virtual directory (Autodiscover) is created under both the internal website and the external website, on both Front End Servers and Directors.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bd092-142">Le service de découverte automatique est répertorié ici, car il reste un composant essentiel lors de la fourniture de services client mobiles.</span><span class="sxs-lookup"><span data-stu-id="bd092-142">The Autodiscover Service is listed here because it remains a critical component when providing mobile client services.</span></span> <span data-ttu-id="bd092-143">Le rôle de découverte automatique dans Lync Server 2013 a été étendu pour fournir des services pour tous les clients.</span><span class="sxs-lookup"><span data-stu-id="bd092-143">The role of Autodiscover in Lync Server 2013 has been expanded to provide services for all clients.</span></span> <span data-ttu-id="bd092-144">Pour plus d’informations sur la planification du service de découverte automatique, voir <A href="lync-server-2013-planning-for-autodiscover.md">Planning for Autodiscover in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="bd092-144">For details about planning for the Autodiscover Service, see <A href="lync-server-2013-planning-for-autodiscover.md">Planning for Autodiscover in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="bd092-145">Service de notifications d' **envoi**     Ce service est basé sur le nuage et se trouve dans le centre de données Lync Online.</span><span class="sxs-lookup"><span data-stu-id="bd092-145">**Push Notification Service**   This service is a cloud-based service that is located in the Lync Online data center.</span></span> <span data-ttu-id="bd092-146">Lorsque l’application mobile Lync sur un périphérique iOS ou Windows Phone pris en charge est inactive, elle ne peut pas répondre à de nouveaux événements, tels qu’une nouvelle invitation de messagerie instantanée, un message instantané manqué, un appel manqué ou une messagerie vocale, car ces appareils ne prennent pas en charge les applications mobiles en cours d’exécution en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="bd092-146">When the Lync mobile application on a supported Apple iOS device or Windows Phone is inactive, it cannot respond to new events, such as a new instant messaging (IM) invitation, a missed instant message, a missed call, or voice mail, because these devices do not support mobile applications running in the background.</span></span> <span data-ttu-id="bd092-147">Dans ce cas, une notification de nouvel événement, appelée notification de *transmission*, est envoyée à l’appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="bd092-147">In these cases, a notification of the new event—called a *push notification*—is sent to the mobile device.</span></span> <span data-ttu-id="bd092-148">Le service de mobilité envoie la notification au service de notifications d’envoi sur le Cloud, qui envoie ensuite la notification au service de notifications d’appels poussés Apple (APNS) (pour les appareils iOS d’Apple pris en charge) ou au service de notifications Microsoft (MPNS) (pour Windows Phone), qui l’envoie ensuite à l’appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="bd092-148">The Mobility Service sends the notification to the cloud-based Push Notification Service, which then sends the notification either to the Apple Push Notification Service (APNS) (for supported Apple iOS devices) or to the Microsoft Push Notification Service (MPNS) (for Windows Phone), which then sends it on to the mobile device.</span></span> <span data-ttu-id="bd092-149">L’utilisateur peut ensuite répondre à la notification sur l’appareil mobile pour activer l’application.</span><span class="sxs-lookup"><span data-stu-id="bd092-149">The user can then respond to the notification on the mobile device to activate the application.</span></span>
    
    <span data-ttu-id="bd092-150">Les appareils Lync 2010 mobile sur Apple et Windows Phone utilisent des notifications de type transmission.</span><span class="sxs-lookup"><span data-stu-id="bd092-150">The Lync 2010 Mobile on Apple and Windows Phone devices use push notifications.</span></span> <span data-ttu-id="bd092-151">Le client mobile Lync 2013 pour les périphériques Apple introduits avec les mises à jour cumulatives pour Lync Server 2013 : février 2013 n’utilise plus de notifications d’envoi ou le centre d’échanges de notifications (échanges).</span><span class="sxs-lookup"><span data-stu-id="bd092-151">The Lync 2013 Mobile client for Apple devices introduced with the Cumulative Updates for Lync Server 2013: February 2013 no longer uses push notification or the push notification clearing house (PNCH).</span></span>

<span data-ttu-id="bd092-152">Le diagramme suivant illustre comment le service de notifications d’envoi de notifications est adapté dans une topologie Lync Server 2013 qui utilise les clients mobiles UCWA et Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="bd092-152">The following diagram illustrates how the Push Notification Service fits within a Lync Server 2013 topology that uses UCWA and Lync 2013 Mobile clients.</span></span>

<span data-ttu-id="bd092-153">![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")</span><span class="sxs-lookup"><span data-stu-id="bd092-153">![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")</span></span>

<span data-ttu-id="bd092-154">Introduit dans la mise à jour cumulative pour Lync Server 2010 : novembre 2011, le service MCX fournit des services aux clients mobiles Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="bd092-154">Introduced in Cumulative Update for Lync Server 2010: November 2011, the Mcx service provides services to Lync 2010 Mobile clients.</span></span> <span data-ttu-id="bd092-155">Le diagramme suivant illustre le service de notifications d’envoi tel qu’il s’applique à une topologie à l’aide des clients mobiles MCX et Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="bd092-155">The following diagram illustrates the Push Notification Service as it applies to a topology using Mcx and Lync 2010 Mobile clients.</span></span>

<span data-ttu-id="bd092-156">![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")</span><span class="sxs-lookup"><span data-stu-id="bd092-156">![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="bd092-157">Topologies prises en charge</span><span class="sxs-lookup"><span data-stu-id="bd092-157">Supported Topologies</span></span>

<span data-ttu-id="bd092-158">Application des mises à jour cumulatives pour Lync Server 2013 : le 2013 février ajoute les composants Web UCWA pour prendre en charge la mobilité pour les fonctionnalités de client mobile Lync 2013 dans les topologies suivantes :</span><span class="sxs-lookup"><span data-stu-id="bd092-158">Applying the Cumulative Updates for Lync Server 2013: February 2013 adds the UCWA web components to support mobility for Lync 2013 Mobile client features in the following topologies:</span></span>

  - <span data-ttu-id="bd092-159">Lync Server 2013 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="bd092-159">Lync Server 2013 Standard Edition</span></span>

  - <span data-ttu-id="bd092-160">Lync Server 2013 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="bd092-160">Lync Server 2013 Enterprise Edition</span></span>

<span data-ttu-id="bd092-161">Le serveur Edge peut être un serveur Edge Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bd092-161">The Edge Server can be a Lync Server 2010 Edge Server.</span></span>

<span data-ttu-id="bd092-162">Un déploiement Lync Server 2013 sans les mises à jour cumulatives pour Lync Server 2013 : le 2013 février utilisera le service de mobilité MCX et ne pourra fournir des services que pour Lync 2010 mobile.</span><span class="sxs-lookup"><span data-stu-id="bd092-162">A Lync Server 2013 deployment without the Cumulative Updates for Lync Server 2013: February 2013 will use the Mcx Mobility Service and can provide services only for Lync 2010 Mobile.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bd092-163">Le service de mobilité est pris en charge sur les serveurs frontaux colocalisés avec le rôle de serveur de médiation avec deux interfaces réseau, mais vous devez prendre les mesures nécessaires pour configurer les interfaces.</span><span class="sxs-lookup"><span data-stu-id="bd092-163">The Mobility Service is supported on Front End Servers that is collocated with the Mediation Server role with two network interfaces, but you must take appropriate steps to configure the interfaces.</span></span> <span data-ttu-id="bd092-164">Vous devez affecter les adresses IP à l’interface spécifique qui communiquera en tant que serveur de médiation, et l’adresse IP de l’interface réseau qui communiquera en tant que serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="bd092-164">You must assign the IP addresses to the specific interface that will communicate as the Mediation Server, and the network interface IP that will communicate as the Front End Server.</span></span> <span data-ttu-id="bd092-165">Vous pouvez effectuer cette opération dans le générateur de topologie en sélectionnant l’adresse IP correcte pour chaque service, au lieu d’utiliser la valeur par défaut <STRONG>utiliser toutes les adresses IP configurées</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="bd092-165">You can do this in Topology Builder by selecting the correct IP address for each service, instead of using the default <STRONG>Use all configured IP addresses</STRONG>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bd092-166">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bd092-166">See Also</span></span>


[<span data-ttu-id="bd092-167">Planification de l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd092-167">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="bd092-168">Déploiement de l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd092-168">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)  
[<span data-ttu-id="bd092-169">Planification de la découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd092-169">Planning for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

