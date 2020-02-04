---
title: 'Lync Server 2013 : composants VoIP du serveur frontal'
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
ms.openlocfilehash: 8bab5751fc0291047f3795731f379d1e14f5f12b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739734"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-server-voip-components-for-lync-server-2013"></a><span data-ttu-id="7d44f-102">Composants VoIP du serveur frontal pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d44f-102">Front End Server VoIP components for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d44f-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="7d44f-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="7d44f-104">Les composants VoIP situés sur les serveurs frontaux sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="7d44f-104">The VoIP components located on Front End Servers are as follows:</span></span>

  - <span data-ttu-id="7d44f-105">Service de conversion</span><span class="sxs-lookup"><span data-stu-id="7d44f-105">Translation Service</span></span>

  - <span data-ttu-id="7d44f-106">Composant de routage entrant</span><span class="sxs-lookup"><span data-stu-id="7d44f-106">Inbound Routing component</span></span>

  - <span data-ttu-id="7d44f-107">Composant de routage sortant</span><span class="sxs-lookup"><span data-stu-id="7d44f-107">Outbound Routing component</span></span>

  - <span data-ttu-id="7d44f-108">Composant de routage de messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="7d44f-108">Exchange UM Routing component</span></span>

  - <span data-ttu-id="7d44f-109">Composant de routage InterCluster</span><span class="sxs-lookup"><span data-stu-id="7d44f-109">Intercluster Routing component</span></span>

  - [<span data-ttu-id="7d44f-110">Composant serveur de médiation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d44f-110">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)

<div>

## <a name="translation-service"></a><span data-ttu-id="7d44f-111">Service de conversion</span><span class="sxs-lookup"><span data-stu-id="7d44f-111">Translation Service</span></span>

<span data-ttu-id="7d44f-p101">Le service de conversion est le composant serveur chargé de convertir un numéro composé au format E.164 ou autre format, selon les règles de normalisation définies par l’administrateur. Il est capable de convertir vers des formats autres qu’E.164 si votre organisation utilise un système de numérotation privé ou une passerelle, ou encore un système PBX qui ne prend pas en charge le format E.164.</span><span class="sxs-lookup"><span data-stu-id="7d44f-p101">The Translation Service is the server component that is responsible for translating a dialed number into the E.164 format or another format, according to the normalization rules that are defined by the administrator. The Translation Service can translate to formats other than E.164 if your organization uses a private numbering system or uses a gateway or PBX that does not support E.164.</span></span>

</div>

<div>

## <a name="inbound-routing-component"></a><span data-ttu-id="7d44f-114">Composant de routage entrant</span><span class="sxs-lookup"><span data-stu-id="7d44f-114">Inbound Routing Component</span></span>

<span data-ttu-id="7d44f-115">Le composant de routage entrant gère les appels entrants en fonction des préférences spécifiées par les utilisateurs sur leurs clients vocaux d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="7d44f-115">The Inbound Routing component handles incoming calls largely according to preferences that are specified by users on their Enterprise Voice clients.</span></span> <span data-ttu-id="7d44f-116">Il permet également l’activation de la sonnerie sur le poste de délégués et de sonneries simultanées, si ces fonctionnalités sont configurées par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7d44f-116">It also facilitates delegate ringing and simultaneous ringing, if configured by the user.</span></span> <span data-ttu-id="7d44f-117">Par exemple, les utilisateurs spécifient si les appels sans réponse doivent être transférés ou simplement consignés pour notification.</span><span class="sxs-lookup"><span data-stu-id="7d44f-117">For example, users specify whether unanswered calls are forwarded or simply logged for notification.</span></span> <span data-ttu-id="7d44f-118">Si le transfert d’appel est activé, les utilisateurs peuvent spécifier si les appels sans réponse doivent être transférés vers un autre numéro ou vers un serveur de messagerie unifiée configuré pour fournir les réponses aux appels.</span><span class="sxs-lookup"><span data-stu-id="7d44f-118">If call forwarding is enabled, users can specify whether unanswered calls should be forwarded to another number or to a Exchange UM server that has been configured to provide call answering.</span></span> <span data-ttu-id="7d44f-119">Le composant de routage de trafic entrant est installé par défaut sur tous les serveurs frontaux et serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="7d44f-119">The Inbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

</div>

<div>

## <a name="outbound-routing-component"></a><span data-ttu-id="7d44f-120">Composant de routage sortant</span><span class="sxs-lookup"><span data-stu-id="7d44f-120">Outbound Routing Component</span></span>

<span data-ttu-id="7d44f-121">Le composant de routage sortant achemine les appels vers des destinations PBX ou RTC.</span><span class="sxs-lookup"><span data-stu-id="7d44f-121">The Outbound Routing component routes calls to PBX or PSTN destinations.</span></span> <span data-ttu-id="7d44f-122">Il applique aux appelants des règles d’autorisation d’appels issues de la stratégie de voix de l’utilisateur et détermine la meilleure passerelle RTC pour le routage de chaque appel.</span><span class="sxs-lookup"><span data-stu-id="7d44f-122">It applies call authorization rules, as defined by the user’s voice policy, to callers and determines the optimal PSTN gateway for routing each call.</span></span> <span data-ttu-id="7d44f-123">Le composant de routage sortant est installé par défaut sur tous les serveurs frontaux et serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="7d44f-123">The Outbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

<span data-ttu-id="7d44f-124">La logique de routage qu’il utilise est en grande partie configurée par les administrateurs réseau ou de téléphonie en fonction des exigences de leur organisation.</span><span class="sxs-lookup"><span data-stu-id="7d44f-124">The routing logic that is used by the Outbound Routing component is in large measure configured by network or telephony administrators according to the requirements of their organizations.</span></span>

</div>

<div>

## <a name="exchange-um-routing-component"></a><span data-ttu-id="7d44f-125">Composant de routage de messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="7d44f-125">Exchange UM Routing Component</span></span>

<span data-ttu-id="7d44f-126">Le composant routage de messagerie unifiée Exchange gère le routage entre le serveur Lync et les serveurs exécutant la messagerie unifiée Exchange, pour intégrer Lync Server aux fonctionnalités de messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="7d44f-126">The Exchange UM routing component handles routing between Lync Server and servers running Exchange Unified Messaging (UM), to integrate Lync Server with Unified Messaging features.</span></span>

<span data-ttu-id="7d44f-127">Le composant routage de messagerie UNIFIÉe Exchange gère également le reroutage de la messagerie vocale sur le RTC si des serveurs de messagerie unifiée Exchange ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="7d44f-127">The Exchange UM routing component also handles rerouting of voice mail over the PSTN if Exchange UM servers are unavailable.</span></span> <span data-ttu-id="7d44f-128">Si vous avez des utilisateurs d’Enterprise Voice sur des sites de succursale qui n’ont pas de lien réseau étendu fiable vers un site central, l’unité de branchement survivant que vous déployez sur le site de succursale fournit une survie de la messagerie vocale pour les utilisateurs de succursales en cas de panne du réseau étendu.</span><span class="sxs-lookup"><span data-stu-id="7d44f-128">If you have Enterprise Voice users at branch sites that do not have a resilient WAN link to a central site, the Survivable Branch Appliance that you deploy at the branch site provides voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="7d44f-129">Lorsque le lien WAN n’est pas disponible, l’unité de branchement Survivable effectue les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="7d44f-129">When the WAN link is unavailable, the Survivable Branch Appliance does the following:</span></span>

  - <span data-ttu-id="7d44f-130">réachemine les appels sans réponse via la passerelle RTC vers le serveur de messagerie unifiée Exchange localisé sur le site central ;</span><span class="sxs-lookup"><span data-stu-id="7d44f-130">reroutes unanswered calls over the PSTN to the Exchange Unified Messaging server in the central site</span></span>

  - <span data-ttu-id="7d44f-131">permet aux utilisateurs de récupérer leurs messages vocaux via la passerelle RTC ;</span><span class="sxs-lookup"><span data-stu-id="7d44f-131">provides the ability for a user to retrieve voice mail messages over the PSTN</span></span>

  - <span data-ttu-id="7d44f-132">met en file d’attente les notifications d’appels manqués, puis les télécharge vers le serveur de messagerie unifiée Exchange lorsque la liaison de réseau étendu est rétablie.</span><span class="sxs-lookup"><span data-stu-id="7d44f-132">queues missed call notifications, and then uploads them to the Exchange UM server when the WAN link is restored.</span></span>

<span data-ttu-id="7d44f-133">Pour activer le reroutage de la messagerie vocale, nous vous conseillons de configurer le standard automatique de votre administrateur Exchange pour qu’il accepte uniquement les messages.</span><span class="sxs-lookup"><span data-stu-id="7d44f-133">To enable voice mail rerouting, we recommend that your Exchange administrator configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span>

<span data-ttu-id="7d44f-134">Pour plus d’informations sur ces fonctionnalités, reportez-vous à la rubrique [planification de l’intégration de la messagerie unifiée Exchange dans Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) et [planification de la résilience vocale entreprise dans Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md), respectivement.</span><span class="sxs-lookup"><span data-stu-id="7d44f-134">For details about these features, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Planning for Enterprise Voice resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md), respectively.</span></span>

</div>

<div>

## <a name="intercluster-routing-component"></a><span data-ttu-id="7d44f-135">Composant de routage InterCluster</span><span class="sxs-lookup"><span data-stu-id="7d44f-135">Intercluster Routing Component</span></span>

<span data-ttu-id="7d44f-p105">Le composant de routage Intercluster est chargé d’acheminer les appels vers le pool de serveurs d’inscriptions principal du destinataire de l’appel. S’il n’est pas disponible, le composant achemine l’appel vers le pool d’inscriptions secondaire du destinataire de l’appel. Si ces deux pools ne sont pas joignables via le réseau IP, le composant de routage Intercluster réachemine l’appel vers le numéro de téléphone de l’utilisateur via la passerelle RTC.</span><span class="sxs-lookup"><span data-stu-id="7d44f-p105">The Intercluster routing component is responsible for routing calls to the callee’s primary Registrar pool. If that is unavailable, the component routes the call to the callee’s backup Registrar pool. If the callee’s primary and backup Registrar pools are unreachable over the IP network, the Intercluster routing component reroutes the call over the PSTN to the user’s telephone number.</span></span>

</div>

<div>

## <a name="other-front-end-server-components-required-for-voip"></a><span data-ttu-id="7d44f-139">Autres composants du serveur frontal requis pour la voix sur IP (VoIP)</span><span class="sxs-lookup"><span data-stu-id="7d44f-139">Other Front End Server Components Required for VoIP</span></span>

<span data-ttu-id="7d44f-140">D’autres composants résidant sur le serveur frontal ou le directeur qui fournissent une prise en charge essentielle de VoIP, mais qui ne sont pas eux-mêmes des composants VoIP, incluent les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="7d44f-140">Other components residing on the Front End Server or Director that provide essential support for VoIP, but are not themselves VoIP components, include the following:</span></span>

  - <span data-ttu-id="7d44f-141">**Services d’utilisateurs**</span><span class="sxs-lookup"><span data-stu-id="7d44f-141">**User Services.**</span></span> <span data-ttu-id="7d44f-142">: effectuent une recherche inversée de numéros sur le numéro de téléphone de destination de chaque appel entrant et associent ce numéro à l’URI SIP de l’utilisateur de destination.</span><span class="sxs-lookup"><span data-stu-id="7d44f-142">Perform reverse number lookup on the destination phone number of each incoming call and match that number to the SIP URI of the destination user.</span></span> <span data-ttu-id="7d44f-143">À l’aide de ces informations, le composant de routage entrant dirige l’appel vers les points de terminaison SIP enregistrés de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7d44f-143">Using this information, the Inbound Routing component distributes the call to that user’s registered SIP endpoints.</span></span> <span data-ttu-id="7d44f-144">User Services est un composant principal de tous les serveurs et directeurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="7d44f-144">User Services is a core component on all Front End Servers and Directors.</span></span>

  - <span data-ttu-id="7d44f-145">**Réplicateur d’utilisateurs**</span><span class="sxs-lookup"><span data-stu-id="7d44f-145">**User Replicator.**</span></span> <span data-ttu-id="7d44f-146">Extrait les numéros de téléphone des utilisateurs des services de domaine Active Directory et les écrit dans les tables de la base de données RTC qui sont accessibles aux services d’utilisateurs et au serveur du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="7d44f-146">Extracts user phone numbers from Active Directory Domain Services and writes them to tables in the RTC database, where they are available to User Services and Address Book Server.</span></span> <span data-ttu-id="7d44f-147">Le réplicateur d’utilisateurs est un composant principal sur tous les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="7d44f-147">User Replicator is a core component on all Front End Servers.</span></span>

  - <span data-ttu-id="7d44f-148">**Serveur de carnet d’adresses**</span><span class="sxs-lookup"><span data-stu-id="7d44f-148">**Address Book Server.**</span></span> <span data-ttu-id="7d44f-149">Fournit des informations de liste d’adresses globale provenant des services de domaine Active Directory aux clients Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7d44f-149">Provides global address list information from Active Directory Domain Services to Lync Server clients.</span></span> <span data-ttu-id="7d44f-150">Elle récupère également les informations d’utilisateur et de contact de la base de données RTC, enregistre les informations dans les fichiers du carnet d’adresses, puis stocke les fichiers dans un dossier partagé dans lequel ils sont téléchargés par les clients Lync.</span><span class="sxs-lookup"><span data-stu-id="7d44f-150">It also retrieves user and contact information from the RTC database, writes the information to the Address Book files, and then stores the files on a shared folder where they are downloaded by Lync clients.</span></span> <span data-ttu-id="7d44f-151">Le serveur du carnet d’adresses écrit les informations dans la base de données RTCAb, qui est utilisée par le service de requête sur le carnet d’adresses pour répondre aux requêtes de recherche utilisateur de Microsoft Lync 2010 mobile.</span><span class="sxs-lookup"><span data-stu-id="7d44f-151">The Address Book Server writes the information to the RTCAb database, which is used by the Address Book Web Query service to respond to user search queries from Microsoft Lync 2010 Mobile.</span></span> <span data-ttu-id="7d44f-152">Il est également normalisé de mettre en place les numéros de téléphone des utilisateurs d’entreprise qui sont écrits dans la base de données RTC dans le cadre de la mise en service des contacts utilisateur dans Lync.</span><span class="sxs-lookup"><span data-stu-id="7d44f-152">It optionally normalizes enterprise user phone numbers that are written to the RTC database for the purpose of provisioning user contacts in Lync.</span></span> <span data-ttu-id="7d44f-153">Le service de carnet d’adresses est installé par défaut sur tous les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="7d44f-153">The Address Book service is installed by default on all Front End Servers.</span></span> <span data-ttu-id="7d44f-154">Le service de requête sur le carnet d’adresses est installé par défaut avec les services Web sur chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="7d44f-154">The Address Book Web Query service is installed by default with the Web services on each Front End Servers.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

