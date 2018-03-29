---
title: Configuration d’un service Informations d’emplacement secondaire dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Configurer une base de données de la source (SLS) emplacement secondaire pour E9-1-1 dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: 03de4369b8473142e7a76e3698bb9fe7f129d546
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server-2015"></a><span data-ttu-id="4f45b-103">Configuration d’un service Informations d’emplacement secondaire dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="4f45b-103">Configure a secondary Location Information service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4f45b-104">Configurer une base de données de la source (SLS) emplacement secondaire pour E9-1-1 dans Skype pour Business Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="4f45b-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="4f45b-105">Skype pour Business Server fournit une interface de service web que vous pouvez utiliser pour le service d’informations d’emplacement à une base de données de la Source d’emplacement secondaire (SLS).</span><span class="sxs-lookup"><span data-stu-id="4f45b-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="4f45b-106">L’interface de service web qui se connecte à la base de données SLS doit se conformer au service d’informations de l’emplacement WSDL.</span><span class="sxs-lookup"><span data-stu-id="4f45b-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="4f45b-107">Si une base de données de l’emplacement et la base de données du site secondaire sont configurés, le service d’informations d’emplacement tout d’abord interroge la base de données de l’emplacement et si aucune correspondance n’est trouvée, envoie la demande de l’emplacement à partir du client à la base de données SLS.</span><span class="sxs-lookup"><span data-stu-id="4f45b-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="4f45b-108">Si l’emplacement existe dans le contrat SLS, le service d’informations d’emplacement envoie ensuite l’emplacement au client.</span><span class="sxs-lookup"><span data-stu-id="4f45b-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="4f45b-109">Pour configurer une base de données d’emplacements secondaires</span><span class="sxs-lookup"><span data-stu-id="4f45b-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="4f45b-110">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="4f45b-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="4f45b-111">Exécutez l’applet de commande ci-dessous pour configurer l’URL de l’emplacement de la base de données d’emplacements secondaires.</span><span class="sxs-lookup"><span data-stu-id="4f45b-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="4f45b-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4f45b-112">See also</span></span>

#### 

[<span data-ttu-id="4f45b-113">Ensemble-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="4f45b-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

