---
title: Expanseur des paramètres du service de médiation
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 'Serveur de médiation, vous pouvez spécifier les éléments suivants :'
ms.openlocfilehash: e322b2ffd383c2bd0170852a6fec6c3122251700
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="mediation-service-settings-expander"></a><span data-ttu-id="c12e6-103">Expanseur des paramètres du service de médiation</span><span class="sxs-lookup"><span data-stu-id="c12e6-103">Mediation Service Settings Expander</span></span>
 
<span data-ttu-id="c12e6-104">Dans **Serveur de médiation**, vous pouvez spécifier les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="c12e6-104">For **Mediation Server**, you can specify the following:</span></span>
  
<span data-ttu-id="c12e6-105">Si vous sont COLLOCATION sur le pool frontal, le serveur de médiation ou le serveur Standard Edition server, activez la case à cocher **serveur de médiation colocalisés activé**.</span><span class="sxs-lookup"><span data-stu-id="c12e6-105">If you are collocating the Mediation Server onto the Front End pool or the Standard Edition server, select the check box **Collocated Mediation Server enabled**.</span></span> <span data-ttu-id="c12e6-106">Si vous choisissez de ne pas colocaliser le serveur de médiation, il n’y a pas de paramètres définis dans cette section.</span><span class="sxs-lookup"><span data-stu-id="c12e6-106">If you choose not to collocate the Mediation Server, there are no definable settings in this section.</span></span> 
  
<span data-ttu-id="c12e6-107">Si vous avez activé la colocalisation du serveur de médiation, vous devez définir la plage de ports à l’écoute sur le serveur de sécurité TLS (Transport Layer).</span><span class="sxs-lookup"><span data-stu-id="c12e6-107">If you have enabled the collocation of the Mediation Server, you need to define the listening port range on the server for Transport Layer Security (TLS).</span></span> <span data-ttu-id="c12e6-108">Par défaut, il s’agit du port 5067.</span><span class="sxs-lookup"><span data-stu-id="c12e6-108">By default, this port is 5067.</span></span> <span data-ttu-id="c12e6-109">Si vous sélectionnez **Activer le port TCP**, vous devez définir un protocole TCP pour le serveur de médiation colocalisé.</span><span class="sxs-lookup"><span data-stu-id="c12e6-109">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="c12e6-110">Il s’agit d’un paramètre facultatif, et vous devez vous reporter aux conditions requises de votre passerelle ou de votre réseau public commuté pour déterminer si vous en avez besoin.</span><span class="sxs-lookup"><span data-stu-id="c12e6-110">This is an optional setting, and you should refer to the requirements of your gateway or public switched telephone network (PSTN) requirements to determine if you need this.</span></span> <span data-ttu-id="c12e6-111">Par défaut, la valeur du port TCP est le port 5068.</span><span class="sxs-lookup"><span data-stu-id="c12e6-111">By default, the TCP port value is 5068.</span></span>
  
<span data-ttu-id="c12e6-112">Vous définissez les passerelles RTPC qui sont associés au serveur de médiation colocalisée.</span><span class="sxs-lookup"><span data-stu-id="c12e6-112">You define PSTN gateways that are associated with the collocated Mediation Server.</span></span> <span data-ttu-id="c12e6-113">Si vous avez déjà défini des passerelles, ils seront disponibles à associer avec le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="c12e6-113">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span> 
  
<span data-ttu-id="c12e6-114">Si vous avez plus d’une passerelle associée à un serveur de médiation, la première passerelle associée sera la passerelle par défaut.</span><span class="sxs-lookup"><span data-stu-id="c12e6-114">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway.</span></span> <span data-ttu-id="c12e6-115">Si vous devez sélectionner une autre passerelle comme passerelle par défaut, sélectionnez la passerelle à utiliser par défaut, puis cliquez sur **Utiliser par défaut**.</span><span class="sxs-lookup"><span data-stu-id="c12e6-115">If you need to choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span> <span data-ttu-id="c12e6-116">Pour désélectionner la passerelle par défaut, cliquez sur **Annuler par défaut**.</span><span class="sxs-lookup"><span data-stu-id="c12e6-116">To unselect the gateway as the default, click **Unmake Default**.</span></span>
  
<span data-ttu-id="c12e6-117">Pour plus d’informations sur la définition et la configuration des paramètres pour le serveur Standard Edition server ou le pool frontal de Enterprise Edition, consultez [définition et configuration de la topologie](http://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) et le [déploiement de serveurs de médiation et de définir des homologues](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span><span class="sxs-lookup"><span data-stu-id="c12e6-117">For details about defining and configuring the settings for the Enterprise Edition Front End pool or Standard Edition server, see [Defining and Configuring the Topology](http://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>
  

