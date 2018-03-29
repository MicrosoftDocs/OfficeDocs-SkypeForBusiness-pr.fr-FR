---
title: Contour Machine paramètres Expander
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 'Pour modifier les propriétés d’un serveur dans un pool de serveurs Edge, effectuez les opérations suivantes :'
ms.openlocfilehash: 04b8d8efc455203e49aeb81e533604a405e37cc5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="5ec12-103">Contour Machine paramètres Expander</span><span class="sxs-lookup"><span data-stu-id="5ec12-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="5ec12-104">Pour modifier les propriétés d’un serveur dans un pool de serveurs Edge, effectuez les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="5ec12-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="5ec12-105">**nom interne ou le nom de domaine complet** peut être modifié en modifiant le nom de domaine pleinement qualifié (FQDN).</span><span class="sxs-lookup"><span data-stu-id="5ec12-105">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN).</span></span> <span data-ttu-id="5ec12-106">Le nom de domaine complet doit correspondre à l’hôte (A) enregistrement de Domain Name System (DNS) et le nom du sujet du certificat affecté au serveur de l’interface réseau de bord interne.</span><span class="sxs-lookup"><span data-stu-id="5ec12-106">The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface.</span></span> <span data-ttu-id="5ec12-107">La valeur de **l’adresse IP interne** définit l’adresse IP qui est assignée à l’interface réseau qui est défini comme un réseau interne, par rapport à la conception du réseau de périmètre.</span><span class="sxs-lookup"><span data-stu-id="5ec12-107">The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="5ec12-108">Les trois sections de la boîte de dialogue définissent les adresses IP pour la configuration externe de ce serveur de transport Edge.</span><span class="sxs-lookup"><span data-stu-id="5ec12-108">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server.</span></span> <span data-ttu-id="5ec12-109">La possibilité de modifier les adresses IP est affectée par le paramètre **Activer distinct nom de domaine complet et l’adresse IP pour les conférences web et A / V** au niveau du pool sur les paramètres des propriétés au niveau du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="5ec12-109">The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="5ec12-110">Accès SIP</span><span class="sxs-lookup"><span data-stu-id="5ec12-110">SIP Access</span></span>

<span data-ttu-id="5ec12-111">Modifier l’adresse IP externe qui est affectée à l’interface réseau pour l’accès de Session Initiation Protocol (SIP).</span><span class="sxs-lookup"><span data-stu-id="5ec12-111">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access.</span></span> <span data-ttu-id="5ec12-112">Cette adresse IP peut être une adresse IP publique ou une adresse dans la plage d’adresses IP privées.</span><span class="sxs-lookup"><span data-stu-id="5ec12-112">This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5ec12-113">Si le paramètre **Activer distinct nom de domaine complet et l’adresse IP pour les conférences web et A / V** sur le pool de page Paramètres est activé, seuls l’adresse IP pour un accès SIP sont disponible pour l’édition.</span><span class="sxs-lookup"><span data-stu-id="5ec12-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="5ec12-114">Conférence web</span><span class="sxs-lookup"><span data-stu-id="5ec12-114">Web Conferencing</span></span>

<span data-ttu-id="5ec12-115">Modifier l’adresse IP externe qui est affectée à l’interface réseau pour la conférence web.</span><span class="sxs-lookup"><span data-stu-id="5ec12-115">Edit the external IP address that is assigned to the network interface for web conferencing.</span></span> <span data-ttu-id="5ec12-116">Cette adresse IP peut être soit une adresse IP publique ou une adresse dans la plage d’adresses IP privées.</span><span class="sxs-lookup"><span data-stu-id="5ec12-116">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="5ec12-117">Audio/vidéo</span><span class="sxs-lookup"><span data-stu-id="5ec12-117">Audio/Video</span></span>

<span data-ttu-id="5ec12-118">Modifier l’adresse IP externe est affectée à l’interface réseau pour audio/vidéo (A / V).</span><span class="sxs-lookup"><span data-stu-id="5ec12-118">Edit the external IP address that is assigned to the network interface for audio/video (A/V).</span></span> <span data-ttu-id="5ec12-119">Cette adresse IP peut être soit une adresse IP publique ou une adresse dans la plage d’adresses IP privées.</span><span class="sxs-lookup"><span data-stu-id="5ec12-119">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="5ec12-120">Le paramètre de **NAT activé adresse IP publique** est l’adresse publique utilisée par l’interface externe de l’A / V réseau interface ou le serveur de transport Edge en général.</span><span class="sxs-lookup"><span data-stu-id="5ec12-120">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general.</span></span> <span data-ttu-id="5ec12-121">Si le paramètre **Activer distinct nom de domaine complet et l’adresse IP pour les conférences web et A / V** est activée, cette adresse IP publique est utilisée pour toutes les interfaces externes trois.</span><span class="sxs-lookup"><span data-stu-id="5ec12-121">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

