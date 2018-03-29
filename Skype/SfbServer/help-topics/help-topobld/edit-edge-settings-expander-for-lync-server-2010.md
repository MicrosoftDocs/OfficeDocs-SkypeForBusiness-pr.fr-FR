---
title: Modifier l’agrandissement de paramètres de bord pour Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Vous modifiez les paramètres pour le serveur de transport Edge ou le pool de bord en configurant les propriétés suivantes :'
ms.openlocfilehash: 682412e1a486cc7351f081d903d8db1131367623
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a><span data-ttu-id="e490f-103">Modifier l’agrandissement de paramètres de bord pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e490f-103">Edit Edge Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="e490f-104">Vous modifiez les paramètres pour le serveur de transport Edge ou le pool de bord en configurant les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="e490f-104">You edit the settings for the Edge Server or Edge pool by configuring the following properties:</span></span> 
  
 <span data-ttu-id="e490f-105">**Général**</span><span class="sxs-lookup"><span data-stu-id="e490f-105">**General**</span></span>
  
- <span data-ttu-id="e490f-106">**Nom de domaine complet de pool interne**: le nom de domaine complet du pool interne est l’identité du serveur de transport Edge ou pool de bord tel que défini dans l’enregistrement d’hôte (A ou AAAA pour IPv6) domaine nom système (DNS).</span><span class="sxs-lookup"><span data-stu-id="e490f-106">**Internal pool FQDN**: The internal pool fully qualified domain name is the identity of the Edge Server or Edge pool as defined in the domain name system (DNS) host (A or AAAA for IPv6) record.</span></span>
    
- <span data-ttu-id="e490f-107">Sélectionnez **Activer la fédération pour ce pool de bord (le port 5061)** si vous souhaitez activer le serveur de transport Edge ou le pool de bord pour la fédération avec d’autres partenaires de protocole de lancement de session.</span><span class="sxs-lookup"><span data-stu-id="e490f-107">Select **Enable federation for this Edge pool (port 5061)** if you want to enable the Edge Server or Edge pool for federation with other session initiation protocol partners.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e490f-108">Vous ne pouvez définir qu’un serveur de transport Edge ou pool de bord activement pour la fédération.</span><span class="sxs-lookup"><span data-stu-id="e490f-108">You can only define one Edge Server or Edge pool actively for federation.</span></span> <span data-ttu-id="e490f-109">La configuration illustrée dans la capture d’écran associé indique qu’un autre pool de serveur de transport Edge ou Edge est déjà configuré pour la fédération.</span><span class="sxs-lookup"><span data-stu-id="e490f-109">The configuration shown in the associated screen shot indicates that another Edge Server or Edge pool is already configured for federation.</span></span> <span data-ttu-id="e490f-110">L’enregistrement DNS SRV externe pour la fédération (_sipfederationtls._tcp.\< nom de domaine externe\>) pointe vers le serveur de transport Edge ou le pool de bord pour la fédération.</span><span class="sxs-lookup"><span data-stu-id="e490f-110">The external DNS SRV record for federation (_sipfederationtls._tcp.\<external domain name\>) will point to the Edge Server or Edge pool for federation.</span></span> 
  
- <span data-ttu-id="e490f-111">Le **Port de réplication interne Configuration (HTTPS)**, par défaut sur le port TCP 4443, est le port qui local (c'est-à-dire local sur les serveurs Edge) copie du magasin Central de gestion est répliquée sur.</span><span class="sxs-lookup"><span data-stu-id="e490f-111">The **Internal Configuration Replication Port (HTTPS)**, by default at TCP port 4443, is the port that the local (that is, local to the Edge Servers) copy of the Central Management store is replicated over.</span></span> <span data-ttu-id="e490f-112">La copie locale du magasin Central de gestion se trouve dans la base de données **RTCLOCAL** dans le SQL Server sur chaque ordinateur.</span><span class="sxs-lookup"><span data-stu-id="e490f-112">The local copy of the Central Management store is in the **RTCLOCAL** database in the SQL Server on each computer.</span></span> <span data-ttu-id="e490f-113">La réplication est à sens unique, initiée à partir du serveur d’administration centrale (ou, le pool de Front-End ou de serveur frontal qui détient le rôle de serveur de gestion Central) vers les serveurs Edge et est un port de l’interface interne.</span><span class="sxs-lookup"><span data-stu-id="e490f-113">The replication is one-way, initiated from the Central Management Server (or, the Front End Server or Front End pool that holds the Central Management Server role) to the Edge Servers and is an internal interface port.</span></span>
    
 <span data-ttu-id="e490f-114">**Sélection de saut suivante**</span><span class="sxs-lookup"><span data-stu-id="e490f-114">**Next hop selection**</span></span>
  
- <span data-ttu-id="e490f-115">Pour la liste, sélectionnez le **pool du tronçon suivant**.</span><span class="sxs-lookup"><span data-stu-id="e490f-115">Select for the list your **Next hop pool**.</span></span> <span data-ttu-id="e490f-116">Vous définissez soit un directeur, directeur pool, pool de Front-End ou de serveur frontal pour assumer ce rôle.</span><span class="sxs-lookup"><span data-stu-id="e490f-116">You define either a Director, Director pool, Front End Server or Front End pool to assume this role.</span></span> <span data-ttu-id="e490f-117">Le pool du tronçon suivant est le serveur ou le pool de serveur qui accepte les messages entrants de SIP du serveur Edge ou interface de bord pool interne et envoi sortant SIP vers l’interface interne du bord.</span><span class="sxs-lookup"><span data-stu-id="e490f-117">The next hop pool is the server or server pool that will accept inbound SIP messages from the Edge Server or Edge pool internal interface and send outbound SIP to the Edge internal interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e490f-118">Le directeur est un rôle facultatif et si vous décidez de ne pas déployer les directeurs, les serveurs frontaux (ordinateur unique ou pool) suppose que le rôle de directeur.</span><span class="sxs-lookup"><span data-stu-id="e490f-118">The Director is an optional role and if you decide not to deploy Directors, the Front End Servers (single computer or pool) will assume the Director role.</span></span> 
  
 <span data-ttu-id="e490f-119">**Paramètres externes**</span><span class="sxs-lookup"><span data-stu-id="e490f-119">**External settings**</span></span>
  
<span data-ttu-id="e490f-120">Cette section de propriétés vous permet de modifier les propriétés des paramètres du serveur Edge ou pool de bord externes.</span><span class="sxs-lookup"><span data-stu-id="e490f-120">This section of the properties allows you to edit properties for the external settings of the Edge Server or Edge pool.</span></span> <span data-ttu-id="e490f-121">Les propriétés suivantes sont disponibles pour modifier :</span><span class="sxs-lookup"><span data-stu-id="e490f-121">The following properties are available to edit:</span></span>
  
- <span data-ttu-id="e490f-122">Sélectionnez le **Activer distinct nom de domaine complet et l’adresse IP pour les conférences web et A / V** noms de case à cocher si vous souhaitez affecter des adresses IP distinctes et domaine pleinement qualifié à chaque service de serveur de transport Edge.</span><span class="sxs-lookup"><span data-stu-id="e490f-122">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to assign distinct IP addresses and fully qualified domain names to each Edge Server service.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e490f-123">Si vous choisissez pour ne pas sélectionner la case à cocher, vous devez utiliser des ports distincts pour chaque service de bord.</span><span class="sxs-lookup"><span data-stu-id="e490f-123">If you choose to not select the check box, you must use separate ports for each Edge service.</span></span> <span data-ttu-id="e490f-124">Chaque service de bord partage le nom de domaine complet défini pour le service Edge d’accès et par conséquent utilise la même adresse IP.</span><span class="sxs-lookup"><span data-stu-id="e490f-124">Each Edge service will share the FQDN defined for the Access Edge service, and will therefore use the same IP address.</span></span> <span data-ttu-id="e490f-125">Chaque service de bord doit être identifié de manière unique en une adresse IP distincte et même port, ou la même adresse IP et les valeurs de port unique.</span><span class="sxs-lookup"><span data-stu-id="e490f-125">Each Edge service must be uniquely identified by either a distinct IP address and same port, or the same IP address and unique port values.</span></span> 
  
- <span data-ttu-id="e490f-126">Sélectionnez **A / V Edge service NAT activé** si vous souhaitez configurer l’A / V Edge service d’utiliser une adresse privée ou autres adresses qui seront masquées derrière un périphérique de traduction d’adresses réseau.</span><span class="sxs-lookup"><span data-stu-id="e490f-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span></span>
    
- <span data-ttu-id="e490f-127">Pour modifier le **service Edge d’accès**, vous définissez le **Nom FQDN du Pool** pour le service Edge d’accès tel que défini dans le système DNS par hôte (AAAA si IPv6 est utilisé et A) les enregistrements et une valeur de port</span><span class="sxs-lookup"><span data-stu-id="e490f-127">To edit the **Access Edge service**, you define the **Pool FQDN** for the Access Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="e490f-128">Pour modifier le **serveur Edge de conférence Web service**, vous définissez un **Pool de nom de domaine complet** pour le service serveur Edge de conférence Web tel que défini dans le système DNS par hôte (AAAA si IPv6 est utilisé et A) les enregistrements et une valeur de port</span><span class="sxs-lookup"><span data-stu-id="e490f-128">To edit the **Web Conferencing Edge service**, you define a **Pool FQDN** for the Web Conferencing Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="e490f-129">Pour modifier la **A / V Edge service**, vous définissez un **Nom de domaine complet Pool** pour l’un / V Edge service tel que défini dans le système DNS par hôte (AAAA si IPv6 est utilisé et A) enregistrements et une valeur de port</span><span class="sxs-lookup"><span data-stu-id="e490f-129">To edit the **A/V Edge service**, you define a **Pool FQDN** for the A/V Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e490f-130">Si vous avez sélectionné la **Activer distinct nom de domaine complet et l’adresse IP pour les conférences web et A / V** case à cocher, seul le service Edge d’accès FQDN du Pool seront disponible pour l’édition.</span><span class="sxs-lookup"><span data-stu-id="e490f-130">If you have selected the **Enable separate FQDN and IP address for web conferencing and A/V** check box, only the Access Edge service Pool FQDN will be available for editing.</span></span> <span data-ttu-id="e490f-131">Affecter des ports distincts pour chacun des trois services Edge.</span><span class="sxs-lookup"><span data-stu-id="e490f-131">Assign distinct ports for each of the three Edge services.</span></span>
  
 <span data-ttu-id="e490f-132">**OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e490f-132">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="e490f-133">**Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e490f-133">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="e490f-134">**Aide** : permet d’afficher cet écran d’aide.</span><span class="sxs-lookup"><span data-stu-id="e490f-134">**Help** Displays this help screen.</span></span>
  

