---
title: Développeur des paramètres de l’ordinateur Edge
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
ROBOTS: NOINDEX, NOFOLLOW
description: 'Pour modifier les propriétés d’un serveur dans une liste de serveurs Edge, procédez comme suit :'
ms.openlocfilehash: 22f1e46481ce2392a806eadd6029ab51292d5585
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41702289"
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="08de8-103">Développeur des paramètres de l’ordinateur Edge</span><span class="sxs-lookup"><span data-stu-id="08de8-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="08de8-104">Pour modifier les propriétés d’un serveur dans une liste de serveurs Edge, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="08de8-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="08de8-105">Vous pouvez modifier le **nom interne ou le nom** de domaine complet en modifiant le nom de domaine complet (FQDN).</span><span class="sxs-lookup"><span data-stu-id="08de8-105">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN).</span></span> <span data-ttu-id="08de8-106">Le nom de domaine complet (FQDN) doit correspondre à l’enregistrement de l’hôte DNS (Domain Name System) et au nom du sujet du certificat attribué au serveur pour l’interface du réseau Edge interne.</span><span class="sxs-lookup"><span data-stu-id="08de8-106">The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface.</span></span> <span data-ttu-id="08de8-107">La valeur de l' **adresse IP interne** définit l’adresse IP qui est affectée à l’interface réseau qui est définie en tant que réseau interne, par rapport à la conception du réseau de périmètre.</span><span class="sxs-lookup"><span data-stu-id="08de8-107">The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="08de8-108">Les trois sections suivantes de la boîte de dialogue définissent les adresses IP pour la configuration externe de ce serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="08de8-108">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server.</span></span> <span data-ttu-id="08de8-109">La possibilité de modifier les adresses IP est affectée par le paramètre **autorisez un nom de domaine complet et une adresse IP distincts pour les conférences Web et A/V** sur les paramètres de propriétés au niveau du pool de serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="08de8-109">The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="08de8-110">Accès SIP</span><span class="sxs-lookup"><span data-stu-id="08de8-110">SIP Access</span></span>

<span data-ttu-id="08de8-111">Modifiez l’adresse IP externe qui est affectée à l’interface réseau pour l’accès au protocole SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="08de8-111">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access.</span></span> <span data-ttu-id="08de8-112">Cette adresse IP peut être une adresse IP publique ou une adresse dans la plage d’adresses IP privées.</span><span class="sxs-lookup"><span data-stu-id="08de8-112">This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="08de8-113">Si le paramètre **activer le nom de domaine complet et l’adresse IP séparés pour les conférences Web et a/V** sur la page Paramètres du pool est activé, seule l’adresse IP de l’accès SIP sera disponible pour modification.</span><span class="sxs-lookup"><span data-stu-id="08de8-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="08de8-114">Conférence web</span><span class="sxs-lookup"><span data-stu-id="08de8-114">Web Conferencing</span></span>

<span data-ttu-id="08de8-115">Modifiez l’adresse IP externe qui est affectée à l’interface réseau pour les conférences Web.</span><span class="sxs-lookup"><span data-stu-id="08de8-115">Edit the external IP address that is assigned to the network interface for web conferencing.</span></span> <span data-ttu-id="08de8-116">Cette adresse IP peut être une adresse IP publique ou une adresse dans la plage d’adresses IP privées.</span><span class="sxs-lookup"><span data-stu-id="08de8-116">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="08de8-117">Audio/vidéo</span><span class="sxs-lookup"><span data-stu-id="08de8-117">Audio/Video</span></span>

<span data-ttu-id="08de8-118">Modifiez l’adresse IP externe qui est affectée à l’interface réseau pour les appels audio/vidéo (A/V).</span><span class="sxs-lookup"><span data-stu-id="08de8-118">Edit the external IP address that is assigned to the network interface for audio/video (A/V).</span></span> <span data-ttu-id="08de8-119">Cette adresse IP peut être une adresse IP publique ou une adresse dans la plage d’adresses IP privées.</span><span class="sxs-lookup"><span data-stu-id="08de8-119">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="08de8-120">Le paramètre de l' **adresse IP publique activée pour tar** est l’adresse publique utilisée par l’interface externe pour l’interface réseau A/V ou le serveur Edge en général.</span><span class="sxs-lookup"><span data-stu-id="08de8-120">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general.</span></span> <span data-ttu-id="08de8-121">Si le paramètre **activer le nom de domaine complet et l’adresse IP séparés pour les conférences Web et si a/V** est activé, cette adresse IP publique est utilisée pour les trois interfaces externes.</span><span class="sxs-lookup"><span data-stu-id="08de8-121">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

