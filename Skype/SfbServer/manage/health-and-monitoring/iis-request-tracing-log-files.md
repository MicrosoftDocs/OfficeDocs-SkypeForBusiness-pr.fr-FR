---
title: Surveillance des fichiers journaux de suivi des demandes de services Internet (IIS) dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 'Résumé : en savoir plus sur le service de mobilité (MCX) dans Skype entreprise Server 2015 support pour les clients hérités.'
ms.openlocfilehash: f519a04f878caf953c54873a6a704232245b344b
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992179"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="adfc4-103">Surveillance des fichiers journaux de suivi des demandes de services Internet (IIS) dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="adfc4-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="adfc4-104">**Résumé :** En savoir plus sur le service de mobilité (MCX) dans Skype entreprise Server 2015 support pour les clients hérités.</span><span class="sxs-lookup"><span data-stu-id="adfc4-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="adfc4-105">Cette rubrique concerne les déploiements prenant en charge uniquement les clients Lync Mobile de Lync 2010, et en particulier le service Mcx (Mobility Service).</span><span class="sxs-lookup"><span data-stu-id="adfc4-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>

> [!NOTE]
> <span data-ttu-id="adfc4-106">La prise en charge de MCX (service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="adfc4-106">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="adfc4-107">Tous les clients mobiles Skype entreprise actuels utilisent déjà UCWA (Unified Communications Web API) pour la prise en charge de la messagerie instantanée, de la présence et des contacts.</span><span class="sxs-lookup"><span data-stu-id="adfc4-107">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="adfc4-108">Les utilisateurs des clients hérités utilisant MCX doivent effectuer une mise à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="adfc4-108">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="adfc4-109">Lorsque vous activez le suivi des demandes d’accès à Internet Information Services (IIS) pour le service de mobilité Skype entreprise Server (MCX), les fichiers journaux générés peuvent utiliser jusqu’à 3 Go d’espace disque par jour.</span><span class="sxs-lookup"><span data-stu-id="adfc4-109">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="adfc4-110">La journalisation du suivi IIS est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="adfc4-110">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="adfc4-111">Vous devez surveiller les serveurs front-end pour vous assurer qu’ils ne sont pas à court d’espace disque.</span><span class="sxs-lookup"><span data-stu-id="adfc4-111">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="adfc4-112">Par défaut, les services Internet (IIS) stockent les fichiers journaux dans %SystemDrive%\inetpub\logs\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="adfc4-112">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="adfc4-113">Pour désactiver le suivi des demandes IIS pour un serveur entier, tapez ce qui suit sur la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="adfc4-113">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="adfc4-114">Pour plus d’informations sur la commande **httpLogging** , consultez [la référence des commandes](https://go.microsoft.com/fwlink/p/?linkId=234927).</span><span class="sxs-lookup"><span data-stu-id="adfc4-114">For details about the **httpLogging** command, see [the command reference](https://go.microsoft.com/fwlink/p/?linkId=234927).</span></span>
  

