---
title: Expanseur des paramètres de la passerelle PSTN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
description: 'Pour éditer les paramètres d’une passerelle réseau téléphonique commuté (PSTN), modifiez les champs suivants :'
ms.openlocfilehash: 10669d4355acc8d2ea1a8546275116660c1ac7a7
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216585"
---
# <a name="pstn-gateway-settings-expander"></a><span data-ttu-id="0e8e7-103">Expanseur des paramètres de la passerelle PSTN</span><span class="sxs-lookup"><span data-stu-id="0e8e7-103">PSTN Gateway Settings Expander</span></span>
 
<span data-ttu-id="0e8e7-104">Pour éditer les paramètres d’une passerelle réseau téléphonique commuté (PSTN), modifiez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="0e8e7-104">To edit or modify the settings for a public switched telephone network (PSTN) gateway, modify the following fields:</span></span>
  
<span data-ttu-id="0e8e7-105">Nom de domaine complet (FQDN) ou l’adresse IP de la passerelle est une entrée requise. Elle détermine si le **Nom de domaine complet (FQDN)** de la passerelle du réseau téléphonique commuté (PSTN) est défini par l’enregistrement DNS hôte (A), une entrée de fichier HÔTE statique, ou par l’adresse IP de la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="0e8e7-105">Gateway FQDN or IP Address is a required entry and defines wither the **Fully qualified domain name (FQDN)** of the PSTN gateway as defined by a Domain Name System (DNS) host (A) record, a static HOSTS file entry, or by the IP address of the PSTN gateway.</span></span>
  
<span data-ttu-id="0e8e7-p101">Le protocole de transport SIP est soit TCP (Transmission Control Protocol), soit TLS (Transport Layer Security). TLS est le protocole par défaut. Consultez la documentation du fournisseur de la passerelle pour connaître la prise en charge de la passerelle. TLS, protocole par défaut, représente un choix plus sécurisé si la passerelle le prend en charge.</span><span class="sxs-lookup"><span data-stu-id="0e8e7-p101">The SIP Transport Protocol can either be Transmission Control Protocol (TCP) or Transport Layer Security (TLS). TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>
  
<span data-ttu-id="0e8e7-110">Choisissez d’activer IPv4 et IPv6 pour la passerelle.</span><span class="sxs-lookup"><span data-stu-id="0e8e7-110">Select whether to enable IPv4 and IPv6 for the gateway.</span></span>
  
<span data-ttu-id="0e8e7-p102">L’**Adresse IP média de remplacement** définit le serveur de médiation : la passerelle PSTN déployée dispose d’une adresse IP différente pour le trafic multimédia par rapport à l’adresse IP configurée par défaut, généralement dédiée au trafic SIP. Si vous définissez ce paramètre, la passerelle PSTN prend en charge une interface réseau ou un chemin d’accès des médias différent. Si cette adresse n’est pas remplie, la passerelle PSTN ne prend pas en charge un autre chemin d’accès des médias.</span><span class="sxs-lookup"><span data-stu-id="0e8e7-p102">The **Alternate media IP address** is a definition for the Mediation Server for which the deployed PSTN gateway has a different IP address for media traffic than the default configured IP address, which is typically dedicated for SIP traffic. If you define this parameter, then the PSTN gateway supports a different supports a different network interface or path for media. If this address is left blank, then the PSTN gateway does not support the alternate path for media.</span></span>
  

