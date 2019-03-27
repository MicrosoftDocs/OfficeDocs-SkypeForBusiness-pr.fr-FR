---
title: Développeur des paramètres de l’ordinateur Edge
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 'Pour modifier les propriétés d’un serveur dans un pool de serveurs de périphérie, procédez comme suit :'
ms.openlocfilehash: 3d24eba1a24cf54da26b00b7b84b5b1b9fe52b61
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876235"
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="08aff-103">Développeur des paramètres de l’ordinateur Edge</span><span class="sxs-lookup"><span data-stu-id="08aff-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="08aff-104">Pour modifier les propriétés d’un serveur dans un pool de serveurs de périphérie, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="08aff-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="08aff-105">**nom interne ou nom de domaine complet** peut être modifié en modifiant le nom de domaine complet (FQDN).</span><span class="sxs-lookup"><span data-stu-id="08aff-105">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN).</span></span> <span data-ttu-id="08aff-106">Le nom de domaine complet doit correspondre à l’hôte (A) enregistrement de nom de domaine DNS (Domain Name System) et le nom du sujet du certificat à assigner au serveur pour l’interface réseau de périphérie interne.</span><span class="sxs-lookup"><span data-stu-id="08aff-106">The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface.</span></span> <span data-ttu-id="08aff-107">La valeur de **l’adresse IP interne** définit l’adresse IP qui est affectée à l’interface réseau qui est défini comme un réseau interne, par rapport à la conception de réseau de périmètre.</span><span class="sxs-lookup"><span data-stu-id="08aff-107">The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="08aff-108">Les trois sections de la boîte de dialogue définissent les adresses IP pour la configuration de ce serveur Edge externe.</span><span class="sxs-lookup"><span data-stu-id="08aff-108">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server.</span></span> <span data-ttu-id="08aff-109">La possibilité de modifier les adresses IP est affectée par le paramètre **Activer distinct nom de domaine complet et l’adresse IP pour les conférences web et A / V** sur les paramètres des propriétés au niveau du serveur Edge au niveau du pool.</span><span class="sxs-lookup"><span data-stu-id="08aff-109">The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="08aff-110">Accès SIP</span><span class="sxs-lookup"><span data-stu-id="08aff-110">SIP Access</span></span>

<span data-ttu-id="08aff-111">Modifier l’adresse IP externe qui est affectée à l’interface réseau pour l’accès protocole SIP (Session Initiation).</span><span class="sxs-lookup"><span data-stu-id="08aff-111">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access.</span></span> <span data-ttu-id="08aff-112">Cette adresse IP peut être une adresse IP publique ou une adresse dans la plage d’adresses IP privée.</span><span class="sxs-lookup"><span data-stu-id="08aff-112">This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="08aff-113">Si le paramètre **Activer distinct nom de domaine complet et l’adresse IP pour les conférences web et A / V** sur le pool page Paramètres n’est activée, que l’adresse IP pour l’accès SIP sera disponible pour la modification.</span><span class="sxs-lookup"><span data-stu-id="08aff-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="08aff-114">Conférence web</span><span class="sxs-lookup"><span data-stu-id="08aff-114">Web Conferencing</span></span>

<span data-ttu-id="08aff-115">Modifier l’adresse IP externe qui est affectée à l’interface réseau pour les conférences web.</span><span class="sxs-lookup"><span data-stu-id="08aff-115">Edit the external IP address that is assigned to the network interface for web conferencing.</span></span> <span data-ttu-id="08aff-116">Cette adresse IP peut être une adresse IP publique ou une adresse dans la plage d’adresses IP privée.</span><span class="sxs-lookup"><span data-stu-id="08aff-116">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="08aff-117">Audio/vidéo</span><span class="sxs-lookup"><span data-stu-id="08aff-117">Audio/Video</span></span>

<span data-ttu-id="08aff-118">Modifier l’adresse IP externe qui est affectée à l’interface réseau pour l’audio/vidéo (A / V).</span><span class="sxs-lookup"><span data-stu-id="08aff-118">Edit the external IP address that is assigned to the network interface for audio/video (A/V).</span></span> <span data-ttu-id="08aff-119">Cette adresse IP peut être une adresse IP publique ou une adresse dans la plage d’adresses IP privée.</span><span class="sxs-lookup"><span data-stu-id="08aff-119">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="08aff-120">Le paramètre de **NAT activé l’adresse IP publique** est l’adresse publique utilisée par l’interface externe soit a / V réseau interface ou le serveur de périphérie en général.</span><span class="sxs-lookup"><span data-stu-id="08aff-120">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general.</span></span> <span data-ttu-id="08aff-121">Si le paramètre **Activer distinct nom de domaine complet et l’adresse IP pour les conférences web et A / V** est activé, cette adresse IP publique est utilisée pour les trois interfaces externes.</span><span class="sxs-lookup"><span data-stu-id="08aff-121">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

