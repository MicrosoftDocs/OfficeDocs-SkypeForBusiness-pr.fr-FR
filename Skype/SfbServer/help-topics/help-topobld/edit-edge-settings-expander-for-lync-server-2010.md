---
title: Modifier l’expanseur des paramètres de l’ordinateur Edge pour Lync Server 2010
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
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Pour modifier les paramètres du serveur Edge ou du pool de serveurs Edge, configurez les propriétés suivantes :'
ms.openlocfilehash: ab558edd16370d46d452f4e3d146dbf2153f3d9e
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216115"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a><span data-ttu-id="5bacb-103">Modifier l’expanseur des paramètres de l’ordinateur Edge pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="5bacb-103">Edit Edge Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="5bacb-104">Pour modifier les paramètres du serveur Edge ou du pool de serveurs Edge, configurez les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="5bacb-104">You edit the settings for the Edge Server or Edge pool by configuring the following properties:</span></span> 
  
 <span data-ttu-id="5bacb-105">**Général**</span><span class="sxs-lookup"><span data-stu-id="5bacb-105">**General**</span></span>
  
- <span data-ttu-id="5bacb-106">Nom de domaine **complet du pool interne**: le nom de domaine complet du pool interne est l’identité du serveur Edge ou du pool de serveurs Edge tel qu’il est défini dans l’enregistrement DNS (A ou AAAA pour IPv6) de l’hôte DNS.</span><span class="sxs-lookup"><span data-stu-id="5bacb-106">**Internal pool FQDN**: The internal pool fully qualified domain name is the identity of the Edge Server or Edge pool as defined in the domain name system (DNS) host (A or AAAA for IPv6) record.</span></span>
    
- <span data-ttu-id="5bacb-107">Sélectionnez **activer la Fédération pour ce pool Edge (port 5061)** si vous souhaitez activer le serveur Edge ou le pool de serveurs Edge pour la Fédération avec d’autres partenaires de protocole d’initiation de session.</span><span class="sxs-lookup"><span data-stu-id="5bacb-107">Select **Enable federation for this Edge pool (port 5061)** if you want to enable the Edge Server or Edge pool for federation with other session initiation protocol partners.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5bacb-108">Vous ne pouvez définir qu’un seul serveur Edge ou pool de serveurs Edge activement pour la Fédération.</span><span class="sxs-lookup"><span data-stu-id="5bacb-108">You can only define one Edge Server or Edge pool actively for federation.</span></span> <span data-ttu-id="5bacb-109">La configuration illustrée dans la capture d’écran associée indique qu’un autre serveur Edge ou pool de serveurs Edge est déjà configuré pour la Fédération.</span><span class="sxs-lookup"><span data-stu-id="5bacb-109">The configuration shown in the associated screen shot indicates that another Edge Server or Edge pool is already configured for federation.</span></span> <span data-ttu-id="5bacb-110">L’enregistrement SRV DNS externe pour la Fédération (_sipfederationtls. _tcp. \<external domain name\> ) pointe vers le serveur Edge ou le pool de serveurs Edge pour la Fédération.</span><span class="sxs-lookup"><span data-stu-id="5bacb-110">The external DNS SRV record for federation (_sipfederationtls._tcp.\<external domain name\>) will point to the Edge Server or Edge pool for federation.</span></span> 
  
- <span data-ttu-id="5bacb-111">Le **port de réplication de configuration interne (https)**, par défaut sur le port TCP 4443, est le port que la copie locale (c’est-à-dire, locale vers les serveurs Edge) du magasin central de gestion est répliquée sur.</span><span class="sxs-lookup"><span data-stu-id="5bacb-111">The **Internal Configuration Replication Port (HTTPS)**, by default at TCP port 4443, is the port that the local (that is, local to the Edge Servers) copy of the Central Management store is replicated over.</span></span> <span data-ttu-id="5bacb-112">La copie locale du magasin central de gestion se trouve dans la base de données **RTCLOCAL** du serveur SQL Server sur chaque ordinateur.</span><span class="sxs-lookup"><span data-stu-id="5bacb-112">The local copy of the Central Management store is in the **RTCLOCAL** database in the SQL Server on each computer.</span></span> <span data-ttu-id="5bacb-113">La réplication est unidirectionnelle, initiée à partir du serveur de gestion centralisée (ou, le serveur frontal ou le pool frontal qui détient le rôle de serveur de gestion centralisée) vers les serveurs Edge et est un port d’interface interne.</span><span class="sxs-lookup"><span data-stu-id="5bacb-113">The replication is one-way, initiated from the Central Management Server (or, the Front End Server or Front End pool that holds the Central Management Server role) to the Edge Servers and is an internal interface port.</span></span>
    
  <span data-ttu-id="5bacb-114">**Sélection du tronçon suivant**</span><span class="sxs-lookup"><span data-stu-id="5bacb-114">**Next hop selection**</span></span>
  
- <span data-ttu-id="5bacb-115">Sélectionnez dans la liste votre **Pool du tronçon suivant**.</span><span class="sxs-lookup"><span data-stu-id="5bacb-115">Select for the list your **Next hop pool**.</span></span> <span data-ttu-id="5bacb-116">Vous définissez un directeur, un pool Directeur, un serveur frontal ou un pool frontal pour assumer ce rôle.</span><span class="sxs-lookup"><span data-stu-id="5bacb-116">You define either a Director, Director pool, Front End Server or Front End pool to assume this role.</span></span> <span data-ttu-id="5bacb-117">Le pool de tronçon suivant est le serveur ou le pool de serveurs qui accepte les messages SIP entrants à partir de l’interface interne du serveur Edge ou du pool de serveur Edge et envoie le SIP sortant à l’interface interne du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="5bacb-117">The next hop pool is the server or server pool that will accept inbound SIP messages from the Edge Server or Edge pool internal interface and send outbound SIP to the Edge internal interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5bacb-118">Le directeur est un rôle facultatif et si vous décidez de ne pas déployer les directeurs, les serveurs frontaux (ordinateur ou pool unique) assumeront le rôle de directeur.</span><span class="sxs-lookup"><span data-stu-id="5bacb-118">The Director is an optional role and if you decide not to deploy Directors, the Front End Servers (single computer or pool) will assume the Director role.</span></span> 
  
  <span data-ttu-id="5bacb-119">**Paramètres externes**</span><span class="sxs-lookup"><span data-stu-id="5bacb-119">**External settings**</span></span>
  
<span data-ttu-id="5bacb-120">Cette section des propriétés vous permet de modifier les propriétés des paramètres externes du serveur Edge ou du pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="5bacb-120">This section of the properties allows you to edit properties for the external settings of the Edge Server or Edge pool.</span></span> <span data-ttu-id="5bacb-121">Les propriétés suivantes peuvent être modifiées :</span><span class="sxs-lookup"><span data-stu-id="5bacb-121">The following properties are available to edit:</span></span>
  
- <span data-ttu-id="5bacb-122">Activez la case à cocher **activer un nom de domaine complet et une adresse IP distincts pour la conférence Web et A/V** si vous voulez affecter des adresses IP et des noms de domaine complets distincts à chaque service serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="5bacb-122">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to assign distinct IP addresses and fully qualified domain names to each Edge Server service.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5bacb-123">Si vous choisissez de ne pas activer la case à cocher, vous devez utiliser des ports distincts pour chaque service Edge.</span><span class="sxs-lookup"><span data-stu-id="5bacb-123">If you choose to not select the check box, you must use separate ports for each Edge service.</span></span> <span data-ttu-id="5bacb-124">Chaque service Edge partagera le nom de domaine complet défini pour le service Edge d’accès et utilisera donc la même adresse IP.</span><span class="sxs-lookup"><span data-stu-id="5bacb-124">Each Edge service will share the FQDN defined for the Access Edge service, and will therefore use the same IP address.</span></span> <span data-ttu-id="5bacb-125">Chaque service Edge doit être identifié de manière unique soit par une adresse IP distincte et le même port, soit par la même adresse IP et des valeurs de port uniques.</span><span class="sxs-lookup"><span data-stu-id="5bacb-125">Each Edge service must be uniquely identified by either a distinct IP address and same port, or the same IP address and unique port values.</span></span> 
  
- <span data-ttu-id="5bacb-126">Sélectionnez **NAT est activé pour le service Edge a/v** si vous voulez configurer le service Edge a/v pour qu’il utilise une adresse privée ou une autre adresse qui sera masquée derrière un périphérique de traduction d’adresses réseau (NAT).</span><span class="sxs-lookup"><span data-stu-id="5bacb-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span></span>
    
- <span data-ttu-id="5bacb-127">Pour modifier le **service Edge d’accès**, vous définissez le **nom de domaine complet du pool** pour le service Edge d’accès comme défini dans DNS par les enregistrements d’hôte (a et aaaa si IPv6 est utilisé) et une valeur de port</span><span class="sxs-lookup"><span data-stu-id="5bacb-127">To edit the **Access Edge service**, you define the **Pool FQDN** for the Access Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="5bacb-128">Pour modifier le **service Edge de conférence Web**, vous définissez un **nom de domaine complet du pool** pour le service Edge de conférence Web comme défini dans DNS par les enregistrements d’hôte (a et aaaa si IPv6 est utilisé) et une valeur de port</span><span class="sxs-lookup"><span data-stu-id="5bacb-128">To edit the **Web Conferencing Edge service**, you define a **Pool FQDN** for the Web Conferencing Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="5bacb-129">Pour modifier le **service Edge a/v**, vous définissez un **nom de domaine complet du pool** pour le service Edge a/v comme défini dans DNS par les enregistrements d’hôte (a et aaaa si IPv6 est utilisé) et une valeur de port</span><span class="sxs-lookup"><span data-stu-id="5bacb-129">To edit the **A/V Edge service**, you define a **Pool FQDN** for the A/V Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5bacb-130">Si vous avez activé la case à cocher **activer un nom de domaine complet et une adresse IP distincts pour les conférences Web et A/V** , seul le nom de domaine complet du pool de service Edge d’accès sera disponible pour modification.</span><span class="sxs-lookup"><span data-stu-id="5bacb-130">If you have selected the **Enable separate FQDN and IP address for web conferencing and A/V** check box, only the Access Edge service Pool FQDN will be available for editing.</span></span> <span data-ttu-id="5bacb-131">Assignez des ports distincts à chacun des trois services Edge.</span><span class="sxs-lookup"><span data-stu-id="5bacb-131">Assign distinct ports for each of the three Edge services.</span></span>
  
  <span data-ttu-id="5bacb-132">**OK** permet d’accepter et de valider les modifications de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="5bacb-132">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="5bacb-133">**Annuler** permet d’annuler les modifications et de fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="5bacb-133">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="5bacb-134">**Aide** permet d’afficher cet écran d’aide.</span><span class="sxs-lookup"><span data-stu-id="5bacb-134">**Help** Displays this help screen.</span></span>
  

