---
title: Contour Machine paramètres Expander pour Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Pour modifier les propriétés pour les ordinateurs de serveur de transport Edge sous la forme d’un seul serveur de transport Edge ou ordinateurs membres dans un pool d’arête, vous configurez le nom du serveur et les paramètres de configuration d’adresse IP :'
ms.openlocfilehash: d1bc35683ff70e1666a46d478aa97b3bcc3d5593
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a><span data-ttu-id="8b500-103">Contour Machine paramètres Expander pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="8b500-103">Edge Machine Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="8b500-104">Pour modifier les propriétés pour les ordinateurs de serveur de transport Edge sous la forme d’un seul serveur de transport Edge ou ordinateurs membres dans un pool d’arête, vous configurez les paramètres de **configuration d’adresse IP et de nom de serveur** :</span><span class="sxs-lookup"><span data-stu-id="8b500-104">To edit the properties for Edge Server computers as an single Edge Server or as member computers in an Edge pool, you configure **Server name and IP address configuration** settings:</span></span>
  
- <span data-ttu-id="8b500-105">**Nom interne ou le nom de domaine complet**: tapez le nom de l’ordinateur, car il est référencé dans le système de nom de domaine (DNS).</span><span class="sxs-lookup"><span data-stu-id="8b500-105">**Internal name or FQDN**: Type the name of the computer as it is referenced in the domain name system (DNS).</span></span> 
    
- <span data-ttu-id="8b500-106">**Adresse IPv4 interne**: tapez l’adresse IPv4 de la carte d’interface réseau interne (NIC) pour cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="8b500-106">**Internal IPv4 address**: Type the IPv4 address of the internal network interface card (NIC) for this computer.</span></span>
    
- <span data-ttu-id="8b500-107">Vous configurez **service Edge d’accès** **adresse IPv4 externes** associés à cet ordinateur</span><span class="sxs-lookup"><span data-stu-id="8b500-107">You configure the **Access Edge service** **External IPv4 address** associated with this computer</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8b500-108">Si vous avez sélectionné utiliser une seule adresse IP pour la configuration du serveur de transport Edge, vous pourrez uniquement modifier l’adresse IPv4 externe pour le service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="8b500-108">If you selected to use a single IP address for the Edge Server configuration, you will only be able to edit the external IPv4 address for the Access Edge service.</span></span> <span data-ttu-id="8b500-109">Les autres services de bord partagent la même adresse IPv4 en tant que le service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="8b500-109">The other Edge services will share the same IPv4 address as the Access Edge service.</span></span> 
  
- <span data-ttu-id="8b500-110">Si elle est disponible pour les modifier, vous configurez **service de conférence Web** **adresse IPv4 externes** associés à cet ordinateur</span><span class="sxs-lookup"><span data-stu-id="8b500-110">If available to edit, you configure the **Web Conferencing service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="8b500-111">Si disponible pour les modifier, vous configurez la **A / V Edge service** **adresse IPv4 externes** associés à cet ordinateur</span><span class="sxs-lookup"><span data-stu-id="8b500-111">If available to edit, you configure the **A/V Edge service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="8b500-112">Si elle est disponible pour les modifier, vous configurez **NAT activé les adresses IPv4 publiques** associées à cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="8b500-112">If available to edit, you configure the **NAT-enabled public IPv4 address** associated with this computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8b500-113">La propriété de configuration pour **laquelle NAT est activé les adresses IPv4 publiques** n’est disponible pour modifier si vous avez choisi de fournir la traduction d’adresses réseau (NAT) pour l’un / V Edge service</span><span class="sxs-lookup"><span data-stu-id="8b500-113">The configuration property for **NAT-enabled public IPv4 address** will only be available to edit if you chose to provide network address translation (NAT) for the A/V Edge service</span></span>
  
 <span data-ttu-id="8b500-114">**OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="8b500-114">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="8b500-115">**Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="8b500-115">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="8b500-116">**Aide** : permet d’afficher cet écran d’aide.</span><span class="sxs-lookup"><span data-stu-id="8b500-116">**Help** Displays this help screen.</span></span>
  

