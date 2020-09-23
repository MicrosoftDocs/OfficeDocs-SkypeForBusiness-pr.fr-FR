---
title: Expanseur des paramètres de l’ordinateur Edge
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: "Pour modifier les propriétés d'un serveur dans un pool de serveurs Edge, procédez comme suit :"
ms.openlocfilehash: e62cfa000379ed7318c5780bf91ac40035e6beee
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218915"
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="3d6b1-103">Expanseur des paramètres de l’ordinateur Edge</span><span class="sxs-lookup"><span data-stu-id="3d6b1-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="3d6b1-104">Pour modifier les propriétés d'un serveur dans un pool de serveurs Edge, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="3d6b1-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="3d6b1-p101">Le **nom interne ou nom de domaine complet** peut être changé en modifiant le nom de domaine complet (FQDN). Le nom de domaine complet doit correspondre à l’enregistrement DNS A (hôte), et au nom du sujet du certificat assigné au serveur pour l’interface réseau Edge interne. La valeur de l’**Adresse IP interne** définit l’adresse IP assignée à l’interface réseau définie comme réseau interne, en fonction de la conception du réseau de périmètre.</span><span class="sxs-lookup"><span data-stu-id="3d6b1-p101">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN). The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface. The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="3d6b1-p102">Les trois sections suivantes de la boîte de dialogue définissent les adresses IP pour la configuration externe de ce serveur Edge. La possibilité de modifier les adresses IP est influencée par le paramètre **Activer un nom de domaine complet et une adresse IP distincts pour la conférence web et les fonctionnalités audio/vidéo** dans les paramètres Propriétés au niveau du pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="3d6b1-p102">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server. The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="3d6b1-110">Accès SIP</span><span class="sxs-lookup"><span data-stu-id="3d6b1-110">SIP Access</span></span>

<span data-ttu-id="3d6b1-p103">Modifier l'adresse IP externe assignée à l'interface réseau pour l'accès SIP (Session Initiation Protocol). Cette adresse IP peut être soit une adresse IP publique, soit une adresse dans la plage d'adresses IP privées.</span><span class="sxs-lookup"><span data-stu-id="3d6b1-p103">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access. This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3d6b1-113">Si le paramètre **Activer un nom de domaine complet et une adresse IP distincts pour la conférence Web et A/V** est activé sur la page des paramètres du pool, seule l'adresse IP pour l'accès SIP est modifiable.</span><span class="sxs-lookup"><span data-stu-id="3d6b1-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="3d6b1-114">Conférence web</span><span class="sxs-lookup"><span data-stu-id="3d6b1-114">Web Conferencing</span></span>

<span data-ttu-id="3d6b1-p104">Modifiez l’adresse IP externe assignée à l’interface réseau pour la conférence web. Cette adresse IP peut être soit une adresse IP publique, soit une adresse dans la plage d’adresses IP privées.</span><span class="sxs-lookup"><span data-stu-id="3d6b1-p104">Edit the external IP address that is assigned to the network interface for web conferencing. This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="3d6b1-117">Audio/Vidéo</span><span class="sxs-lookup"><span data-stu-id="3d6b1-117">Audio/Video</span></span>

<span data-ttu-id="3d6b1-p105">Modifiez l’adresse IP externe assignée à l’interface réseau pour l’audio/vidéo (A/V). Cette adresse IP peut être soit une adresse IP publique, soit une adresse dans la plage d’adresses IP privées.</span><span class="sxs-lookup"><span data-stu-id="3d6b1-p105">Edit the external IP address that is assigned to the network interface for audio/video (A/V). This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="3d6b1-p106">Le paramètre **Adresse IP publique compatible avec NAT utilisée** est l’adresse publique utilisée par l’interface externe soit pour l’interface réseau A/V, soit pour le serveur Edge en général. Si le paramètre **Activer un nom de domaine complet et une adresse IP distincts pour la conférence web et les fonctionnalités audio/vidéo** est activé, cette adresse IP publique est utilisée pour ces trois interfaces externes.</span><span class="sxs-lookup"><span data-stu-id="3d6b1-p106">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general. If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

