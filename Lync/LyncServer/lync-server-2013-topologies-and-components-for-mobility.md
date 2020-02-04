---
title: 'Lync Server 2013 : Topologies et composants pour la mobilité'
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
ms.openlocfilehash: 739deecf47e25e57ca0175c29a2721e509f8dbe2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745224"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a><span data-ttu-id="725e1-102">Topologies et composants pour la mobilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="725e1-102">Topologies and components for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="725e1-103">_**Dernière modification de la rubrique :** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="725e1-103">_**Topic Last Modified:** 2013-02-17_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="725e1-104">Pour prendre en charge les applications mobiles Lync sur les appareils mobiles, Lync Server 2013 fournit trois services : Lync Server 2013 MCX Mobility service, Lync Server 2013 de découverte automatique et service de notification Poussée Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="725e1-104">To support Lync mobile applications on mobile devices, Lync Server 2013 provides three services: Lync Server 2013 Mcx Mobility Service, Lync Server 2013 Autodiscover Service, and Lync Server 2013 Push Notification Service.</span></span> <span data-ttu-id="725e1-105">Les mises à jour cumulatives de Lync Server 2013 : février 2013 ajoute un service gratuit, mais avancé, pour les clients mobiles Lync 2013 : prise en charge de la mobilité par le biais de l’utilisation de l’API Web de communications unifiées, ou UCWA.</span><span class="sxs-lookup"><span data-stu-id="725e1-105">The Cumulative Updates for Lync Server 2013: February 2013 adds a complimentary, but advanced, service for Lync 2013 Mobile clients—mobility support through the use of the Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="725e1-106">Cette section décrit brièvement ces composants et identifie les topologies Lync Server 2013 qui prennent en charge la mobilité.</span><span class="sxs-lookup"><span data-stu-id="725e1-106">This section briefly describes these components and identifies the Lync Server 2013 topologies that support mobility.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="725e1-107">Les services de mobilité sont également disponibles dans les déploiements hybrides.</span><span class="sxs-lookup"><span data-stu-id="725e1-107">Mobility services are also available in hybrid deployments.</span></span> <span data-ttu-id="725e1-108">Vous n’êtes pas tenu de déployer des services pour la mobilité si vos utilisateurs sont hébergés en ligne.</span><span class="sxs-lookup"><span data-stu-id="725e1-108">You are not required to deploy services for supporting mobility if your users are homed online.</span></span> <span data-ttu-id="725e1-109">Pour permettre aux utilisateurs mobiles de rechercher leur identité en ligne, vous devez définir un paramètre pour le service de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="725e1-109">You do need to define a setting for the Autodiscover Service to enable mobile users to find their online identity.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="725e1-110">Si vous planifiez une connectivité utilisateur externe (par exemple, une Fédération, un accès utilisateur externe ou des fonctionnalités de mobilité), vous devez utiliser les serveurs Edge avec Standard Edition Server, le serveur frontal ou le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="725e1-110">If you are planning any external user connectivity (for example, federation, external user access, or mobility features), you must use Edge Servers with Standard Edition server and the Front End Server or Front End pool.</span></span> <span data-ttu-id="725e1-111">Le serveur Standard Edition et le serveur frontal ou le pool frontal ne disposent pas des composants nécessaires pour permettre aux utilisateurs externes d’accéder à votre déploiement interne ou pour le déploiement interne de communiquer avec les utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="725e1-111">The Standard Edition server and the Front End Server or Front End pool do not have the necessary components to enable external users to access your internal deployment, or for the internal deployment to communicate with your external users.</span></span> <span data-ttu-id="725e1-112">Dans tous les cas où les utilisateurs externes collaborent ou communiquent avec des utilisateurs internes, y compris la mobilité, vous devez déployer au moins un serveur Edge et un proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="725e1-112">For all scenarios that include external users collaborating or communicating with internal users, including mobility, you must deploy at least one Edge Server and one reverse proxy.</span></span><BR><span data-ttu-id="725e1-113">La <EM>notification de transmission</EM> utilise un type de Fédération pour les services Lync Online, qui héberge le centre de suppression des notifications de transmission (PNCH).</span><span class="sxs-lookup"><span data-stu-id="725e1-113"><EM>Push notification</EM> uses a type of federation to the Lync Online services, which hosts the Push Notification Clearing House (PNCH).</span></span> <span data-ttu-id="725e1-114">La notification push fait référence aux alertes sonores, aux alertes à l’écran (texte) et aux badges envoyés par les applications sur l’Apple iPhone, iPad et Windows Phone, lorsque l’appareil mobile n’est pas actif.</span><span class="sxs-lookup"><span data-stu-id="725e1-114">Push notification refers to the sound alerts, on-screen alerts (text), and badges that are pushed by applications to the Apple iPhone, iPad, and Windows Phone, when the mobile device is inactive.</span></span> <span data-ttu-id="725e1-115">PNCH reçoit les notifications de transmission de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="725e1-115">PNCH receives push notifications from Lync Server.</span></span> <span data-ttu-id="725e1-116">Lorsque PNCH reçoit une notification de message, PNCH envoie une notification aux clients mobiles par le biais du service de notifications d’applets d’Apple ou du service de notifications de transmission de Lync Server 2013, en fonction du client mobile pour lequel le message est destiné.</span><span class="sxs-lookup"><span data-stu-id="725e1-116">When PNCH receives a notification of a message, PNCH forwards a notification to mobile clients through either the Apple Push Notification Services or Lync Server 2013 Push Notification Service, based on the mobile client that the message is intended for.</span></span> <span data-ttu-id="725e1-117">PNCH est un service requis pour ces clients mobiles.</span><span class="sxs-lookup"><span data-stu-id="725e1-117">PNCH is a required service for these mobile clients.</span></span> <span data-ttu-id="725e1-118">Pour fédérer sur Lync Online, PNCH utilise des serveurs de périphérie et des certificats pour garantir la confidentialité et l’authentification, les politiques et les enregistrements DNS (Domain Name System) correctement configurés.</span><span class="sxs-lookup"><span data-stu-id="725e1-118">To federate to Lync Online, PNCH uses Edge Servers and certificates to ensure confidentiality and authentication, policies, and correctly configured domain name system (DNS) records.</span></span> <span data-ttu-id="725e1-119">Les clients mobiles Lync Symbian et Android n’utilisent pas PNCH.</span><span class="sxs-lookup"><span data-stu-id="725e1-119">Nokia Symbian and Android-based Lync Mobile clients do not use PNCH.</span></span> <span data-ttu-id="725e1-120">Pour plus d’informations sur la planification et le déploiement de serveurs Edge, voir <A href="lync-server-2013-planning-for-external-user-access.md">planification d’un accès utilisateur externe dans Lync server 2013</A> et déploiement d’un <A href="lync-server-2013-deploying-external-user-access.md">accès utilisateur externe dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="725e1-120">For details about planning and deploying Edge Servers, see <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external user access in Lync Server 2013</A> and <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="725e1-121">Les clients mobiles Lync 2013 pour les appareils Apple introduits avec les mises à jour cumulatives de Lync Server 2013 : février 2013 n’utilise plus la notification d’émission ou la chambre d’échanges de notifications de transmission (PNCH).</span><span class="sxs-lookup"><span data-stu-id="725e1-121">The Lync 2013 Mobile clients for Apple devices introduced with the Cumulative Updates for Lync Server 2013: February 2013 no longer use push notification or the push notification clearing house (PNCH).</span></span> <span data-ttu-id="725e1-122">Les clients mobiles Lync 2013 sur Windows Phone utilisent toujours les notifications de transmission et le (PNCH).</span><span class="sxs-lookup"><span data-stu-id="725e1-122">Lync 2013 Mobile clients on Windows Phone still use push notification and the (PNCH).</span></span>



</div>

<div>

## <a name="mobility-components"></a><span data-ttu-id="725e1-123">Composants de mobilité</span><span class="sxs-lookup"><span data-stu-id="725e1-123">Mobility Components</span></span>

<span data-ttu-id="725e1-124">Les services qui prennent en charge la mobilité sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="725e1-124">The services that support mobility are as follows:</span></span>

  - <span data-ttu-id="725e1-125">**L’API Web de communications unifiées (UCWA)**   Lync Server 2013 fournit des services pour communiquer en temps réel avec des clients mobiles et Web dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="725e1-125">**Lync Server 2013 Unified Communications Web API (UCWA)**   Provides services for real-time communications with mobile and web clients in Lync Server 2013.</span></span> <span data-ttu-id="725e1-126">Lorsque vous déployez les mises à jour cumulatives pour Lync Server 2013 : février 2013 sur le serveur frontal et le directeur, l’installation crée un répertoire virtuel dans les services Web internes et externes (Ucwa).</span><span class="sxs-lookup"><span data-stu-id="725e1-126">When you deploy the Cumulative Updates for Lync Server 2013: February 2013 to the Front End Server and Director, the installation creates a virtual directory in the internal and external web services (Ucwa).</span></span> <span data-ttu-id="725e1-127">Un composant WebPart qui fait partie du répertoire virtuel Ucwa accepte les appels de clients UCWA.</span><span class="sxs-lookup"><span data-stu-id="725e1-127">A web component that is part of the Ucwa virtual directory accepts calls from UCWA-enabled clients.</span></span> <span data-ttu-id="725e1-128">Les applications clientes communiquent par le biais d’une interface REST pour la présence, les contacts, la messagerie instantanée, les appels VoIP, les conférences vidéo et la collaboration.</span><span class="sxs-lookup"><span data-stu-id="725e1-128">The client apps communicate over a REST interface for presence, contacts, instant messaging, VoIP, video conferencing, and collaboration.</span></span> <span data-ttu-id="725e1-129">UCWA utilise un canal basé sur P pour envoyer des événements, tels qu’un appel entrant, un message instantané entrant ou un message à l’application cliente.</span><span class="sxs-lookup"><span data-stu-id="725e1-129">UCWA uses a P-GET based channel to send events, such as an incoming call, incoming instant message, or a message to the client app.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="725e1-130">Le transfert d’état <EM>Rest</EM> ou de présentation est un style architectural logiciel pour les systèmes distribués qui ont été largement adoptés dans de nombreuses formes et qui sont bien adaptés aux exigences des services Web en général.</span><span class="sxs-lookup"><span data-stu-id="725e1-130"><EM>REST</EM> or representational state transfer, is a software architectural style for distributed systems that has been widely adopted in many forms and is well suited to the requirements of Web services in general.</span></span>

    
    </div>

  - <span data-ttu-id="725e1-131">**Service de mobilité Lync Server 2013 (MCX)**   ce service prend en charge les fonctionnalités de Lync, telles que la messagerie instantanée, la présence et les contacts, sur les appareils mobiles.</span><span class="sxs-lookup"><span data-stu-id="725e1-131">**Lync Server 2013 Mobility Service (Mcx)**   This service supports Lync functionality, such as instant messaging (IM), presence, and contacts, on mobile devices.</span></span> <span data-ttu-id="725e1-132">Le service de mobilité est installé sur chaque serveur frontal de chaque pool prenant en charge la fonctionnalité Lync sur les appareils mobiles.</span><span class="sxs-lookup"><span data-stu-id="725e1-132">The Mobility Service is installed on every Front End Server in each pool that is to support Lync functionality on mobile devices.</span></span> <span data-ttu-id="725e1-133">Lorsque vous installez Lync Server 2013, un nouveau répertoire virtuel (MCX) est créé sous le site Web interne et le site Web externe sur votre serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="725e1-133">When you install Lync Server 2013, a new virtual directory (Mcx) is created under both the internal website and the external website on your Front End Servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="725e1-134">Lync Server 2013 avec les mises à jour cumulatives de Lync Server 2013:2013 février prend en charge à la fois le service de mobilité présenté dans la mise à jour cumulative de Lync Server 2010 : de 2011 novembre, connu sous le nom de MCX et du composant WebPart UCWA.</span><span class="sxs-lookup"><span data-stu-id="725e1-134">Lync Server 2013 with the Cumulative Updates for Lync Server 2013: February 2013 supports both the Mobility service introduced in the Cumulative Update for Lync Server 2010: November 2011, commonly known as Mcx, and the UCWA web component.</span></span> <span data-ttu-id="725e1-135">La combinaison de ces deux services de mobilité fournit une interopérabilité et une utilisation par les utilisateurs des clients de Lync 2010 mobile et de Lync 2013 mobile sur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="725e1-135">The combination of these two mobility services provides interoperability and use by users with Lync 2010 Mobile and Lync 2013 Mobile clients on Lync Server 2013.</span></span>

    
    </div>

  - <span data-ttu-id="725e1-136">**Service de découverte automatique Lync Server 2013**   ce service identifie l’emplacement de l’utilisateur et permet aux appareils mobiles et aux autres clients Lync de rechercher des ressources (par exemple, les URL internes et externes pour les services Web de Lync Server 2013) et l’URL du MCX ou UCWA, quel que soit l’emplacement réseau.</span><span class="sxs-lookup"><span data-stu-id="725e1-136">**Lync Server 2013 Autodiscover Service**   This service identifies the location of the user and enables mobile devices and other Lync clients to locate resources—such as the internal and external URLs for Lync Server 2013 Web Services, and the URL for the Mcx or UCWA—regardless of network location.</span></span> <span data-ttu-id="725e1-137">La découverte automatique utilise des noms d’hôtes encodés (lyncdiscoverinternal pour les utilisateurs à l’intérieur du réseau ; lyncdiscover pour les utilisateurs en dehors du réseau) et le domaine SIP de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="725e1-137">Automatic discovery uses hardcoded host names (lyncdiscoverinternal for users inside the network; lyncdiscover for users outside the network) and the SIP domain of the user.</span></span> <span data-ttu-id="725e1-138">Elle prend en charge les connexions clientes qui utilisent le protocole HTTP ou HTTPS.</span><span class="sxs-lookup"><span data-stu-id="725e1-138">It supports client connections that use either HTTP or HTTPS.</span></span>
    
    <span data-ttu-id="725e1-139">Le service de découverte automatique est installé sur chaque serveur frontal et sur tous les directeurs de chaque liste qui prend en charge la fonctionnalité Lync sur les appareils mobiles.</span><span class="sxs-lookup"><span data-stu-id="725e1-139">The Autodiscover Service is installed on every Front End Server and on every Director in each pool that is to support Lync functionality on mobile devices.</span></span> <span data-ttu-id="725e1-140">Lorsque vous installez le service de découverte automatique, un nouveau répertoire virtuel (découverte automatique) est créé sous le site Web interne et le site Web externe, sur les serveurs et les directeurs du serveur principal.</span><span class="sxs-lookup"><span data-stu-id="725e1-140">When you install the Autodiscover Service, a new virtual directory (Autodiscover) is created under both the internal website and the external website, on both Front End Servers and Directors.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="725e1-141">Le service de découverte automatique est répertorié ici, car il reste un composant essentiel lors de la fourniture de services pour les clients mobiles.</span><span class="sxs-lookup"><span data-stu-id="725e1-141">The Autodiscover Service is listed here because it remains a critical component when providing mobile client services.</span></span> <span data-ttu-id="725e1-142">Le rôle de découverte automatique dans Lync Server 2013 a été développé de manière à fournir des services à tous les clients.</span><span class="sxs-lookup"><span data-stu-id="725e1-142">The role of Autodiscover in Lync Server 2013 has been expanded to provide services for all clients.</span></span> <span data-ttu-id="725e1-143">Pour plus d’informations sur la planification du service de découverte automatique, voir <A href="lync-server-2013-planning-for-autodiscover.md">planification de la découverte automatique dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="725e1-143">For details about planning for the Autodiscover Service, see <A href="lync-server-2013-planning-for-autodiscover.md">Planning for Autodiscover in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="725e1-144">**Service de notifications de transmission**   ce service est un service basé sur le Cloud qui se trouve dans le centre de données Lync Online.</span><span class="sxs-lookup"><span data-stu-id="725e1-144">**Push Notification Service**   This service is a cloud-based service that is located in the Lync Online data center.</span></span> <span data-ttu-id="725e1-145">Lorsque l’application mobile Lync sur un appareil iOS Apple ou Windows Phone pris en charge est désactivée, elle ne peut pas répondre aux nouveaux événements, tels qu’une nouvelle invitation à une messagerie instantanée, un message instantané manqué, un appel manqué ou une messagerie vocale, car ces appareils ne sont pas pris en charge. applications mobiles s’exécutant en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="725e1-145">When the Lync mobile application on a supported Apple iOS device or Windows Phone is inactive, it cannot respond to new events, such as a new instant messaging (IM) invitation, a missed instant message, a missed call, or voice mail, because these devices do not support mobile applications running in the background.</span></span> <span data-ttu-id="725e1-146">Dans ces cas, une notification du nouvel événement (appelé notification de *transmission*) est envoyée à l’appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="725e1-146">In these cases, a notification of the new event—called a *push notification*—is sent to the mobile device.</span></span> <span data-ttu-id="725e1-147">Le service de mobilité envoie la notification au service de notifications de transmission Cloud, qui envoie ensuite la notification au service de notifications de transmission d’Apple (APNS) (pour les appareils iOS iOS pris en charge) ou au service de notifications Microsoft émission (MPNS ) (pour Windows Phone), qui l’envoie ensuite à l’appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="725e1-147">The Mobility Service sends the notification to the cloud-based Push Notification Service, which then sends the notification either to the Apple Push Notification Service (APNS) (for supported Apple iOS devices) or to the Microsoft Push Notification Service (MPNS) (for Windows Phone), which then sends it on to the mobile device.</span></span> <span data-ttu-id="725e1-148">L’utilisateur peut alors répondre à la notification sur l’appareil mobile pour activer l’application.</span><span class="sxs-lookup"><span data-stu-id="725e1-148">The user can then respond to the notification on the mobile device to activate the application.</span></span>
    
    <span data-ttu-id="725e1-149">Le mobile Lync 2010 sur les appareils Apple et Windows Phone utilisent les notifications de transmission.</span><span class="sxs-lookup"><span data-stu-id="725e1-149">The Lync 2010 Mobile on Apple and Windows Phone devices use push notifications.</span></span> <span data-ttu-id="725e1-150">Le client mobile 2013 Lync pour les appareils Apple introduits avec les mises à jour cumulatives pour Lync Server 2013:2013 février n’utilise plus la notification d’émission ou la chambre d’échanges de notifications de transmission (PNCH).</span><span class="sxs-lookup"><span data-stu-id="725e1-150">The Lync 2013 Mobile client for Apple devices introduced with the Cumulative Updates for Lync Server 2013: February 2013 no longer uses push notification or the push notification clearing house (PNCH).</span></span>

<span data-ttu-id="725e1-151">Le diagramme suivant illustre le fonctionnement du service de notifications d’émission au sein d’une topologie Lync Server 2013 qui utilise les clients mobiles UCWA et Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="725e1-151">The following diagram illustrates how the Push Notification Service fits within a Lync Server 2013 topology that uses UCWA and Lync 2013 Mobile clients.</span></span>

<span data-ttu-id="725e1-152">![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")</span><span class="sxs-lookup"><span data-stu-id="725e1-152">![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")</span></span>

<span data-ttu-id="725e1-153">Introduction dans la mise à jour cumulative pour Lync Server 2010:2011 novembre, le service MCX fournit des services aux clients mobiles Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="725e1-153">Introduced in Cumulative Update for Lync Server 2010: November 2011, the Mcx service provides services to Lync 2010 Mobile clients.</span></span> <span data-ttu-id="725e1-154">Le diagramme suivant illustre le service de notifications d’émission tel qu’il s’applique à une topologie utilisant des clients mobiles MCX et Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="725e1-154">The following diagram illustrates the Push Notification Service as it applies to a topology using Mcx and Lync 2010 Mobile clients.</span></span>

<span data-ttu-id="725e1-155">![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")</span><span class="sxs-lookup"><span data-stu-id="725e1-155">![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="725e1-156">Topologies prises en charge</span><span class="sxs-lookup"><span data-stu-id="725e1-156">Supported Topologies</span></span>

<span data-ttu-id="725e1-157">L’application des mises à jour cumulatives pour Lync Server 2013 : février 2013 ajoute les composants Web UCWA pour la prise en charge de la mobilité pour les fonctionnalités du client mobile Lync 2013 dans les topologies suivantes :</span><span class="sxs-lookup"><span data-stu-id="725e1-157">Applying the Cumulative Updates for Lync Server 2013: February 2013 adds the UCWA web components to support mobility for Lync 2013 Mobile client features in the following topologies:</span></span>

  - <span data-ttu-id="725e1-158">Lync Server 2013 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="725e1-158">Lync Server 2013 Standard Edition</span></span>

  - <span data-ttu-id="725e1-159">Lync Server 2013 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="725e1-159">Lync Server 2013 Enterprise Edition</span></span>

<span data-ttu-id="725e1-160">Le serveur Edge peut être un serveur Edge Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="725e1-160">The Edge Server can be a Lync Server 2010 Edge Server.</span></span>

<span data-ttu-id="725e1-161">Un déploiement de Lync Server 2013 sans les mises à jour cumulatives de Lync Server 2013:2013 février utilise le service de mobilité MCX et peut fournir des services uniquement pour Lync 2010 mobile.</span><span class="sxs-lookup"><span data-stu-id="725e1-161">A Lync Server 2013 deployment without the Cumulative Updates for Lync Server 2013: February 2013 will use the Mcx Mobility Service and can provide services only for Lync 2010 Mobile.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="725e1-162">Le service de mobilité est pris en charge sur les serveurs front-end possédant le rôle serveur de médiation avec deux interfaces réseau, mais vous devez prendre les mesures appropriées pour configurer les interfaces.</span><span class="sxs-lookup"><span data-stu-id="725e1-162">The Mobility Service is supported on Front End Servers that is collocated with the Mediation Server role with two network interfaces, but you must take appropriate steps to configure the interfaces.</span></span> <span data-ttu-id="725e1-163">Vous devez affecter les adresses IP à l’interface spécifique qui communiquera en tant que serveur de médiation et l’adresse IP de l’interface réseau qui communiquera en tant que serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="725e1-163">You must assign the IP addresses to the specific interface that will communicate as the Mediation Server, and the network interface IP that will communicate as the Front End Server.</span></span> <span data-ttu-id="725e1-164">Pour cela, vous pouvez sélectionner l’adresse IP correcte pour chaque service au lieu d’utiliser la valeur par défaut <STRONG>utiliser toutes les adresses IP configurées</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="725e1-164">You can do this in Topology Builder by selecting the correct IP address for each service, instead of using the default <STRONG>Use all configured IP addresses</STRONG>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="725e1-165">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="725e1-165">See Also</span></span>


[<span data-ttu-id="725e1-166">Planification de l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="725e1-166">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="725e1-167">Déploiement de l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="725e1-167">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)  
[<span data-ttu-id="725e1-168">Planification de la découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="725e1-168">Planning for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

