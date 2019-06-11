---
title: Activer le contrôle d’appel distant
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Enable remote call control
ms:assetid: 0b91d418-e6ed-4556-97af-e8523e01f249
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204664(v=OCS.15)
ms:contentKeyID: 48183380
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 310a140d3497a77ddcaeb8ba32403aa8f28b68e5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838873"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-remote-call-control"></a><span data-ttu-id="a0de5-102">Activer le contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="a0de5-102">Enable remote call control</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0de5-103">_**Dernière modification de la rubrique:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="a0de5-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="a0de5-104">Le contrôle d’appel distant permet aux utilisateurs de contrôler leurs téléphones PBX (Private Branch Exchange) à l’aide de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a0de5-104">Remote call control enables users to control their desktop private branch exchange (PBX) phones by using Lync Server 2013.</span></span> <span data-ttu-id="a0de5-105">Si vous avez déployé le contrôle d’appel distant dans votre environnement hérité et souhaitez le migrer vers Lync Server 2013, vous devez effectuer les tâches suivantes:</span><span class="sxs-lookup"><span data-stu-id="a0de5-105">If you deployed remote call control in your legacy environment and want to migrate it Lync Server 2013, you need to perform the following tasks:</span></span>

1.  <span data-ttu-id="a0de5-106">Installez une passerelle SIP/CSTA et configurez-la pour communiquer avec votre système PBX.</span><span class="sxs-lookup"><span data-stu-id="a0de5-106">Install a SIP/CSTA gateway and configure it to communicate with your PBX.</span></span> <span data-ttu-id="a0de5-107">Vous devez effectuer cette étape lors du déploiement de votre pool de pilotes Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a0de5-107">You need to do this step when you deploy your Lync Server 2013 pilot pool.</span></span>

2.  <span data-ttu-id="a0de5-108">Après avoir fusionné votre topologie et effectué la migration de vos stratégies et paramètres, configurez Lync Server 2013 pour acheminer les demandes CSTA vers la passerelle SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="a0de5-108">After you merge your topology and migrate your policies and settings, configure Lync Server 2013 to route CSTA requests to the SIP/CSTA gateway.</span></span> <span data-ttu-id="a0de5-109">Cette étape est une étape manuelle qui suit la migration automatique.</span><span class="sxs-lookup"><span data-stu-id="a0de5-109">This step is a manual step that follows the automated migration.</span></span> <span data-ttu-id="a0de5-110">Pour configurer le routage des requêtes CSTA, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="a0de5-110">To configure routing for CSTA requests, do the following:</span></span>
    
      - <span data-ttu-id="a0de5-111">Supprimer les entrées d’hébergement d’ancienne génération (connues sous le nom d' *entrées de serveurs de confiance* dans Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="a0de5-111">Remove legacy authorized host entries (known as *trusted server entries* in Lync Server 2013).</span></span> <span data-ttu-id="a0de5-112">Si vous migrez des utilisateurs à partir de votre déploiement hérité, assurez-vous que vous avez supprimé toutes les entrées d’hôtes approuvées que vous avez créées pour la passerelle SIP/CSTA avant de configurer de nouvelles entrées de l’application fiable sur le pool de pilotes de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a0de5-112">If you are migrating users from your legacy deployment, ensure that you remove all existing authorized host entries that you created for the SIP/CSTA gateway before you configure new trusted application entries on the Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="a0de5-113">Pour plus d’informations sur la façon de supprimer des entrées d’hébergement héritées, voir [supprimer une entrée d’hôte autorisé](remove-an-authorized-host-entry.md).</span><span class="sxs-lookup"><span data-stu-id="a0de5-113">For details about how to remove legacy authorized host entries, see [Remove an authorized host entry](remove-an-authorized-host-entry.md).</span></span>
    
      - <span data-ttu-id="a0de5-114">Configurer un itinéraire statique pour le contrôle d’appel distant.</span><span class="sxs-lookup"><span data-stu-id="a0de5-114">Configure a static route for remote call control.</span></span> <span data-ttu-id="a0de5-115">Vous pouvez configurer un itinéraire statique pour les pools individuels que vous voulez prendre en charge le contrôle d’appel distant, ou vous pouvez configurer un itinéraire statique global de telle sorte que chaque liste qui n’est pas configuré avec un itinéraire statique au niveau du pool utilise l’itinéraire statique global.</span><span class="sxs-lookup"><span data-stu-id="a0de5-115">You can configure a static route for individual pools that you want to support remote call control, or you can configure a global static route so that each pool that is not configured with a pool-level static route uses the global static route.</span></span> <span data-ttu-id="a0de5-116">Pour plus d’informations sur la configuration de l’itinéraire statique, voir [configurer un itinéraire statique pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="a0de5-116">For details about how to configure the static route, see [Configure a static route for remote call control in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="a0de5-117">Configurez une entrée d’application fiable pour le contrôle d’appel distant de chaque pool pour lequel vous souhaitez prendre en charge le contrôle d’appel distant.</span><span class="sxs-lookup"><span data-stu-id="a0de5-117">Configure a trusted application entry for remote call control on each pool for which you want to support remote call control.</span></span> <span data-ttu-id="a0de5-118">Pour plus d’informations sur la configuration d’une entrée d’application fiable, voir [configurer une entrée d’application fiable pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="a0de5-118">For details about how to configure a trusted application entry, see [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="a0de5-119">Si vous avez déployé une passerelle SIP/CSTA qui utilise le protocole TCP (Transmission Control Protocol) pour vous connecter à Lync Server 2013, définissez l’adresse IP de la passerelle dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="a0de5-119">If you deployed a SIP/CSTA gateway that uses Transmission Control Protocol (TCP) to connect to Lync Server 2013, define the IP address of the gateway in Topology Builder.</span></span> <span data-ttu-id="a0de5-120">Pour plus d’informations sur la définition de l’adresse IP, voir [définir une adresse IP de passerelle SIP/CSTA dans Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="a0de5-120">For details about defining the IP address, see [Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) in the Deployment documentation.</span></span>

4.  <span data-ttu-id="a0de5-121">Configurez les utilisateurs de Lync 2013 pour le contrôle d’appel distant en activant le contrôle d’appel distant et en assignant un URI (Uniform Resource Identifier) et un URI de ligne.</span><span class="sxs-lookup"><span data-stu-id="a0de5-121">Configure Lync 2013 users for remote call control by enabling remote call control and assigning a line server Uniform Resource Identifier (URI) and a line URI.</span></span> <span data-ttu-id="a0de5-122">Lorsque vous migrez des utilisateurs de votre déploiement hérité vers Lync Server 2013, les paramètres de contrôle des appels distants sont migrés avec les paramètres d’autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a0de5-122">When you migrate users from your legacy deployment to Lync Server 2013, the remote call control settings are migrated along with the other user settings.</span></span>

5.  <span data-ttu-id="a0de5-123">Si vous personnalisez les règles de normalisation des numéros de téléphone de votre carnet d’adresses dans votre déploiement hérité, vous devez effectuer certaines tâches manuelles après la migration automatique de stratégies et de paramètres pour migrer les règles de normalisation personnalisées.</span><span class="sxs-lookup"><span data-stu-id="a0de5-123">If you customized Address Book phone number normalization rules in your legacy deployment, you need to perform some manual tasks after the automated migration of policies and settings is complete to migrate the customized normalization rules.</span></span> <span data-ttu-id="a0de5-124">Si vous n’avez pas personnalisé de règles de normalisation, le carnet d’adresses est migré avec le reste de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="a0de5-124">If you did not customize normalization rules, Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="a0de5-125">Pour plus d’informations sur la migration manuelle de règles de normalisation personnalisées, voir migrer le [carnet d’adresses](migrate-address-book_1.md).</span><span class="sxs-lookup"><span data-stu-id="a0de5-125">For details about manually migrating customized normalization rules, see [Migrate Address Book](migrate-address-book_1.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

