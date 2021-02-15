---
title: Configurer un service informations d’emplacement secondaire dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Configurez une base de données SLS (Secondary Location Source) pour E9-1-1 dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: fd70957526d193951b56211c0d5a6623a26419e2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830644"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a><span data-ttu-id="6b5fa-103">Configurer un service informations d’emplacement secondaire dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="6b5fa-103">Configure a secondary Location Information service in Skype for Business Server</span></span>
 
<span data-ttu-id="6b5fa-104">Configurez une base de données SLS (Secondary Location Source) pour E9-1-1 dans Skype Entreprise Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="6b5fa-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="6b5fa-105">Skype Entreprise Server fournit une interface de service web que vous pouvez utiliser pour faire pointer le service Informations d’emplacement vers une base de données SLS (Secondary Location Source).</span><span class="sxs-lookup"><span data-stu-id="6b5fa-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="6b5fa-106">L’interface de service web qui se connecte à la base de données SLS doit être conforme au WSDL du service d’informations d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="6b5fa-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="6b5fa-107">Si une base de données d’emplacements et une base de données d’emplacements secondaires sont configurées, le service Informations sur l’emplacement interroge d’abord la base de données d’emplacements et, si aucune correspondance n’est trouvée, envoie la demande d’emplacement du client à la base de données SLS.</span><span class="sxs-lookup"><span data-stu-id="6b5fa-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="6b5fa-108">Si l’emplacement existe dans le service SLS, le service Informations d’emplacement renvoie l’emplacement au client.</span><span class="sxs-lookup"><span data-stu-id="6b5fa-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="6b5fa-109">Pour configurer une base de données d’emplacements secondaires</span><span class="sxs-lookup"><span data-stu-id="6b5fa-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="6b5fa-110">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="6b5fa-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="6b5fa-111">Exécutez l’applet de commande suivante pour configurer l’URL de l’emplacement de la base de données d’emplacements secondaires.</span><span class="sxs-lookup"><span data-stu-id="6b5fa-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="6b5fa-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6b5fa-112">See also</span></span>

[<span data-ttu-id="6b5fa-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="6b5fa-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

