---
title: Expanseur des paramètres de l’ordinateur Edge pour Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Pour modifier les propriétés des ordinateurs serveurs Edge en tant que serveur Edge unique ou en tant qu’ordinateurs membres dans un pool de serveurs Edge, vous configurez les paramètres de configuration du nom du serveur et de l’adresse IP :'
ms.openlocfilehash: e25f68ec510cf15cd58872a8c584dc71aa939f48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807134"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a><span data-ttu-id="bd4df-103">Expandeur des paramètres de l’ordinateur Edge pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="bd4df-103">Edge Machine Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="bd4df-104">Pour modifier les propriétés des ordinateurs serveurs Edge en tant que serveur Edge unique ou en tant qu’ordinateurs membres dans un pool de serveurs Edge, vous configurez les paramètres de configuration du nom du serveur et de l’adresse **IP** :</span><span class="sxs-lookup"><span data-stu-id="bd4df-104">To edit the properties for Edge Server computers as an single Edge Server or as member computers in an Edge pool, you configure **Server name and IP address configuration** settings:</span></span>
  
- <span data-ttu-id="bd4df-105">**Nom interne ou nom de domaine complet**: tapez le nom de l’ordinateur tel qu’il est référencé dans le DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="bd4df-105">**Internal name or FQDN**: Type the name of the computer as it is referenced in the domain name system (DNS).</span></span> 
    
- <span data-ttu-id="bd4df-106">**Adresse IPv4 interne**: tapez l’adresse IPv4 de la carte d’interface réseau interne (NIC) de cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="bd4df-106">**Internal IPv4 address**: Type the IPv4 address of the internal network interface card (NIC) for this computer.</span></span>
    
- <span data-ttu-id="bd4df-107">Vous configurez l’adresse **IPv4** externe du **service Edge** d’accès associée à cet ordinateur</span><span class="sxs-lookup"><span data-stu-id="bd4df-107">You configure the **Access Edge service** **External IPv4 address** associated with this computer</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="bd4df-108">Si vous avez choisi d’utiliser une seule adresse IP pour la configuration du serveur Edge, vous ne pourrez modifier que l’adresse IPv4 externe pour le service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="bd4df-108">If you selected to use a single IP address for the Edge Server configuration, you will only be able to edit the external IPv4 address for the Access Edge service.</span></span> <span data-ttu-id="bd4df-109">Les autres services Edge partagent la même adresse IPv4 que le service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="bd4df-109">The other Edge services will share the same IPv4 address as the Access Edge service.</span></span> 
  
- <span data-ttu-id="bd4df-110">Si vous pouvez le modifier, vous configurez l’adresse **IPv4** externe du service de conférence **Web** associée à cet ordinateur</span><span class="sxs-lookup"><span data-stu-id="bd4df-110">If available to edit, you configure the **Web Conferencing service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="bd4df-111">Si disponible pour modification, vous configurez l’adresse **IPv4** externe du **service Edge A/V** associée à cet ordinateur</span><span class="sxs-lookup"><span data-stu-id="bd4df-111">If available to edit, you configure the **A/V Edge service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="bd4df-112">Si vous pouvez le modifier, vous configurez l’adresse **IPv4 publique activée** pour NAT associée à cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="bd4df-112">If available to edit, you configure the **NAT-enabled public IPv4 address** associated with this computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="bd4df-113">La propriété de configuration de l’adresse **IPv4** publique activée pour NAT ne pourra être modifiée que si vous avez choisi de fournir la traduction d’adresses réseau (NAT) pour le service Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="bd4df-113">The configuration property for **NAT-enabled public IPv4 address** will only be available to edit if you chose to provide network address translation (NAT) for the A/V Edge service</span></span>
  
  <span data-ttu-id="bd4df-114">**OK** permet d’accepter et de valider les modifications de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="bd4df-114">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="bd4df-115">**Annuler** permet d’annuler les modifications et de fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="bd4df-115">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="bd4df-116">**Aide** permet d’afficher cet écran d’aide.</span><span class="sxs-lookup"><span data-stu-id="bd4df-116">**Help** Displays this help screen.</span></span>
  

