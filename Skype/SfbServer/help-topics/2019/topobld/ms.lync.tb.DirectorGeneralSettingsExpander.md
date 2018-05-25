---
title: Expanseur des paramètres généraux du directeur
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
description: 'Pour modifier les paramètres d’un directeur existant, vous permettent des sections suivantes :'
ms.openlocfilehash: e806f917dbcfe3e626410d3bb76caad3c40ed5d3
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2018
---
# <a name="director-general-settings-expander"></a><span data-ttu-id="04935-103">Expanseur des paramètres généraux du directeur</span><span class="sxs-lookup"><span data-stu-id="04935-103">Director General Settings Expander</span></span>
 
<span data-ttu-id="04935-104">Pour modifier les paramètres d’un directeur existant, vous permettent des sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="04935-104">To edit the settings for an existing Director, you are presented with the following sections:</span></span>
  
- <span data-ttu-id="04935-105">Paramètres généraux</span><span class="sxs-lookup"><span data-stu-id="04935-105">General settings</span></span>
    
- <span data-ttu-id="04935-106">Services web</span><span class="sxs-lookup"><span data-stu-id="04935-106">Web services</span></span>
    
## 

### <a name="general-settings"></a><span data-ttu-id="04935-107">Paramètres généraux</span><span class="sxs-lookup"><span data-stu-id="04935-107">General settings</span></span>

<span data-ttu-id="04935-108">Nom de domaine complet (FQDN) du pool directeur.</span><span class="sxs-lookup"><span data-stu-id="04935-108">Fully qualified domain name (FQDN) of the Director pool.</span></span> <span data-ttu-id="04935-109">Modifiez le nom de domaine complet du serveur pour changer la valeur.</span><span class="sxs-lookup"><span data-stu-id="04935-109">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="04935-110">Vous devez disposer d’un enregistrement d’hôte DNS (A) correspondant à la nouvelle valeur.</span><span class="sxs-lookup"><span data-stu-id="04935-110">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="04935-111">Dans **Associations**, vous pouvez modifier ou spécifier les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="04935-111">In **Associations** you can edit or specify the following:</span></span>
  
<span data-ttu-id="04935-112">Partage de fichiers pour le pool directeur à utiliser.</span><span class="sxs-lookup"><span data-stu-id="04935-112">File share for the Director pool to use.</span></span> <span data-ttu-id="04935-113">Sélectionnez un partage de fichiers existant qui a déjà été défini dans le Générateur de topologie, ou cliquez sur **Nouveau** pour créer une nouvelle définition de partage de fichier.</span><span class="sxs-lookup"><span data-stu-id="04935-113">Select an existing file share that has already been defined in Topology Builder, or click **New** to create a new file share definition.</span></span>
  
<span data-ttu-id="04935-114">Surveillance du magasin SQL Server.</span><span class="sxs-lookup"><span data-stu-id="04935-114">Monitoring SQL Server store.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="04935-115">Avant de publier la nouvelle topologie que vous venez de définir, le serveur que vous spécifiez doit exister et être joint au domaine.</span><span class="sxs-lookup"><span data-stu-id="04935-115">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span> <span data-ttu-id="04935-116">Si vous avez créé un nouveau partage de fichiers, le partage de fichiers doit être créé sur le serveur que vous désignez.</span><span class="sxs-lookup"><span data-stu-id="04935-116">If you created a new file share, the file share must be created on the server that you designate.</span></span> 
  
### <a name="web-services"></a><span data-ttu-id="04935-117">Services web</span><span class="sxs-lookup"><span data-stu-id="04935-117">Web services</span></span>

<span data-ttu-id="04935-118">Pour modifier ou spécifier des paramètres supplémentaires pour les services Web sur le pool directeur, vous modifiez ou spécifiez des paramètres dans les services Web internes et les services Web externes.</span><span class="sxs-lookup"><span data-stu-id="04935-118">To edit or specify additional settings for the Web services on the Director pool, you modify or specify settings in the Internal Web services and External Web services.</span></span>
  
<span data-ttu-id="04935-119">**Interne des services web** vous pouvez spécifier les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="04935-119">For **Internal web services** you can specify the following:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="04935-120">Si vous avez plus d’un pool frontal ou serveur frontal des services Web externes nom de domaine complet doit être unique.</span><span class="sxs-lookup"><span data-stu-id="04935-120">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="04935-121">Par exemple, si vous définissez les nom de domaine complet d’un serveur frontal des services Web externes comme **pool01.contoso.com**, vous ne pouvez pas utiliser **pool01.contoso.com** pour un autre pool frontal ou serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="04935-121">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="04935-122">Si vous déployez également les directeurs, nom de domaine complet défini pour n’importe quel directeur des services Web externe ou pool directeur doit être unique à partir de n’importe quelle autre directeur ou directeur du pool ainsi qu’un pool frontal ou un serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="04935-122">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="04935-123">Si vous décidez de remplacer les services web internes avec un nom de domaine complet automatiquement défini, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou un pool directeur.</span><span class="sxs-lookup"><span data-stu-id="04935-123">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
<span data-ttu-id="04935-124">Si vous sélectionnez Remplacer nom de domaine complet, vous pouvez spécifier un autre nom de domaine complet pour l’identité des services Web internes sur le pool.</span><span class="sxs-lookup"><span data-stu-id="04935-124">If you select Override FQDN, you can specify a different FQDN for the Internal Web services identity on the pool.</span></span> <span data-ttu-id="04935-125">Par défaut, le paramètre est le nom du pool actuel défini pour le pool directeur.</span><span class="sxs-lookup"><span data-stu-id="04935-125">By default, the setting is the current pool name as defined for the Director pool.</span></span>
  
<span data-ttu-id="04935-126">Vous pouvez spécifier les ports d’écoute et publiés pour HTTP et HTTPS exigés par votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="04935-126">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="04935-127">Le paramètre par défaut du port 80 pour HTTP et le port 443 pour le protocole HTTPS sont les paramètres les plus courants et généralement n’avez pas besoin d’être modifié, sauf si vous avez des exigences spécifiques au sein de votre organisation et la conception de l’infrastructure.</span><span class="sxs-lookup"><span data-stu-id="04935-127">The default setting of port 80 for HTTP and port 443 for HTTPS are the most common settings and typically do not need to be changed unless you have specific requirements within your organization and infrastructure design.</span></span>
  
<span data-ttu-id="04935-128">Pour les **services web externes**, vous pouvez spécifier les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="04935-128">For **External web services**, you can specify the following:</span></span>
  
<span data-ttu-id="04935-129">Vous pouvez définir le nom de domaine complet des services Web externes.</span><span class="sxs-lookup"><span data-stu-id="04935-129">You can define the FQDN of the External Web services.</span></span> <span data-ttu-id="04935-130">Le nom de domaine complet spécifié ici sera généralement défini par les exigences de votre connexion externe, comme le proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="04935-130">The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>
  
<span data-ttu-id="04935-131">Vous pouvez spécifier les ports d’écoute et publiés pour HTTP et HTTPS exigés par votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="04935-131">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="04935-132">Les paramètres par défaut, le port 8080 pour le protocole HTTP et le port 4443 pour le protocole HTTPS, sont définis initialement.</span><span class="sxs-lookup"><span data-stu-id="04935-132">The default settings of port 8080 for HTTP and port 4443 for HTTPS are defined initially.</span></span> <span data-ttu-id="04935-133">Vous pouvez modifier ces paramètres pour les ports d’écoute en fonction des exigences de votre proxy inverse et de votre réseau externe.</span><span class="sxs-lookup"><span data-stu-id="04935-133">You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements.</span></span> <span data-ttu-id="04935-134">Les ports publiés sont définis par défaut sur le port 80 pour le protocole HTTP et sur le port 443 pour le protocole HTTPS.</span><span class="sxs-lookup"><span data-stu-id="04935-134">The published ports are set to default of port 80 for HTTP and port 443 for HTTPS.</span></span> <span data-ttu-id="04935-135">Ces valeurs déterminent quels ports d’écoute pour les demandes entrantes du pool directeur ou serveur directeur.</span><span class="sxs-lookup"><span data-stu-id="04935-135">These values determine what ports the Director pool or Director server will listen for incoming requests.</span></span> <span data-ttu-id="04935-136">En règle générale, il est inutile à modifier, sauf s’il existe des conflits de ports requis sur le pool.</span><span class="sxs-lookup"><span data-stu-id="04935-136">Typically, these do not need to be changed, unless there is conflict of port requirements on the pool.</span></span> <span data-ttu-id="04935-137">Ports publiés internes et externes qui utilisent les mêmes valeurs de port sont prévus.</span><span class="sxs-lookup"><span data-stu-id="04935-137">Internal and external published ports that use the same port values are expected.</span></span> <span data-ttu-id="04935-138">Cela n’entraîne aucun conflit.</span><span class="sxs-lookup"><span data-stu-id="04935-138">This is not a conflict.</span></span>
  

