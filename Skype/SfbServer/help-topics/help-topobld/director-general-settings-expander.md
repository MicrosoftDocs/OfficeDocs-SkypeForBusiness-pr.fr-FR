---
title: Expanseur des paramètres généraux du directeur
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
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
description: 'Les sections suivantes vous permettent de modifier les paramètres d’un directeur existant :'
ms.openlocfilehash: 261593cd7b1f8f79588462cb57eb8ecc517dd4a3
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218985"
---
# <a name="director-general-settings-expander"></a><span data-ttu-id="3b07a-103">Expanseur des paramètres généraux du directeur</span><span class="sxs-lookup"><span data-stu-id="3b07a-103">Director General Settings Expander</span></span>
 
<span data-ttu-id="3b07a-104">Les sections suivantes vous permettent de modifier les paramètres d’un directeur existant :</span><span class="sxs-lookup"><span data-stu-id="3b07a-104">To edit the settings for an existing Director, you are presented with the following sections:</span></span>
  
- <span data-ttu-id="3b07a-105">Paramètres généraux</span><span class="sxs-lookup"><span data-stu-id="3b07a-105">General settings</span></span>
    
- <span data-ttu-id="3b07a-106">Services Web</span><span class="sxs-lookup"><span data-stu-id="3b07a-106">Web services</span></span>
    


## <a name="general-settings"></a><span data-ttu-id="3b07a-107">Paramètres généraux</span><span class="sxs-lookup"><span data-stu-id="3b07a-107">General settings</span></span>

<span data-ttu-id="3b07a-p101">Nom de domaine complet (FQDN) du pool directeur. Modifiez le nom de domaine complet du serveur pour changer la valeur. Vous devez disposer d’un enregistrement DNS A (hôte) qui corresponde à la nouvelle valeur.</span><span class="sxs-lookup"><span data-stu-id="3b07a-p101">Fully qualified domain name (FQDN) of the Director pool. Edit the FQDN of the server to change the value. You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="3b07a-111">Dans **Associations**, vous pouvez modifier ou spécifier les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="3b07a-111">In **Associations** you can edit or specify the following:</span></span>
  
<span data-ttu-id="3b07a-112">Partage de fichiers utilisé par le pool directeur.</span><span class="sxs-lookup"><span data-stu-id="3b07a-112">File share for the Director pool to use.</span></span> <span data-ttu-id="3b07a-113">Sélectionnez un partage de fichiers existant qui a déjà été défini dans le générateur de topologie, ou cliquez sur **nouveau** pour créer une définition de partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="3b07a-113">Select an existing file share that has already been defined in Topology Builder, or click **New** to create a new file share definition.</span></span>
  
<span data-ttu-id="3b07a-114">Magasin SQL Server de surveillance</span><span class="sxs-lookup"><span data-stu-id="3b07a-114">Monitoring SQL Server store.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3b07a-p103">Avant de publier la nouvelle topologie que vous venez de définir, le serveur que vous spécifiez doit exister et être joint au domaine. Si vous avez créé un nouveau partage de fichiers, le partage de fichiers doit être créé sur le serveur que vous désignez.</span><span class="sxs-lookup"><span data-stu-id="3b07a-p103">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain. If you created a new file share, the file share must be created on the server that you designate.</span></span> 
  
## <a name="web-services"></a><span data-ttu-id="3b07a-117">Services Web</span><span class="sxs-lookup"><span data-stu-id="3b07a-117">Web services</span></span>

<span data-ttu-id="3b07a-118">Pour modifier ou spécifier des paramètres supplémentaires pour les services web sur le pool directeur, vous modifiez ou spécifiez des paramètres dans les services web internes et externes.</span><span class="sxs-lookup"><span data-stu-id="3b07a-118">To edit or specify additional settings for the Web services on the Director pool, you modify or specify settings in the Internal Web services and External Web services.</span></span>
  
<span data-ttu-id="3b07a-119">Dans le cas des **Services web internes**, vous pouvez spécifier les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="3b07a-119">For **Internal web services** you can specify the following:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="3b07a-120">Si vous avez plusieurs pools frontaux ou serveurs frontaux, le nom de domaine complet (FQDN) des services Web externes doit être unique.</span><span class="sxs-lookup"><span data-stu-id="3b07a-120">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="3b07a-121">Par exemple, si vous définissez le nom de domaine complet des services Web externes d’un serveur frontal en tant que **pool01.contoso.com**, vous ne pouvez pas utiliser **pool01.contoso.com** pour un autre pool frontal ou serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="3b07a-121">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="3b07a-122">Si vous déployez également des directeurs, le nom de domaine complet des services Web externes défini pour tout directeur ou pool directeur doit être unique à partir d’un autre directeur ou pool Directeur, ainsi que d’un pool frontal ou d’un serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="3b07a-122">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="3b07a-123">Si vous décidez de remplacer les services Web internes par un nom de domaine complet indépendant, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool directeur.</span><span class="sxs-lookup"><span data-stu-id="3b07a-123">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
<span data-ttu-id="3b07a-p105">Si vous sélectionnez Remplacer le nom de domaine complet, vous pouvez indiquer un nom de domaine complet différent pour l’identité des services web sur le pool. Par défaut, le paramètre est le nom de pool actuel comme défini pour le pool directeur.</span><span class="sxs-lookup"><span data-stu-id="3b07a-p105">If you select Override FQDN, you can specify a different FQDN for the Internal Web services identity on the pool. By default, the setting is the current pool name as defined for the Director pool.</span></span>
  
<span data-ttu-id="3b07a-p106">Vous pouvez spécifier des ports d’écoute et publiés pour HTTP et HTTPS nécessaires à votre déploiement. Le paramètre par défaut du port 80 pour HTTP et du port 443 pour HTTPS sont les paramètres les plus courants et ne doivent généralement pas être modifiés, à moins que vous n’ayez des exigences particulières au sein de votre organisation et de votre infrastructure.</span><span class="sxs-lookup"><span data-stu-id="3b07a-p106">You can specify listening and published ports for HTTP and HTTPS that your deployment requires. The default setting of port 80 for HTTP and port 443 for HTTPS are the most common settings and typically do not need to be changed unless you have specific requirements within your organization and infrastructure design.</span></span>
  
<span data-ttu-id="3b07a-128">Dans le cas des **Services web externes**, vous pouvez spécifier les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="3b07a-128">For **External web services**, you can specify the following:</span></span>
  
<span data-ttu-id="3b07a-p107">Vous pouvez définir le nom de domaine complet des services web externes. Le nom de domaine complet spécifié ici sera généralement défini par les exigences de votre connexion externe, comme le proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="3b07a-p107">You can define the FQDN of the External Web services. The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>
  
<span data-ttu-id="3b07a-p108">Vous pouvez spécifier des ports d’écoute et publiés pour HTTP et HTTPS nécessaires à votre déploiement. Les paramètres par défaut du port 8080 pour HTTP et du port 4443 pour HTTPS sont initialement définis. Vous pouvez modifier ces paramètres pour les ports d’écoute en fonction des exigences liées à votre proxy inverse et à votre réseau externe. Les ports publiés sont définis par défaut sur le port 80 pour HTTP et le port 443 pour HTTPS. Ces valeurs déterminent les ports que le pool directeur ou le serveur directeur vont écouter pour les demandes entrantes. Elles ne doivent généralement pas être modifiées, sauf en cas de conflit entre les exigences en matière de port sur le pool. Les ports publiés internes et externes doivent utiliser les mêmes valeurs de port et cela n’entraîne aucun conflit.</span><span class="sxs-lookup"><span data-stu-id="3b07a-p108">You can specify listening and published ports for HTTP and HTTPS that your deployment requires. The default settings of port 8080 for HTTP and port 4443 for HTTPS are defined initially. You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements. The published ports are set to default of port 80 for HTTP and port 443 for HTTPS. These values determine what ports the Director pool or Director server will listen for incoming requests. Typically, these do not need to be changed, unless there is conflict of port requirements on the pool. Internal and external published ports that use the same port values are expected. This is not a conflict.</span></span>
  

