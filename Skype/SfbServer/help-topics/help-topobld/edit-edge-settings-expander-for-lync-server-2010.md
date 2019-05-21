---
title: Modifier le développeur des paramètres de l’ordinateur Edge pour Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Vous pouvez modifier les paramètres du serveur de périphérie ou du pool de bords en configurant les propriétés suivantes:'
ms.openlocfilehash: 1b349d5640ea2debb4730ce262795616258b3475
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282523"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a><span data-ttu-id="50d67-103">Modifier le développeur des paramètres de l’ordinateur Edge pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="50d67-103">Edit Edge Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="50d67-104">Vous pouvez modifier les paramètres du serveur de périphérie ou du pool de bords en configurant les propriétés suivantes:</span><span class="sxs-lookup"><span data-stu-id="50d67-104">You edit the settings for the Edge Server or Edge pool by configuring the following properties:</span></span> 
  
 <span data-ttu-id="50d67-105">**Général**</span><span class="sxs-lookup"><span data-stu-id="50d67-105">**General**</span></span>
  
- <span data-ttu-id="50d67-106">Nom de domaine **complet (FQDN**) du pool interne: il s’agit de l’identité du serveur Edge ou du pool Edge, tel que défini dans l’enregistrement DNS (Domain Name System) (A ou AAAA pour IPv6).</span><span class="sxs-lookup"><span data-stu-id="50d67-106">**Internal pool FQDN**: The internal pool fully qualified domain name is the identity of the Edge Server or Edge pool as defined in the domain name system (DNS) host (A or AAAA for IPv6) record.</span></span>
    
- <span data-ttu-id="50d67-107">Sélectionnez **activer la Fédération pour ce pool Edge (port 5061)** si vous voulez activer le serveur Edge ou le pool de périphérie pour la Fédération avec d’autres partenaires de protocole d’initiation de session.</span><span class="sxs-lookup"><span data-stu-id="50d67-107">Select **Enable federation for this Edge pool (port 5061)** if you want to enable the Edge Server or Edge pool for federation with other session initiation protocol partners.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="50d67-108">Vous pouvez uniquement définir un serveur Edge ou un pool Edge pour la Fédération.</span><span class="sxs-lookup"><span data-stu-id="50d67-108">You can only define one Edge Server or Edge pool actively for federation.</span></span> <span data-ttu-id="50d67-109">La configuration affichée dans la capture d’écran associée indique qu’un autre serveur Edge ou pool d’arêtes est déjà configuré pour la Fédération.</span><span class="sxs-lookup"><span data-stu-id="50d67-109">The configuration shown in the associated screen shot indicates that another Edge Server or Edge pool is already configured for federation.</span></span> <span data-ttu-id="50d67-110">L’enregistrement SRV DNS pour la Fédération (_sipfederationtls. _ TCP\< . nom\>de domaine externe) pointe vers le serveur de périphérie ou le pool de bords pour la Fédération.</span><span class="sxs-lookup"><span data-stu-id="50d67-110">The external DNS SRV record for federation (_sipfederationtls._tcp.\<external domain name\>) will point to the Edge Server or Edge pool for federation.</span></span> 
  
- <span data-ttu-id="50d67-111">Le **port de réplication de configuration interne (https)**, par défaut sur le port TCP 4443, est le port que la copie locale (qui est locale vers la serveur Edge) du magasin de gestion central est répliquée.</span><span class="sxs-lookup"><span data-stu-id="50d67-111">The **Internal Configuration Replication Port (HTTPS)**, by default at TCP port 4443, is the port that the local (that is, local to the Edge Servers) copy of the Central Management store is replicated over.</span></span> <span data-ttu-id="50d67-112">La copie locale du magasin de gestion central figure dans la base de données **RTCLOCAL** du serveur SQL sur chaque ordinateur.</span><span class="sxs-lookup"><span data-stu-id="50d67-112">The local copy of the Central Management store is in the **RTCLOCAL** database in the SQL Server on each computer.</span></span> <span data-ttu-id="50d67-113">La réplication est unidirectionnelle, lancée à partir du serveur de gestion central (ou, du serveur frontal ou du pool frontal qui conserve le rôle serveur central de gestion) sur les serveurs de périphérie et est un port d’interface interne.</span><span class="sxs-lookup"><span data-stu-id="50d67-113">The replication is one-way, initiated from the Central Management Server (or, the Front End Server or Front End pool that holds the Central Management Server role) to the Edge Servers and is an internal interface port.</span></span>
    
  <span data-ttu-id="50d67-114">**Sélection du saut suivant**</span><span class="sxs-lookup"><span data-stu-id="50d67-114">**Next hop selection**</span></span>
  
- <span data-ttu-id="50d67-115">Sélectionnez pour la liste votre **pool de sauts suivant**.</span><span class="sxs-lookup"><span data-stu-id="50d67-115">Select for the list your **Next hop pool**.</span></span> <span data-ttu-id="50d67-116">Vous définissez un réalisateur, un pool de réalisateurs, un serveur frontal ou un pool frontal pour assumer ce rôle.</span><span class="sxs-lookup"><span data-stu-id="50d67-116">You define either a Director, Director pool, Front End Server or Front End pool to assume this role.</span></span> <span data-ttu-id="50d67-117">Le pool de prochains tronçons est le serveur ou le pool de serveurs qui acceptera les messages SIP entrants à partir de l’interface interne du serveur Edge ou du pool de périphériques et envoyer le SIP sortant vers l’interface interne latérale.</span><span class="sxs-lookup"><span data-stu-id="50d67-117">The next hop pool is the server or server pool that will accept inbound SIP messages from the Edge Server or Edge pool internal interface and send outbound SIP to the Edge internal interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="50d67-118">Le directeur est un rôle facultatif et, si vous décidez de ne pas déployer les directeurs, les serveurs frontaux (ordinateur ou pool unique) assument le rôle de directeur.</span><span class="sxs-lookup"><span data-stu-id="50d67-118">The Director is an optional role and if you decide not to deploy Directors, the Front End Servers (single computer or pool) will assume the Director role.</span></span> 
  
  <span data-ttu-id="50d67-119">**Paramètres externes**</span><span class="sxs-lookup"><span data-stu-id="50d67-119">**External settings**</span></span>
  
<span data-ttu-id="50d67-120">Cette section des propriétés vous permet d’apporter des modifications aux propriétés des paramètres externes du serveur Edge ou du pool Edge.</span><span class="sxs-lookup"><span data-stu-id="50d67-120">This section of the properties allows you to edit properties for the external settings of the Edge Server or Edge pool.</span></span> <span data-ttu-id="50d67-121">Vous pouvez modifier les propriétés suivantes:</span><span class="sxs-lookup"><span data-stu-id="50d67-121">The following properties are available to edit:</span></span>
  
- <span data-ttu-id="50d67-122">Activez les cases à cocher Activer les noms **de domaine complet et adresse IP pour les conférences Web et A/V** , si vous voulez attribuer des adresses IP distinctes et des noms de domaine complets à chaque service de serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="50d67-122">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to assign distinct IP addresses and fully qualified domain names to each Edge Server service.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="50d67-123">Si vous choisissez de ne pas activer la case à cocher, vous devez utiliser des ports séparés pour chaque service Edge.</span><span class="sxs-lookup"><span data-stu-id="50d67-123">If you choose to not select the check box, you must use separate ports for each Edge service.</span></span> <span data-ttu-id="50d67-124">Chaque service Edge partage le nom de domaine complet défini pour le service Edge d’accès et utilise par conséquent la même adresse IP.</span><span class="sxs-lookup"><span data-stu-id="50d67-124">Each Edge service will share the FQDN defined for the Access Edge service, and will therefore use the same IP address.</span></span> <span data-ttu-id="50d67-125">Chaque service Edge doit être identifié de façon unique par une adresse IP distincte et le même port, ou par la même adresse IP et les mêmes valeurs de port uniques.</span><span class="sxs-lookup"><span data-stu-id="50d67-125">Each Edge service must be uniquely identified by either a distinct IP address and same port, or the same IP address and unique port values.</span></span> 
  
- <span data-ttu-id="50d67-126">Le **fait de sélectionner service Edge a/v est activé** si vous souhaitez configurer le service Edge a/v pour qu’il utilise une adresse privée ou une autre adresse qui sera masquée sur un appareil de traduction d’adresses réseau (NAT).</span><span class="sxs-lookup"><span data-stu-id="50d67-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span></span>
    
- <span data-ttu-id="50d67-127">Pour modifier le **service Edge d’accès**, vous devez définir le **nom de domaine complet du pool** pour le service Edge d’accès tel que défini dans les enregistrements DNS par hôte (A et aaaa si le protocole IPv6 est utilisé) et une valeur de port.</span><span class="sxs-lookup"><span data-stu-id="50d67-127">To edit the **Access Edge service**, you define the **Pool FQDN** for the Access Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="50d67-128">Pour modifier le **service Edge de conférence Web**, vous devez définir un **nom de domaine complet (FQDN** ) de pool pour le service Edge de conférence Web tel que défini dans les enregistrements DNS par hôte (A et aaaa si le protocole IPv6 est utilisé) et une valeur de port</span><span class="sxs-lookup"><span data-stu-id="50d67-128">To edit the **Web Conferencing Edge service**, you define a **Pool FQDN** for the Web Conferencing Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="50d67-129">Pour modifier le **service Edge a/v**, vous devez définir un **nom de domaine complet (FQDN** ) de pool pour le service Edge a/v, tel que défini dans les enregistrements DNS par hôte (A et aaaa si le protocole IPv6 est utilisé) et une valeur de port</span><span class="sxs-lookup"><span data-stu-id="50d67-129">To edit the **A/V Edge service**, you define a **Pool FQDN** for the A/V Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="50d67-130">Si vous avez activé la case à cocher **activer le nom de domaine complet (FQDN) et l’adresse IP pour les conférences Web et A/V**</span><span class="sxs-lookup"><span data-stu-id="50d67-130">If you have selected the **Enable separate FQDN and IP address for web conferencing and A/V** check box, only the Access Edge service Pool FQDN will be available for editing.</span></span> <span data-ttu-id="50d67-131">Attribuez des ports distincts à chacun des trois services Edge.</span><span class="sxs-lookup"><span data-stu-id="50d67-131">Assign distinct ports for each of the three Edge services.</span></span>
  
  <span data-ttu-id="50d67-132">**OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="50d67-132">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="50d67-133">**Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="50d67-133">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="50d67-134">**Aide** : permet d’afficher cet écran d’aide.</span><span class="sxs-lookup"><span data-stu-id="50d67-134">**Help** Displays this help screen.</span></span>
  

