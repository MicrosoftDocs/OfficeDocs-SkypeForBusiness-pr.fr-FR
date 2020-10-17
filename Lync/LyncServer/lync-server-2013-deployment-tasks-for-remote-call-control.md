---
title: 'Lync Server 2013 : tâches de déploiement pour le contrôle d’appel distant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment tasks for remote call control
ms:assetid: 20218871-4f27-4611-9b7e-c0ca55908284
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558624(v=OCS.15)
ms:contentKeyID: 48183599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd2ac45e0f589ac155d2e0f51b0115036a97809e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499051"
---
# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="11c9c-102">Tâches de déploiement pour le contrôle d’appel distant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11c9c-102">Deployment tasks for remote call control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11c9c-103">_**Dernière modification de la rubrique :** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="11c9c-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="11c9c-104">Cette rubrique décrit les tâches de déploiement que vous devez effectuer pour activer le contrôle d’appel distant pour les utilisateurs dans votre environnement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="11c9c-104">This topic describes the deployment tasks that you must perform to enable remote call control for users in your Lync Server environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="11c9c-105">Si vous migrez des utilisateurs précédemment activés pour le contrôle d’appel distant dans Microsoft Office Communicator 2007 R2, vous devez effectuer une tâche de déploiement supplémentaire avant de commencer à exécuter les tâches de déploiement du contrôle d’appel distant décrites dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="11c9c-105">If you are migrating users previously enabled for remote call control in Microsoft Office Communicator 2007 R2, you must perform an additional deployment task before you begin performing the remote call control deployment tasks described in this topic.</span></span> <span data-ttu-id="11c9c-106">Lors du processus de migration vers Lync Server, les entrées d’applications approuvées (précédemment appelées <EM>entrées d’hôte autorisé</EM>) doivent être supprimées à l’aide des outils d’administration Office Communications Server 2007 R2, selon le cas.</span><span class="sxs-lookup"><span data-stu-id="11c9c-106">During the migration process to Lync Server, trusted application entries (previously known as <EM>authorized host entries</EM>) must be removed by using the Office Communications Server 2007 R2 administrative tools, as appropriate.</span></span><BR><span data-ttu-id="11c9c-107">Pour plus d’informations sur la suppression des hôtes autorisés, voir <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a Legacy Authorized Host in Lync Server 2013 (optional)</A>.</span><span class="sxs-lookup"><span data-stu-id="11c9c-107">For details about removing authorized hosts, see <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a legacy authorized host in Lync Server 2013 (optional)</A>.</span></span>



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a><span data-ttu-id="11c9c-108">Étape 1 : Installer la passerelle SIP/CSTA et la configurer de sorte qu’elle communique avec le PBX</span><span class="sxs-lookup"><span data-stu-id="11c9c-108">Step 1: Install and Configure the SIP/CSTA Gateway to Communicate with Your PBX</span></span>

<span data-ttu-id="11c9c-109">Vous devez installer au moins une passerelle SIP/CSTA qui peut se connecter à Lync Server et au PBX (Private Branch Exchange) existant dans votre environnement afin de fournir des fonctionnalités de contrôle d’appel distant à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="11c9c-109">You need to install at least one SIP/CSTA gateway that can connect to both Lync Server and the existing private branch exchange (PBX) in your environment in order to provide remote call control features to your users.</span></span> <span data-ttu-id="11c9c-110">Une passerelle SIP/CSTA est une passerelle entre un serveur SIP et une application CSTA (Computer-Supported Telecommunications Application).</span><span class="sxs-lookup"><span data-stu-id="11c9c-110">A SIP/CSTA gateway is a gateway between SIP and a computer-supported telecommunications application (CSTA).</span></span> <span data-ttu-id="11c9c-111">Quel que soit le nombre de passerelles que vous installez, chaque utilisateur ne peut être configuré qu’avec une seule passerelle ou un seul PBX.</span><span class="sxs-lookup"><span data-stu-id="11c9c-111">Whether you install multiple gateways or just one, each user can be configured with only one gateway or PBX.</span></span> <span data-ttu-id="11c9c-112">Si votre PBX existant ne dispose pas d’une interface SIP/CSTA, déployez une passerelle SIP/CSTA pouvant prendre en charge le PBX, ainsi que les protocoles de signalisation propriétaires propres au fournisseur du PBX.</span><span class="sxs-lookup"><span data-stu-id="11c9c-112">If your existing PBX does not have a SIP/CSTA interface, ensure you deploy a SIP/CSTA gateway that can support the PBX, including support for proprietary PBX vendor-specific signaling protocols.</span></span> <span data-ttu-id="11c9c-113">Pour plus d’informations sur ce que les passerelles prennent en charge, renseignez-vous directement auprès du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="11c9c-113">For details about capabilities, consult each vendor directly.</span></span>

<span data-ttu-id="11c9c-114">Lorsque vous êtes prêt à déployer une passerelle SIP/CSTA qui peut s’intégrer à Lync Server pour le contrôle d’appel distant, consultez également votre fournisseur de passerelle ou la documentation de passerelle du fournisseur concernant la syntaxe requise par la passerelle pour obtenir les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="11c9c-114">When you are ready to deploy a SIP/CSTA gateway that can integrate with Lync Server for remote call control, also consult with your gateway vendor or the vendor’s gateway documentation regarding the syntax required by the gateway for the following information:</span></span>

  - <span data-ttu-id="11c9c-115">URI du serveur de ligne de la passerelle</span><span class="sxs-lookup"><span data-stu-id="11c9c-115">Line server URI of the gateway</span></span>

  - <span data-ttu-id="11c9c-116">URI de ligne pour les utilisateurs qui seront affectés à la passerelle</span><span class="sxs-lookup"><span data-stu-id="11c9c-116">Line URI for users that will be assigned to the gateway</span></span>

<span data-ttu-id="11c9c-117">Vous devez fournir les valeurs des paramètres précédents au cours de la configuration des utilisateurs, car la passerelle en a besoin pour se connecter correctement au PBX et lui transmettre le trafic.</span><span class="sxs-lookup"><span data-stu-id="11c9c-117">The preceding settings are required during user configuration and must be specified as expected by the gateway to route and connect to the PBX properly.</span></span>

<span data-ttu-id="11c9c-118">Vous pouvez vous reporter à la rubrique fournisseurs sur le site Web du programme d’interopérabilité Microsoft Unified Communications à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309) .</span><span class="sxs-lookup"><span data-stu-id="11c9c-118">You can refer to vendors on the Microsoft Unified Communications Open Interoperability Program website at [https://go.microsoft.com/fwlink/p/?linkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a><span data-ttu-id="11c9c-119">Étape 2 : configurer Lync Server pour acheminer les demandes CSTA vers la passerelle SIP/CSTA</span><span class="sxs-lookup"><span data-stu-id="11c9c-119">Step 2: Configure Lync Server to Route CSTA Requests to the SIP/CSTA Gateway</span></span>

<span data-ttu-id="11c9c-120">Vous devez créer des itinéraires statiques sur les pools de serveurs Lync Server vers l’adresse de destination (URI du serveur) de toutes les passerelles SIP/CSTA de votre déploiement vers lequel vous envisagez d’acheminer les demandes de contrôle d’appel distant.</span><span class="sxs-lookup"><span data-stu-id="11c9c-120">You must create static routes on Lync Server pools to the destination address (server URI) of all SIP/CSTA gateways in your deployment to which you intend to route remote call control requests.</span></span> <span data-ttu-id="11c9c-121">Vous devez également créer une entrée d’application approuvée qui correspond à chaque adresse de destination.</span><span class="sxs-lookup"><span data-stu-id="11c9c-121">You must also create a trusted application entry that corresponds to each destination address.</span></span> <span data-ttu-id="11c9c-122">Lorsque vous désignez la passerelle en tant qu’application approuvée, elle reçoit un État approuvé à exécuter dans le cadre de l’environnement Lync Server même si elle est développée par un tiers (et exécute ce qui est appelé *service externe* , car il s’agit d’un service qui n’est pas intégré au produit).</span><span class="sxs-lookup"><span data-stu-id="11c9c-122">When you designate the gateway as a trusted application, it is given trusted status to run as part of the Lync Server environment even though it is developed by a third party (and runs what is referred to as an *external service* because it is a service that is not a built-in part of the product).</span></span> <span data-ttu-id="11c9c-123">Enfin, si Lync Server se connecte à la passerelle SIP/CSTA à l’aide d’une connexion TCP (Transmission Control Protocol) au lieu d’une connexion TLS (Transport Layer Security), vous devez également définir l’adresse IP de la passerelle à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="11c9c-123">Finally, if Lync Server will connect to the SIP/CSTA gateway using a Transmission Control Protocol (TCP) connection instead of a Transport Layer Security (TLS) connection, you must also define the gateway IP address by using Topology Builder.</span></span>

<span data-ttu-id="11c9c-124">Pour plus d’informations sur la configuration des itinéraires statiques, voir [configurer un itinéraire statique pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="11c9c-124">For details about configuring static routes, see [Configure a static route for remote call control in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).</span></span>

<span data-ttu-id="11c9c-125">Pour plus d’informations sur la configuration des entrées d’applications approuvées, voir [Configure a Trusted application Entry for Remote Call Control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="11c9c-125">For details about configuring trusted application entries, see [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).</span></span>

<span data-ttu-id="11c9c-126">Pour plus d’informations sur la définition d’une adresse IP de passerelle SIP/CSTA dans le générateur de topologies, voir [define a SIP/CSTA Gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).</span><span class="sxs-lookup"><span data-stu-id="11c9c-126">For details about defining a SIP/CSTA gateway IP address in Topology Builder, see [Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).</span></span>

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a><span data-ttu-id="11c9c-127">Étape 3 : configuration des utilisateurs Lync pour le contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="11c9c-127">Step 3: Configure Lync Users for Remote Call Control</span></span>

<span data-ttu-id="11c9c-128">Une fois que les utilisateurs ont été activés pour Lync Server, vous pouvez utiliser le panneau de configuration Lync Server ou Lync Server Management Shell pour les activer pour le contrôle d’appel distant.</span><span class="sxs-lookup"><span data-stu-id="11c9c-128">After users have been enabled for Lync Server, you can use Lync Server Control Panel or Lync Server Management Shell to enable them for remote call control.</span></span> <span data-ttu-id="11c9c-129">C’est également au cours de cette étape que vous devez affecter à chaque utilisateur un URI de serveur de ligne et un URI de ligne.</span><span class="sxs-lookup"><span data-stu-id="11c9c-129">It is during this deployment step that you assign each user a line server URI and a line URI.</span></span> <span data-ttu-id="11c9c-130">L’URI de serveur de ligne est l’URI SIP de la passerelle SIP/CSTA que vous envisagez d’affecter à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="11c9c-130">The line server URI is the SIP URI of the SIP/CSTA gateway that you plan to assign to the user.</span></span> <span data-ttu-id="11c9c-131">L’URI de ligne est le numéro de téléphone unique affecté à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="11c9c-131">The line URI is the unique phone number assigned to the user.</span></span>

<span data-ttu-id="11c9c-132">Pour plus d’informations sur la configuration des utilisateurs pour le contrôle d’appel distant, reportez-vous à la rubrique [activation des utilisateurs Lync pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="11c9c-132">For details about configuring users for remote call control, see [Enable Lync users for remote call control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span></span>

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a><span data-ttu-id="11c9c-133">Étape 4 : Définir les règles de normalisation des numéros de téléphone Lync Server</span><span class="sxs-lookup"><span data-stu-id="11c9c-133">Step 4: Define the Lync Server Phone Number Normalization Rules</span></span>

<span data-ttu-id="11c9c-134">Dans les scénarios de contrôle d’appel distant, Lync Server utilise les règles de normalisation des numéros de téléphone pour convertir les numéros de téléphone qu’il reçoit de la passerelle SIP/CSTA au format E. 164.</span><span class="sxs-lookup"><span data-stu-id="11c9c-134">In remote call control scenarios, Lync Server uses phone number normalization rules to convert phone numbers it receives from the SIP/CSTA gateway to E.164 format.</span></span> <span data-ttu-id="11c9c-135">Les numéros de téléphone doivent être dans ce format standard pour que certaines fonctionnalités de contrôle d’appel distant fonctionnent correctement.</span><span class="sxs-lookup"><span data-stu-id="11c9c-135">Phone numbers must be in this standardized format for certain remote call control features to function properly.</span></span> <span data-ttu-id="11c9c-136">Le contrôle d’appel distant utilise les mêmes règles de normalisation des numéros de téléphone que celles que vous configurez pour la normalisation des numéros de téléphone du Service de carnet d’adresses, qui sont différentes des règles de normalisation utilisées pour Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="11c9c-136">Remote call control uses the same phone number normalization rules that you configure for Address Book Service phone number normalization, which are different from the phone number normalization rules used for Enterprise Voice.</span></span>

<span data-ttu-id="11c9c-137">Pour plus d’informations sur la façon dont le contrôle d’appel distant utilise les règles de normalisation des numéros de téléphone, consultez la rubrique [contrôle d’appel distant et normalisation des numéros de téléphone dans Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md).</span><span class="sxs-lookup"><span data-stu-id="11c9c-137">For details about how remote call control uses phone number normalization rules, see [Remote call control and phone number normalization in Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md).</span></span> <span data-ttu-id="11c9c-138">Pour plus d’informations sur les règles de normalisation des numéros de téléphone pour le service de carnet d’adresses, voir [administration de la rubrique Service de carnet d’adresses dans Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="11c9c-138">For details about phone number normalization rules for Address Book Service, see [Administering the Address Book Service in Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) topic in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

