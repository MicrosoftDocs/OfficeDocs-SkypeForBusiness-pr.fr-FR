---
title: 'Lync Server 2013 : Tâches de déploiement du contrôle d’appel distant'
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
ms.openlocfilehash: df80ebcdc879598677a037d60c9eeeee46ba5209
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="b6c0f-102">Tâches de déploiement du contrôle d’appel distant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6c0f-102">Deployment tasks for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6c0f-103">_**Dernière modification de la rubrique :** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="b6c0f-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="b6c0f-104">Cette rubrique décrit les tâches de déploiement que vous devez effectuer pour activer le contrôle d’appel distant pour les utilisateurs de votre environnement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b6c0f-104">This topic describes the deployment tasks that you must perform to enable remote call control for users in your Lync Server environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b6c0f-105">Si vous migrez des utilisateurs précédemment activés pour le contrôle d’appel distant dans Microsoft Office Communicator 2007 R2, vous devez effectuer une tâche de déploiement supplémentaire avant de commencer à effectuer les tâches de déploiement de contrôle d’appel distant décrites dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="b6c0f-105">If you are migrating users previously enabled for remote call control in Microsoft Office Communicator 2007 R2, you must perform an additional deployment task before you begin performing the remote call control deployment tasks described in this topic.</span></span> <span data-ttu-id="b6c0f-106">Pendant le processus de migration vers Lync Server, les entrées d’applications approuvées (auparavant appelées « <EM>entrées d’hébergement d’hébergement</EM>») doivent être supprimées en utilisant les outils d’administration Office Communications Server 2007 R2, selon le cas.</span><span class="sxs-lookup"><span data-stu-id="b6c0f-106">During the migration process to Lync Server, trusted application entries (previously known as <EM>authorized host entries</EM>) must be removed by using the Office Communications Server 2007 R2 administrative tools, as appropriate.</span></span><BR><span data-ttu-id="b6c0f-107">Pour plus d’informations sur la suppression d’hôtes autorisés, voir <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">supprimer un hôte autorisé hérité dans Lync Server 2013 (facultatif)</A>.</span><span class="sxs-lookup"><span data-stu-id="b6c0f-107">For details about removing authorized hosts, see <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a legacy authorized host in Lync Server 2013 (optional)</A>.</span></span>



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a><span data-ttu-id="b6c0f-108">Étape 1 : installer et configurer la passerelle SIP/CSTA pour communiquer avec votre système PBX</span><span class="sxs-lookup"><span data-stu-id="b6c0f-108">Step 1: Install and Configure the SIP/CSTA Gateway to Communicate with Your PBX</span></span>

<span data-ttu-id="b6c0f-109">Vous devez installer au moins une passerelle SIP/CSTA qui peut se connecter à Lync Server et au PBX (PBX) existant dans votre environnement afin de fournir aux utilisateurs des fonctionnalités de contrôle d’appel distant.</span><span class="sxs-lookup"><span data-stu-id="b6c0f-109">You need to install at least one SIP/CSTA gateway that can connect to both Lync Server and the existing private branch exchange (PBX) in your environment in order to provide remote call control features to your users.</span></span> <span data-ttu-id="b6c0f-110">Une passerelle SIP/CSTA est une passerelle entre le SIP et une application de communication prenant en charge l’ordinateur (CSTA).</span><span class="sxs-lookup"><span data-stu-id="b6c0f-110">A SIP/CSTA gateway is a gateway between SIP and a computer-supported telecommunications application (CSTA).</span></span> <span data-ttu-id="b6c0f-111">Qu’il s’agisse d’installer plusieurs passerelles ou une seule, chaque utilisateur peut être configuré avec une seule passerelle ou PBX.</span><span class="sxs-lookup"><span data-stu-id="b6c0f-111">Whether you install multiple gateways or just one, each user can be configured with only one gateway or PBX.</span></span> <span data-ttu-id="b6c0f-112">Si votre système PBX existant ne dispose pas d’une interface SIP/CSTA, assurez-vous de déployer une passerelle SIP/CSTA qui peut prendre en charge le PBX, y compris la prise en charge de protocoles de signalisation spécifiques du fabricant PBX.</span><span class="sxs-lookup"><span data-stu-id="b6c0f-112">If your existing PBX does not have a SIP/CSTA interface, ensure you deploy a SIP/CSTA gateway that can support the PBX, including support for proprietary PBX vendor-specific signaling protocols.</span></span> <span data-ttu-id="b6c0f-113">Pour plus d’informations sur les fonctionnalités, consultez directement chaque fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b6c0f-113">For details about capabilities, consult each vendor directly.</span></span>

<span data-ttu-id="b6c0f-114">Lorsque vous êtes prêt à déployer une passerelle SIP/CSTA qui peut être intégrée à Lync Server pour le contrôle d’appel distant, contactez également le fournisseur de votre passerelle ou la documentation de la passerelle du fournisseur en ce qui concerne la syntaxe requise par la passerelle pour les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="b6c0f-114">When you are ready to deploy a SIP/CSTA gateway that can integrate with Lync Server for remote call control, also consult with your gateway vendor or the vendor’s gateway documentation regarding the syntax required by the gateway for the following information:</span></span>

  - <span data-ttu-id="b6c0f-115">URI de serveur ligne de la passerelle</span><span class="sxs-lookup"><span data-stu-id="b6c0f-115">Line server URI of the gateway</span></span>

  - <span data-ttu-id="b6c0f-116">URI de ligne pour les utilisateurs qui seront assignés à la passerelle</span><span class="sxs-lookup"><span data-stu-id="b6c0f-116">Line URI for users that will be assigned to the gateway</span></span>

<span data-ttu-id="b6c0f-117">Les paramètres précédents sont requis lors de la configuration de l’utilisateur et doivent être spécifiés comme prévu par la passerelle pour le routage et la connexion au PBX correctement.</span><span class="sxs-lookup"><span data-stu-id="b6c0f-117">The preceding settings are required during user configuration and must be specified as expected by the gateway to route and connect to the PBX properly.</span></span>

<span data-ttu-id="b6c0f-118">Vous pouvez consulter les fournisseurs sur le site Web Microsoft Unified Communications Open Interoperability du [http://go.microsoft.com/fwlink/p/?linkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)programme à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="b6c0f-118">You can refer to vendors on the Microsoft Unified Communications Open Interoperability Program website at [http://go.microsoft.com/fwlink/p/?linkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a><span data-ttu-id="b6c0f-119">Étape 2 : configurer Lync Server pour acheminer les demandes CSTA vers la passerelle SIP/CSTA</span><span class="sxs-lookup"><span data-stu-id="b6c0f-119">Step 2: Configure Lync Server to Route CSTA Requests to the SIP/CSTA Gateway</span></span>

<span data-ttu-id="b6c0f-120">Vous devez créer des itinéraires statiques sur les pools de serveurs Lync vers l’adresse de destination (URI du serveur) de toutes les passerelles SIP/CSTA de votre déploiement pour lesquelles vous souhaitez acheminer les demandes de contrôle d’appel distant.</span><span class="sxs-lookup"><span data-stu-id="b6c0f-120">You must create static routes on Lync Server pools to the destination address (server URI) of all SIP/CSTA gateways in your deployment to which you intend to route remote call control requests.</span></span> <span data-ttu-id="b6c0f-121">Vous devez également créer une entrée d’application fiable qui correspond à chaque adresse de destination.</span><span class="sxs-lookup"><span data-stu-id="b6c0f-121">You must also create a trusted application entry that corresponds to each destination address.</span></span> <span data-ttu-id="b6c0f-122">Lorsque vous désignez la passerelle en tant qu’application approuvée, son état de confiance s’exécute dans le cadre de l’environnement Lync Server, même si elle est développée par une tierce partie (et exécute ce qu’il est désigné sous le terme de *service externe* , car il s’agit d’un service qui n’est pas intégré au produit).</span><span class="sxs-lookup"><span data-stu-id="b6c0f-122">When you designate the gateway as a trusted application, it is given trusted status to run as part of the Lync Server environment even though it is developed by a third party (and runs what is referred to as an *external service* because it is a service that is not a built-in part of the product).</span></span> <span data-ttu-id="b6c0f-123">Enfin, si Lync Server se connecte à la passerelle SIP/CSTA par le biais d’une connexion TCP (Transmission Control Protocol) au lieu d’une connexion TLS (Transport Layer Security), vous devez également définir l’adresse IP de la passerelle à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="b6c0f-123">Finally, if Lync Server will connect to the SIP/CSTA gateway using a Transmission Control Protocol (TCP) connection instead of a Transport Layer Security (TLS) connection, you must also define the gateway IP address by using Topology Builder.</span></span>

<span data-ttu-id="b6c0f-124">Pour plus d’informations sur la configuration des itinéraires statiques, voir [configurer un itinéraire statique pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="b6c0f-124">For details about configuring static routes, see [Configure a static route for remote call control in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).</span></span>

<span data-ttu-id="b6c0f-125">Pour plus d’informations sur la configuration d’entrées d’applications approuvées, voir [configurer une entrée d’application fiable pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="b6c0f-125">For details about configuring trusted application entries, see [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).</span></span>

<span data-ttu-id="b6c0f-126">Pour plus d’informations sur la définition d’une adresse IP de passerelle SIP/CSTA dans le générateur de topologie, voir [définir une adresse IP de passerelle SIP/CSTA dans Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).</span><span class="sxs-lookup"><span data-stu-id="b6c0f-126">For details about defining a SIP/CSTA gateway IP address in Topology Builder, see [Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).</span></span>

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a><span data-ttu-id="b6c0f-127">Étape 3 : configurer les utilisateurs de Lync pour le contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="b6c0f-127">Step 3: Configure Lync Users for Remote Call Control</span></span>

<span data-ttu-id="b6c0f-128">Une fois les utilisateurs activés pour Lync Server, vous pouvez utiliser le panneau de configuration de Lync Server ou Lync Server Management Shell pour les activer pour le contrôle d’appel distant.</span><span class="sxs-lookup"><span data-stu-id="b6c0f-128">After users have been enabled for Lync Server, you can use Lync Server Control Panel or Lync Server Management Shell to enable them for remote call control.</span></span> <span data-ttu-id="b6c0f-129">Au cours de cette étape de déploiement, vous affectez à chaque utilisateur un URI de ligne et un URI de ligne.</span><span class="sxs-lookup"><span data-stu-id="b6c0f-129">It is during this deployment step that you assign each user a line server URI and a line URI.</span></span> <span data-ttu-id="b6c0f-130">L’URI de Line Server est l’URI SIP de la passerelle SIP/CSTA que vous envisagez d’affecter à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b6c0f-130">The line server URI is the SIP URI of the SIP/CSTA gateway that you plan to assign to the user.</span></span> <span data-ttu-id="b6c0f-131">L’URI de ligne correspond au numéro de téléphone unique attribué à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b6c0f-131">The line URI is the unique phone number assigned to the user.</span></span>

<span data-ttu-id="b6c0f-132">Pour plus d’informations sur la configuration des utilisateurs pour le contrôle d’appel distant, voir [activer les utilisateurs de Lync pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="b6c0f-132">For details about configuring users for remote call control, see [Enable Lync users for remote call control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span></span>

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a><span data-ttu-id="b6c0f-133">Étape 4 : définir les règles de normalisation des numéros de téléphone de Lync Server</span><span class="sxs-lookup"><span data-stu-id="b6c0f-133">Step 4: Define the Lync Server Phone Number Normalization Rules</span></span>

<span data-ttu-id="b6c0f-134">Dans les scénarios de contrôle d’appel distant, Lync Server utilise des règles de normalisation des numéros de téléphone pour convertir les numéros de téléphone reçus de la passerelle SIP/CSTA au format E. 164.</span><span class="sxs-lookup"><span data-stu-id="b6c0f-134">In remote call control scenarios, Lync Server uses phone number normalization rules to convert phone numbers it receives from the SIP/CSTA gateway to E.164 format.</span></span> <span data-ttu-id="b6c0f-135">Les numéros de téléphone doivent avoir le format standard pour que certaines fonctionnalités de contrôle d’appel distantes fonctionnent correctement.</span><span class="sxs-lookup"><span data-stu-id="b6c0f-135">Phone numbers must be in this standardized format for certain remote call control features to function properly.</span></span> <span data-ttu-id="b6c0f-136">Le contrôle d’appel distant utilise les mêmes règles de normalisation des numéros de téléphone que celles configurées pour la normalisation des numéros de téléphone du service de carnet d’adresses, qui diffèrent des règles de normalisation des numéros de téléphone pour Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="b6c0f-136">Remote call control uses the same phone number normalization rules that you configure for Address Book Service phone number normalization, which are different from the phone number normalization rules used for Enterprise Voice.</span></span>

<span data-ttu-id="b6c0f-137">Pour plus d’informations sur la façon dont le contrôle d’appel distant utilise les règles de normalisation des numéros de téléphone, voir [contrôle d’appel distant et normalisation du numéro de téléphone dans Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md).</span><span class="sxs-lookup"><span data-stu-id="b6c0f-137">For details about how remote call control uses phone number normalization rules, see [Remote call control and phone number normalization in Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md).</span></span> <span data-ttu-id="b6c0f-138">Pour plus d’informations sur les règles de normalisation des numéros de téléphone pour le service de carnet d’adresses, voir [administration du service de carnet d’adresses dans Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) , rubrique documentation sur les opérations.</span><span class="sxs-lookup"><span data-stu-id="b6c0f-138">For details about phone number normalization rules for Address Book Service, see [Administering the Address Book Service in Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) topic in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

