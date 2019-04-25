---
title: Développeur des paramètres de l’ordinateur Edge pour Lync Server 2010
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Pour modifier les propriétés pour les ordinateurs de serveur de transport Edge en tant qu’un serveur de périphérie unique ou en tant qu’ordinateurs membres d’un pool de serveurs Edge, vous configurez le nom du serveur et les paramètres de configuration d’adresses IP :'
ms.openlocfilehash: f0125ba8d9c7ff181aff0a29f69a5077b1ad0818
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225362"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a><span data-ttu-id="84f3a-103">Développeur des paramètres de l’ordinateur Edge pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="84f3a-103">Edge Machine Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="84f3a-104">Pour modifier les propriétés pour les ordinateurs de serveur de transport Edge en tant qu’un serveur de périphérie unique ou en tant qu’ordinateurs membres d’un pool de serveurs Edge, configurer les paramètres de **configuration d’adresse IP et de nom de serveur** :</span><span class="sxs-lookup"><span data-stu-id="84f3a-104">To edit the properties for Edge Server computers as an single Edge Server or as member computers in an Edge pool, you configure **Server name and IP address configuration** settings:</span></span>
  
- <span data-ttu-id="84f3a-105">**Nom interne ou nom de domaine complet**: tapez le nom de l’ordinateur car il est référencé dans le système de nom de domaine (DNS).</span><span class="sxs-lookup"><span data-stu-id="84f3a-105">**Internal name or FQDN**: Type the name of the computer as it is referenced in the domain name system (DNS).</span></span> 
    
- <span data-ttu-id="84f3a-106">**Adresse IPv4 interne**: tapez l’adresse IPv4 de la carte d’interface réseau interne (NIC) pour cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="84f3a-106">**Internal IPv4 address**: Type the IPv4 address of the internal network interface card (NIC) for this computer.</span></span>
    
- <span data-ttu-id="84f3a-107">Vous configurez **service Edge d’accès** **adresse IPv4 externe** associé à cet ordinateur</span><span class="sxs-lookup"><span data-stu-id="84f3a-107">You configure the **Access Edge service** **External IPv4 address** associated with this computer</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="84f3a-108">Si vous avez sélectionné à utiliser une adresse IP unique pour la configuration du serveur Edge, vous pourrez uniquement modifier l’adresse IPv4 externe pour le service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="84f3a-108">If you selected to use a single IP address for the Edge Server configuration, you will only be able to edit the external IPv4 address for the Access Edge service.</span></span> <span data-ttu-id="84f3a-109">Autres services Edge partagent la même adresse IPv4 en tant que service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="84f3a-109">The other Edge services will share the same IPv4 address as the Access Edge service.</span></span> 
  
- <span data-ttu-id="84f3a-110">Si elle est disponible pour le modifier, vous configurez **service de conférence Web** **adresse IPv4 externe** associé à cet ordinateur</span><span class="sxs-lookup"><span data-stu-id="84f3a-110">If available to edit, you configure the **Web Conferencing service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="84f3a-111">Si Modifier disponible, configurez la **A / V Edge service** **adresse IPv4 externe** associé à cet ordinateur</span><span class="sxs-lookup"><span data-stu-id="84f3a-111">If available to edit, you configure the **A/V Edge service** **External IPv4 address** associated with this computer</span></span>
    
- <span data-ttu-id="84f3a-112">Si elle est disponible pour modifier, vous configurez l' **adresse IPv4 publique du NAT activé** associée à cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="84f3a-112">If available to edit, you configure the **NAT-enabled public IPv4 address** associated with this computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="84f3a-113">La propriété de configuration pour **laquelle NAT est activé les adresse IPv4 publique** ne seront disponible pour modifier si vous avez choisi pour fournir la traduction d’adresses réseau (NAT) a / V Edge service</span><span class="sxs-lookup"><span data-stu-id="84f3a-113">The configuration property for **NAT-enabled public IPv4 address** will only be available to edit if you chose to provide network address translation (NAT) for the A/V Edge service</span></span>
  
  <span data-ttu-id="84f3a-114">**OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="84f3a-114">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="84f3a-115">**Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="84f3a-115">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="84f3a-116">**Aide** : permet d’afficher cet écran d’aide.</span><span class="sxs-lookup"><span data-stu-id="84f3a-116">**Help** Displays this help screen.</span></span>
  

