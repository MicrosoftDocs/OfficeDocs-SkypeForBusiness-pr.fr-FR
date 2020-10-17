---
title: 'Lync Server 2013 : composants VoIP de serveur frontal'
description: 'Lync Server 2013 : composants VoIP de serveur frontal.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End Server VoIP components
ms:assetid: 310e81a7-da45-47d4-95d0-92837e386502
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425812(v=OCS.15)
ms:contentKeyID: 48183765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9390d06cf6277ef79ec2ec785bad4b497bc04a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567090"
---
# <a name="front-end-server-voip-components-for-lync-server-2013"></a><span data-ttu-id="164b4-103">Composants VoIP de serveur frontal pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="164b4-103">Front End Server VoIP components for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="164b4-104">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="164b4-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="164b4-105">Les composants VoIP situés sur les serveurs frontaux sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="164b4-105">The VoIP components located on Front End Servers are as follows:</span></span>

  - <span data-ttu-id="164b4-106">Service de traduction</span><span class="sxs-lookup"><span data-stu-id="164b4-106">Translation Service</span></span>

  - <span data-ttu-id="164b4-107">Composant de routage entrant</span><span class="sxs-lookup"><span data-stu-id="164b4-107">Inbound Routing component</span></span>

  - <span data-ttu-id="164b4-108">Composant de routage sortant</span><span class="sxs-lookup"><span data-stu-id="164b4-108">Outbound Routing component</span></span>

  - <span data-ttu-id="164b4-109">Composant de routage de messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="164b4-109">Exchange UM Routing component</span></span>

  - <span data-ttu-id="164b4-110">Composant de routage InterCluster</span><span class="sxs-lookup"><span data-stu-id="164b4-110">Intercluster Routing component</span></span>

  - [<span data-ttu-id="164b4-111">Composant de serveur de médiation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="164b4-111">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)

<div>

## <a name="translation-service"></a><span data-ttu-id="164b4-112">Service de traduction</span><span class="sxs-lookup"><span data-stu-id="164b4-112">Translation Service</span></span>

<span data-ttu-id="164b4-p101">Le service de traduction est le composant serveur chargé de convertir un numéro composé au format E.164 ou autre format, selon les règles de normalisation définies par l’administrateur. Il est capable de traduire vers des formats autres qu’E.164 si votre organisation utilise un système de numérotation privé ou une passerelle, ou encore un système PBX qui ne prend pas en charge le format E.164.</span><span class="sxs-lookup"><span data-stu-id="164b4-p101">The Translation Service is the server component that is responsible for translating a dialed number into the E.164 format or another format, according to the normalization rules that are defined by the administrator. The Translation Service can translate to formats other than E.164 if your organization uses a private numbering system or uses a gateway or PBX that does not support E.164.</span></span>

</div>

<div>

## <a name="inbound-routing-component"></a><span data-ttu-id="164b4-115">Composant de routage entrant</span><span class="sxs-lookup"><span data-stu-id="164b4-115">Inbound Routing Component</span></span>

<span data-ttu-id="164b4-116">Le composant de routage entrant gère essentiellement les appels entrants selon les préférences que les utilisateurs ont spécifiées sur leurs clients Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="164b4-116">The Inbound Routing component handles incoming calls largely according to preferences that are specified by users on their Enterprise Voice clients.</span></span> <span data-ttu-id="164b4-117">Il permet également l’activation de la sonnerie sur le poste de délégués et de sonneries simultanées, si ces fonctionnalités sont configurées par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="164b4-117">It also facilitates delegate ringing and simultaneous ringing, if configured by the user.</span></span> <span data-ttu-id="164b4-118">Par exemple, les utilisateurs spécifient si les appels sans réponse doivent être transférés ou simplement consignés pour notification.</span><span class="sxs-lookup"><span data-stu-id="164b4-118">For example, users specify whether unanswered calls are forwarded or simply logged for notification.</span></span> <span data-ttu-id="164b4-119">Si le transfert d’appel est activé, les utilisateurs peuvent spécifier si les appels sans réponse doivent être transférés vers un autre numéro ou vers un serveur de messagerie unifiée Exchange configuré pour fournir le répondeur automatique.</span><span class="sxs-lookup"><span data-stu-id="164b4-119">If call forwarding is enabled, users can specify whether unanswered calls should be forwarded to another number or to a Exchange UM server that has been configured to provide call answering.</span></span> <span data-ttu-id="164b4-120">Le composant de routage entrant est installé par défaut sur tous les serveurs Standard Edition et serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="164b4-120">The Inbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

</div>

<div>

## <a name="outbound-routing-component"></a><span data-ttu-id="164b4-121">Composant de routage sortant</span><span class="sxs-lookup"><span data-stu-id="164b4-121">Outbound Routing Component</span></span>

<span data-ttu-id="164b4-122">Le composant de routage sortant achemine les appels vers des destinations PBX ou PSTN.</span><span class="sxs-lookup"><span data-stu-id="164b4-122">The Outbound Routing component routes calls to PBX or PSTN destinations.</span></span> <span data-ttu-id="164b4-123">Il applique aux appelants des règles d’autorisation d’appels issues de la stratégie de voix de l’utilisateur et détermine la meilleure passerelle PSTN pour le routage de chaque appel.</span><span class="sxs-lookup"><span data-stu-id="164b4-123">It applies call authorization rules, as defined by the user’s voice policy, to callers and determines the optimal PSTN gateway for routing each call.</span></span> <span data-ttu-id="164b4-124">Le composant de routage sortant est installé par défaut sur tous les serveurs Standard Edition et serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="164b4-124">The Outbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

<span data-ttu-id="164b4-125">La logique de routage qu’il utilise est en grande partie configurée par les administrateurs réseau ou de téléphonie en fonction des exigences de leur organisation.</span><span class="sxs-lookup"><span data-stu-id="164b4-125">The routing logic that is used by the Outbound Routing component is in large measure configured by network or telephony administrators according to the requirements of their organizations.</span></span>

</div>

<div>

## <a name="exchange-um-routing-component"></a><span data-ttu-id="164b4-126">Composant de routage de messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="164b4-126">Exchange UM Routing Component</span></span>

<span data-ttu-id="164b4-127">Le composant de routage de messagerie unifiée Exchange gère le routage entre Lync Server et les serveurs exécutant la messagerie unifiée Exchange, pour intégrer Lync Server aux fonctionnalités de messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="164b4-127">The Exchange UM routing component handles routing between Lync Server and servers running Exchange Unified Messaging (UM), to integrate Lync Server with Unified Messaging features.</span></span>

<span data-ttu-id="164b4-128">Le composant de routage de messagerie unifiée Exchange gère également le réacheminement de la messagerie vocale sur le réseau téléphonique commuté si les serveurs de messagerie unifiée Exchange sont indisponibles.</span><span class="sxs-lookup"><span data-stu-id="164b4-128">The Exchange UM routing component also handles rerouting of voice mail over the PSTN if Exchange UM servers are unavailable.</span></span> <span data-ttu-id="164b4-129">Si vous avez des utilisateurs de voix entreprise sur des sites de succursale qui n’ont pas de liaison de réseau étendu résiliente à un site central, le Survivable Branch Appliance que vous déployez sur le site de succursale offre une survivabilité de la messagerie vocale pour les utilisateurs de succursale lors d’une panne de réseau étendu.</span><span class="sxs-lookup"><span data-stu-id="164b4-129">If you have Enterprise Voice users at branch sites that do not have a resilient WAN link to a central site, the Survivable Branch Appliance that you deploy at the branch site provides voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="164b4-130">Lorsque la liaison WAN est indisponible, l'appareil Survivable Branch Appliance procède comme suit :</span><span class="sxs-lookup"><span data-stu-id="164b4-130">When the WAN link is unavailable, the Survivable Branch Appliance does the following:</span></span>

  - <span data-ttu-id="164b4-131">réachemine les appels sans réponse via la passerelle PSTN vers le serveur de messagerie unifiée Exchange localisé sur le site central ;</span><span class="sxs-lookup"><span data-stu-id="164b4-131">reroutes unanswered calls over the PSTN to the Exchange Unified Messaging server in the central site</span></span>

  - <span data-ttu-id="164b4-132">permet aux utilisateurs de récupérer leurs messages vocaux via la passerelle PSTN ;</span><span class="sxs-lookup"><span data-stu-id="164b4-132">provides the ability for a user to retrieve voice mail messages over the PSTN</span></span>

  - <span data-ttu-id="164b4-133">met en file d’attente les notifications d’appels manqués, puis les télécharge vers le serveur de messagerie unifiée Exchange lorsque la liaison de réseau étendu est rétablie.</span><span class="sxs-lookup"><span data-stu-id="164b4-133">queues missed call notifications, and then uploads them to the Exchange UM server when the WAN link is restored.</span></span>

<span data-ttu-id="164b4-134">Pour activer le reroutage de la messagerie vocale, il est recommandé que votre administrateur Exchange configurez le standard automatique de messagerie unifiée Exchange (AA) pour accepter uniquement les messages.</span><span class="sxs-lookup"><span data-stu-id="164b4-134">To enable voice mail rerouting, we recommend that your Exchange administrator configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span>

<span data-ttu-id="164b4-135">Pour plus d’informations sur ces fonctionnalités, reportez-vous à la rubrique [Planning for Exchange Unified Messaging Integration in Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) et [Planning for Enterprise Voice Resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md), respectivement.</span><span class="sxs-lookup"><span data-stu-id="164b4-135">For details about these features, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Planning for Enterprise Voice resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md), respectively.</span></span>

</div>

<div>

## <a name="intercluster-routing-component"></a><span data-ttu-id="164b4-136">Composant de routage InterCluster</span><span class="sxs-lookup"><span data-stu-id="164b4-136">Intercluster Routing Component</span></span>

<span data-ttu-id="164b4-p105">Le composant de routage Intercluster est chargé d’acheminer les appels vers le pool de serveurs d’inscriptions principal du destinataire de l’appel. S’il n’est pas disponible, le composant achemine l’appel vers le pool d’inscriptions secondaire du destinataire de l’appel. Si ces deux pools ne sont pas joignables via le réseau IP, le composant de routage Intercluster réachemine l’appel vers le numéro de téléphone de l’utilisateur via la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="164b4-p105">The Intercluster routing component is responsible for routing calls to the callee’s primary Registrar pool. If that is unavailable, the component routes the call to the callee’s backup Registrar pool. If the callee’s primary and backup Registrar pools are unreachable over the IP network, the Intercluster routing component reroutes the call over the PSTN to the user’s telephone number.</span></span>

</div>

<div>

## <a name="other-front-end-server-components-required-for-voip"></a><span data-ttu-id="164b4-140">Autres composants du serveur frontal requis pour la voix sur IP (VoIP)</span><span class="sxs-lookup"><span data-stu-id="164b4-140">Other Front End Server Components Required for VoIP</span></span>

<span data-ttu-id="164b4-141">Les autres composants qui résident sur le serveur frontal ou le directeur qui fournissent la prise en charge essentielle de VoIP, mais qui ne sont pas eux-mêmes des composants VoIP, incluent les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="164b4-141">Other components residing on the Front End Server or Director that provide essential support for VoIP, but are not themselves VoIP components, include the following:</span></span>

  - <span data-ttu-id="164b4-142">**Services d’utilisateurs**</span><span class="sxs-lookup"><span data-stu-id="164b4-142">**User Services.**</span></span> <span data-ttu-id="164b4-143">: effectuent une recherche inversée de numéros sur le numéro de téléphone de destination de chaque appel entrant et associent ce numéro à l’URI SIP de l’utilisateur de destination.</span><span class="sxs-lookup"><span data-stu-id="164b4-143">Perform reverse number lookup on the destination phone number of each incoming call and match that number to the SIP URI of the destination user.</span></span> <span data-ttu-id="164b4-144">À l’aide de ces informations, le composant de routage entrant dirige l’appel vers les points de terminaison SIP enregistrés de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="164b4-144">Using this information, the Inbound Routing component distributes the call to that user’s registered SIP endpoints.</span></span> <span data-ttu-id="164b4-145">Services d’utilisateurs est un composant de base sur tous les serveurs frontaux et les directeurs.</span><span class="sxs-lookup"><span data-stu-id="164b4-145">User Services is a core component on all Front End Servers and Directors.</span></span>

  - <span data-ttu-id="164b4-146">**Réplicateur d’utilisateurs**</span><span class="sxs-lookup"><span data-stu-id="164b4-146">**User Replicator.**</span></span> <span data-ttu-id="164b4-147">Extrait les numéros de téléphone des utilisateurs des services de domaine Active Directory et les écrit dans les tables de la base de données RTC, où ils sont disponibles pour les services d’utilisateurs et le serveur de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="164b4-147">Extracts user phone numbers from Active Directory Domain Services and writes them to tables in the RTC database, where they are available to User Services and Address Book Server.</span></span> <span data-ttu-id="164b4-148">Le réplicateur d’utilisateurs est un composant principal sur tous les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="164b4-148">User Replicator is a core component on all Front End Servers.</span></span>

  - <span data-ttu-id="164b4-149">**Serveur de carnet d’adresses**</span><span class="sxs-lookup"><span data-stu-id="164b4-149">**Address Book Server.**</span></span> <span data-ttu-id="164b4-150">Fournit des informations sur les listes d’adresses globales des services de domaine Active Directory aux clients Lync Server.</span><span class="sxs-lookup"><span data-stu-id="164b4-150">Provides global address list information from Active Directory Domain Services to Lync Server clients.</span></span> <span data-ttu-id="164b4-151">Il récupère également les informations d’utilisateur et de contact de la base de données RTC, écrit les informations dans les fichiers du carnet d’adresses, puis stocke les fichiers dans un dossier partagé dans lequel ils sont téléchargés par les clients Lync.</span><span class="sxs-lookup"><span data-stu-id="164b4-151">It also retrieves user and contact information from the RTC database, writes the information to the Address Book files, and then stores the files on a shared folder where they are downloaded by Lync clients.</span></span> <span data-ttu-id="164b4-152">Le serveur de carnet d’adresses écrit les informations dans la base de données RTCAb, qui est utilisée par le service de requête Web du carnet d’adresses pour répondre aux requêtes de recherche utilisateur à partir de Microsoft Lync 2010 mobile.</span><span class="sxs-lookup"><span data-stu-id="164b4-152">The Address Book Server writes the information to the RTCAb database, which is used by the Address Book Web Query service to respond to user search queries from Microsoft Lync 2010 Mobile.</span></span> <span data-ttu-id="164b4-153">Elle normalise éventuellement les numéros de téléphone des utilisateurs de l’entreprise qui sont écrits dans la base de données RTC à des fins de mise en service des contacts utilisateur dans Lync.</span><span class="sxs-lookup"><span data-stu-id="164b4-153">It optionally normalizes enterprise user phone numbers that are written to the RTC database for the purpose of provisioning user contacts in Lync.</span></span> <span data-ttu-id="164b4-154">Le service de carnet d’adresses est installé par défaut sur tous les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="164b4-154">The Address Book service is installed by default on all Front End Servers.</span></span> <span data-ttu-id="164b4-155">Le service de requête Web du carnet d’adresses est installé par défaut avec les services Web sur chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="164b4-155">The Address Book Web Query service is installed by default with the Web services on each Front End Servers.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

