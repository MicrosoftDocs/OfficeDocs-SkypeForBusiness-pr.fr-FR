---
title: Modifier l’expanseur des paramètres de l’ordinateur Edge pour Lync Server 2010
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
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Vous modifiez les paramètres du serveur Edge ou du pool de serveurs Edge en configurant les propriétés suivantes :'
ms.openlocfilehash: f77eb71948bbbe6d2fe3e24b400d29e3bf5fd5a5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803294"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a><span data-ttu-id="e7689-103">Modifier l’expandeur des paramètres de l’ordinateur Edge pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e7689-103">Edit Edge Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="e7689-104">Vous modifiez les paramètres du serveur Edge ou du pool de serveurs Edge en configurant les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7689-104">You edit the settings for the Edge Server or Edge pool by configuring the following properties:</span></span> 
  
 <span data-ttu-id="e7689-105">**Général**</span><span class="sxs-lookup"><span data-stu-id="e7689-105">**General**</span></span>
  
- <span data-ttu-id="e7689-106">Nom de domaine complet du **pool** interne : le nom de domaine complet du pool interne est l’identité du serveur Edge ou du pool edge tel que défini dans l’enregistrement d’hôte DNS (A ou AAAA pour IPv6).</span><span class="sxs-lookup"><span data-stu-id="e7689-106">**Internal pool FQDN**: The internal pool fully qualified domain name is the identity of the Edge Server or Edge pool as defined in the domain name system (DNS) host (A or AAAA for IPv6) record.</span></span>
    
- <span data-ttu-id="e7689-107">Sélectionnez Activer la fédération pour ce **pool Edge (port 5061)** si vous souhaitez activer le serveur Edge ou le pool edge pour la fédération avec d’autres partenaires de protocole d’initiation de session.</span><span class="sxs-lookup"><span data-stu-id="e7689-107">Select **Enable federation for this Edge pool (port 5061)** if you want to enable the Edge Server or Edge pool for federation with other session initiation protocol partners.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e7689-108">Vous ne pouvez définir qu’un seul serveur Edge ou pool edge activement pour la fédération.</span><span class="sxs-lookup"><span data-stu-id="e7689-108">You can only define one Edge Server or Edge pool actively for federation.</span></span> <span data-ttu-id="e7689-109">La configuration indiquée dans la capture d’écran associée indique qu’un autre serveur Edge ou pool de serveurs Edge est déjà configuré pour la fédération.</span><span class="sxs-lookup"><span data-stu-id="e7689-109">The configuration shown in the associated screen shot indicates that another Edge Server or Edge pool is already configured for federation.</span></span> <span data-ttu-id="e7689-110">L’enregistrement SRV DNS externe pour la fédération (_sipfederationtls._tcp. ) pointe vers le serveur Edge ou le \<external domain name\> pool edge pour la fédération.</span><span class="sxs-lookup"><span data-stu-id="e7689-110">The external DNS SRV record for federation (_sipfederationtls._tcp.\<external domain name\>) will point to the Edge Server or Edge pool for federation.</span></span> 
  
- <span data-ttu-id="e7689-111">Le port de réplication de configuration **interne (HTTPS),** par défaut sur le port TCP 4443, est le port sur qui la copie locale (c’est-à-dire, locale des serveurs Edge) du magasin central de gestion est répliquée.</span><span class="sxs-lookup"><span data-stu-id="e7689-111">The **Internal Configuration Replication Port (HTTPS)**, by default at TCP port 4443, is the port that the local (that is, local to the Edge Servers) copy of the Central Management store is replicated over.</span></span> <span data-ttu-id="e7689-112">La copie locale du magasin central de gestion se trouve dans la base de données **RTCLOCAL** du SQL Server sur chaque ordinateur.</span><span class="sxs-lookup"><span data-stu-id="e7689-112">The local copy of the Central Management store is in the **RTCLOCAL** database in the SQL Server on each computer.</span></span> <span data-ttu-id="e7689-113">La réplication est à sens unique, initiée à partir du serveur central de gestion (ou du serveur frontal ou du pool frontal qui détient le rôle serveur de gestion centralisée) vers les serveurs Edge et est un port d’interface interne.</span><span class="sxs-lookup"><span data-stu-id="e7689-113">The replication is one-way, initiated from the Central Management Server (or, the Front End Server or Front End pool that holds the Central Management Server role) to the Edge Servers and is an internal interface port.</span></span>
    
  <span data-ttu-id="e7689-114">**Sélection du tronçon suivant**</span><span class="sxs-lookup"><span data-stu-id="e7689-114">**Next hop selection**</span></span>
  
- <span data-ttu-id="e7689-115">Sélectionnez dans la liste votre **Pool du tronçon suivant**.</span><span class="sxs-lookup"><span data-stu-id="e7689-115">Select for the list your **Next hop pool**.</span></span> <span data-ttu-id="e7689-116">Vous définissez un directeur, un pool directeur, un serveur frontal ou un pool frontal pour assumer ce rôle.</span><span class="sxs-lookup"><span data-stu-id="e7689-116">You define either a Director, Director pool, Front End Server or Front End pool to assume this role.</span></span> <span data-ttu-id="e7689-117">Le pool du saut suivant est le serveur ou le pool de serveurs qui acceptera les messages SIP entrants provenant de l’interface interne du serveur Edge ou du pool de serveurs Edge et enverra le SIP sortant à l’interface interne Edge.</span><span class="sxs-lookup"><span data-stu-id="e7689-117">The next hop pool is the server or server pool that will accept inbound SIP messages from the Edge Server or Edge pool internal interface and send outbound SIP to the Edge internal interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e7689-118">Le directeur est un rôle facultatif et si vous décidez de ne pas déployer les directeurs, les serveurs frontux (un seul ordinateur ou pool) assumeront le rôle directeur.</span><span class="sxs-lookup"><span data-stu-id="e7689-118">The Director is an optional role and if you decide not to deploy Directors, the Front End Servers (single computer or pool) will assume the Director role.</span></span> 
  
  <span data-ttu-id="e7689-119">**Paramètres externes**</span><span class="sxs-lookup"><span data-stu-id="e7689-119">**External settings**</span></span>
  
<span data-ttu-id="e7689-120">Cette section des propriétés vous permet de modifier les propriétés des paramètres externes du serveur Edge ou du pool edge.</span><span class="sxs-lookup"><span data-stu-id="e7689-120">This section of the properties allows you to edit properties for the external settings of the Edge Server or Edge pool.</span></span> <span data-ttu-id="e7689-121">Les propriétés suivantes peuvent être modifiées :</span><span class="sxs-lookup"><span data-stu-id="e7689-121">The following properties are available to edit:</span></span>
  
- <span data-ttu-id="e7689-122">Activez la case à cocher Activer un nom de domaine complet et une adresse IP distincts pour la conférence web et activez la case à cocher **A/V** si vous souhaitez affecter des adresses IP distinctes et des noms de domaine complets à chaque service de serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="e7689-122">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to assign distinct IP addresses and fully qualified domain names to each Edge Server service.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e7689-123">Si vous choisissez de ne pas activer la case à cocher, vous devez utiliser des ports distincts pour chaque service Edge.</span><span class="sxs-lookup"><span data-stu-id="e7689-123">If you choose to not select the check box, you must use separate ports for each Edge service.</span></span> <span data-ttu-id="e7689-124">Chaque service Edge partagera le nom de complet défini pour le service Edge d’accès et utilisera donc la même adresse IP.</span><span class="sxs-lookup"><span data-stu-id="e7689-124">Each Edge service will share the FQDN defined for the Access Edge service, and will therefore use the same IP address.</span></span> <span data-ttu-id="e7689-125">Chaque service Edge doit être identifié de manière unique soit par une adresse IP distincte et le même port, soit par la même adresse IP et des valeurs de port uniques.</span><span class="sxs-lookup"><span data-stu-id="e7689-125">Each Edge service must be uniquely identified by either a distinct IP address and same port, or the same IP address and unique port values.</span></span> 
  
- <span data-ttu-id="e7689-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span><span class="sxs-lookup"><span data-stu-id="e7689-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span></span>
    
- <span data-ttu-id="e7689-127">Pour modifier le **service Edge** d’accès, vous définissez le nom de groupe complet du **pool** pour le service Edge d’accès tel que défini dans DNS par les enregistrements d’hôte (A et AAAA si IPv6 est utilisé) et une valeur de port</span><span class="sxs-lookup"><span data-stu-id="e7689-127">To edit the **Access Edge service**, you define the **Pool FQDN** for the Access Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="e7689-128">Pour modifier le service Edge de conférence **Web,** vous définissez un nom de pool de **FQDN** pour le service Edge de conférence Web tel que défini dans DNS par les enregistrements d’hôte (A et AAAA si IPv6 est utilisé) et une valeur de port</span><span class="sxs-lookup"><span data-stu-id="e7689-128">To edit the **Web Conferencing Edge service**, you define a **Pool FQDN** for the Web Conferencing Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="e7689-129">Pour modifier le **service Edge A/V,** vous définissez un nom de pool pour le service Edge A/V tel que défini dans DNS par les enregistrements d’hôte (A et AAAA si IPv6 est utilisé) et une valeur de port </span><span class="sxs-lookup"><span data-stu-id="e7689-129">To edit the **A/V Edge service**, you define a **Pool FQDN** for the A/V Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e7689-130">Si vous avez activé la case à cocher Activer un FQDN et une adresse IP distincts pour la conférence web et **A/V,** seul le FQDN du pool de services Edge d’accès sera disponible pour modification.</span><span class="sxs-lookup"><span data-stu-id="e7689-130">If you have selected the **Enable separate FQDN and IP address for web conferencing and A/V** check box, only the Access Edge service Pool FQDN will be available for editing.</span></span> <span data-ttu-id="e7689-131">Assignez des ports distincts à chacun des trois services Edge.</span><span class="sxs-lookup"><span data-stu-id="e7689-131">Assign distinct ports for each of the three Edge services.</span></span>
  
  <span data-ttu-id="e7689-132">**OK** permet d’accepter et de valider les modifications de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e7689-132">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="e7689-133">**Annuler** permet d’annuler les modifications et de fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e7689-133">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="e7689-134">**Aide** permet d’afficher cet écran d’aide.</span><span class="sxs-lookup"><span data-stu-id="e7689-134">**Help** Displays this help screen.</span></span>
  

