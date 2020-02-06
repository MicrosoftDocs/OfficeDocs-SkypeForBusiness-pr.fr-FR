---
title: Développeur des paramètres de l’ordinateur Edge pour Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Pour modifier les propriétés pour les ordinateurs du serveur de périphérie en tant que serveur à périphérie unique ou en tant qu’ordinateurs membres d’un pool de périphériques, vous pouvez configurer les paramètres de configuration de nom de serveur et d’adresse IP :'
ms.openlocfilehash: b90a3a00dcb1198e696112fc3d3ded08ff00060d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820096"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a><span data-ttu-id="2d6f3-103">Développeur des paramètres de l’ordinateur Edge pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="2d6f3-103">Edge Machine Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="2d6f3-104">Pour modifier les propriétés pour les ordinateurs du serveur de périphérie en tant que serveur à périphérie unique ou en tant qu’ordinateurs membres d’un pool de périphériques, vous pouvez configurer les paramètres de **configuration de nom de serveur et d’adresse IP** :</span><span class="sxs-lookup"><span data-stu-id="2d6f3-104">To edit the properties for Edge Server computers as an single Edge Server or as member computers in an Edge pool, you configure **Server name and IP address configuration** settings:</span></span>
  
- <span data-ttu-id="2d6f3-105">**Nom interne ou nom de domaine complet**: tapez le nom de l’ordinateur tel qu’il est référencé dans le DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="2d6f3-105">**Internal name or FQDN**: Type the name of the computer as it is referenced in the domain name system (DNS).</span></span> 
    
- <span data-ttu-id="2d6f3-106">**Adresse IPv4 interne**: tapez l’adresse IPv4 de la carte d’interface réseau (NIC) interne de cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="2d6f3-106">**Internal IPv4 address**: Type the IPv4 address of the internal network interface card (NIC) for this computer.</span></span>
    
- <span data-ttu-id="2d6f3-107">Vous configurez l' **adresse IPv4 externe** du **service Edge d’accès** associée à cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="2d6f3-107">You configure the **Access Edge service** **External IPv4 address** associated with this computer</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="2d6f3-108">Si vous avez choisi d’utiliser une adresse IP unique pour la configuration de serveur Edge, vous pouvez uniquement modifier l’adresse IPv4 externe du service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="2d6f3-108">If you selected to use a single IP address for the Edge Server configuration, you will only be able to edit the external IPv4 address for the Access Edge service.</span></span> <span data-ttu-id="2d6f3-109">Les autres services Edge partageront la même adresse IPv4 que le service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="2d6f3-109">The other Edge services will share the same IPv4 address as the Access Edge service.</span></span> 
  
- <span data-ttu-id="2d6f3-110">S’il est possible de modifier, vous configurez l' **adresse IPv4 externe** du **service de conférence Web** associée à cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="2d6f3-110">If available to edit, you configure the **Web Conferencing service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="2d6f3-111">S’il est possible de procéder à la modification, vous configurez l' **adresse IPv4 externe** du service à l’extérieur **A/V** associée à cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="2d6f3-111">If available to edit, you configure the **A/V Edge service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="2d6f3-112">S’il est possible de modifier, vous configurez l' **adresse IPv4 publique compatible NAT** associée à cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="2d6f3-112">If available to edit, you configure the **NAT-enabled public IPv4 address** associated with this computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="2d6f3-113">La propriété de configuration pour l' **adresse IPv4 publique compatible NAT** ne sera disponible qu’en modification si vous choisissez de fournir la traduction d’adresses réseau (NAT) pour le service Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="2d6f3-113">The configuration property for **NAT-enabled public IPv4 address** will only be available to edit if you chose to provide network address translation (NAT) for the A/V Edge service</span></span>
  
  <span data-ttu-id="2d6f3-114">**OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="2d6f3-114">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="2d6f3-115">**Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="2d6f3-115">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="2d6f3-116">**Aide** : permet d’afficher cet écran d’aide.</span><span class="sxs-lookup"><span data-stu-id="2d6f3-116">**Help** Displays this help screen.</span></span>
  

