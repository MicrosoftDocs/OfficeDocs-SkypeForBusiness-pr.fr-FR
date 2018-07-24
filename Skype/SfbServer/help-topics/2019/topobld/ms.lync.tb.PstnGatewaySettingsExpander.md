---
title: Expanseur des paramètres de la passerelle PSTN
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
ROBOTS: NOINDEX, NOFOLLOW
description: 'Pour modifier les paramètres d’une passerelle réseau téléphonique commuté (RTC), modifiez les champs suivants :'
ms.openlocfilehash: 6b23d419b12fcb13dc5de07e550fbedd3a866ab5
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21058335"
---
# <a name="pstn-gateway-settings-expander"></a><span data-ttu-id="85890-103">Expanseur des paramètres de la passerelle PSTN</span><span class="sxs-lookup"><span data-stu-id="85890-103">PSTN Gateway Settings Expander</span></span>
 
<span data-ttu-id="85890-104">Pour modifier les paramètres d’une passerelle réseau téléphonique commuté (RTC), modifiez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="85890-104">To edit or modify the settings for a public switched telephone network (PSTN) gateway, modify the following fields:</span></span>
  
<span data-ttu-id="85890-105">Le nom de domaine complet (FQDN) ou l’adresse IP de la passerelle doit être renseigné. Il détermine si le **nom de domaine complet (FQDN)** de la passerelle du réseau téléphonique commuté (RTC) est défini par l’enregistrement d’hôte DNS (A), une entrée de fichier HÔTE statique ou par l’adresse IP de la passerelle RTC.</span><span class="sxs-lookup"><span data-stu-id="85890-105">Gateway FQDN or IP Address is a required entry and defines wither the **Fully qualified domain name (FQDN)** of the PSTN gateway as defined by a Domain Name System (DNS) host (A) record, a static HOSTS file entry, or by the IP address of the PSTN gateway.</span></span>
  
<span data-ttu-id="85890-p101">Le protocole de transport SIP est le protocole  TCP (Transmission Control Protocol) ou le protocole TLS (Transport Layer Security). Le protocole TLS est le protocole par défaut. Pour connaître la prise en charge de la passerelle, reportez-vous à la documentation du fournisseur. Le protocole par défaut, le protocole TLS, est un choix plus sécurisé si la passerelle le prend en charge.</span><span class="sxs-lookup"><span data-stu-id="85890-p101">The SIP Transport Protocol can either be Transmission Control Protocol (TCP) or Transport Layer Security (TLS). TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>
  
<span data-ttu-id="85890-110">Choisissez d’activer IPv4 et IPv6 pour la passerelle.</span><span class="sxs-lookup"><span data-stu-id="85890-110">Select whether to enable IPv4 and IPv6 for the gateway.</span></span>
  
<span data-ttu-id="85890-111">L' **adresse IP média de remplacement** est une définition pour le serveur de médiation pour lequel la passerelle RTC déployée a une adresse IP différente pour le trafic multimédia à l’adresse IP configurée par défaut, qui est généralement dédié pour le trafic SIP.</span><span class="sxs-lookup"><span data-stu-id="85890-111">The **Alternate media IP address** is a definition for the Mediation Server for which the deployed PSTN gateway has a different IP address for media traffic than the default configured IP address, which is typically dedicated for SIP traffic.</span></span> <span data-ttu-id="85890-112">Si vous définissez ce paramètre, la passerelle RTC prend en charge une interface réseau ou un chemin d’accès aux médias différent.</span><span class="sxs-lookup"><span data-stu-id="85890-112">If you define this parameter, then the PSTN gateway supports a different supports a different network interface or path for media.</span></span> <span data-ttu-id="85890-113">Si cette adresse n’est pas renseignée, la passerelle RTC ne prend pas en charge un autre chemin d’accès des médias.</span><span class="sxs-lookup"><span data-stu-id="85890-113">If this address is left blank, then the PSTN gateway does not support the alternate path for media.</span></span>
  

