---
title: Surveillance des fichiers journaux de suivi des demandes de services Internet (IIS) dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 'Résumé : En savoir plus sur le Service de mobilité (Mcx) dans Skype pour Business Server 2015 prise en charge pour les clients hérités.'
ms.openlocfilehash: 6c885c441531dc02e149ee1fb37f0001d252811f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873463"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="b300e-103">Surveillance des fichiers journaux de suivi des demandes de services Internet (IIS) dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="b300e-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b300e-104">**Résumé :** Découvrez le Service de mobilité (Mcx) dans Skype pour Business Server 2015 prise en charge pour les clients hérités.</span><span class="sxs-lookup"><span data-stu-id="b300e-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="b300e-105">Cette rubrique concerne les déploiements prenant en charge uniquement les clients Lync Mobile de Lync 2010, et en particulier le service Mcx (Mobility Service).</span><span class="sxs-lookup"><span data-stu-id="b300e-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>

> [!NOTE]
> <span data-ttu-id="b300e-106">Prise en charge MCX (Service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b300e-106">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="b300e-107">Tous les Skype en cours pour les clients mobiles métiers utilisent déjà Unified Communications Web API (UCWA) pour prendre en charge la messagerie instantanée, présence et les contacts.</span><span class="sxs-lookup"><span data-stu-id="b300e-107">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="b300e-108">Les utilisateurs avec les clients hérités MCX doivent mettre à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="b300e-108">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="b300e-109">Lorsque vous activez le suivi des demandes Internet Information Services (IIS) pour le Skype pour le Service de mobilité Business Server (Mcx), les fichiers journaux générés peuvent consommer jusqu'à trois gigaoctets d’espace disque par jour.</span><span class="sxs-lookup"><span data-stu-id="b300e-109">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="b300e-110">La journalisation du suivi IIS est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="b300e-110">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="b300e-111">Vous devez surveiller les serveurs frontaux pour vous assurer qu’ils n’exécutent pas suffisamment d’espace disque.</span><span class="sxs-lookup"><span data-stu-id="b300e-111">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="b300e-112">Par défaut, les services Internet (IIS) stockent les fichiers journaux dans %SystemDrive%\inetpub\logs\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="b300e-112">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="b300e-113">Pour désactiver le suivi des demandes IIS pour un serveur entier, tapez ce qui suit sur la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="b300e-113">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="b300e-114">Pour plus d’informations sur la commande **httpLogging** , voir [la référence des commandes](https://go.microsoft.com/fwlink/p/?linkId=234927).</span><span class="sxs-lookup"><span data-stu-id="b300e-114">For details about the **httpLogging** command, see [the command reference](https://go.microsoft.com/fwlink/p/?linkId=234927).</span></span>
  

