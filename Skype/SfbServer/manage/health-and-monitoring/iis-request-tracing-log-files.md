---
title: Surveillance des fichiers journaux de suivi des demandes de services Internet (IIS) dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 'Résumé : En savoir plus sur le Service de mobilité (Mcx) dans Skype pour Business Server 2015 prise en charge pour les clients hérités.'
ms.openlocfilehash: 5ed817290bdf86d11dd4a2cf0e95c83fb4c31d9a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20983825"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="eb847-103">Surveillance des fichiers journaux de suivi des demandes de services Internet (IIS) dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="eb847-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="eb847-104">**Résumé :** Découvrez le Service de mobilité (Mcx) dans Skype pour Business Server 2015 prise en charge pour les clients hérités.</span><span class="sxs-lookup"><span data-stu-id="eb847-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="eb847-105">Cette rubrique concerne les déploiements prenant en charge uniquement les clients Lync Mobile de Lync 2010, et en particulier le service Mcx (Mobility Service).</span><span class="sxs-lookup"><span data-stu-id="eb847-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>

> [!NOTE]
> <span data-ttu-id="eb847-106">Prise en charge MCX pour les clients mobiles hérités n’est plus disponible dans Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="eb847-106">MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="eb847-107">Vos utilisateurs devez mettre à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="eb847-107">Your users will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="eb847-108">Lorsque vous activez le suivi des demandes Internet Information Services (IIS) pour le Skype pour le Service de mobilité Business Server (Mcx), les fichiers journaux générés peuvent consommer jusqu'à trois gigaoctets d’espace disque par jour.</span><span class="sxs-lookup"><span data-stu-id="eb847-108">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="eb847-109">La journalisation du suivi IIS est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="eb847-109">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="eb847-110">Vous devez surveiller les serveurs frontaux pour vous assurer qu’ils n’exécutent pas suffisamment d’espace disque.</span><span class="sxs-lookup"><span data-stu-id="eb847-110">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="eb847-111">Par défaut, les services Internet (IIS) stockent les fichiers journaux dans %SystemDrive%\inetpub\logs\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="eb847-111">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="eb847-112">Pour désactiver le suivi des demandes IIS pour un serveur entier, tapez ce qui suit sur la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="eb847-112">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="eb847-113">Pour plus d’informations sur la commande **httpLogging** , voir [la référence des commandes](https://go.microsoft.com/fwlink/p/?linkId=234927).</span><span class="sxs-lookup"><span data-stu-id="eb847-113">For details about the **httpLogging** command, see [the command reference](https://go.microsoft.com/fwlink/p/?linkId=234927).</span></span>
  

