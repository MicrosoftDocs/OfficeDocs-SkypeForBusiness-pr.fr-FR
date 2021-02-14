---
title: Surveillance des fichiers journaux de suivi des demandes IIS dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 'Résumé : Découvrez la prise en charge du service de mobilité (Mcx) dans Skype Entreprise Server 2015 pour les clients hérités.'
ms.openlocfilehash: 5fb9e66efa468e8755fe369c3ce4f2a4b8979e57
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823504"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="65c0d-103">Surveillance des fichiers journaux de suivi des demandes IIS dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="65c0d-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="65c0d-104">**Résumé :** Découvrez la prise en charge de Mobility Service (Mcx) dans Skype Entreprise Server 2015 pour les clients hérités.</span><span class="sxs-lookup"><span data-stu-id="65c0d-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="65c0d-105">Cette rubrique s’applique uniquement aux déploiements qui ne sont pas destinés aux clients Lync Mobile Lync 2010 et est destinée au service de mobilité (Mcx).</span><span class="sxs-lookup"><span data-stu-id="65c0d-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>

> [!NOTE]
> <span data-ttu-id="65c0d-106">La prise en charge de MCX (Mobility Service) pour les clients mobiles hérités n’est plus disponible dans Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="65c0d-106">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="65c0d-107">Tous les clients mobiles Skype Entreprise actuels utilisent déjà l’API web de communications unifiées (UCWA) pour prendre en charge la messagerie instantanée, la présence et les contacts.</span><span class="sxs-lookup"><span data-stu-id="65c0d-107">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="65c0d-108">Les utilisateurs ayant des clients hérités utilisant MCX devront mettre à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="65c0d-108">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="65c0d-109">Lorsque vous activez le suivi des demandes IIS (Internet Information Services) pour le service de mobilité De Skype Entreprise Server (Mcx), les fichiers journaux générés peuvent consommer jusqu’à trois gigaoctets d’espace disque par jour.</span><span class="sxs-lookup"><span data-stu-id="65c0d-109">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="65c0d-110">La journalisation du suivi IIS est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="65c0d-110">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="65c0d-111">Vous devez surveiller les serveurs frontux pour vous assurer qu’ils ne manquent pas d’espace disque.</span><span class="sxs-lookup"><span data-stu-id="65c0d-111">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="65c0d-112">Par défaut, les services Internet (IIS) stockent les fichiers journaux dans %SystemDrive%\inetpub\logs\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="65c0d-112">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="65c0d-113">Pour désactiver le suivi des demandes IIS pour un serveur entier, tapez ce qui suit sur la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="65c0d-113">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="65c0d-114">Pour plus d’informations sur la **commande httpLogging,** voir [la référence de commande.](https://go.microsoft.com/fwlink/p/?linkId=234927)</span><span class="sxs-lookup"><span data-stu-id="65c0d-114">For details about the **httpLogging** command, see [the command reference](https://go.microsoft.com/fwlink/p/?linkId=234927).</span></span>
  

